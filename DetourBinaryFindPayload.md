DetourBinaryFindPayload
=======================

Find a payload within a binary.

Definition
----------

>     _Writable_bytes_(*pcbData)
>     _Readable_bytes_(*pcbData)
>     _Success_(return != NULL)
>     PVOID DetourBinaryFindPayload(
>         _In_  PDETOUR_BINARY pBinary,
>         _In_  REFGUID rguid,
>         _Out_ DWORD * pcbData
>         );

Parameters
----------

*pBinary*
:   Pointer to the binary opened by
    [DetourBinaryOpen](DetourBinaryOpen) .

*rguid*
:   GUID of the specified payload.

*pcbData*
:   Pointer to the variable that receives the size of the specified
    payload in bytes.

Remarks
-------

`DetourBinaryFindPayload`Finds a specific payload within a binary opened
by [DetourBinaryOpen](DetourBinaryOpen).

For more information on binary editing with Detours and paylods, see
[Payloads and DLL Import Editing](OverviewPayloads) in the [Detours
Overview](Home).

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.
