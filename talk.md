

# OMG, what did we build?
## Recovering from the hangover of application success

---

![](images/wthhyb.png)

---
# OMG

<br/>
<br/>

## Rick Bradley
### Principal Engineer, Puppet Labs

### github.com/rick

---

## Lives

#### (past and otherwise)

---

### Spent a couple of years trying to rewrite a large clinical system.

<br/>

#### This looked a lot like "green field" work.
#### It totally wasn't.

<br/>

#### "Rewrites" are a messy thing, and quite possibly impossible at any non-trivial scale.

---

### The project was a failure.

---

![](images/tire-fire.jpg)

---

### I mean, I learned a lot.
<br/>

### But, just, fire and craters.

---

### Fortunately, business is often like diplomacy:
<br/>

### There are no "failures", just "frank exchanges of views" and "going back to the table".

---

### Spent 5 years in a 3-person consultancy.

<br/>

#### We thought we were going to do "green field" work.

#### We ended up mostly doing app and team rescues.

---

### Spent 2 1/2 years at GitHub.

<br/>

#### We kind of thought we were going to do "green field" work. _(§)_

#### We ended up mostly doing app and team rescues.

---

### That's a pretty consistent streak of cleaning up after people.

---

### I found myself asking "what is the common factor here?"

---

![](images/rick.png)

---

### Obviously, it's working on "apps".

---

###  I've been at Puppet Labs for just over a year.

<br/>

#### Had no illusions that I would be doing "green field" work.

#### I am not working on "apps" now.

#### Currently revamping our processes and streamlining testing, delivery, etc.

---

### i.e., "(_something something_) and team rescues"...

---

![](images/wthhybl.jpg)

---

---

## "Rescues"

---

### What does that even mean?

---

Something exists that is worth keeping around

---

(it's probably getting more and more valuable over time)

---

That something is in a far from ideal state

---

It's big enough that starting over isn't really an option

---

### We are often inclined to believe that the "something" is the code we have built

---

---

## Conway's Law

---

> Organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations.

<div align="right"><em> -- Melvin Conway</em></div>

---

### Blah blah blah

<br/>

### We've probably all heard this before

---

> If you have four groups working on a compiler, you'll get a 4-pass compiler.

<div align="right"><em> -- ESR</em></div>

---

### Same thing, but for those people who like to talk about ALGOL

---

> The structure of a problem reflects the structure of the organization that created it.

<div align="right"><em> -- Bill Corcoran</em></div>

---

### Now we're getting somewhere

---

### I would actually go further

---

> Every aspect of a system is a direct result of the interactions of the personalities who built that system.

---

### The features of a system derive from the personalities who built it, acting during a time when those features made some sort of sense.

---

### The haphazard construction of parts of a system result from a time where the people involved could do nothing but make those parts haphazard.

---

### The connections and couplings between parts of a system reflect times when people worked together on those systems.

---

### A "rescue" is taking a thing which excelled by a set of past values and transforming it to excel by a set of current or future values.

---

### Treating a "rescue" as a technical problem misses the fundamental reality, and will fail.

---

### Not managing the technical aspects of changing a system will also result in failure.

---

### To get where we need to be, we need to:

 - Understand what is actually important, right now
 - Evaluate paths forward to move towards our goals
 - Change the direction of the people and systems involved

---

## How did we get here?

---

TODO: expand
short version:

 - insight: we saw a need for a tool
   - venn diagram: this was something that we could do better than someone else, it was something that solves a clear and persistent problem, and it is something someone is willing to pay for (h/t @ahpook)
   - we got into the market and had some early success
   - we built on that success and chased the market up
   - we ended up being one of those groups of people who were still left standing some time down the road

 - prioritization:
   - we have only limited resources
   - on the way up we are best spent capturing as much of the market as we can per unit of work
   - if we spend much time otherwise engaged we die
   - "technical debt" is like the aggregate affects of lung can_create_repository
   - gunslingers are way more likely to get shot than they are to live until they develop cancer or emphysema

 - At some point the Wild West settles down
   - the gunslinger has a little ranch, maybe a family
   - it's probably time to quit smoking

 - That was totally a metaphor, y'all


## The technical

---

# TODO: work here -- cut out most of the low-level refactoring stuff; include the characterization testing and long refactorings stuff

# TODO: bring DDD back in
#  - shared language
#  - building consensus
#  - organizing / self-organizing
#  - communicating
#  - prioritizing
#  - "big ball of mud" is totally fine; focus on the one thing
#  - for cross-cutting concerns: introduce metrics; understand the goal; iteratively, repeatedly refine against metrics; set standards and best practices internally

## long refactorings
<br/>

---

## long refactorings are simply refactorings
### only, (IN HINDSIGHT) they end up taking a lot longer than most refactorings

---

### Stepping back for a second...
## What *is* "refactoring"?

---

## Refactoring...

<br/>

### **"behavior-preserving changes to the implementation of a system"**

---

![](images/refactoringBook.jpg)

---

![](images/extract-method.png)

<br/>

<br/>

<br/>

`http://refactoring.com/catalog/extractMethod.html`

---

![](images/inline-method.png)

<br/>

<br/>

<br/>

`http://refactoring.com/catalog/inlineMethod.html`

---

## **"behavior-preserving changes to the implementation of a system"**

<br/>

### This is really only true for the smallest of refactorings.

<br/>
<br/>

### In larger-scale refactorings we're typically chaining together a series of behavior-preserving changes, interspersed with behavior changes.

<br/>

### The important things are to always know which is which, and to do them intentionally.

---

## why do we refactor?

---

### **wankery**

---

### (primarily)

---

### but also...

---

### to understand the system

---


### to understand the system
### to bring behavior under test

---

### to understand the system
### to bring behavior under test
### to extract code for reuse

---

### to understand the system
### to bring behavior under test
### to extract code for reuse
### to improve some facet of the system (performance, memory use, coupling, cohesion, etc., etc., etc.)

---

### to understand the system
### to bring behavior under test
### to extract code for reuse
### to improve some facet of the system (performance, memory use, coupling, cohesion, etc., etc., etc.)
### to reuse existing code elsewhere

---

### to understand the system
### to bring behavior under test
### to extract code for reuse
### to improve some facet of the system (performance, memory use, coupling, cohesion, etc., etc., etc.)
### to reuse existing code elsewhere
### to make room for a new feature

---

### to understand the system
### to bring behavior under test
### to extract code for reuse
### to improve some facet of the system (performance, memory use, coupling, cohesion, etc., etc., etc.)
### to reuse existing code elsewhere
### to make room for a new feature
### to prepare to fix a bug

---

### to understand the system
### to bring behavior under test
### to extract code for reuse
### to improve some facet of the system (performance, memory use, coupling, cohesion, etc., etc., etc.)
### to reuse existing code elsewhere
### to make room for a new feature
### to prepare to fix a bug
### ...

---

### to understand the system
### to bring behavior under test
### to extract code for reuse
### to improve some facet of the system (performance, memory use, coupling, cohesion, etc., etc., etc.)
### to reuse existing code elsewhere
### to make room for a new feature
### to prepare to fix a bug

---

## optimization
<br/>
<br/>

---

## optimization
<br/>
### no, I mean, like, life optimization

---

![](images/small-car.jpg)

## refactoring a toy system

---

![](images/small-car.jpg)

## refactoring a toy system

### it could be for learning purposes
### or perhaps the hope is that some day it will grow up to be a big system
#### one that someone has a use for

---

![](images/small-car.jpg)

## refactoring a toy system

### The value is in building something useful

<br/>

### Even here, though, we have finite time and resources
### So we choose what to work on

---

![](images/india-bus.jpg)

## refactoring a system that people are actively using

---

![](images/india-bus.jpg)

### Again, limited time and resources,
### so we must make choices about what to work on,
### because the time spent on one thing cannot be spent on another.

---

## refactoring to understand a system
### &nbsp;

---

## refactoring to understand a system
### is useful if it is directed towards implementing a feature or fixing a bug
---

## refactoring to bring behavior under test
### &nbsp;
### &nbsp;

---

## refactoring to bring behavior under test
### &nbsp;
### &nbsp;

---

## refactoring to bring behavior under test
### is wasteful, unless it's being immediately driven by fixing a bug or implementing a feature

---

## refactoring to extract code for reuse
### &nbsp;
### &nbsp;

---

## refactoring to extract code for reuse
### is wasteful, unless we have reached the point where a new feature is ready to use that extraction

---

## refactoring to improve some facet of the system
### &nbsp;
### &nbsp;

---

## refactoring to improve some facet of the system
### is generally a good reason to refactor, if this is the most important thing you could be working on right now

---

## refactoring to make room for a new feature
### &nbsp;

---

## refactoring to make room for a new feature
### is great, presuming you're implementing that feature right now

---

## refactoring to prepare to fix a bug
### &nbsp;

---

## refactoring to prepare to fix a bug
### also great, if you're fixing the bug right now

---

---

## optimization
### part deux

---

![](images/matchbox-car.jpg)

## most refactorings are small or trivial

<br/>

### There's really no estimation involved:
### look at the code, start making the changes.

<br/>

### We're using techniques in Martin Fowler's _Refactoring_ book.

<br/>

### The refactorings are a commit or few,
### inside the boundary of a larger pull request,
### dedicated to a feature or a bugfix.

---

![](images/tonka-truck.jpg)

## many refactorings are a bit larger

<br />

### Suitable for a pair of programmers working on an afternoon,
### we can estimate them fairly accurately or do without estimation.

<br />
### We can use simple tools and processes, like feature branches, pair programming, a second or third Pull Request.

<br />

### We start to use more advanced techniques.

---

![](images/working-effectively.jpg)

## We start to draw on these techniques

<br/>

### characterization testing, refactoring to tests, sensing variables, etc.

---

---

![](images/dump-truck-large.jpg)

---

![](images/dump-truck-med.jpg)

## We eventually encounter refactorings that we know are projects

---


![](images/dump-truck-med.jpg)

## We eventually encounter refactorings that we know are projects

<br/>

### These refactorings are non-trivial and perhaps not even possible.
### Even the process of estimation is difficult.

---

![](images/road-block.jpg)

<br/>

### We only consider them because they are roadblocks to important features, or there are real quality problems in this part of the system, and piecemeal attempts at bugfixing fail to eliminate problems.

---

### Developers who go into these areas come back angry and muttering, they turn to the solace of drink.

<br/>

<center>
![](images/dat-rooster.jpg)
</center>

<br/>

## Good people are reduced to bad things.

---

## Tackling these ugly jobs is what we're here to talk about.

---

![](images/mechanic.jpg)

## So how do we tackle these huge refactorings?

---

## There are enough risks that success is unlikely

<br/>

### &nbsp;
### &nbsp;
---

## There are enough risks that success is unlikely

<br/>

### So, aim to minimize costs.
### &nbsp;

---

## There are enough risks that success is unlikely

<br/>

### Aim to never be a roadblock.
### &nbsp;

---

## There are enough risks that success is unlikely

<br/>

### Avoid building the Second System™ -- the promised land of endless biscuits and gravy.

---

## There are enough risks that success is unlikely

<br/>

### Integrate constantly.  Long-running branches are kryptonite.
### &nbsp;
---

## There are enough risks that success is unlikely

<br/>

### Don't go in for Flag Day.
### &nbsp;
---

## There are enough risks that success is unlikely

<br/>

### When the project "lands", it's quietly been in use for weeks or months already.
---

## There are enough risks that success is unlikely

<br/>

### Be like water.
### &nbsp;

---

![](images/be-like-water.jpg)

---

![](images/miner.jpg)

<br/>

## Start with exploration

<br/>

### Spec out possible alternate architectures as proofs of concept.
### &nbsp;

---

![](images/miner.jpg)

<br/>


## Start with exploration

<br/>

### Various people in ones and twos take stabs at feasibility over the course of months or years.

---

![](images/miner.jpg)

<br/>


## Start with exploration

<br/>

### Do throw-away experimental refactorings of a smaller scope just to see if a large refactoring might be possible.

---

![](images/mikado.jpg)

<br/>

### use techniques like those from _The Mikado Method_ to even explore the possible refactorings

---

![](images/mikado-graph.png)

 1. Start with a goal
 2. Do the first small refactoring along the way
 3. See what breaks -- write down a graph node
 4. Repeat until no more dependencies

---

## getting real

---

## "abilities"

---

![](images/permission-bug-0.png)

**June 2012**

---

![](images/permission-bug-1.png)

**July 2012**

---

![](images/permission-bug-2.png)

**July 2012**

---

![](images/permission-bug-3.png)

**July 2012**


---

![](images/permission-bug-4.png)

**July 2012**

---


![](images/permission-bug-5.png)

**August 2012**

---

![](images/permission-bug-6.png)

**September 2012**

---

![](images/permission-bug-7.png)

**September 2012**

---

![](images/permission-bug-8.png)

**September 2012**

---


![](images/permission-bug-9.png)

**September 2012**

---


![](images/permission-bug-10.png)

**November 2012**

---

## A Long Refactoring Kicks Off

### Ongoing quality problems in an important part of the system
### Repeated bugfixing did not improve quality significantly
### High level feature changes roadblocked by this core subsystem

---

![](images/abilities-team.png)

![](images/orgs-team.png)

---

## The Abilities project:

<br/>

### 4 primary developers
### 795 Pull Requests and Issues from November 2012 until August 2014

<br/>

### Multiple iterations of complete new permissioning systems
### Tight collaboration with ongoing Organization improvements

---

## (let's look at those issues)

---

---

![](images/capabilities.png)

**November 2012**

---

![](images/capabilities-1.png)

### Capabilities lived as a new permissions system, side-by-side with existing permissions until August, 2013

---

![](images/recaps.png)

### Until Abilities came onto the scene.

### Extensive performance testing led us to remodel capabilities so that granting operations were more performant

---

## How did we know?

---

![](images/scientist.jpg)

---

![](images/dat-science.png)

---

![](images/dat-science-perf.png)

### We built tools to let us (and anyone) run two code paths side-by-side.
### Then performance data is published by instrumentation into our graphite cluster.

---

![](images/adminable-by-science.png)

---

## Don't Roadblock

<br/>

### Long-running branches are kryptonite.
### We can land short-lived branches to "dark ship" new code.
### With science and instrumentation tools we can gather real production measurements in a controlled fashion.

---

## How to run two permission systems at the same time

### One system is the source of all truth.
### Have a migrator that creates the second system's data from the first.
### The data for the second system is updated by actions on the first system.
### Start with just a subset of users.
### Trash the data and re-run the migrator.
### Eventually never re-run the migrator.


---

![](images/caps-transitions.png)

---

## The project will ebb and flow

<br/>

### Always have enough side project work available that you can stay fresh and not get bogged down.
### People will come and go (and often return) on a truly long refactoring.
### You will be at an impasse many times.
### Rely on your team, and allow yourself to experiment with crazy things.
### Your creativity is an asset.


---

![](images/backscatter.png)

### Sometimes it's just hard to figure out if the code you are changing is even being used. Try to be 100% safe.

---


![](images/backscatter-1.png)

---

![](images/backscatter-2.png)

### Just a glorified wrapper around ruby's `caller` method.

---

![](images/nil-can.png)

### ... which can be put to holy or horrible uses.
---

![](images/horrible-people.png)

### Because, really, we're all such horrible people.

---

## Staying alive

<br/>

### Keep your sense of humor.
### Rely on your peoples.
### Keep close.
### Work-life balance is important.
### This is a marathon.
### Take a vacation.
### You actually can leave and do something else.
### It's fine.

---

## Setbacks

<br/>

### Repository Networks were all jacked up at the model level.
### &nbsp;
### &nbsp;

---

## Setbacks

<br/>

### Repository Networks were all jacked up at the model level.
### "plan owner" data was all shitty due to old bad job processes.
### &nbsp;

---

## Setbacks

<br/>

### Repository Networks were all jacked up at the model level.
### "plan owner" data was all shitty due to old bad job processes.
### Forking and collaborators were all sorts of stupid.

---

## Setbacks

<br />

### You re-learn that you everything is connected.
### You end up having to fix way more things than you hoped.
### And you make some trade-offs and draw boundaries.

---

## Setbacks

<br />

### So we wrote data quality scripts to find problems.
### We wrote transition scripts to clean up problems.
### We wrote throttling tools to make massive transitions never hurt production.

---

![](images/replication-lag-throttler.png)

---

## Estimation

### There is no way I have seen to estimate a long refactoring.
### What you can do is not be a blocker, and continue to negotiate what is the most important thing to fix Right Now.

---

![](images/enterprise.jpg)

## Enterprise

---

## Enterprise

### Installed GitHub instances behind company firewalls.
### Often 6 months behind github.com code base.
### Customers can be 300+ days behind last Enterprise release.
### We have almost zero visibility into installed versions and data quality at a customer's site.
### There are disabled and enabled github.com features on Enterprise.

---

## Enterprise

### Data transitions for github.com are bundled with migrations for Enterprise upgrades.
### Database tables and ActiveRecord models persist in github.com code until Enterprise is fully upgraded.

---

![](images/big-ship.jpg)

## Shipping

---

## Shipping

### Made abilities be the "source of truth" for read queries on teams, and orgs.
### Made abilities be the "source of truth" for repository read queries.
### Continue writing data to *both* permissions systems.
### Gradual removal of science experiment code.

---

![](images/last-science.jpg)

---

![](images/last-ship.png)

---

![](images/last-ship-2.png)

---

![](images/deploy-lol.png)

---

![](images/raptor.gif)

---

## Other long ships

---

![](images/rails3.png)

## Rails 3

<br/>

### Yup.  LOL.

---

![](images/gitrpc.gif)

## GitRPC

---

## Image credits:

https://www.flickr.com/photos/jobless_photoman/7512657396/
octocats: [the octodex](https://octodex.github.com) and its creators

---

## Image credits:

https://www.flickr.com/photos/mozul/31304173/
https://www.flickr.com/photos/uspn/4894253589/
https://www.flickr.com/photos/nate_marsh/5213604228/
https://www.flickr.com/photos/steveallen/3324325493/
https://www.flickr.com/photos/ckrug/162099232/
https://www.flickr.com/photos/slagheap/156203875/

---

## Image credits:

https://www.flickr.com/photos/j3net/480637896/
https://www.flickr.com/photos/jmabel/4516193497/
https://www.flickr.com/photos/27271711@N04/3643199789/
https://www.flickr.com/photos/pixbymaia/9662665997/
https://www.flickr.com/photos/usnavy/7070501561/
https://www.flickr.com/photos/loshak/4839254506/

<br/>

## Images origin unknown:

 - "What the hell have you built."
 - the drinking rooster
 - "What the hell did you build, Luke???"

---
= data-x="1000" data-scale-"2" data-rotate-y="45" data-z="10000"

![](images/riddlocat.png)
