DetourSetIgnoreTooSmall
=======================

Enable or disable transaction abort on a failure to attach or detach an
individual detour function.

Definition
----------

>     BOOL DetourSetIgnoreTooSmall(
>         _In_ BOOL fIgnore
>         );

Return value
------------

Returns true if Detours was previously ignoring failures to detour
target functions too smal for detouring.

Parameters
----------

*fIgnore*
:   Specifies whether to ignore functions that are too small to detour.
    If this parameter is set to **TRUE**, these functions will be
    ignored if encountered. If this parameter is set to **FALSE**, then
    encountering a function too small to be detoured will cause
    [DetourTransactionCommit](DetourTransactionCommit) to fail.

Remarks
-------

`DetourSetIgnoreTooSmall` sets the flag to determine if failure to
detour a target function that is too small for detouring is sufficient
error to cause abort of the current detour transaction.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception) or [Using
Detours](OverviewUsing) in the [Detours Overview](Home).

Related Samples
---------------

[Traceapi](SampleTraceapi).
