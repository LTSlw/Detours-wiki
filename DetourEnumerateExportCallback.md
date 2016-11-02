PF\_DETOUR\_ENUMERATE\_EXPORT\_CALLBACK
=======================================

Pointer to function called once for each export enumerated by
[DetourEnumerateExports](DetourEnumerateExports).

Definition
----------

>     BOOL EnumerateExportCallback(
>         _In_opt_ PVOID pContext,
>         _In_     ULONG nOrdinal,
>         _In_opt_ LPCSTR pszName,
>         _In_opt_ PVOID pCode
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourEnumerateExports](DetourEnumerateExports).

*nOrdinal*
:   Ordinal of export function.

*pszName*
:   Name of export function.

*pCode*
:   Pointer to code implementing the function.

Return value
------------

`TRUE` to continue enumeration of export symbols or `FALSE` to abort
enumeration.
