DetourAttachEx
==============

Attach a detour to a target function and retrieve additional detail
about the ultimate target.

Definition
----------

>     LONG DetourAttachEx(
>         _Inout_   PVOID * ppPointer,
>         _In_      PVOID pDetour,
>         _Out_opt_ PDETOUR_TRAMPOLINE * ppRealTrampoline
>         _Out_opt_ PVOID * ppRealTarget
>         _Out_opt_ PVOID * ppRealDetour
>         );

Parameters
----------

*ppPointer*
:   Pointer to the target pointer to which the detour will be attached.

*pDetour*
:   Pointer to the detour function.

*ppRealTrampoline*
:   Variable to receive the address of the trampoline.

*ppRealTarget*
:   Variable to receive the final address of the target function.

*ppRealDetour*
:   Variable to receive the final address of the detour function.

Return value
------------

Returns NO\_ERROR if successful; otherwise, returns an error code.

Error codes
-----------

**ERROR\_INVALID\_BLOCK**
:   The function referenced is too small to be detoured.

**ERROR\_INVALID\_HANDLE**
:   The ppPointer parameter is null or points to a null pointer.

**ERROR\_INVALID\_OPERATION**
:   No pending transaction exists.

**ERROR\_NOT\_ENOUGH\_MEMORY**
:   Not enough memory exists to complete the operation.

Remarks
-------

`DetourAttachEx` attaches a detour to a target function and retrieves
additional detail about the ultimate target as part of the current
transaction opened by the
[DetourTransactionBegin](DetourTransactionBegin) API.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception) or [Using
Detours](OverviewUsing) in the [Detours Overview](Home).
