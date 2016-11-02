DetourFindFunction
==================

Find the address of a target function by name.

Definition
----------

>     PVOID DetourFindFunction(
>         _In_ LPCSTR pszModule,
>         _In_ LPCSTR pszFunction
>         );

Parameters
----------

*pszModule*
:   The path of the DLL or binary in which the function should be found.

*pszFunction*
:   The name of the function to be found.

Return value
------------

If successful, returns the address of the function *pszFunction*;
otherwise, returns `NULL`.

Remarks
-------

`DetourFindFunction` tries to retrieve a function pointer for a named
function through the dynamic linking export tables of the named module
and then, if that fails, through debugging symbols using the DbgHelp
APIs if available.

`DetourFindFunction` uses the DbgHelp APIs to access debug symbols. It
dynamically links to the DbgHelp APIs by dynamically loading
`DBGHELP.DLL`.

If your program can't find debug symbols that you know are available,
the most likely cause is that system either can't find `DBGHELP.DLL` or
the version of `DBGHELP.DLL` loaded by the system is broken. This can
happen on 64-bit machines (X64 and IA64) where the system will often
load a 32-bit version of `DBGHELP.DLL` even though you have written
64-bit code. Some 32-bit versions of Windows also included a
non-functional `DBGHELP.DLL` stub.

You can test your version of `DBGHELP.DLL` by using the `SymTest`
program from the [FindFunc](SampleFindFunc.md). directory..

Related Samples
---------------

[Cping](SampleCping.md), [Excep](SampleExcep.md).
[FindFunc](SampleFindFunc.md).
