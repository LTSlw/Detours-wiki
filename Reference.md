Detours API Reference
=====================

The Table of Contents provides an alphabetical listing of the available
API functions, which can be grouped as follows:

APIs For Detouring Target Functions
-----------------------------------

-   [DetourTransactionBegin](DetourTransactionBegin.md)
-   [DetourUpdateThread](DetourUpdateThread.md)
-   [DetourAttach](DetourAttach.md)
-   [DetourAttachEx](DetourAttachEx.md)
-   [DetourDetach](DetourDetach.md)
-   [DetourSetIgnoreTooSmall](DetourSetIgnoreTooSmall.md)
-   [DetourSetRetainRegions](DetourSetRetainRegions.md)
-   [DetourSetSystemRegionLowerBound](DetourSetSystemRegionLowerBound.md)
-   [DetourSetSystemRegionUpperBound](DetourSetSystemRegionUpperBound.md)
-   [DetourTransactionAbort](DetourTransactionAbort.md)
-   [DetourTransactionCommit](DetourTransactionCommit.md)
-   [DetourTransactionCommitEx](DetourTransactionCommitEx.md)

APIs For Finding Target Functions
---------------------------------

-   [DetourFindFunction](DetourFindFunction.md)
-   [DetourCodeFromPointer](DetourCodeFromPointer.md)

APIs For Accessing Loaded Binaries and Payloads
-----------------------------------------------

-   [DetourEnumerateModules](DetourEnumerateModules.md)
-   [DetourGetEntryPoint](DetourGetEntryPoint.md)
-   [DetourGetModuleSize](DetourGetModuleSize.md)
-   [DetourEnumerateExports](DetourEnumerateExports.md)
-   [DetourEnumerateImport](DetourEnumerateImports.md)
-   [DetourEnumerateImportEx](DetourEnumerateImportsEx.md)
-   [DetourFindPayload](DetourFindPayload.md)
-   [DetourGetContainingModule](DetourGetContainingModule.md)
-   [DetourGetSizeOfPayloads](DetourGetSizeOfPayloads.md)

APIs For Modifying Binaries
---------------------------

-   [DetourBinaryOpen](DetourBinaryOpen.md)
-   [DetourBinaryEnumeratePayloads](DetourBinaryEnumeratePayloads.md)
-   [DetourBinaryFindPayload](DetourBinaryFindPayload.md)
-   [DetourBinarySetPayload](DetourBinarySetPayload.md)
-   [DetourBinaryDeletePayload](DetourBinaryDeletePayload.md)
-   [DetourBinaryPurgePayloads](DetourBinaryPurgePayloads.md)
-   [DetourBinaryEditImports](DetourBinaryEditImports.md)
-   [DetourBinaryResetImports](DetourBinaryResetImports.md)
-   [DetourBinaryWrite](DetourBinaryWrite.md)
-   [DetourBinaryClose](DetourBinaryClose.md)

APIs For Inserting DLLs and Payloads Into New Processes
-------------------------------------------------------

-   [DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx.md)
-   [DetourCreateProcessWithDlls](DetourCreateProcessWithDlls.md)
-   [DetourCopyPayloadToProcess](DetourCopyPayloadToProcess.md)
-   [DetourFinishHelperProcess](DetourFinishHelperProcess.md)
-   [DetourIsHelperProcess](DetourIsHelperProcess.md)
-   [DetourRestoreAfterWith](DetourRestoreAfterWith.md)

