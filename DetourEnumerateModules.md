DetourEnumerateModules
======================

Enumerate the PE binaries in a process.

Definition
----------

>     HMODULE DetourEnumerateModules(
>         _In_opt_ HMODULE hModuleLast
>         );

Parameters
----------

*hModuleLast*
:   The handle of the last module enumerated. Pass NULL to start
    enumeration for the beginning of the process.

Return value
------------

Handle to the next module loaded in a process.

Remarks
-------

`DetourEnumerateModules` enumerates all of the PE binaries loaded into a
process. Once a module has been enumerated, its entry point can be
located with the [DetourGetEntryPoint](DetourGetEntryPoint.md) API,
its exports can be enumerated with the
[DetourEnumerateExports](DetourEnumerateExports.md) API, and its
payloads can be found using the
[DetourFindPayload](DetourFindPayload.md) API.

Related Samples
---------------

[Disas](SampleDisas.md), [Einst](SampleEinst.md),
[Tracebld](SampleTracebld.md), [Tracelnk](SampleTracelnk.md),
[Tracereg](SampleTracereg.md).
