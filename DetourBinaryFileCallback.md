PF\_DETOUR\_BINARY\_FILE\_CALLBACK
==================================

Pointer to function called once for file while editing an import table
using the [DetourBinaryEditImports](DetourEnumerateExports.md) API.

Definition
----------

>     BOOL BinaryFileCallback(
>         _In_opt_                  PVOID pContext,
>         _In_                      LPCSTR pszOrigFile,
>         _In_                      LPCSTR pszFile,
>         _Outptr_result_maybenull_ LPCSTR * ppszOutFile
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourBinaryEditImports](DetourBinaryEditImports.md).

*pszOrigFile*
:   Name of file listed in original import table.

*pszFile*
:   Name of file listed in current import table

*ppszOutFile*
:   Pointer to output desired import table name.

Return value
------------

`TRUE` to continue editing import table or `FALSE` to abort.
