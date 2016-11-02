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
[syelogd.exe](SampleSyelog) daemon and hook `CreateProcessW` to load
themselves into any child processes. For example, typing
`withdll -d:traceapi.dll cmd.exe` will create a command shell under
which all processes log their API calls through
[traceapi.dll](SampleTraceapi).

Detours includes the following samples:

-   [Commem](SampleCommem)
-   [Cping](SampleCping)
-   [Disas](SampleDisas)
-   [Dtest](SampleDtest)
-   [Dumpe](SampleDumpe)
-   [Dumpi](SampleDumpi)
-   [Einst](SampleEinst)
-   [Excep](SampleExcep)
-   [FindFunc](SampleFindFunc)
-   [Impmunge](SampleImpmunge)
-   [Member](SampleMember)
-   [Region](SampleRegion)
-   [Setdll](SampleSetdll)
-   [Simple](SampleSimple)
-   [Slept](SampleSlept)
-   [Syelog](SampleSyelog)
-   [Traceapi](SampleTraceapi)
-   [Tracebld](SampleTracebld)
-   [Tracelnk](SampleTracelnk)
-   [Tracemem](SampleTracemem)
-   [Tracereg](SampleTracereg)
-   [Traceser](SampleTraceser)
-   [Tracetcp](SampleTracetcp)
-   [Tryman](SampleTryman)
-   [Withdll](SampleWithdll)

