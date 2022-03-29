---
layout: post
title:  "Why we are not as agile as we could be"
date:   2018-01-12
---
The promise of Agile is that we should be able to develop and modify our software to meet the needs of the quickly changing business. I think we have improved comparing to how it used to be in the waterfall era, but I still think we can do much better that we currently do. We’re still struggling with problems like:

* having a hard time understand what our users need
* our software is hard to change
* fire-fighting to fix bugs
* long cycle times from idea to production deployment

Let’s break down each of those issues and see how we can improve.

## Having a hard time understand what our users need

Many organizations follow the Scrum methodology, or at least they say they do. In Scrum there is a role called _Product Owner_. The Product Owner is supposed to be a representative for the business and hence should “know” what the business, i.e. the users, need. In many cases the Product Owner is part of the IT organization and therefore acts as a proxy for the business at best. In practice they are more of a traditional project manager.

What if we could get a person that actually uses or will use the system we’re building to sit with the development team? Then the team can discuss how the system should work with a person who is an expert on the business processes the system should support. The team could do rapid prototyping and get immediate feedback. It might not be realistic to have this person sitting with the team at all times, since she or he have other duties as well. But maybe a few hours every day? Since this person will get the benefits of the software system, this person is the real Customer.

## Our software is hard to change

There are many reasons why a system is hard to change, but most of it boils down to one thing: it is poorly designed. It might have been in good shape when it was new, but over time it has suffered from design rot. There is a well-known remedy for design rot, it is called Refactoring. If we continuously refactor our system, we will not only prevent the design to go bad but we will actually improve the design over time.

The design needs to be improved at all times, interrupting the usual workflow to do a “refactoring sprint” from time to time will not do. Whenever a developer finds an opportunity to improve the design, even the smallest thing, they should take a moment and refactor. For this to work, it is essential that there is a culture in the team that allows for anyone to make changes to any part of the software. This is called _Collective Code Ownership_.

Another practice that supports good design is Test Driven Development (TDD). When TDD is done properly it includes refactoring as well.

It’s not just that design tends to go bad over time, we make bad design by introducing unnecessary complexity. Usually this comes from applying complex frameworks and patterns that is not needed to solve the problem at hand. If we aim for the simplest design possible we will be better off.

## Fire-fighting to fix bugs

One category of bugs comes from misunderstandings of the business. Those can be avoided if we use the practice with an embedded Customer described above.

Another category of bugs are those that are actual errors in our program, where the software does not behave as the programmer intended. Those bugs can most of the time be eliminated with automated tests that the developers write. Writing tests after the implementation is done is hard and boring. Therefore it’s common that developers don’t write them at all. Again, Test Driven Development helps you here by mandating that the tests are written before the implementation. If you apply TDD rigorously, you will cover all the important parts of the system with tests and you will see that the number of bugs that slips through are drastically reduced.

## Long cycle times from idea to production deployment

One effective way of shorten the cycle time is to eliminate waiting time and non-productive work. It is very common that teams use the Pull Requests model from the open source world. Typically this means that one or more developers work on a feature in a branch in the version control system until they feel it is finished. They then submit a Pull Request and waits for another developer to review their changes and rubber-stamp an approval. When approved, the feature branch can be merged into the main (master or trunk) branch.

One problem with this approach is the review process. Since the Pull Request includes a full feature, it is usually quite large with changes in hundreds or even thousands of lines of code. This makes it very hard to review which means that usually it is only glanced over quickly before it is approved. Hence the review is not very effective. Another problem is that the developers who issued the PR has to wait for the review to be completed. This can take days. During that time they can of course start something new, but the reviewer might actually spot things that need to be changed and thus the developers has to switch context.

When the branch is going to be merged into the main branch, there can for sure be problems. The main branch has probably changed quite a bit since the branching and hence there are risks of merge conflicts and other integration problems.

Again, there are established solutions to those problems. Instead of a review process, the team can program in pairs. Then there is no need for a separate review, since the code is being reviewed all the time!

To avoid integration problems and merge conflicts, the team could integrate with the main branch every day. Or even several times a day! This is known as Continuous Integration.

## Putting it all together

To be more agile than we are today we could start practicing:

* Embedded Customer in the team
* Refactoring
* Collective Code Ownership
* Test Driven Development
* Simple Design
* Pair Programming
* Continuous Integration

Those practices are not part of Scrum, but they are in fact all prescribed practices in another, sadly almost forgotten, agile process called Extreme Programming (XP). Extreme Programming is best described in Kent Beck’s book [Extreme Programming Explained](https://www.goodreads.com/book/show/67833.Extreme_Programming_Explained). So go ahead and read this fantastic book and become as agile as you could be!
