PF\_DETOUR\_IMPORT\_FUNC\_CALLBACK
==================================

Pointer to function called once for each function enumerated by
[DetourEnumerateImports](DetourEnumerateImports.md).

Definition
----------

>     BOOL ImportFuncCallback(
>         _In_opt_ PVOID pContext,
>         _In_     ULONG nOrdinal,
>         _In_opt_ PCSTR pszName,
>         _In_opt_ PVOID pvFunc
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourEnumerateImports](DetourEnumerateImports.md).

*nOrdinal*
:   Ordinal of imported function. 0 if the import is by name.

*pszName*
:   Name of imported function. NULL if the import is by ordinal.

*pvFunc*
:   Pointer to code implementing the function (or less commonly, data).
    NULL if the end of the module.

Return value
------------

`TRUE` to continue enumeration of import functions or `FALSE` to abort
enumeration.
