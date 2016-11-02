PF\_DETOUR\_IMPORT\_FILE\_CALLBACK
==================================

Pointer to function called once for each file enumerated by
[DetourEnumerateImports](DetourEnumerateImports.md).

Definition
----------

>     BOOL ImportFileCallback(
>         _In_opt_ PVOID pContext,
>         _In_opt_ HMODULE nOrdinal,
>         _In_opt_ LPCSTR pszName
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourEnumerateImports](DetourEnumerateImports.md).

*hModule*
:   Module handle within the process of the imported file. NULL to
    indicate end of enumeration.

*pszName*
:   Name of imported file. NULL to indicate end of enumeration.

Return value
------------

`TRUE` to continue enumeration of import files or `FALSE` to abort
enumeration.
