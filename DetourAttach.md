DetourAttach
============

Attach a detour to a target function.

Definition
----------

>     LONG DetourAttach(
>         _Inout_ PVOID * ppPointer,
>         _In_    PVOID pDetour
>         );

Parameters
----------

*ppPointer*
:   Pointer to the target pointer to which the detour will be attached.

*pDetour*
:   Pointer to the detour function.

Return value
------------

Returns NO\_ERROR if successful; otherwise, returns an error code.

Error codes
-----------

**ERROR\_INVALID\_BLOCK**
:   The function referenced is too small to be detoured.

**ERROR\_INVALID\_HANDLE**
:   The ppPointer parameter is null or points to a null pointer.

**ERROR\_INVALID\_OPERATION**
:   No pending transaction exists.

**ERROR\_NOT\_ENOUGH\_MEMORY**
:   Not enough memory exists to complete the operation.

Remarks
-------

`DetourAttach` attaches a detour to a target function as part of the
current transaction opened by the
[DetourTransactionBegin](DetourTransactionBegin) API.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception) or [Using
Detours](OverviewUsing) in the [Detours Overview](Home).

Related Samples
---------------

[Commem](SampleCommem), [Cping](SampleCping),
[Dtest](SampleDtest), [Excep](SampleExcep),
[FindFunc](SampleFindFunc), [Simple](SampleSimple),
[Slept](SampleSlept), [Traceapi](SampleTraceapi),
[Tracebld](SampleTracebld), [Tracelnk](SampleTracelnk),
[Tracemem](SampleTracemem), [Tracereg](SampleTracereg),
[Traceser](SampleTraceser), [Tracetcp](SampleTracetcp),
[Tryman](SampleTryman).
