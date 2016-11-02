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

[DetourAttach](DetourAttach),
[DetourAttachEx](DetourAttachEx),
[DetourCodeFromPointer](DetourCodeFromPointer),
[DetourCopyPayloadToProcess](DetourCopyPayloadToProcess),
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx),
[DetourDetach](DetourDetach),
[DetourEnumerateImports](DetourEnumerateImports),
[DetourEnumerateModules](DetourEnumerateModules),
[DetourFindPayload](DetourFindPayload),
[DetourGetEntryPoint](DetourGetEntryPoint),
[DetourGetModuleSize](DetourGetModuleSize),
[DetourFinishHelperProcess](DetourFinishHelperProcess),
[DetourIsHelperProcess](DetourIsHelperProcess),
[DetourRestoreAfterWith](DetourRestoreAfterWith),
[DetourTransactionBegin](DetourTransactionBegin),
[DetourTransactionCommit](DetourTransactionCommit),
[DetourUpdateThread](DetourUpdateThread).
