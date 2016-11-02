DetourCreateProcessWithDlls
===========================

Create a new process and load DLLs into it. Chooses the appropriate
32-bit or 64-bit DLL based on the target process.

Replaces
[DetourCreateProcessWithDll](DetourCreateProcessWithDll).

Definition
----------

>     BOOL DetourCreateProcessWithDlls(
>         _In_opt_          LPCTSTR lpApplicationName,
>         _Inout_opt_       LPTSTR lpCommandLine,
>         _In_opt_          LPSECURITY_ATTRIBUTES lpProcessAttributes,
>         _In_opt_          LPSECURITY_ATTRIBUTES lpThreadAttributes,
>         _In_              BOOL bInheritHandles,
>         _In_              DWORD dwCreationFlags,
>         _In_opt_          LPVOID lpEnvironment,
>         _In_opt_          LPCTSTR lpCurrentDirectory,
>         _In_              LPSTARTUPINFOW lpStartupInfo,
>         _Out_             LPPROCESS_INFORMATION lpProcessInformation,
>         _In_              DWORD nDlls,
>         _In_reads_(nDlls) LPCSTR *rlpDlls,
>         _In_opt_          PDETOUR_CREATE_PROCESS_ROUTINEW pfCreateProcessW
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

*nDlls*
:   Count of the number of DLLs in *rlpDlls*.

*rlpDlls*
:   Array of pathnames of the DLL to be insert into the new process. To
    support both 32-bit and 64-bit applications, The DLL names should
    end with "32" if the DLL contains 32-bit code and should end with
    "64" if the DLL contains 64-bit code. If the target process differs
    in size from the parent process, Detours will automatically replace
    "32" with "64" or "64" with "32" in the path name.

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

`DetourCreateProcessWithDlls` creates a new process with the specified
DLL inserted into it.

The process is created in a suspended state with the CREATE\_SUSPENDED
flag to CreateProcess. Detours then modifies the image of the
application binary in the new process to include the specified DLL as
its first import. Execution in the process is then resumed. When
execution resumes, the Windows process loader will first load the target
DLL and then any other DLLs in the application's import table, before
calling the application entry point.

`DetourCreateProcessWithDlls` modifies the in-memory import table of the
target PE binary program in the new process it creates. The updated
import table will contain a reference to function ordinal \#1 exported
from the target DLL. If the target process is 32-bit and the parent
process is 64-bit, or if the target process is 64-bit and the parent
process is 32-bit, `DetourCreateProcessWithDlls` will use `rundll32.exe`
to load the DLL into a helper process that matches the target process
temporarily in order to update the target processes import table with
the correct DLL.

**Note:** The new process will fail to start if the target DLL does not
contain a exported function with ordinal \#1.

After the target DLL has been loaded, it can reverse changes to the
in-memory import table by calling
[`DetourRestoreAfterWith`](DetourRestoreAfterWith). To
facilitate reversing these changes, `DetourCreateProcessWithDlls` copies
relevant reversal data into a payload in the target process using the
[`DetourCopyPayloadToProcess`](DetourCopyPayloadToProcess) API.
The loaded DLL should call the
[`DetourRestoreAfterWith`](DetourRestoreAfterWith) API to
restores the contents of the import table.

Related Samples
---------------

[Traceapi](SampleTraceapi), [Tracebld](SampleTracebld),
[Tracemem](SampleTracemem), [Tracereg](SampleTracereg),
[Traceser](SampleTraceser), [Tryman](SampleTryman),
[Withdll](SampleWithdll).
