DetourBinaryWrite
=================

Write an updated binary to a file.

Definition
----------

>     BOOL DetourBinaryWrite(
>         _In_ PDETOUR_BINARY pBinary,
>         _In_ HANDLE hFile
>         );

Parameters
----------

*pBinary*
:   Pointer to the binary to be written to a file.

*hFile*
:   Handle of the file to receive the contents of the binary.

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.

Remarks
-------

`DetourBinaryWrite` writes the updated binary, opened by
[DetourBinaryOpen](DetourBinaryOpen.md), to a file.

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OwerviewPayloads.md) in the [Detours
Overview](Home.md).

Related Samples
---------------

[Impmunge](SampleImpmunge.md), [Setdll](SampleSetdll.md).
