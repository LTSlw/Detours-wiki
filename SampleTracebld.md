Tracebld
========

Traces the file access patterns of a process and all of its children.
Unlike the other tracing samples, Tracebld is entirely self-contained.
It includes a parent process that initiates a child process with
instrumentation and aggregates the results for the child and its
children. Output from the children is delivered to the parent process
via a named pipe created by the parent.

Uses
----

[DetourAttach](DetourAttach.md),
[DetourAttachEx](DetourAttachEx.md),
[DetourCodeFromPointer](DetourCodeFromPointer.md),
[DetourCopyPayloadToProcess](DetourCopyPayloadToProcess.md),
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx.md),
[DetourDetach](DetourDetach.md),
[DetourEnumerateImports](DetourEnumerateImports.md),
[DetourEnumerateModules](DetourEnumerateModules.md),
[DetourFindPayload](DetourFindPayload.md),
[DetourGetEntryPoint](DetourGetEntryPoint.md),
[DetourGetModuleSize](DetourGetModuleSize.md),
[DetourFinishHelperProcess](DetourFinishHelperProcess.md),
[DetourIsHelperProcess](DetourIsHelperProcess.md),
[DetourRestoreAfterWith](DetourRestoreAfterWith.md),
[DetourTransactionBegin](DetourTransactionBegin.md),
[DetourTransactionCommit](DetourTransactionCommit.md),
[DetourUpdateThread](DetourUpdateThread.md).
