DetourBinaryResetImports
========================

Remove all edits by Detours of the binary's import table.

Definition
----------

>     BOOL DetourBinaryResetImports(
>         _In_ PDETOUR_BINARY pBinary
>         );

Parameters
----------

*pBinary*
:   Pointer to the binary opened by
    [DetourBinaryOpen](DetourBinaryOpen).

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.

Remarks
-------

`DetourBinaryResetImports`Removes all Detours edits made to the import
table of a binary opened by
[DetourBinaryOpen](DetourBinaryOpen).

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OverviewPayloads) in the [Detours
Overview](Home).

Related Samples
---------------

[Setdll](SampleSetdll).
