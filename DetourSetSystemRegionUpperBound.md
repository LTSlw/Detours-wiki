DetourSetSystemRegionUpperBound
===============================

Set the lower bound of the region of memory that cannot be used for
trampolines because it is reserved for system DLLs.

Definition
----------

>     PVOID DetourSetSystemRegionUpperBound(
>         _In_ PVOID pSystemRegionUpperBound
>         );

Return value
------------

Returns the previous upper bound value.

Parameters
----------

*pSystemRegionUpperBound*
:   Specifies the upper bound of the system region into which Detours
    must avoid placing trampolines.

Remarks
-------

The [DetourAttach](DetourAttach.md) and
[DetourAttachEx](DetourAttachEx.md) APIs allocate a trampoline for
each detoured function. To avoid fragmenting memory, Detours attempts to
create the region from which it allocates trampoline as close as
possible to the code being detoured. In some circumstances, trampoline
region can collides with memory that is silently set aside by the OS or
the application for DLLs that are loaded later. When this happens, the
application continues to bahave correctly, but the OS can be forced to
relocate one or more DLLs to another location, which increase the
virtual memory required for the process.

To avoid these DLL-relocation collisions, Detours is programmed to avoid
placing any trampolines in region of memory called the "system region".
By default, this region is from 0x70000000 to 0x80000000. Call
[DetourSetSystemRegionLowerBound](DetourSetSystemRegionLowerBound.md)
and
[DetourSetSystemRegionUpperBound](DetourSetSystemRegionUpperBound.md)
and to change the region. For example, one might increase the region if
the CLR is loaded into a process after system DLLs are detoured.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception.md) or [Using
Detours](OverviewUsing.md) in the [Detours Overview](Home.md).

Related Samples
---------------

[Region](SampleRegion.md).
