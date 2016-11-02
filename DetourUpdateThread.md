DetourUpdateThread
==================

Enlist a thread for update in the current transaction.

Definition
----------

>     LONG DetourUpdateThread(
>         _In_ HANDLE hThread
>         );

Parameters
----------

*hThread*
:   The handle of the thread to be updated with the pending transaction.

Return value
------------

Returns NO\_ERROR if successful; otherwise, returns an error code.

Error codes
-----------

**ERROR\_NOT\_ENOUGH\_MEMORY**
:   Not enough memory to record identity of thread.

Remarks
-------

`DetourUpdateThread` enlists the specified thread for update when the
current transaction, opened by the
[DetourTransactionBegin](DetourTransactionBegin.md) API, commits.

When a detour transaction commmits, Detours insures that all threads
enlisted in the transcation via the `DetourUpdateThread` API are updated
if their instruction pointer lies within the rewritten code in either
the target function or the trampoline function.

Threads not enlisted in the transaction are not updated when the
transaction commits. As a result, they may attempt to execute an illegal
combination of old and new code.

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
