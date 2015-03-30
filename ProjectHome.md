This is a snapshot of the ongoing work to use the Linux Seccomp mode for implementing a sandboxing solution.

This code is intended to be used in the Linux version Google Chrome as means to restrict security critical parts of the browser from making arbitrary unsafe system calls.

Ultimately, we intend to write a general purpose library that can be used by any program that has sandboxing requirements. But it will probably be still a while before we get there.