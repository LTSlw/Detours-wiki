Traceapi
========

Win32 API tracing sample. Detours and prints tracing statements for 1401
Win32 API functions. Output from the trace is logged to the
[syelogd.exe](SampleSyelog) deamon.

Uses
----

[DetourAttach](DetourAttach),
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx),
[DetourDetach](DetourDetach),
[DetourFinishHelperProcess](DetourFinishHelperProcess),
[DetourIsHelperProcess](DetourIsHelperProcess),
[DetourRestoreAfterWith](DetourRestoreAfterWith),
[DetourSetIgnoreTooSmall](DetourSetIgnoreTooSmall),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourTransactionCommitEx](DetourTransactionCommitEx),
[DetourUpdateThread](DetourUpdateThread).
