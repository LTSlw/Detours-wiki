Simple
======

Simplest example of a Detours-based DLL which modifies and adds
functionality to a Windows API. Modifies the `Sleep` API to record the
number of ticks spent sleeping.

The Simple example is described in more detail in [Using
Detours](Home.md).

Uses
----

[DetourAttach](DetourAttach.md),
[DetourDetach](DetourDetach.md),
[DetourTransactionBegin](DetourTransactionBegin.md),
[DetourTransactionCommit](DetourTransactionCommit.md),
[DetourUpdateThread](DetourUpdateThread.md).
