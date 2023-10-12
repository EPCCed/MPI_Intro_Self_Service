# Overview

The world’s largest supercomputers are used almost exclusively to run applications which are parallelised using the *message passing* programming model. This course covers all the basic knowledge required to write parallel programs using this programming model, and is directly applicable to almost every parallel computer architecture.

Parallel programming by definition involves co-operation between multiple processors to solve a common task. The programmer has to define the tasks that will be executed by the processors, and also how these tasks are to synchronise and exchange data with one another. In the message passing model the tasks are separate operating-system processes that *communicate* and *synchronise* by explicitly sending each other messages. All these parallel operations are performed via calls to some message-passing interface that is entirely responsible for interfacing with the physical communication network which actually links the processors together.

This course uses the de facto standard for message passing, the *Message Passing Interface* (MPI), which comprises a library of functions. It covers point-to-point communication, non-blocking operations, derived datatypes, virtual topologies, collective communication and general design issues.

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

Before starting the lecture material it is important that you obtain an account on one of the target HPC systems, ARCHER2 or Cirrus, and that you can log in. 
This block also contains some information on options for viewing the videos which are hosted by the University of Edinburgh's Media Hopper Create service.


## Prerequisites

This course has prerequisite for the students to get the most out of the material:
```{prereq}
  Experience programming in C, C++ or Fortran. 
```

Note that the course does not cover the details of how to use MPI from Python.

## Requirements and Logging In

You will have been given instructions on how to obtain an ARCHER2 or Cirrus account after registering for the course.
To connect to the EPCC systems for the practicals, participants must use a Mac, Linux, or Windows system (not a tablet, Chromebook, etc.). All attendees are also required to abide by the ARCHER2 Training [Code of Conduct](https://www.archer2.ac.uk/about/policies/code-of-conduct.html).

Full instructions on how to log in to ARCHER2 are available in the [online ARCHER2 documentation](https://docs.archer2.ac.uk/user-guide/connecting/). If you have any problems connecting then please contact the ARCHER2 helpdesk (support@archer2.ac.uk).
Full instructions on how to log in to Cirrus are available in the online [Cirrus documentation](https://cirrus.readthedocs.io/en/main/user-guide/connecting.html). If you have any problems connecting then please contact the Cirrus helpdesk (support@cirrus.ac.uk).


## Questionnaires
Before you begin this self-service course, we would be most grateful if you could complete this [short pre-course questionnaire](https://forms.office.com/r/gjT6ME4cmr). 

Once you have completed the course, please complete the [post-course questionnaire](https://forms.office.com/r/aUth2aKHvD).


## Feedback

When you have finished the course, please fill in the [Feedback Form](https://www.archer2.ac.uk/training/feedback/?course=210000-mpi-self-service). This is designed to be anonymous, although you can leave your contact details if you wish. We use the same form for all training courses, so some questions (e.g. regarding the venue) may not be relevant.

---


```{figure} ./../images/BayesInterior.jpg
```

## About EPCC

Since 1990, EPCC has developed a reputation for leading-edge capability in all aspects of High Performance Computing (HPC). Based at the University of Edinburgh, we work with industry, academia, public and third-sector organisations to promote the adoption and value of HPC.

With a team of more than 110 highly qualified specialists, we have an exceptional pool of talent. Our engineers and technical staff have a powerful combination of practical and theoretical knowledge that keeps EPCC at the forefront of industry and research.

```{raw} html
<iframe width="700" height="400" src="https://www.youtube.com/embed/NEgbVNIo560" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br><br>
```

EPCC aims to accelerate the effective exploitation of novel computing throughout industry, academia and commerce. 

This has been our mission for over 30 years as we strive to be the UK’s premier Supercomputing centre, renowned internationally for innovation and leading-edge research.

Our work is guided by key goals and objectives that support this mission and place EPCC at the heart of the Exascale era.

**Delivering world-class services**

We will continue to deliver world-class High Performance Computing (HPC) and data services to benefit our users and partners. As well as supporting businesses with our advanced computing facilities and capabilities.

**Leading data-driven innovation** 

We are a pivotal element in the success of the Edinburgh and South East Scotland City Region Deal and its Data-Driven Innovation initiative.

**Collaborating globally**

We will continue to build and maintain collaborations and strong relationships with key organisations worldwide, undertaking globally-important computing research.

**Promoting teaching excellence**

We endeavour to maintain our position as a major provider of HPC training in Europe.

---


## Media Hopper Create

This short video shows you the different viewing options you have for the videos with multiple streams.

Most of the lectures in the course have two streams - one for the slides and one for the camera - but some of the earlier lectures do not. Screen captures (e.g. recordings of coding sessions) also only have a single stream.

Note that this video itself is a screen capture with a single stream - having a multi-stream video containing a demo of a multi-stream video would be rather unwieldy!

```{raw} html
<iframe width="700" height="400" src="https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/2010292/uiconf_id/32599141/entry_id/1_w169hu09?wid=_2010292&iframeembed=true&playerId=kaltura_player&entry_id=1_w169hu09&flashvars[streamerType]=auto&flashvars[localizationCode]=en&flashvars[leadWithHTML5]=true&flashvars[sideBarContainer.plugin]=true&flashvars[sideBarContainer.position]=left&flashvars[sideBarContainer.clickToClose]=true&flashvars[chapters.plugin]=true&flashvars[chapters.layout]=vertical&flashvars[chapters.thumbnailRotator]=false&flashvars[streamSelector.plugin]=true&flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&flashvars[dualScreen.plugin]=true&flashvars[Kaltura.addCrossoriginToIframe]=true&&wid=1_b0t8dczm#" title="Kaltura video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

```

---


## Using the Command Line

Hopefully, you have managed to log on to ARCHER2 without too much trouble. If this was your first experience using the terminal it is worth spending some time to familiarise yourself with it. At the very least, you should understand what the below commands do (try them on ARCHER2!) and be comfortable using them.

    ls
    cd
    mkdir
    touch
    rm
    cp
    mv
    pwd
    find or locate
    grep
    man

There is a lot of materials online on basic shell commands - feel free to use whichever you find the most useful. For an entertaining introduction to basic commands see Joe Topjian's book [Unix for the Beginning Mage](../exercises/shell-tutorial.pdf). There is also material at the Software Carpentry site on using the Unix shell - [http://swcarpentry.github.io/shell-novice/](http://swcarpentry.github.io/shell-novice/). 


