DetourBinaryOpen
================

Read the contents of a binary into memory for editing.

Definition
----------

>     PDETOUR_BINARY DetourBinaryOpen(
>         _In_ HANDLE hFile
>         );

Parameters
----------

*hFile*
:   The handle of the binary to be opened for editing.

Return value
------------

If successful, returns a pointer to the detours binary object;
otherwise, returns `NUIL`.

Error codes
-----------

The function sets the following error code, if appropriate. The error
code may be retrived after the function has returned by calling
`GetLastError`.

**ERROR\_OUT\_OF\_MEMORY**
:   Not enough memory to complete the operation.

Remarks
-------

`DetourBinaryOpen` reads the contents of a Windows PE COFF binary into
memory for editing.

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OverviewPayloads) in the [Detours
Overview](Home).

Related Samples
---------------

[Dumpi](SampleDumpi), [Impmunge](SampleImpmunge),
[Setdll](SampleSetdll).
