Traceser
========

Traces activity through the serial ports (com1 or com2). Output from the
trace is logged to the [syelogd.exe](SampleSyelog) deamon.

Uses
----

[DetourAttach](DetourAttach),
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx),
[DetourDetach](DetourDetach),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourUpdateThread](DetourUpdateThread).
