# Hall of Fame Architecture Diagrams - Birds Eye View of your Enterprise

Have you been in the middle of a production incident trying to figure out where it all started? A slight change in UI that allows users to enter a quote in their first name might end up blowing up a report somewhere in EDW. And that process would fail exactly at 3:30 AM when you are in deep sleep. Incidents happen all the time, and nobody can build a perfect system. But the question is: When you are woken up at 3 AM, do you have all the tools & resources you need to find the root cause? This is where Hall of Fame Architecture diagrams fill in the gap.

As a quick preface, I’ll credit my L.L. Bean colleagues Sally Hassey and Andrew Skvorak, who came up with the term “Hall of Presidents”. It will all make sense in a bit."_\*\* Hall of Fame\*\*_" in general terms honors a set of people in a certain field. Presidents Hall of Fame honors all the presidents, WWF Hall of Fame honors of the most successful wrestlers. Just like how we IT nerds repurpose all those common terms and embed it in IT, we will do the same thing with _“Hall of Fame”_

“Hall of Fame” in my terms is a broad view of everything that matters to the enterprise or a Line of Business or both. If I were to write a definition,

> **Hall of Fame (HOF) Architecture** accurately highlights all the critical processes, functions, and channels right from where the data of interest originates all the way to every point of the data’s rest and exit. This architecture is not confined to a single application, domain, line of business or even an organization.

### WHY

Let's start with the why? I mean, why would you need this architecture? I used to be an Integration Architecture handling every integration need for an enterprise. As if that's not overwhelming enough, I was on-call for those integrations. I realized overtime that I am spending more time looking at code, tracing back to an app team to another app team until we find out that the original application has been decommissioned, upgraded, modified, or replaced.

So, I sat down to re-invest the time to connect the dots. We produced this massive 6–8-page of Visio diagram that connects all the dots related to that product data. Looking at that journey of how the product flows across the organization helped me achieve a few things

1. If I get called at 3 a.m. I no longer must look at the code, I just need the HOF Architecture.
2. It gave me glaring insight of how many times app teams have copied this product data to their own domain, and how many processes are running to keep them in sync.
3. I can in a flick tell you who will be impacted if we change the product data. - 0 time on analysis. literally

### WHAT

So what is Hall of Fame Architecture diagrams. How does it differ from the blue print , physical arch or the logical arch. I like using examples. Lets take retail orders data for example:

_An order originates from various channels and potentially merges into an omni channel service layer, most likely a micro service backed by a document database. The order journey goes thru various steps along the way such as marketing emails, transaction emails, inventory, shipping, tracking so on eventually ending up a warehouse._

Following this example, A blueprint, shows a 30,000 ft view of how these systems & applications will “likely” integrate. Its not accurate at the same time, its not wrong either.

A physical architecture shows how the systems should integrate, its still a 15,000 ft view. The architecture is more tailored towards the security and infrastructure. This artifact usually serves as a guidance, and there is factual data for the infrastructure, but not the processes.

High/low level diagrams are factual but are at much more detailed level and usually consumed by leads/developers.

The gap here is, there are no artifacts that have a 30,000 ft. factual view of your orders flow. There are many reasons, such as time, ownership etc., one primarily being architects disengage once the design is complete. Hall of Fame Architecture fills this gap.

This HoF artifact will have every process associated with its property without going into the details. Each process is a text box with its property and where its executing from, simple as that. These processes are then connected with all the associated processes. The key is, the process name is tangible. Below diagramis a simple illustration of Hof architecture for the above example:&#x20;

As you see, each process is a member of the hall of fame, and each process is real and tangible. The checkout page exists, the order\_acceptance is a node.js module and it calls those apis, the edw jobs load the tables with its real table name and so on.

Another thing to observe is, the diagram goes beyond a specific domain/lob. It llustrates how and where the order data physically resides. The architecture also goes deep into which topic/event and channel the data flows thru. The key is, everything is real not just names. If you have a github enterprise, you should be able to find the code/module.

In reality this diagram might be huge, with 100's of process. Please note that we are not going into any detail other than the asset name and some key notes.

### HOW

Its easier said than done, but its worth it. Some may disagree, but the product owner should be responsible for maintaining this artifact. While it may sound like a teadious task, there are certain process that could help make it simple. Here are some of the ideas.you
