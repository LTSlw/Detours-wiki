Microsoft Research Detours Package Overview
===========================================

Detours is a library for intercepting binary functions on ARM, x86, x64,
and IA64 machines. Detours is most commonly used to intercept Win32
APIs calls within an application, such as to add debugging
instrumentation. Interception code is applied dynamically at runtime.
Detours replaces the first few instructions of the *target function*
with an unconditional jump to the user-provided *detour function*.
Instructions from the target function are placed in a *trampoline*. The
address of the trampoline is placed in a *target pointer*. The detour
function can either replace the target function or extend its semantics
by invoking the target function as a subroutine through the target
pointer to the trampoline.

Detours are inserted at execution time. The code of the target function
is modified in memory, not on disk, thus enabling interception of binary
functions at a very fine granularity. For example, the procedures in a
DLL can be detoured in one execution of an application, while the
original procedures are not detoured in another execution running at the
same time. Unlike DLL re-linking or static redirection, the interception
techniques used in the Detours library are guaranteed to work regardless
of the method used by application or system code to locate the target
function.

In addition to basic detour functionality, Detours also includes
functions to edit the DLL import table of any binary, to attach
arbitrary data segments to existing binaries, and to load a DLL into a
new process. Once loaded into a process, the instrumentation DLL can
detour any function in the process, whether in the application or the
system libraries, such as the Windows APIs.

This technical overview of Detours is divided into four sections:

-   [Interception of Binary Functions](OverviewInterception.md)
-   [Using Detours](OverviewUsing.md)
-   [Payloads and DLL Import Editing](OwerviewPayloads.md)
-   [Detouring 32-bit and 64-bit Processes](OverviewHelpers.md)

Developers new to Detours will find the it very useful to read all four
technical overview sections and the [Simple](SampleSimple.md) sample.

This documentation also contains the following information:

-   [Detours API reference](Reference.md)
-   [Sample programs using the Detours APIs.](Samples.md)
-   [Frequently Asked Questions (FAQ)](FAQ.md)

