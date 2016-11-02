DetourBinarySetPayload
======================

Attach a payload to a binary.

Definition
----------

>     PVOID DetourBinarySetPayload(
>         _In_                   PDETOUR_BINARY pBinary,
>         _In_                   REFGUID rguid,
>         _In_reads_opt_(cbData) PVOID pData,
>         _In_                   DWORD cbData
>         );

Parameters
----------

*pBinary*
:   Pointer to the binary opened by
    [DetourBinaryOpen](DetourBinaryOpen)

*rguid*
:   GUID of the payload to be added to binary.

*pData*
:   Pointer to payload data.

*cbData*
:   Size of the payload data in bytes.

Remarks
-------

`DetourBinarySetPayload` attaches a payload to a binary opened by
[DetourBinaryOpen](DetourBinaryOpen). The payload can be located
at runtime using the [DetourFindPayload](DetourFindPayload) API.

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OverviewPayloads) in the [Detours
Overview](Home).

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.
