DetourTransactionCommit
=======================

Commit the current transaction.

Definition
----------

>     LONG DetourTransactionCommit(VOID);

Return value
------------

Returns NO\_ERROR if successful; otherwise, returns an error code.

Error codes
-----------

**ERROR\_INVALID\_DATA**
:   Target function was changed by third party between steps of
    the transaction.

**ERROR\_INVALID\_OPERATION**
:   No pending transaction exists.

**Other**
:   Error code returned by API within
    [DetourAttach](DetourAttach.md),
    [DetourAttachEx](DetourAttachEx.md), or
    [DetourDetach](DetourAttachEx.md) that caused transaction
    to fail.

Remarks
-------

`DetourTransactionCommit` commits the current transaction created with
[DetourTransactionBegin](DetourTransactionBegin.md). Commiting a
transaction make all updates specified in any calls to the
[DetourAttach](DetourAttach.md),
[DetourAttachEx](DetourAttachEx.md),
[DetourDetach](DetourDetach.md), or
[DetourUpdateThread](DetourUpdateThread.md) APIs within the
transaction.

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
