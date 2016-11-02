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
located with the [DetourGetEntryPoint](DetourGetEntryPoint) API,
its exports can be enumerated with the
[DetourEnumerateExports](DetourEnumerateExports) API, and its
payloads can be found using the
[DetourFindPayload](DetourFindPayload) API.

Related Samples
---------------

[Disas](SampleDisas), [Einst](SampleEinst),
[Tracebld](SampleTracebld), [Tracelnk](SampleTracelnk),
[Tracereg](SampleTracereg).
