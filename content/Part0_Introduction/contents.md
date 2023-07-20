# Overview

The world’s largest supercomputers are used almost exclusively to run applications which are parallelised using the message passing programming model. This course covers all the basic knowledge required to write parallel programs using this programming model, and is directly applicable to almost every parallel computer architecture.

Parallel programming by definition involves co-operation between multiple processors to solve a common task. The programmer has to define the tasks that will be executed by the processors, and also how these tasks are to synchronise and exchange data with one another. In the message passing model the tasks are separate operating-system processes that communicate and synchronise by explicitly sending each other messages. All these parallel operations are performed via calls to some message-passing interface that is entirely responsible for interfacing with the physical communication network which actually links the processors together.

This course uses the de facto standard for message passing, the Message Passing Interface (MPI), which comprises a library of functions. It covers point-to-point communication, non-blocking operations, derived datatypes, virtual topologies, collective communication and general design issues.

This version of the course is designed for online self-study with all lectures pre-recorded. MPI is completely portable across all systems, so it can even be installed on your own laptop, but the exercises for this instance have been configured for the UK national supercomputers ARCHER2 and Cirrus. You will be provided with an account on one of these systems.

This course is free to all academics.


---

## Learning Outcomes

On completion of this course students should be able to:

- Understand the message-passing model in detail
- Implement standard message-passing algorithms in MPI
- Debug simple MPI codes
- Measure and comment on the performance of MPI codes
- Design and implement efficient parallel programs to solve regular-grid problems


## Prerequsites

This course does have a couple of prerequisites in order to get the most out of the material:
```{prereq}

   Experience programming in C, C++ or Fortran.

```

Note that the course does not cover the details of how to use MPI from Python.

---


```{figure} ./../images/BayesInterior.jpg
```

## About EPCC

Since 1990, EPCC has developed a reputation for leading-edge capability in all aspects of High Performance Computing (HPC). Based at the University of Edinburgh, we work with industry, academia, public and third-sector organisations to promote the adoption and value of HPC.

With a team of more than 110 highly qualified specialists, we have an exceptional pool of talent. Our engineers and technical staff have a powerful combination of practical and theoretical knowledge that keeps EPCC at the forefront of industry and research.

```{raw} html
<iframe width="700" height="400" src="https://www.youtube.com/embed/NEgbVNIo560" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

EPCC aims to accelerate the effective exploitation of novel computing throughout industry, academia and commerce. 

This has been our mission for over 30 years as we strive to be the UK’s premier Supercomputing centre, renowned internationally for innovation and leading-edge research.

Our work is guided by key goals and objectives that support this mission and place EPCC at the heart of the Exascale era.

Delivering world-class services
We will continue to deliver world-class High Performance Computing (HPC) and data services to benefit our users and partners. As well as supporting businesses with our advanced computing facilities and capabilities.

Leading data-driven innovation 
We are a pivotal element in the success of the Edinburgh and South East Scotland City Region Deal and its Data-Driven Innovation initiative.

Collaborating globally
We will continue to build and maintain collaborations and strong relationships with key organisations worldwide, undertaking globally-important computing research.

Promoting teaching excellence
We endeavour to maintain our position as a major provider of HPC training in Europe.

---

## About {{ machine_name }}

{{ '{include} ../../substitutions/substitutions_REPLACE/REPLACE_description.md\n'.replace("REPLACE",machine_name) }}

