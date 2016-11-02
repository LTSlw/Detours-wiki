DetourGetModuleSize
===================

Return the load size of a module.

Definition
----------

>     ULONG DetourGetModuleSize(
>         _In_ HMODULE hModule
>         );

Parameters
----------

*hModule*
:   The handle to the module whose load size is desired.

Return value
------------

Returns the size of the module in bytes, if it can be determined;
otherwise, returns 0.

Error codes
-----------

The function sets one of the following error codes, as appropriate. The
error code may be retrived after the function has returned by calling
`GetLastError`.

**ERROR\_BAD\_EXE\_FORMAT**
:   The MZ header of specified module is invalid.

**ERROR\_EXE\_MARKED\_INVALID**
:   The NT COFF header of the specified module is invalid.

**ERROR\_INVALID\_EXE\_SIGNATURE**
:   The NT COFF header of the specified module has an invalid signature.

Related Samples
---------------

[Disas](SampleDisas.md), [Tracebld](SampleTracebld.md).
