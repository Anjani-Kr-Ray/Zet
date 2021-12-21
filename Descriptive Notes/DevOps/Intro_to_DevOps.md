# Intro To DevOps

## Complete Software Development Process

Let us take an example of Facebook. To build an application we require all different `IT roles`

1. Programming
	- Software is programmed by developers
	- in different languages, e.g. Java, Python, JavaScript
	- one team per app or feature
	- new functionality
	- fix bugs

2. Software Testing
	- test the **new features**
	- test the **old code/functionality**
	- testing is done by developers and dedicated testers
	- **automated** testing

3. Release of Software
	- build application 
	- run on servers
	- update the existing applications

To release a software, operation team comes into play.

4. Operations 
	- run software in production
	- release software with no downtime meaning upgrade should be seamless so that person using that software don't have to wait whenever an update pops up
	- handle huge traffics

So, from the above reading we can say that Development and Operations team have `different responsibilities`, `different technical knowledge` and works with `different tools`.

Development side is more about knowing:
- programming languages
- test frameworks
- databases 
- version control

Whereas, Operations Teams deals with:
- OS, mostly Linux
- command line
- scripting
- monitoring tools

But as they work together, there must be good communication between both of the teams. In reality,  there is silos between these two. So there is big communication gap.

Software development team developes the software and testers test them and basically it is ready to get released. But to release operations team `requires configuration` which can be anything like `environment variables` or `folder on servers` or may need a `database` with certain configurations. Whatever it is, OP team has to prepare the server and deploy the software.

To help with it, dev team **documents instructions** on how to deploy the software. Then they hand the build artifact with the instructions to the operations team. 
OP team tries to follow these instructions but usually this doesn't work because either the instructions are not clear or something is missing. 

To solve this prolem DevOps culture was introduced. 
- DevOps was just a way of working between DEV's and OP's
- Common language to communicate
- Became its own role and job because many new concepts and tools were introduced and to become an DevOps engineer we had to learn them

## DevOps tasks and responsibilities
- needs some know-how from DEV and OPs team
- **additional DevOps specific skills and know-how** like building **CI/CD Pipelines** to make the process of transitioning the ready application to release process as well as some other technologies like **docker and Kubernetes** to help transitioning process easier and effective

**One thing which heavily influence is *`speed`* and *`process of software development`* in an organization or the way organization is developing the applications**

### Traditional way: Waterfall Method
* Requirements --> plan everything before
* Development --> developers code complete app
* Testing --> testing after everything has developed
* Operations --> huge preperation

Though its simple but was ineffective because
-	overtime new requirements
-	many places of failures and miscommuication
-	no fast feedback

### Alternative: Agile Methodology
- speed of development, testing and deployment cycles
- each features gets tested, deployed
- immediate feedback
- fast development and deploymet process
- scrum and kanban - specific implementations
- Agile is the heart of continuous integration and continuous delivery process

> Note: DevOps implements best practices that agile frameworks introduces.










