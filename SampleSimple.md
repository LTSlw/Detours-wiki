Simple
======

Simplest example of a Detours-based DLL which modifies and adds
functionality to a Windows API. Modifies the `Sleep` API to record the
number of ticks spent sleeping.

The Simple example is described in more detail in [Using
Detours](Home).

Uses
----

[DetourAttach](DetourAttach),
[DetourDetach](DetourDetach),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourUpdateThread](DetourUpdateThread).
