PF\_DETOUR\_IMPORT\_FUNC\_CALLBACK\_EX
======================================

Pointer to function called once for each entry in the IAT enumerated by
[DetourEnumerateImportsEx](DetourEnumerateImportsEx.md). This is
similar to
[PF\_DETOUR\_IMPORT\_FUNC\_CALLBACK](DetourImportFuncCallback.md)
except here the last parameter points to the entry in the IAT.

Definition
----------

>     BOOL ImportFuncCallbackEx(
>         _In_opt_ PVOID pContext,
>         _In_     ULONG nOrdinal,
>         _In_opt_ PCSTR pszName,
>         _In_opt_ PVOID *pvFunc
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourEnumerateImportsEx](DetourEnumerateImportsEx.md).

*nOrdinal*
:   Ordinal of imported function. 0 if the import is by name.

*pszName*
:   Name of imported function. NULL if the import is by ordinal.

*pvFunc*
:   Pointer to the address within the Import Address Table ("IAT") for
    the function (or less commonly, data). NULL if the end of
    the module.

Return value
------------

`TRUE` to continue enumeration of import functions or `FALSE` to abort
enumeration.
