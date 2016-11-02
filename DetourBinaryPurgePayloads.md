DetourBinaryPurgePayloads
=========================

Remove all payloads from a binary.

Definition
----------

>     BOOL DetourBinaryPurgePayloads(
>         _In_ PDETOUR_BINARY pBinary
>         );

Parameters
----------

*pBinary*
:   Pointer to binary, opened by
    [DetourBinaryOpen](DetourBinaryOpen), to be purged.

Remarks
-------

`DetourBinaryPurgePayloads`Removes all payloads from a binary opened by
[DetourBinaryOpen](DetourBinaryOpen).

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OwerviewPayloads) in the [Detours
Overview](Home).

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.
