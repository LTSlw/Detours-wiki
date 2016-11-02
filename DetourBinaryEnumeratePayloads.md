DetourBinaryEnumeratePayloads
=============================

Enumerate the payloads in a binary.

Definition
----------

>     _Writable_bytes_(*pcbData)
>     _Readable_bytes_(*pcbData)
>     _Success_(return != NULL)
>     PVOID DetourBinaryEnumeratePayloads(
>         _In_      PDETOUR_BINARY pBinary,
>         _Out_opt_ GUID * pGuid,
>         _Out_     DWORD * pcbData,
>         _Inout_   DWORD * pnIterator
>         );

Parameters
----------

*pBinary*
:   Pointer to the binary opened by
    [DetourBinaryOpen](DetourBinaryOpen) .

*pGuid*
:   Pointer to the variable to receive the GUID of the next payload.

*pcbData*
:   Poiunter to the Variable to receive the size in bytes of the
    next payload.

*pnIterator*
:   Enumeration variable. Should be set to zero to start enumeration.
    The enumeration variable should not be modified between successive
    calls to this function.

Remarks
-------

`DetourBinaryEnumeratePayloads` enumerates all of the payloads in a
binary opened by [DetourBinaryOpen](DetourBinaryOpen) .

For more information on binary editing with Detours and paylods, see
[Payloads and DLL Import Editing](OverviewPayloads) in the [Detours
Overview](Home).

Return value
------------

If successful, returns a pointer to the next payload; otherwise, returns
`NULL`.
