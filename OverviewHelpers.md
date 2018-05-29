Detouring 32-bit and 64-bit Processes
=====================================

The most common usage scenario for Detours is to detour functions in an
existing application without modifying the orginal application binaries.
In these scenarios, the user-supplied detour functions are packaged in a
DLL that is loaded into the applicaiton at startup time using the
[DetourCreateProcessWithDll](DetourCreateProcessWithDll) API.
The [DetourCreateProcessWithDll](DetourCreateProcessWithDll) API
is called from the *parent process*; it alters the in-memory copy of the
application by inserting an import table entry for the detour DLL. This
new import table entry causes the OS loader to load the DLL after the
application process has started, but before any of the application code
can run. The detour DLL then has a chance to hook target functions in
the *target process*.

In computers with 64-bit processors, Windows supports both 32-bit and
64-bit applications. To support both 32-bit and 64-bit applications, you
must create both 32-bit and 64-bit versions of your detour DLL. You must
also replace all uses of the
[DetourCreateProcessWithDll](DetourCreateProcessWithDll) API
with either the
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx) API
or [DetourCreateProcessWithDlls](DetourCreateProcessWithDlls)
API. The
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx) and
[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls) APIs
chooses between the 32-bit or 64-bit versions of your DLL as appropriate
for the target application.

What To Do
----------

To support both 32-bit and 64-bit applications on a single system, you
must create two DLLs. One DLL must contain 32-bit code, the other DLL
must contain 64-bit code. The DLLs must reside in the same directory and
must have identical names except that the name of the 32-bit DLL should
end with "32" and the name of the 64-bit DLL should end with "64". For
example, matching DLLs would be named `foo32.dll` and `foo64.dll`.

You should use the
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx) or
[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls) API
to start a process with your DLL. Furthermore, your DLLs must:

**Export the
[DetourFinishHelperProcess](DetourFinishHelperProcess) API as
export ordinal 1**.

**Call the [DetourIsHelperProcess](DetourIsHelperProcess) API**
in your `DllMain` function. Immediately return TRUE if
[DetourIsHelperProcess](DetourIsHelperProcess) return TRUE.

**Call the
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx) or
[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls) API**
instead of
[DetourCreateProcessWithDll](DetourCreateProcessWithDll) to
create new target processes.

How It Works
------------

In the case where both the parent process and the target process are the
same, such as both 32-bit or both 64-bit, the
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx) API
works the same as the
[DetourCreateProcessWithDll](DetourCreateProcessWithDll) API.

When the parent process is 32-bit and the target is 64-bit or the parent
is 64-bit and the target is 32-bit,
[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx)
creates a *helper process* by loading your DLL into a `rundll32.exe`
process, and calling
[DetourFinishHelperProcess](DetourFinishHelperProcess) through
export Ordinal 1. This API patches up the application's import table
using the correct 32-bit or 64-bit code.

Give It a Try
-------------

To give helper processes a try, first build the Detours samples for
32-bit using a 32-bit build environment. Then build the samples for
64-bit using a 64-bit build environment. Then in the `samples\tryman`
directory, in the 64-bit environment type "`nmake size64`" to run a
recursive set of processes that alternate between 32-bit and 64-bit
processes.

Remarks
-------

For more information on `rundll32.exe`, see
<http://support.microsoft.com/kb/164787>.

Related APIs:
-------------

[DetourCreateProcessWithDllEx](DetourCreateProcessWithDllEx),
[DetourCreateProcessWithDlls](DetourCreateProcessWithDlls),
[DetourFinishHelperProcess](DetourFinishHelperProcess),
[DetourIsHelperProcess](DetourIsHelperProcess),
[DetourRestoreAfterWith](DetourRestoreAfterWith).

Related Samples
---------------

[Simple](SampleFindFunc), [Simple](SampleSimple),
[Slept](SampleSlept), [Traceapi](SampleTraceapi),
[Tracebld](SampleTracebld), [Tracelnk](SampleTracelnk),
[Tracemem](SampleTracemem), [Tracereg](SampleTracereg),
[Traceser](SampleTraceser), [Tracetcp](SampleTracetcp),
[Tryman](SampleTryman).
