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
[DetourAttach](DetourAttach) or
[DetourAttachEx](DetourAttachEx) API to attach a detour to a
target function, calls the [DetourDetach](DetourDetach) API to
detach a detour from a target function, or calls the
[DetourUpdateThread](DetourUpdateThread) API to include include
a thread in the transaction update.

The attach, detach, and thread operations do not take effect until the
program commits the transaction using the
[DetourTransactionCommit](DetourTransactionCommit) or
[DetourTransactionCommitEx](DetourTransactionCommitEx) API.
Alternatively, the program can abort the transaction using the
[DetourTransactionAbort](DetourTransactionAbort) API.

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
