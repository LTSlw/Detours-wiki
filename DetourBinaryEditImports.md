DetourBinaryEditImports
=======================

Edit the import tables of a binary.

Definition
----------

>     BOOL DetourBinaryEditImports(
>         _In_     PDETOUR_BINARY pBinary,
>         _In_opt_ PVOID pContext,
>         _In_opt_ PF_DETOUR_BINARY_BYWAY_CALLBACK pfByway,
>         _In_opt_ PF_DETOUR_BINARY_FILE_CALLBACK pfFile,
>         _In_opt_ PF_DETOUR_BINARY_SYMBOL_CALLBACK pfSymbol,
>         _In_opt_ PF_DETOUR_BINARY_COMMIT_CALLBACK pfFinal
>         );

Parameters
----------

*pBinary*
:   Pointer to binary opened by
    [`DetourBinaryOpen`](DetourBinaryOpen.md) .

*pContext*
:   Program specific context pointer to be passed unmodified to each
    callback function.

*pfByway*
:   Callback function called before each module in the import table.

*pfFile*
:   Callback function called once for each module in the import table.

*pfSymbol*
:   Callback function called once for each symbol in the import table.

*pfCommit*
:   Callback function called at the end of the import table if there
    have been no errors.

Return value
------------

If successful, returns `TRUE`; otherwise, returns `FALSE`.

Remarks
-------

`DetourBinaryEditImports` edits the import tables of a binary opened by
[`         DetourBinaryOpen`](DetourBinaryOpen.md). Detours stores
edits in a reversible format using a Detours payload. The
[`         DetourBinaryResetImports`](DetourBinaryResetImports.md)
function can be used to remove the edits.

`DetourBinaryEditImports` walks sequentially through the import table of
a binary making callbacks on all points of interest. Four points of
interest are currently supported, each with its own callback function:

-   **Files**: The [`pfFile`](DetourBinaryFileCallback.md) function
    is called for each file listed in the import table. The callback
    function can alter the file name at its discretion.
-   **Symbols**: The [`pfSymbol`](DetourBinarySymbolCallback.md)
    function is called for each symbol listed in each file in the
    import table. The callback function can alter the symbol name at
    its discretion.
-   **Byways**: The [`pfByway`](DetourBinaryBywayCallback.md)
    function is called once at the start of the import table, between
    each pair of import functions, and again at the end of the
    import table. The `pfByway` function can at its discretion introduce
    a new import file into the import table. When a byway is inserted,
    the import table is modified to import the function exported with
    ordinal \#1 from the named import file.
-   **Commit**: The [`pfCommit`](DetourBinaryCommitCallback.md)
    function is called at the end of walking the import table if no
    errors have been returned by previous callback functions.

Consider a binary that imports the functions `CreateFileW` and
`CloseHandle` from `Kernel32.dll`, the function `CommandLineToArgvW`
from `Shell32.dll`, the functions `RegOpenKeyExW`, `RegQueryValueW`, and
`RegCloseKey` from `AdvApi32.dll`, and has a byway for `MyDetour.Dll`
inserted from a previous call to `DetoursBinaryEditImports`. A program
calling `DetoursBinaryEditImports` would receive the following
callbacks:

-   `BywayCallback               (..., NULL, ...)`
-   `BywayCallback               (..., "MyDetour.dll", ... )`
-   `BywayCallback               (..., NULL, ...)`
-   `FileCallback               (..., "Kernel32.dll", ...)`
-   `SymbolCallback               (..., "CloseHandle", ...)`
-   `SymbolCallback               (..., "CreateFileW", ...)`
-   `BywayCallback               (..., NULL, ...)`
-   `FileCallback               (..., "Shell32.dll", ...)`
-   `SymbolCallback               (..., "CommandLineToArgvW", ...)`
-   `BywayCallback               (..., NULL, ...)`
-   `FileCallback               (..., "AdvApi32.dll", ...)`
-   `SymbolCallback               (..., "RegCloseKey", ...)`
-   `SymbolCallback               (..., "RegQueryValueW", ...)`
-   `SymbolCallback               (..., "RegOpenKeyExW", ...)`
-   `BywayCallback               (..., NULL, ...)`
-   `CommitCallback               (...)`

For more information on binary editing with Detours, see [Payloads and
DLL Import Editing](OwerviewPayloads.md) in the [Detours
Overview](Home.md).

**Note:** Each DLL inserted as a byway must export a function with
ordinal \#1. If the export table for the DLL does not export a function
with ordinal \#1, the target binary will fail to load correct.

Related Samples
---------------

[Dumpi](SampleDumpi.md), [Impmunge](SampleImpmunge.md),
[Setdll](SampleSetdll.md).
