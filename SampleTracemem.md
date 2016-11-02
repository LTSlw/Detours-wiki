Tracemem
========

Traces all calls to the Windows `HeapAlloc` API. Output from the trace
is logged to the [syelogd.exe](SampleSyelog.md) deamon.

Uses
----

[DetourAttach](DetourAttach.md),
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx.md),
[DetourDetach](DetourDetach.md),
[DetourTransactionBegin](DetourTransactionBegin.md),
[DetourTransactionCommit](DetourTransactionCommit.md),
[DetourUpdateThread](DetourUpdateThread.md).
