DetourIsHelperProcess
=====================

Check if the current process is a helper process or a target process.

Definition
----------

>     BOOL DetourIsHelperProcess(VOID);

Return value
------------

Returns true if this process is a helper process.

Returns false if this process is a target process.

Remarks
-------

When creating a 32-bit target process from a 64-bit parent process or
creating a 64-bit target process from a 32-bit parent process, the
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx.md) API
must create a temporary helper process. It loads a copy of the
user-supplied DLL into the helper process using the `rundll32.exe`
mechanism. The user-supplied DLL should call `DetourIsHelperProcess`
within its `DllMain` function to determine if it has been loaded into a
helper process or into a target process.

When a user-supplied DLL is loaded into a helper process, it **must
not** detour any functions. Instead, it should perform no operations in
`DllMain`. The user-supplied DLL must also export the
[DetourFinishHelperProcess](DetourFinishHelperProcess.md) API as
its Ordinal 1 export function.

For more information, see [Detouring 32-bit and 64-bit
Processes](OverviewHelpers.md).

Related Samples
---------------

[Simple](SampleFindFunc.md), [Simple](SampleSimple.md),
[Slept](SampleSlept.md), [Traceapi](SampleTraceapi.md),
[Tracebld](SampleTracebld.md), [Tracelnk](SampleTracelnk.md),
[Tracemem](SampleTracemem.md), [Tracereg](SampleTracereg.md),
[Traceser](SampleTraceser.md), [Tracetcp](SampleTracetcp.md),
[Tryman](SampleTryman.md).
