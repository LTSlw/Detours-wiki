Tracereg
========

Traces activity through the registry APIs. Output from the trace is
logged to the [syelogd.exe](SampleSyelog) deamon.

Uses
----

[DetourAttach](DetourAttach),
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx),
[DetourDetach](DetourDetach),
[DetourEnumerateModules](DetourEnumerateModules),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourUpdateThread](DetourUpdateThread).
