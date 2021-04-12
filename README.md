Introduction
============

Welcome to HydraGrep. HydraGrep is a grep like utility that lets you search for patterns 
in single files or directories containing files. It is by no means a distributed log search engine
(atleast as of now). It uses multiprocessing to search for the requested pattern recursively, starting from the provided directory.

Differences with UNIX grep
--------------------------

HydraGrep uses a `ProcessPoolExecutor` from the `concurrent.futures` module in the background. It defaults to the system default for the number of parallel workers to use in the pool. 

Inherently, UNIX grep is not parallelizable by default. It needs to be invoked with `xargs` to be parallelized. There is no such external requirement for HydraGrep. It will, by default, use the maximum number of cores available on the machine.

Inspiration
-----------

The name HydraParser is inspired by the Greek Mythological beast called Hydra which was a serpentine monster
with many heads. The heads are analogous to the many threads it uses to run the scans.
