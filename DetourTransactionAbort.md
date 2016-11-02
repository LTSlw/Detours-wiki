DetourTransactionAbort
======================

Abort the current transaction.

Definition
----------

>     LONG DetourTransactionAbort(VOID);

Return value
------------

Returns NO\_ERROR if the pending transaction was completely aborted;
otherwise, returns an error code.

Error codes
-----------

**ERROR\_INVALID\_OPERATION**
:   No pending transaction exists.

Remarks
-------

`DetourTransactionAbort` aborts the current transaction created with
[DetourTransactionBegin](DetourTransactionBegin.md). Aborting a
transaction reverse the effects of any calls to the
[DetourAttach](DetourAttach.md),
[DetourAttachEx](DetourAttachEx.md),
[DetourDetach](DetourDetach.md), or
[DetourUpdateThread](DetourUpdateThread.md) APIs made within the
transaction.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception.md) or [Using
Detours](OverviewUsing.md) in the [Detours Overview](Home.md).
