DetourAllocateRegionWithinJumpBounds
====================================

Allocate an executable region near the given address.

Definition
----------

>     PVOID WINAPI DetourAllocateRegionWithinJumpBounds(
>         _In_ LPCVOID pbTarget,
>         _Out_ PDWORD pcbAllocatedSize
>     );

Parameters
----------

*pbTarget*
:   The address to start searching for an allocatable space from

*pcbAllocatedSize*
:   The variable to receive the size of the allocated region in bytes

Return value
------------

If successful, returns the base address of the allocated region of pages;
otherwise, returns `NULL`.

Remarks
-------

`DetourAllocateRegionWithinJumpBounds` tries to allocate a region near enough to make a jump from the given address.

To free a region allocated by `DetourAllocateRegionWithinJumpBounds`, use the `VirtualFree` function.

As explained in [Interception of Binary Functions](OverviewInterception), Detours writes a relative jump with a signed 32-bit offset into a target function to make a jump to a detour function.  This means the detour function needs to be placed within +/- 2GB of the target.  `DetourAllocateRegionWithinJumpBounds` allocates an executable region which Detours can write a jump from the given target address to.  This is useful if you want to dynamically craft a detour function.