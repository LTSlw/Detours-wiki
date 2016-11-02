DetourTransactionBegin
======================

Begin a new transaction for attaching or detaching detours.

Definition
----------

>     LONG DetourTransactionBegin(VOID);

Return value
------------

Returns NO\_ERROR if successful; otherwise returns
ERROR\_INVALID\_OPERATION.

Error codes
-----------

**ERROR\_INVALID\_OPERATION**
:   A pending transaction alrady exists.

Remarks
-------

`DetourTransactionBegin` begins a new transaction for attaching or
detaching detours.

After beginning a transaction, a program calls the
[DetourAttach](DetourAttach.md) or
[DetourAttachEx](DetourAttachEx.md) API to attach a detour to a
target function, calls the [DetourDetach](DetourDetach.md) API to
detach a detour from a target function, or calls the
[DetourUpdateThread](DetourUpdateThread.md) API to include include
a thread in the transaction update.

The attach, detach, and thread operations do not take effect until the
program commits the transaction using the
[DetourTransactionCommit](DetourTransactionCommit.md) or
[DetourTransactionCommitEx](DetourTransactionCommitEx.md) API.
Alternatively, the program can abort the transaction using the
[DetourTransactionAbort](DetourTransactionAbort.md) API.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception.md) or [Using
Detours](OverviewUsing.md) in the [Detours Overview](Home.md).

Related Samples
---------------

[Commem](SampleCommem.md), [Cping](SampleCping.md),
[Dtest](SampleDtest.md), [Excep](SampleExcep.md),
[FindFunc](SampleFindFunc.md), [Member](SampleMember.md),
[Simple](SampleSimple.md), [Slept](SampleSlept.md),
[Traceapi](SampleTraceapi.md), [Tracebld](SampleTracebld.md),
[Tracelnk](SampleTracelnk.md), [Tracemem](SampleTracemem.md),
[Tracereg](SampleTracereg.md), [Traceser](SampleTraceser.md),
[Tracetcp](SampleTracetcp.md), [Tryman](SampleTryman.md).
