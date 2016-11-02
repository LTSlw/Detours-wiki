DetourCopyPayloadToProcess
==========================

Copy a payload into a target process.

Definition
----------

>     BOOL DetourCopyPayloadToProcess(
>         _In_                     HANDLE hProcess,
>         _In_                     REFGUID rguid,
>         _In_reads_bytes_(cbData) PVOID pvData,
>         _In_                     DWORD cbData
>         );

Parameters
----------

*hProcess*
:   Process into which payload should be copied.

*rguid*
:   GUID of the specified payload.

*pvData*
:   Pointer to payload data.

*pcbData*
:   Size in bytes of payload data.

Return value
------------

Returns TRUE if the payload was successfully copied to the target
process.

Error codes
-----------

On failure, `DetourCopyPayloadToProcess` will return FALSE. Extended
error code information may be retrieved by calling `GetLastError`.

Remarks
-------

`DetourCopyPayloadToProcess` allocated a region of memory in the target
process using the `VirtualAllocEx` API. It then uses the
WriteProcessMemory API to create an artificial PE binary module in the
target memory. In the artificial module, `DetourCopyPayloadToProcess`
creates a `.detours` section with the specified payload data.

Code in the target process can find the payload by enumerating through
all modules using the
[DetourEnumerateModules](DetourEnumerateModules.md) API and
querying each module for the payload using the
[DetourFindPayload](DetourFindPayload.md) API.

Related Samples
---------------

[Tracebld](SampleTracebld.md), [WithDll](Sam_WithDll.md).
