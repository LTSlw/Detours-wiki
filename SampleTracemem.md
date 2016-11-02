Tracemem
========

Traces all calls to the Windows `HeapAlloc` API. Output from the trace
is logged to the [syelogd.exe](SampleSyelog) deamon.

Uses
----

[DetourAttach](DetourAttach),
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx),
[DetourDetach](DetourDetach),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourUpdateThread](DetourUpdateThread).
