---
layout: post
title:  "How to develop Microservices without bogging down your laptop"
date:   2018-10-12
---
When you walk in to a room full of developers these days, you get immediately struck by the noise and heat from their development laptops. The computers are really struggling under the load of multiple Docker containers all want to have their fair share of the CPU and memory. Even though everyone is working on a single service at a time, they still need to deploy a handful of other services and a few different data stores a message bus and perhaps a web server. Without all those other things, their service won’t even start. A common solution to this problem is to throw in more hardware. Faster CPUs! More memory! Faster and bigger SSDs! Now your development machine has become a server.

## There are better ways

Let’s start with the most fundamental question: Why do you need to run the service on your laptop at all? The obvious response is: To see that it’s working! The thing is that there is another well-established way of finding out if your software is doing what it is supposed to do: automated tests. If you have to start the whole application to check if it’s working, I would argue that you have some tests to write. Tests that can give you confidence that your new functionality is good and that you haven’t broken anything that worked before. Many tests can be written to run without any external dependencies, but you also need tests that can verify that your code works together with other services and infrastructure components. For that you need integration tests. You _could_ run those on your laptop, but you don’t have to. Set up the build server to deploy the new code to a test environment and have it run the tests there. A bonus benefit is that you will avoid the problem of “it works on my machine!”.

There are situations when you actually do need to run your service locally. The most common is when you’re developing a GUI. Humans are still better than machines to see if a GUI looks and feels good. But that doesn’t mean you necessarily need to go all the way and run all those dependencies.

## Fake it

Let’s say your working on service A which needs to make requests to service B to fetch some data. It does that using HTTP and Json. Instead of firing up service B you have three choices:

1. Point to an instance of service B in some test environment. The main advantage of this approach is that there is not much you need to do. Just change the configuration and you’re good to go. However, depending on your infrastructure and security policy, the test environment might not be accessible from your office network. Setting up a VPN connection would solve that problem. Another drawback is that someone else might alter data in the test environment with the effect that you cannot trust that you get the same results all the time.

2. Deploy a fake service B. This could be as simple as starting a web server that serves static files that you have captured from the real service B and placed on disk. python -m SimpleHTTPServer is your friend. In some other scenarios you might need something more sophisticated, e.g. tools that can record real interactions and replay those as canned responses.

3. Introduce a stub in your code that will return canned responses without going out over the network. Given that you have introduced proper abstractions in your code, this is fairly easy to implement.

## Final words

My advice is to give your laptop a break. It’s job is to run your IDE, not a full server workload. If you don’t trust that your service is working when your tests pass — write more and better tests. And stub out those dependencies as often as you can.
