PF\_DETOUR\_BINARY\_COMMIT\_CALLBACK
====================================

Pointer to function called at the end of editing an import table using
the [DetourBinaryEditImports](DetourEnumerateExports.md) API.

Definition
----------

>     BOOL BinaryCommitCallback(
>         _In_opt_ PVOID pContext
>         );

Parameters
----------

*pContext*
:   Umodified program specific context pointer passed as pContext
    argument to
    [DetourBinaryEditImports](DetourBinaryEditImports.md).

Return value
------------

`TRUE` to continue editing import table or `FALSE` to abort.
