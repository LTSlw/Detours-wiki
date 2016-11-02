DetourCodeFromPointer
=====================

Return a pointer to the code that implements a function pointer.

Definition
----------

>     PVOID DetourCodeFromPointer(
>         _In_      PVOID pPointer,
>         _Out_opt_ PVOID *ppGlobals
>         );

Parameters
----------

*pPointer*
:   Pointer to the function.

*ppGlobals*
:   Variable to receive the address of the function's globals data.

Return value
------------

Returns a pointer to the code implementing the function.

Remarks
-------

`DetourCodeFromPointer` returns a pointer to the code that implements a
function pointed to by a function pointer. When a binary is statically
linked against a DLL, pointers to functions from the DLL often point not
to the code from the DLL, but to a jump statement in the binary's import
table. `DetourCodeFromPointer` returns the address of the actual target
function, not the jump statement.

On some platforms, function pointer point to indirection labels, not
code. On these platforms, the indirection labels also contains a pointer
to the global (or static) data associated with the function.

For more information on using Detours to intercept function calls, see
[Interception of Binary Functions](OverviewInterception) or [Using
Detours](OverviewUsing) in the [Detours Overview](Home).

Related Samples
---------------

[Slept](SampleSlept), [Tracebld](SampleTracebld).
