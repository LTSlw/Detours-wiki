DetourTransactionCommitEx
=========================

Commit the current transaction.

Definition
----------

>     LONG DetourTransactionCommitEx(
>         _Out_opt_ PVOID ** pppFailedPointer
>         );

Parameters
----------

*pppFailedPointer*
:   Variable to receive the target pointer passed to the
    [DetourAttach](DetourAttach),
    [DetourAttachEx](DetourAttachEx), or
    [DetourDetach](DetourAttachEx) call that caused the latest
    transaction to fail.

Return value
------------

Returns NO\_ERROR if successful; otherwise, returns an error code.

Error codes
-----------

**ERROR\_INVALID\_DATA**
:   Target function was changed by third party before the transaction
    could complete.

**ERROR\_INVALID\_OPERATION**
:   No pending transaction exists.

**Other Codes**
:   Error code returned by API within
    [DetourAttach](DetourAttach),
    [DetourAttachEx](DetourAttachEx), or
    [DetourDetach](DetourAttachEx.htl) that caused transaction
    to fail.

Remarks

`DetourTransactionCommitEx` commits the current transaction created with
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

[Traceapi](SampleTraceapi),
