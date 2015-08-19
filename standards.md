# eQualit.ie Coding Standards and Development Practices

**How to now make crap software/systems**

## Overview

Here in we're going to describe the approach eq will take as an organisation to standardising
its approach to software and system development. As an open source entity, eq has a fundamental
need to create maintainable, shareable, understandable code. As a tech company working on new
problems eq should and will take on the effort of adopting best practices iteratively evolved
in the tech field. It will also share its process and methodologies in the hope of
encouraging and helping others get on track to having clean awesome code.

## How to use this document

Eq has lots of projects, they are written in lots of languages and run on different kinds of
systems and platforms. This guide is intended to run from the general to the specific. To that
end it is broken into sections describing general principles for software dev and specific
things you have to do in terms of specific languages/systems.

This is a living document, contribute to it, update it, improve it or it will die and that
will have been your fault. You could have saved it but you didn't. Why didn't you, you
callous monster?!

## An eq project is born

So you have an eq project, or you're about to start one. What are its component parts?

1. An initial proposal with specification
2. A full project specification
3. A repository on Github.com- private only where absolutely necessary
4. A project skeleton, including automation scripts, a test bed, etc.
5. A description of the contribution process (write, commit, review, feedback, merge, loop)

### Specifications

No project exists without a spec – this is built ideally from a more primordial requirements
document. As eq is primarily grant funded a version of the specs document will have been
created through collaboration with grant team and the dev team. This can form the basis
of the official project specification.

The specs will outline the core elements of a project decomposing from abstract to as
granular as possible. They describe what actions will be taken to build and complete
the entire project, from its modules to its functionality.
This should stop at the level above pseudo code but should describe any reliances
or dependencies.

The purpose of a specs is to expose what elements of a project are clear to build and what
elements are areas of uknown or uncertainty. By identifying areas of potential uncertainty
up front the project can better plan its time and protect itself from black hole caveats. 

### Project timeline / Gantt chart

Once the specs have been drawn up, you can just start coding right? No, get out you're fired.
If the spec is ok and someone else in eq, ideally someone with a critical eye, then the next
thing your project needs is tasks.

At the time of writing this document eq was using redmine – if this has changed this section
should be updated. These are the steps to follow to correctly plan out your project:

1. Create a new Redmine project.
  * If one already exists, the first step is to clean out any old tickets
2. Define abstract tickets covering the major elements of the project
3. Break these "parent" tickets into core elements and pieces of functionality; pieces of work
4. Recurse down through the tickets until you achieve the most attainable level of granularity
  * Tickets at this level should require one to three days to complete, and at most one week
5. Iterate through all the tasks and mark dependencies between them
6. Based on the project timeline allowance and the specs, determine the order to approach tasks
  1. With the interdependencies defined, you should now have a critical path for the project
  2. You should have broken the tasks into their smallest size
  3. Set start and end dates for all these tasks

If you have correctly completed all of these steps you now have a gantt chart – what good is a
Gantt chart...I'm glad you asked. Because a Gantt chart is not just a failed pretty picture
it's a physical representation of where your project is at. Now you will know the following
things:

* Is the project on time?
* Why is the project not on time?
* Which component is behind?
* What is the cause of the block?
* Is the blockage human or software?

### Runbook

In theory this only applies to systems but that doesn't have to be the case. In fact, a run
book for eq projects is invaluable to our sysops team. If you are the dev that gave them not
just a tagged release(discussed under ) but also a complete guide in how to deploy and use
your software. Even better, your deployment instructions will allow them to
generate Ansible scripts..and one beautiful day we might not even need sysadmins :)

A runbook describes:

1. Who has worked on the project
2. What were those peoples' responsibilities, e.g. to modules and functionality
3. Who heads the project
4. What should the service look like when it's running properly
5. What should the service look like when something is broken
6. Where the dependencies and required precondition descriptions can be found
7. Where installation instructions can be found

### Github repository

Most eq projects are open source – our fundamental tenant is that we share. At the time
of writing this document all eq projects are hosted via Github – if this changes, this
section should be updated.

What does an eq Github look like? Some good examples are our
[bundler](https://github.com/equalitie/bundler) and
[edgemanage](https://github.com/equalitie/edgemanage)
projects.

A repository will contain:

1. A detailed README
2. The project source code and automation/build scripts
3. A test bed, including any unit and integration tests
4. The specification documents
5. The project's CI (continuous integration) build badge
6. Issues describing what is currently broken or needs improving
7. Packaged releases

There are some things a repository should **never** contain:

1. Real log files from any system the project is deployed to
2. Information about eq's partner organisations
3. Identifying information about any groups or individuals
4. Passwords, login credentials, keys, or hardcoded configuration settings
5. Unnecessarily specific information about the project's expected use or target audience

## Have you done all that?

Ok then you can start to build an eq project :)...which involves lots more things you have
to do :D BUT once you've done these things you will gain respect, admiration and you will
make your own life easier.

## The development process

As you start to develop the project, here are the things you need to be thinking about.

### Documentation

Your project is described by it's specs but these – while useful for code audits - are
not your front facing propaganda. Eq projects are not only for our own use we are trying
to build libraries of tools that have real use for other people. Part of doing that
requires us to respect what other people need and to be respectful enough not to waste
their time with terrible poorly written docs.

The structural template for a good piece of documentation is as follows.

1. The overview (one paragraph, max)
  * Describes what the project is for
  * What problems the project solves differently
  * Who should use it
  * The kind of technology that's used
2. Installation instructions and system specs and requirements
  * What kind of system the software expects to be run on
  * Dependencies, configurations, and setup requirements
  * How to run the software
3. A (link to a) runbook
  * This should come with the deployment scripts/virtual machines/recipes required to run
4. Software description 
  * Explanation of the underlying technology
  * Diagrams and explanations explaining the design methodology
  * Explanations for the dependencies
  * Caveats in the software
5. An API specification
6. Historical information about the software
7. Contact information
  * Links to eq websites
  * Instructions for how to reach devs/maintainers

### Communication

Do you speak empathy? Projects that do best have a good sense of how to talk to themselves
and to others. There are two forms of comms for a project team comms and stakeholder comms.

#### Team communications

In eq we use a team lead structure – though we are non-hierarchical we steal roles and
responsibilities from the software industry where we feel it benefits us. The job of the
team lead is to maintain internal and external comms for a project.

  * Team members should be able to express their needs and requirements
  * The team should be a safe space where anyone can voice their concerns about the project and thair peers
  * The team lead is responsible for encouraging communication as a means to monitor the project's health
  * Where issue occur within the team, the lead should seek guidance from the technical coordinator, the director, and the director of operations

**Team members should practice respect for each other's efforts and time. Eq does not
consider aggressive, selfish, or behaviour which otherwise negatively impacts someone else
to be acceptable on any level.**

#### Stakeholder communications

Everyone in eq is, to some extent, a stakeholder in our projects. But there are also specific
roles that have specific vested interests in knowing what's happening within a project.

##### Health checks

Once a week the technical coordinator will collect from all teams a health check.
This is essentially a short meeting which covers where the teams is at in terms of
goals met or missed. Depending on the outcome of the meeting any next steps to
rectify problems will be determined and enacted.

##### Quarterly reporting

Eq produces regular detailed reports on its work for funders and ideally also the public,
to let everyone know what we've done and our successes. :)

Reports will be created by the team lead and technical coordinator based on the completed
Redmine tickets for the given quarter.

##### Time logging

At a date set by the Operations Director, each team will submit their logged hours. In
reality, this will be handled by redmine time tracking.

##### Team holidays

In the event that a team member or indeed the team lead wishes to take a holiday. This
must be communicated to the team lead at least 3 -4 weeks prior to the planned break.
This is to allow adequate time to plan for the unavailability of the individual. The
team lead will in turn communicate this to the technical coordinator and operations
director.

Though it is extremely unlikely, in rare occassions, because of pressing deadlines,
it may not be possible to give time off at the chosen moment – if for example it,
conflicts with a deadline or release. With proper advanced planning this kind of
conflict should not occur.

### The development cycle

This process starts when a developer has taken up an issue or a ticket.

1. Create a new branch
  * The branch name should be short but descriptive, ideally including a redmine ticket number
  * The branch should be based on the most stable point to which the task is relevant
2. Write the code
3. Run your tests
  * Code should not be committed **at all** until all tests pass
4. Run any automated tasks
  * Linters
  * Formatters
  * Static analysis tools
  * etc...  
5. Submit a pull request
  * Find someone to review your code
  * Review feedback and make any appropriate adjustments
6. Merge your branch into master and destroy your branch

### Code review

**Code review is mandatory! :)**

Eq projects are typically handled by small teams with diverse skills.
As a convenient way to avoid having projects isolated from other teams, everyone should
participate in code review at different points in a project's development, especially if
you are not directly part of that project.

Code review is not strictly limited to code, but should also include things like recipes
for deployment. Documentation can also be reviewed to ensure it is of sufficiently high
quality and that instructions are clear and accurate.

Our director of operations is a professional editor. All documentation should be passed
to her and other proficient technical individuals.

### Testing

Did you recently commit some code you wrote? Did it have tests? If no, delete it. Also,
you're fired.

What types of tests exists and why do we need them? First of all, the goal of testing is
not to bore you to death instead it's to make the transition from spec to code really
easy. A test is a physical embodiment of what the program is supposed to do. When your
test passes, you're done.

When you begin a project, or retrofit an existing one, the first step is to recreate
the spec/tickets describing your project as a set of modular tests.

* Unit tests
  * Tests the smallest unit of functionality conceivable, such as a single function
  * Shuld be focused on a specific feature
* Integration tests
  * Build on unit tests by testing that the combinations of units function correctly
* Functional tests
  * Check a particular feature for correctness
  * Compares the result for a given input against the specification
* Acceptance tests
  * Abstract tests that track user stories
  * Ensures the system functions as expected in documented use cases

Apart from helping developers to easily write good code, test let us know if a
regression has occurred and, if so, where.  They also give us a lot of information
about what is likely the best way to deal with a problem.

#### Testing systems

##### Python

##### C/C++

##### Javascript

##### Go

##### Java

##### PHP

### Coding standards

For a long time people made god awful code, they lied to themselves and said “I'll fix
it later” or “It's grand it's just one commit” - those people are not us.

Eq uses an array of different languages, tools, platforms and systems. So we have chosen
the following standards for coding practices:

#### Python

#### C/C++

#### Javascript

#### Go

#### Java

#### PHP

#### Ansible

Your project must use and run the appropriate linter for each language you use.
If you feel like it, you can increase the level of pedantry, but never reduce it.

### Releases and versioning

#### Releasing software

Eq defines a software **release** as

> A package containing everything anyone needs to get a piece of software running
> right out of the box.

That means that, when you are ready to submit a release of your software through
Github and/or the project's official website, you should have compiled all of the
resources, binaries, distributables, configuration files, source code, and
documentation that a user needs into one place.

Once your packaged has been created, you are _strongly encouraged_ to (read:
you absolutely **must**) follow these steps before submitting it:

1. Download the package to a virtual machine used exclusively for testing builds
  * Recall that Eq largely builds for the latest [stable Debian](https://www.debian.org/releases/stable/), so use that
2. Set up the software by blindly following the packaged documentation
  * You want to make sure that someone who has never touched the project can run it
  * Assume no background knowledge or preconditions
3. Run the software and verify that it runs as expected

If this final task can be completed without any trouble, you can deploy your release!

#### Versioning releases

It is good practice in software development to use a versioning scheme that
accurately describes the state of the software you are releasing.  Eq has decided to
use and **strictly adhere to** the [semantic versioning](http://semver.org/) scheme.
