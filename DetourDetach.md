DetourDetach
============

Detach a detour from a target function.

Definition
----------

>     LONG DetourDetach(
>         _Inout_ PVOID * ppPointer,
>         _In_    PVOID pDetour
>         );

Parameters
----------

*ppPointer*
:   Pointer to the target pointer from which the detour will
    be detached.

*pDetour*
:   Pointer to the detour function.

Return value
------------

Returns NO\_ERROR if successful; otherwise, returns an error code.

Error codes
-----------

**ERROR\_INVALID\_BLOCK**
:   The function to be detached was too small to be detoured.

**ERROR\_INVALID\_HANDLE**
:   The ppPointer parameter is null or references a null address.

**ERROR\_INVALID\_OPERATION**
:   No pending transaction exists.

**ERROR\_NOT\_ENOUGH\_MEMORY**
:   Not enough memory to complete the operation.

Remarks
-------

`DetourDetach` detaches a detour from a target function as part of the
current transaction opened by the
[DetourTransactionBegin](DetourTransactionBegin.md) API.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception.md) or [Using
Detours](OverviewUsing.md) in the [Detours Overview](Home.md).

Related Samples
---------------

[Commem](SampleCommem.md), [Cping](SampleCping.md),
[FindFunc](SampleFindFunc.md), [Member](SampleMember.md),
[Simple](SampleSimple.md), [Slept](SampleSlept.md),
[Traceapi](SampleTraceapi.md), [Tracebld](SampleTracebld.md),
[Tracelnk](SampleTracelnk.md), [Tracemem](SampleTracemem.md),
[Tracereg](SampleTracereg.md), [Traceser](SampleTraceser.md),
[Tracetcp](SampleTracetcp.md), [Tryman](SampleTryman.md).
