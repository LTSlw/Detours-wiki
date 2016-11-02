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
    [DetourAttach](DetourAttach),
    [DetourAttachEx](DetourAttachEx), or
    [DetourDetach](DetourAttachEx) that caused transaction
    to fail.

Remarks
-------

`DetourTransactionCommit` commits the current transaction created with
[DetourTransactionBegin](DetourTransactionBegin). Commiting a
transaction make all updates specified in any calls to the
[DetourAttach](DetourAttach),
[DetourAttachEx](DetourAttachEx),
[DetourDetach](DetourDetach), or
[DetourUpdateThread](DetourUpdateThread) APIs within the
transaction.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception) or [Using
Detours](OverviewUsing) in the [Detours Overview](Home).

Related Samples
---------------

[Commem](SampleCommem), [Cping](SampleCping),
[Dtest](SampleDtest), [Excep](SampleExcep),
[FindFunc](SampleFindFunc), [Member](SampleMember),
[Simple](SampleSimple), [Slept](SampleSlept),
[Traceapi](SampleTraceapi), [Tracebld](SampleTracebld),
[Tracelnk](SampleTracelnk), [Tracemem](SampleTracemem),
[Tracereg](SampleTracereg), [Traceser](SampleTraceser),
[Tracetcp](SampleTracetcp), [Tryman](SampleTryman).
