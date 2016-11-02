DetourGetSizeOfPayloads
=======================

Return the size of all payloads within a module.

Definition
----------

>     DWORD DetourGetSizeOfPayloads(
>         _In_ HMODULE hModule
>         );

Parameters
----------

*hModule*
:   The module for which the size of the payloads is to be returned.

Return value
------------

If successful, returns the size in bytes of the payloads within a
module; otherwise, returns zero.

Error codes
-----------

The function sets one of the following error codes, as appropriate. The
error code may be retrived after the function has returned by calling
`GetLastError`.

**ERROR\_INVALID\_HANDLE**
:   The module handle was invalid.

Related Samples
---------------

[Einst](SampleEinst.md).
