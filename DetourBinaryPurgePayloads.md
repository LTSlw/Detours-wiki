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
    [DetourBinaryOpen](DetourBinaryOpen.md), to be purged.

Remarks
-------

`DetourBinaryPurgePayloads`Removes all payloads from a binary opened by
[DetourBinaryOpen](DetourBinaryOpen.md).

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OwerviewPayloads.md) in the [Detours
Overview](Home.md).

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.
