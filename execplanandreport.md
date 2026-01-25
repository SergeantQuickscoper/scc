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

## Week 1
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

## Week 2
This stretch involves the collecting of several research papers in the field of static malware analysis,
intermediate code patterns, gcc plugins, LLVM IR and other topics related to the project. The goal is to
identify "gaps" in the current research and address and make a note of it, potentially leading to features
or implementations for `scc`. A summary document should also be made to mention details from all collected
papers and specify said gaps.

Deliverables:
1) Literature Survey summary document
2) Collection of 15 research papers mentioned in the survey

## Week 3
This stretch focuses on analyzing the functional and non-functional requirements for the project, identifying
users, stakeholders and risks associated with the project and compiling everything into an SRS document.
Furthermore, I will need to decide on target features for the project and wishlist features and prepare a
priority order of what to implement first, and then compile them into documentation.

Deliverables:
1) Software Requirements Specification Document
2) Outline of necessary and wishlist features to implement

## Week 4
This stretch focuses on on building an architecture for `scc` based on the SRS and functional requirements
determined during week 3. I'll come up with a software architecture and divide `scc` into more detailed modules,
other than the two described in this plan. I will also finally decide on one tech stack for the project and 
finally make documentation detailing this phase of the plan.

Deliverables:
1) Software Architecture and Design Document (with diagrams)
2) Decision on tech stack for the application


## Week 5 - 6
This stretch will be targeting the development of the IR pattern analyzer, from the aforementioned
list of "malicious" patterns to look out for. I'll study these patterns and try to come up with a
starter list for this project, and then look into what could be added on as well. As I am planning this,
a worry is how to continue program flow when alot of these patterns will be replaced by dummy statements.
I think that will be a tougher challenge so I will dedicate the post mid sem week to that.

Deliverables:

1) A list of "malicious"/"riskque" patterns to detect (and eventually replace).
2) A plugin for the decided compiler toolchain detectting said patterns (maybe output them into a file).

## Week 7 - Week 11
This stretch focuses on development of the dummy library and also actually replacing the patterns
detected in the previous module. The deliverables should be enough to get the picture:

Deliverables:

1) A dummy library for the functions `scc` is supposed to be replacing.
2) Each function replaced is supposed to have its dummy variant report the behavior in a useful manner (thinking probably a log file for now).
3) A plugin to actually replace the IR patterns with dummy patterns referring to the dummy library.

## Week 12 - Week 14
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
