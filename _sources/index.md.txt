# Message-Passing Programming with MPI

## About this course

The world’s largest supercomputers are used almost exclusively to run applications which are parallelised using the message passing programming model. This course covers all the basic knowledge required to write parallel programs using this programming model, and is directly applicable to almost every parallel computer architecture.

Parallel programming by definition involves co-operation between multiple processors to solve a common task. The programmer has to define the tasks that will be executed by the processors, and also how these tasks are to synchronise and exchange data with one another. In the message passing model the tasks are separate operating-system processes that communicate and synchronise by explicitly sending each other messages. All these parallel operations are performed via calls to some message-passing interface that is entirely responsible for interfacing with the physical communication network which actually links the processors together.

This course uses the de facto standard for message passing, the Message Passing Interface (MPI), which comprises a library of functions. It covers point-to-point communication, non-blocking operations, derived datatypes, virtual topologies, collective communication and general design issues.

This version of the course is designed for online self-study with all lectures pre-recorded. MPI is completely portable across all systems, so it can even be installed on your own laptop, but the exercises for this instance have been configured for the UK national supercomputers ARCHER2 and Cirrus. You will be provided with an account on one of these systems.


## Who is the course for?

This course is primarily aimed at scientists, researchers, developers, students and academics who are interested in message passing programming using MPI and in running their applications on the UK national supercomputers ARCHER2 and Cirrus.

## Course Contents

```{toctree}
---
maxdepth: 2
---
Part0_Introduction/contents
Part1_Message_Passing_Overview_and_Introduction_to_MPI/contents
Part2_Point_to_Point_Communication/contents
Part3_Intermediate_Topics/contents
Part4_Case_Study_and_Performance_Metrics/contents
```



