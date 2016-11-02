DetourSetRetainRegions
======================

Force Detours to retain trampoline allocation regions even after the
trampolines have been released.

Definition
----------

>     BOOL DetourSetRetainRegions(
>         _In_ BOOL fRetain
>         );

Return value
------------

Returns true if Detours was previously retaining unused trampoline
regions.

Parameters
----------

*fRetain*
:   Specifies whether trampoline memory allocation regions should be
    retained (and reused) after all of the trampolines in the region
    have been released. If this parameter is set to **TRUE**, these
    regions will be retained. If this parameter is set to **FALSE**,
    then region will not be retained.

Remarks
-------

Detours allocated trampolines from contiguous regions of 64KB of memory.
By default, these regions will be returned to the OS when all of the
trampolines in the region have been release (detached). However, in some
cases, such as when a program frequently attaches, detaches, and
reattaches, it may be desirable to retain the memory regions.

Detours releases prior to version 3.0 always retained trampoline
regions. For backward compatibility, some programs may want to force
this deprecated behavior by calling `DetourSetRetainRegions(TRUE)`.
