Dtest
=====

Detours the Win32 `Sleep` function and a private function. The private
function is first detoured, then detoured recursively 3 times using the
[DetourAttach](DetourAttach.md) API.

Uses
----

[DetourAttach](DetourAttach.md),
[DetourTransactionBegin](DetourTransactionBegin.md),
[DetourTransactionCommit](DetourTransactionCommit.md),
[DetourUpdateThread](DetourUpdateThread.md).
