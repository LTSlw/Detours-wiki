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
    [DetourBinaryOpen](DetourBinaryOpen), .

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.

Remarks
-------

`DetourBinaryClose` closes the binary opened for editing by
[DetourBinaryOpen](DetourBinaryOpen).

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OverviewPayloads) in the [Detours
Overview](Home).

Related Samples
---------------

[Dumpi](SampleDumpi), [Impmunge](SampleImpmunge),
[Setdll](SampleSetdll).
