Using Detours
=============

Two things are necessary in order to detour a target function: a target
pointer containing the address of the target function and a detour
function. For proper interception the target function, detour function,
and the target pointer must have exactly the same call signature
including number of arguments and calling convention. Using the same
calling convention insures that registers will be properly preserved and
that the stack will be properly aligned between detour and target
functions

The code fragment in Figure 5 illustrates the usage of the Detours
library. User code must include the `detours.h` header file and link
with the `detours.lib` library.

------------------------------------------------------------------------

> ``
>
>     #include <windows.h>
>     #include <detours.h>
>
>     static LONG dwSlept = 0;
>
>     // Target pointer for the uninstrumented Sleep API.
>     //
>     static VOID (WINAPI * TrueSleep)(DWORD dwMilliseconds) = Sleep;
>
>     // Detour function that replaces the Sleep API.
>     //
>     VOID WINAPI TimedSleep(DWORD dwMilliseconds)
>     {
>         // Save the before and after times around calling the Sleep API.
>         DWORD dwBeg = GetTickCount();
>         TrueSleep(dwMilliseconds);
>         DWORD dwEnd = GetTickCount();
>
>         InterlockedExchangeAdd(&dwSlept, dwEnd - dwBeg);
>     }
>
>     // DllMain function attaches and detaches the TimedSleep detour to the
>     // Sleep target function.  The Sleep target function is referred to
>     // through the TrueSleep target pointer.
>     //
>     BOOL WINAPI DllMain(HINSTANCE hinst, DWORD dwReason, LPVOID reserved)
>     {
>         if (DetourIsHelperProcess()) {
>             return TRUE;
>         }
>
>         if (dwReason == DLL_PROCESS_ATTACH) {
>             DetourRestoreAfterWith();
>
>             DetourTransactionBegin();
>             DetourUpdateThread(GetCurrentThread());
>             DetourAttach(&(PVOID&)TrueSleep, TimedSleep);
>             DetourTransactionCommit();
>         }
>         else if (dwReason == DLL_PROCESS_DETACH) {
>             DetourTransactionBegin();
>             DetourUpdateThread(GetCurrentThread());
>             DetourDetach(&(PVOID&)TrueSleep, TimedSleep);
>             DetourTransactionCommit();
>         }
>         return TRUE;
>     }

###### Figure 5. [Simple](SampleSimple) detour to modify the Windows Sleep API.

------------------------------------------------------------------------

Interception of the target function is enabled by invoking the
[DetourAttach](DetourAttach) API within a detour transaction. A
detour transaction is marked by calls to the
[DetourTransactionBegin](DetourTransactionBegin) API and the
[DetourTransactionCommit](DetourTransactionCommit) API. The
[DetourAttach](DetourAttach) API takes two arguments: the
address of the target pointer and the pointer to the detour function.
The target function is not given as an argument because it must already
be stored in the target pointer.

The [DetourUpdateThread](DetourUpdateThread) API enlists threads
in the transaction so that their instruction pointers are appropriately
updated when the transaction commits.

The [DetourAttach](DetourAttach) API allocates and prepares a
trampoline for calling the target function. When the detour transaction
commits, the target function and trampoline are rewritten and the target
pointer is updated to point to the trampoline function.

Once a target function has been detoured, any call to the target
function will be re-routed through the detour function. It is the
responsibility of the detour function to copy arguments when invoking
the target function through the trampoline. This is intuitive as the
target function becomes simply a subroutine callable by the detour
function.

Interception of a target function is removed by calling the
[DetourDetach](DetourDetach) API within a detour transaction.
Like the [DetourAttach](DetourAttach) API, the
[DetourDetach](DetourDetach) API takes two arguments: the
address of the target pointer and the pointer to the detour function.
When the detour transaction commits, the target function is rewritten
and restored to its original code, the trampoline function is deleted,
and the target pointer is restored to point to the original target
function.

In cases where detour functions need to inserted into an existing
application without source code access, the detour functions should be
packaged in a DLL. The DLL can be loaded into a new process at creation
time using the
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx) or
[DetourCreateProcessWithDlls](DetourCreateProcessWithDllEx)
APIs. If a DLL is inserted using `DetourCreateProcessWithDllEx` or
`DetourCreateProcessWithDlls`, the DllMain function must call the
[DetourRestoreAfterWith](DetourRestoreAfterWith) API. If the DLL
may be used in mixed 32-bit and 64-bit environments, then the DllMain
function must call the
[DetourIsHelperProcess](DetourIsHelperProcess) API. The DLL must
export the
[DetourFinishHelperProcess](DetourFinishHelperProcess) API as
export Ordinal 1, which will be called by `rundll32.exe` to perform the
helper tasks.

NOTE: Microsoft in no way warrants or supports any Microsoft or
third-party code that has been altered either with a detour or with any
other mechanism.

The [withdll.exe](SampleWithdll) program include in the Detours
package uses the
[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls) API
to start a new process with a named DLL.
