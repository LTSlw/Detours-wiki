Detours API Reference
=====================

The Table of Contents provides an alphabetical listing of the available
API functions, which can be grouped as follows:

APIs For Detouring Target Functions
-----------------------------------

-   [DetourTransactionBegin](DetourTransactionBegin)
-   [DetourUpdateThread](DetourUpdateThread)
-   [DetourAttach](DetourAttach)
-   [DetourAttachEx](DetourAttachEx)
-   [DetourDetach](DetourDetach)
-   [DetourSetIgnoreTooSmall](DetourSetIgnoreTooSmall)
-   [DetourSetRetainRegions](DetourSetRetainRegions)
-   [DetourSetSystemRegionLowerBound](DetourSetSystemRegionLowerBound)
-   [DetourSetSystemRegionUpperBound](DetourSetSystemRegionUpperBound)
-   [DetourTransactionAbort](DetourTransactionAbort)
-   [DetourTransactionCommit](DetourTransactionCommit)
-   [DetourTransactionCommitEx](DetourTransactionCommitEx)

APIs For Finding Target Functions
---------------------------------

-   [DetourFindFunction](DetourFindFunction)
-   [DetourCodeFromPointer](DetourCodeFromPointer)

APIs For Accessing Loaded Binaries and Payloads
-----------------------------------------------

-   [DetourEnumerateModules](DetourEnumerateModules)
-   [DetourGetEntryPoint](DetourGetEntryPoint)
-   [DetourGetModuleSize](DetourGetModuleSize)
-   [DetourEnumerateExports](DetourEnumerateExports)
-   [DetourEnumerateImport](DetourEnumerateImports)
-   [DetourEnumerateImportEx](DetourEnumerateImportsEx)
-   [DetourFindPayload](DetourFindPayload)
-   [DetourGetContainingModule](DetourGetContainingModule)
-   [DetourGetSizeOfPayloads](DetourGetSizeOfPayloads)

APIs For Modifying Binaries
---------------------------

-   [DetourBinaryOpen](DetourBinaryOpen)
-   [DetourBinaryEnumeratePayloads](DetourBinaryEnumeratePayloads)
-   [DetourBinaryFindPayload](DetourBinaryFindPayload)
-   [DetourBinarySetPayload](DetourBinarySetPayload)
-   [DetourBinaryDeletePayload](DetourBinaryDeletePayload)
-   [DetourBinaryPurgePayloads](DetourBinaryPurgePayloads)
-   [DetourBinaryEditImports](DetourBinaryEditImports)
-   [DetourBinaryResetImports](DetourBinaryResetImports)
-   [DetourBinaryWrite](DetourBinaryWrite)
-   [DetourBinaryClose](DetourBinaryClose)

APIs For Inserting DLLs and Payloads Into New Processes
-------------------------------------------------------

-   [DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx)
-   [DetourCreateProcessWithDlls](DetourCreateProcessWithDlls)
-   [DetourCopyPayloadToProcess](DetourCopyPayloadToProcess)
-   [DetourFinishHelperProcess](DetourFinishHelperProcess)
-   [DetourIsHelperProcess](DetourIsHelperProcess)
-   [DetourRestoreAfterWith](DetourRestoreAfterWith)

