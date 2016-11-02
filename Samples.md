Building The Samples
====================

To build the sample applications, type `nmake` in the samples directory.
Note that you must build the setdll and syslog samples in order to use
many of the other sample programs.

Each of the sample directories has a test, which can be invoked by
typing `nmake test`, to demonstrate the usage of the sample. With very
few exceptions, all of the .exe programs also accept a `/?` command to
display a usage message.

The trace samples log their output through the
[syelogd.exe](SampleSyelog.md) daemon and hook `CreateProcessW` to load
themselves into any child processes. For example, typing
`withdll -d:traceapi.dll cmd.exe` will create a command shell under
which all processes log their API calls through
[traceapi.dll](SampleTraceapi.md).

Detours includes the following samples:

-   [Commem](SampleCommem.md)
-   [Cping](SampleCping.md)
-   [Disas](SampleDisas.md)
-   [Dtest](SampleDtest.md)
-   [Dumpe](SampleDumpe.md)
-   [Dumpi](SampleDumpi.md)
-   [Einst](SampleEinst.md)
-   [Excep](SampleExcep.md)
-   [FindFunc](SampleFindFunc.md)
-   [Impmunge](SampleImpmunge.md)
-   [Member](SampleMember.md)
-   [Region](SampleRegion.md)
-   [Setdll](SampleSetdll.md)
-   [Simple](SampleSimple.md)
-   [Slept](SampleSlept.md)
-   [Syelog](SampleSyelog.md)
-   [Traceapi](SampleTraceapi.md)
-   [Tracebld](SampleTracebld.md)
-   [Tracelnk](SampleTracelnk.md)
-   [Tracemem](SampleTracemem.md)
-   [Tracereg](SampleTracereg.md)
-   [Traceser](SampleTraceser.md)
-   [Tracetcp](SampleTracetcp.md)
-   [Tryman](SampleTryman.md)
-   [Withdll](SampleWithdll.md)

