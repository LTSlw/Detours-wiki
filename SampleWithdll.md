Withdll
=======

Demonstrates how to use the
[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls.md) API
to load a detour DLL into a new process without modifying the target
application. Calls `CreateProcess` and loads a named DLL into the target
process.

**Note:** The new process will fail to start if the target DLL does not
contain a exported function with ordinal \#1. For more information, see
the [DetourCreateProcessWithDlls](DetourCreateProcessWithDlls.md)
API.

Related Samples
---------------

[Setdll](SampleSetdll.md).

Uses
----

[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls.md) .
