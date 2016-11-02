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
[DetourTransactionBegin](DetourTransactionBegin). Aborting a
transaction reverse the effects of any calls to the
[DetourAttach](DetourAttach),
[DetourAttachEx](DetourAttachEx),
[DetourDetach](DetourDetach), or
[DetourUpdateThread](DetourUpdateThread) APIs made within the
transaction.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception) or [Using
Detours](OverviewUsing) in the [Detours Overview](Home).
