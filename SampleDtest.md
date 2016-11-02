Dtest
=====

Detours the Win32 `Sleep` function and a private function. The private
function is first detoured, then detoured recursively 3 times using the
[DetourAttach](DetourAttach) API.

Uses
----

[DetourAttach](DetourAttach),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourUpdateThread](DetourUpdateThread).
