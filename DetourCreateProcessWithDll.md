DetourCreateProcessWithDll
==========================

Create a new process and load a DLL into it..

*DetourCreateProcessWithDll has been deprecated. Use
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx) or
[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls)
instead.*

Definition
----------

>     BOOL DetourCreateProcessWithDll(
>         _In_opt_    LPCTSTR lpApplicationName,
>         _Inout_opt_ LPTSTR lpCommandLine,
>         _In_opt_    LPSECURITY_ATTRIBUTES lpProcessAttributes,
>         _In_opt_    LPSECURITY_ATTRIBUTES lpThreadAttributes,
>         _In_        BOOL bInheritHandles,
>         _In_        DWORD dwCreationFlags,
>         _In_opt_    LPVOID lpEnvironment,
>         _In_opt_    LPCTSTR lpCurrentDirectory,
>         _In_        LPSTARTUPINFOW lpStartupInfo,
>         _Out_       LPPROCESS_INFORMATION lpProcessInformation,
>         _In_        LPCSTR lpDllName,
>         _In_opt_    PDETOUR_CREATE_PROCESS_ROUTINEW pfCreateProcessW
>         );

Parameters
----------

*lpApplicationName*
:   Application name as defined for CreateProcess API.

*lpCommandLine*
:   Command line as defined for CreateProcess API.

*lpProcessAttributes*
:   Process attributes as defined for CreateProcess API.

*lpThreadAttributes*
:   Thread attributes as defined for CreateProcess API.

*bInheritHandles*
:   Inherit handle flags as defined for CreateProcess API.

*dwCreationFlags*
:   Creation flags as defined for CreateProcess API.

*lpEnvironment*
:   Process environment variables as defined for CreateProcess API.

*lpCurrentDirectory*
:   Process current directory as defined for CreateProcess API.

*lpStartupInfo*
:   Process startup information as defined for CreateProcess API.

*lpProcessInformation*
:   Process handle information as defined for CreateProcess API.

*lpDllName*
:   Pathname of the DLL to be insert into the new process.

*pfCreateProcessW*
:   Pointer to program specific replacement for the CreateProcess API,
    or NULL if the standard CreateProcess API should be used to create
    the new process.

Return value
------------

Returns `TRUE` if the new process was created; otherwise returns
`FALSE`.

Error codes
-----------

See error code returned from CreateProcess.

Remarks
-------

`DetourCreateProcessWithDll` creates a new process with the specified
DLL inserted into it.

The process is created in a suspended state with the CREATE\_SUSPENDED
flag to CreateProcess. Detours then modifies the image of the
application binary in the new process to include the specified DLL as
its first import. Execution in the process is then resumed. When
execution resumes, the Windows process loader will first load the detour
DLL and then any other DLLs in the application's import table, before
calling the application entry point.

`DetourCreateProcessWithDll` modifies the in-memory import table of the
target PE binary program in the new process it creates. The updated
import table will contain a reference to function ordinal \#1 exported
from the detour DLL.

**Note:** The new process will fail to start if the detour DLL does not
export [DetourFinishHelperProcess](DetourFinishHelperProcess) as
export ordinal \#1.

After the detour DLL has been loaded, it should reverse changes to the
in-memory import table by calling
[`DetourRestoreAfterWith`](DetourRestoreAfterWith). To
facilitate reversing these changes, `DetourCreateProcessWithDll` copies
relevant reversal data into a payload in the target process using the
[`DetourCopyPayloadToProcess`](DetourCopyPayloadToProcess) API.
The loaded DLL should call the
[`DetourRestoreAfterWith`](DetourRestoreAfterWith) API to
restores the contents of the import table.

Related Samples
---------------

[Tracebld](SampleTracebld), [Tracemem](SampleTracemem),
[Tracereg](SampleTracereg), [Traceser](SampleTraceser),
[Withdll](SampleWithdll).
