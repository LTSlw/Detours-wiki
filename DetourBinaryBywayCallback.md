PF\_DETOUR\_BINARY\_BYWAY\_CALLBACK
===================================

Pointer to function called once for each existing byway or opportunity
to insert a new byway while editing an import table using the
[DetourBinaryEditImports](DetourEnumerateExports.md) API.

Definition
----------

>     BOOL BinaryBywayCallback(
>         _In_opt_                  PVOID pContext,
>         _In_opt_                  LPCSTR pszFile,
>         _Outptr_result_maybenull_ LPCSTR * ppszOutFile
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourBinaryEditImports](DetourBinaryEditImports.md).

*pszFile*
:   Name of byway listed in current import table or NULL.

*ppszOutFile*
:   Pointer to output name of desired byway.

Return value
------------

`TRUE` to continue editing import table or `FALSE` to abort.

Remarks
-------

`PF_DETOUR_BINARY_BYWAY_CALLBACK` is called once for each existing byway
in the target binary and once before or after each file or byway listed
in the existing import table. When called for an existing byway,
`pszFile` will have a non-NULL value.

When `PF_DETOUR_BINARY_BYWAY_CALLBACK` is called before or after an
existing file or byway, `pszFile` will be NULL. The callback function
can use this opportunity to insert a new byway if desired.

**Note:** Each DLL inserted as a byway must export a function with
ordinal \#1. If the export table for the DLL does not export a function
with ordinal \#1, the target binary will fail to load correct.
