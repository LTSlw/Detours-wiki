DetourBinaryDeletePayload
=========================

Remove a payload from a binary.

Definition
----------

>     BOOL DetourBinaryDeletePayload(
>         _In_ PDETOUR_BINARY pBinary,
>         _In_ REFGUID rguid
>         );

Parameters
----------

*pBinary*
:   Pointer to the binary opened by
    [DetourBinaryOpen](DetourBinaryOpen.md), .

*rguid*
:   GUID of payload to remove.

Remarks
-------

`DetourBinaryDeletePayload` removes a payload from a binary opened by
[DetourBinaryOpen](DetourBinaryOpen.md) .

For more information on binary editing with Detours and paylods, see
[Payloads and DLL Import Editing](OwerviewPayloads.md) in the [Detours
Overview](Home.md).

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.
