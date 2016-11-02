DetourGetContainingModule
=========================

Find the PE binary in a process containg a known function.

Definition
----------

>     HMODULE DetourGetContainingModule(
>         _In_ PVOID vpAddr
>         );

Parameters
----------

*pvAddr*
:   Address of a function in the process.

Return value
------------

Handle to the containing module or NULL if the address doesn't reside in
a loaded PE binary.
