DetourEnumerateExports
======================

Enumerate exports from a module.

Definition
----------

>     BOOL DetourEnumerateExports(
>         _In_     HMODULE hModule,
>         _In_opt_ PVOID pContext,
>         _In_     PF_DETOUR_ENUMERATE_EXPORT_CALLBACK pfExport
>         );

Parameters
----------

*hModule*
:   The handle to the module whose exports are to be enumerated.

*pContext*
:   Program specific context that will be passed to *pfExport*.

*pfExport*
:   Callback function to be called once per symbol exported from module.

Return value
------------

`TRUE` if module exports are enumerated; otherwise `FALSE`.

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

Related Samples
---------------

[Disas](SampleDisas.md), [Dumpe](SampleDumpe.md), [Disas](SampleDisas.md),
[Einst](SampleEinst.md), [Tracelnk](SampleTracelnk.md),
[Tracereg](SampleTracereg.md).
