DetourGetEntryPoint
===================

Return the entry point for a module..

Definition
----------

>     PVOID DetourGetEntryPoint(
>         _In_opt_ HMODULE hModule
>         );

Parameters
----------

*hModule*
:   The handle of the module to which the entry point is desired.

Return value
------------

Returns the entry point for the module, if found; otherwise, returns
`NULL`.

Error codes
-----------

The function sets one of the following error codes, as appropriate. The
error code may be retrived after the function has returned by calling
`GetLastError`.

**ERROR\_BAD\_EXE\_FORMAT**
:   The MZ header of specified module is invalid.

**ERROR\_EXE\_MARKED\_INVALID**
:   The NT COFF header of the specified module is invalid.

**ERROR\_INVALID\_EXE\_SIGNATURE**
:   The NT COFF header of the specified module has an invalid signature.

Remarks
-------

`DetourGetEntryPoint` returns the entry point for a module. For a `.EXE`
file, the entry point is the start of the code for the runtime startup
runtimes. For a `.DLL file`, the entry point is the start of the code
for the `DllMain` function.

The [Slept](SampleSlept.md) sample shows how to capture program execution
after DLL initialization by detouring the entry point of a program.

Related Samples
---------------

[Disas](SampleDisas.md), [Dumpe](SampleDumpe.md),
[Dumpe](SampleFindFunc.md), [Tracebld](SampleTracebld.md),
[Slept](SampleSlept.md).
