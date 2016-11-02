PF\_DETOUR\_BINARY\_SYMBOL\_CALLBACK
====================================

Pointer to function called once for each symbol while editing an import
table using the
[DetourBinaryEditImports](DetourEnumerateExports) API.

Definition
----------

>     BOOL BinarySymbolCallback(
>         _In_opt_                  PVOID pContext,
>         _In_                      ULONG nOrigOrdinal,
>         _In_                      ULONG nOrdinal,
>         _Out_                     ULONG * pnOutOrdinal,
>         _In_opt_                  PCSTR pszOrigSymbol,
>         _In_opt_                  PCSTR pszSymbol,
>         _Outptr_result_maybenull_ PCSTR *ppszOutSymbol
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourBinaryEditImports](DetourBinaryEditImports).

*nOrigOrdinal*
:   Import ordinal listed in original import table.

*nOrdinal*
:   Import ordinal listed in current import table.

*pnOutOrdinal*
:   Pointer to output desired import ordinal.

*pszOrigSymbol*
:   Import symbol listed in original import table.

*pszSymbol*
:   Import symbol listed in current import table.

*ppszOutSymbol*
:   Pointer to output desire import symbol.

Return value
------------

`TRUE` to continue editing import table or `FALSE` to abort.
