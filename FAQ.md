Detours Frequently Asked Questions (FAQ)
========================================

This page contains a list of questions frequently asked about Detours.
The questions are grouped by general topic and area of interest.

Compatibility
-------------

### *Is Detours compatible with Windows 8?*

Yes. Detours is fully compatible with Windows 8 desktop and server
applications. While Detours can be used in the development and testing
of Window Store apps, new Windows Store apps for Windows 8 can not ship
with Detours.

### *Why can't my Windows Store app for Windows 8 include Detours?*

Windows Store apps may use only a subset of the Win32 API. Detours
requires several Win32 APIs that are forbidden in for Windows App
Certification. Forbidden APIs used by Detours include VirtualAlloc,
VirtualProtect, and FlushInstructionCache.

### *Is Detours compatible with Windows 95, Windows 98, or Windows ME?*

No. Detours is compatible only with the Windows NT family of operating
systems: Windows NT, Windows XP, and Windows Server 2003, etc. Detours
does not work on the Windows 9x family of operating systems because they
have a primitive virtual memory system.

Compiling with Detours Code
---------------------------

### *How do I do thing *X* with Detours?*

Look in the Detours [Samples](Detours_samples.md). The Detours Samples
are quite extensive. It is likely that anything you want to accomplish
with Detours is covered in one of the included samples.

### *Where can I find `detours.lib` and `detours.h`?*

You need to build a version of `detours.lib` for your C/C++ compiler in
the `detours/src` directory by typing `nmake` either in the `detours`
directory or in the `detours/src` directory.

Running with Detours
--------------------

### *Why don't I see any calls to my detour of `malloc`?*

Probably because the target program is not using the `malloc` function
you detoured.

Standard library functions like `malloc` can be linked with a program
either statically, from one of the `libc*.lib` libraries, or
dynamically, from one of the `msvcrt*.dll` libraries. When statically
linked, a program receives its own private version of the standard
library functions. When dynamically linked, a program shares version of
the standard library functions in a DLL. If you detour your private
version of the function, or if the target program uses its own private
version of the function, your detour won't be called by the target
program.

### *Why is Detours packaged as a static library (`detours.lib`) and not as a dynamic link library (say `detours.dll`)?*

Packaging Detours as a statical library minimizes the risk that you will
accidentally detour a function required by the Detours package itself
and reduces versioning problems. Note that Detours adds only about 16KB
when statically linked with your code.

### *Do I still need to use `detoured.dll`?*

No, the `detoured.dll` marker file was removed in Detours 3.0. Before
Detours 3.0, this file was used as marker to guide Microsoft technical
support personnel and tools, like [Windows Error
Reporting](http://msdn.microsoft.com/en-us/library/windows/hardware/gg487440),
by helping them quickly determine that a process has been altered by the
Detours package. Advances in Windows OCA in Windows 7 removed the need
for this marker as Windows 7 maintains a list of DLL that have been
unloaded from a process. Microsoft can not guarantee nor support in any
way, the modification of Microsoft binaries by third parties. Nor can
Microsoft support, in any way, an application that contains Microsoft
binaries modified by third parties. This includes in-memory modification
using the Detours package.

### *How can I debug the startup of my detour DLL?*

The Windbg can single step or break on exceptions in process startup.
Windbg is available in the "Debugging Tools for Windows" download from
on
[www.microsoft.com](http://msdn.microsoft.com/en-us/windows/hardware/gg463009).
For example, you can use the command line:

`windbg -o withdll.exe -d:mydll.dll myexe.exe`

### *Why does my code act differently under a debugger?*

Debuggers insert breakpoints by replacing function code with break
instructions. For example, on the X86 and X64 processors, the debugger
will write a 0xCC (int 3) for a breakpoint. If the breakpoint is written
before a detour is applied, the Detour library will see the 0xCC instead
of the real instructions.

The best way to work around this issue is to ensure that no debugger
breakpoints are set on target functions.

Licensing
---------

### *Can Detours be used in commercial applications?*

Yes, with a Detours Professional license. You can purchase Detours
Professional from the [Microsoft
Store](http://www.microsoftstore.com/store/msstore/en_US/pd/productID.216531800/search.true).

Bug Reports
-----------

### *How do I report a bug?*

Please send detailed bug reports to
[detours@microsoft.com](mailto:detours@microsoft.com?subject=DETOURS%20BUG%20REPORT).
Bug reports may be used to fix bugs in future versions of the Detours
package. Please include the text "DETOURS BUG REPORT" in the subject
line. Within the body of your message, please include the first line
from the README.TXT file which contains the full description of the
version Detours you are using including the Build number.

Before submitted a bug report, please make every effort to insure that
the problem is not an error in your own code or your usage of Detours.
The most common sources of user error are covered in this FAQ.

The detours@microsoft.com email address is for bug reports only, it is
not a product support line.
