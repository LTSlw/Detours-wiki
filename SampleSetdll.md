Setdll
======

Add a DLL to the import table of any binary (a `.DLL` or `.EXE` for
example). Use `setdll.exe` to attach one of the sample DLLs to an
application .EXE file.

**Note:** The target binary will fail to load if the target DLL does not
contain a exported function with ordinal \#1. For more information, see
the [DetourBinaryEditImports](DetourBinaryEditImports) API.

Related Samples
---------------

[Withdll](SampleWithdll).

Uses
----

[DetourBinaryClose](DetourBinaryClose),
[DetourBinaryEditImports](DetourBinaryEditImports),
[DetourBinaryOpen](DetourBinaryOpen),
[DetourBinaryResetImports](DetourBinaryResetImports),
[DetourBinaryWrite](DetourBinaryWrite).
