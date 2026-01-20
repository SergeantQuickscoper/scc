# SCC Execution Plan

Disclaimer: This document is simply for the reference of me 
and the evaluators of my CD course. It's messy, unformatted,
incoherant and not to be read as an actual introduction to 
the project.

Brief: SCC will be a pattern analyzer to extract a list of 
artbitary syscalls and patterns relating to malware or
priviledge escalation and replace them with logs to analyze 
software behavior. It will probably be a completely 
deterministic model and will consist of the following set
of deliiverables:

- A pattern analyzer and replacer designed for a suitable IR set
- A dummy library containing the actual functions to replace the sensitive ones

## Week 1 - 2
- Decide on the following:
    - What compiler toolchain to base this off of? (gcc, LLVM?)
        - Feasability of adding an extra pipeline to the selected toolchain
        - Ease of Reading the IR in question
        - How much of the extra features I want to implement myself?
    - List of calls to restrict (without breaking most of program flow kind of like a debugger), so do research on:
        - Malware development
        - Privilage Escalation
        - Sensitive File R/W
        - whatever else
    - Tech Stack
        - Probably C but implementing the dummy library in Rust seems fun
        - LLVM vs gcc
        - If I have time maybe code some of the frontend myself
    - Get a list of useful research papers to help with this idea ig
    - How to actually detect patterns and replace them without breaking the code?
    - How much memory isolation can be done at compile stage?(look into mmap restrictions)

Deliverables:

1) Useful Research Papers related to IR pattern recognition
2) Create decision with reasoning on each bullet point

## Week 3 - 4
This stretch will be targeting the development of the IR pattern analyzer, from the aforementioned
list of "malicious" patterns to look out for. I'll study these patterns and try to come up with a
starter list for this project, and then look into what could be added on as well. As I am planning this,
a worry is how to continue program flow when alot of these patterns will be replaced by dummy statements.
I think that will be a tougher challenge so I will dedicate the post mid sem week to that.

Deliverables:

1) A list of "malicious"/"riskque" patterns to detect (and eventually replace).
2) A plugin for the decided compiler toolchain detectting said patterns (maybe output them into a file).

## Week 4 - Week 8
This stretch focuses on development of the dummy library and also actually replacing the patterns
detected in the previous module. The deliverables should be enough to get the picture:

Deliverables:

1) A dummy library for the functions `scc` is supposed to be replacing.
2) Each function replaced is supposed to have its dummy variant report the behavior in a useful manner (thinking probably a log file for now).
3) A plugin to actually replace the IR patterns with dummy patterns referring to the dummy library.

## Week 9 - Week 10
This stretch will be to just document this project enough for the semester presentation, create demos,
and make testcases. Also if time permits, get some wishlist features done.

Deliverables:

1) A report detailing the development process, demos and testcases for showcasing `scc`.

## Wishlist (for presentation)
1) An in-depth config system for `scc` so that users could select specific patterns to target.
2) Memory isolation at compile time.
3) Replacing as much of the compile process as possible with my own tools.

## Wishlist (for self-fulfillment)
1) Create an in-depth behavior analysis experience, something beyond just logging.
2) Create a custom environment designed to run these special sandboxed executables. (Could be a whole new project?).
3) Expand the "starter" list.

LaTeX version of doc: https://www.overleaf.com/read/ddpfvycmfvzm#1edb44 
