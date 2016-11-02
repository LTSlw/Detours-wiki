DetourFindPayload
=================

Return the address of the specified payload within a module.

Definition
----------

>     _Writable_bytes_(*pcbData)
>     _Readable_bytes_(*pcbData)
>     _Success_(return != NULL)
>     PVOID DetourFindPayload(
>         _In_opt_ HMODULE hModule,
>         _In_     REFGUID rguid,
>         _Out_    DWORD * pcbData
>         );

Parameters
----------

*hModule*
:   Module holding the payload specified payload.

*rguid*
:   GUID of the specified payload.

*pcbData*
:   Variable to receive the size in bytes of the specified payload.

Return value
------------

Pointer to the specified payload or NULL if the payload doesn't exist.

Error codes
-----------

The function sets one of the following error codes if it was unable to
search the module for the target payload. The error code may be retrived
after the function has returned by calling `GetLastError`.

**ERROR\_BAD\_EXE\_FORMAT**
:   The MZ header of specified module is invalid.

**ERROR\_EXE\_MARKED\_INVALID**
:   The NT COFF header of the specified module is invalid.

**ERROR\_INVALID\_EXE\_SIGNATURE**
:   The NT COFF header of the specified module has an invalid signature.

Remarks
-------

`DetourFindPayload` returns the address of the specified payload within
a module. Payloads can either be created at compile link time, see the
[Einst](SampleEinst), or can be inserted it an existing binary using
the [DetourBinarySetPayload](DetourBinarySetPayload) API.

For more information on binary editing with Detours and paylods, see
[Payloads and DLL Import Editing](OverviewPayloads) in the [Detours
Overview](Home).

Related Samples
---------------

[Einst](SampleEinst), [Tracebld](SampleTracebld).
