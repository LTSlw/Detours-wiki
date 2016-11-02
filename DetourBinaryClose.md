DetourBinaryClose
=================

Close a binary opened for editing.

Definition
----------

>     BOOL DetourBinaryClose(
>         _In_ PDETOUR_BINARY pBinary
>         );

Parameters
----------

*pBinary*
:   Pointer to the binary opened by
    [DetourBinaryOpen](DetourBinaryOpen.md), .

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.

Remarks
-------

`DetourBinaryClose` closes the binary opened for editing by
[DetourBinaryOpen](DetourBinaryOpen.md).

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OwerviewPayloads.md) in the [Detours
Overview](Home.md).

Related Samples
---------------

[Dumpi](SampleDumpi.md), [Impmunge](SampleImpmunge.md),
[Setdll](SampleSetdll.md).
