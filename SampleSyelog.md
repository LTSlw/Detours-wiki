Syelog
======

System event logging library and service. All of the tracing samples
connect to `syelogd.exe` through a named pipe. Syelogd outputs tracing
information to the console. You must run `syelogd.exe` in a seperate
window in order to see the output from any of the following tracing
DLLs: [Traceapi](SampleTraceapi.md), [Tracelnk](SampleTracelnk.md),
[Tracemem](SampleTracemem.md), [Tracereg](SampleTracereg.md),
[Traceser](SampleTraceser.md), or [Tracetcp](SampleTracetcp.md).

Uses
----

Uses none of the Detours APIs.
