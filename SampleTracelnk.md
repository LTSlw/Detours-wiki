Tracelnk
========

Traces all calls to the Windows dynamic linking APIs. Output from the
trace is logged to the [syelogd.exe](SampleSyelog) deamon.

Uses
----

[DetourAttach](DetourAttach),
[DetourDetach](DetourDetach),
[DetourEnumerateModules](DetourEnumerateModules),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourUpdateThread](DetourUpdateThread).
