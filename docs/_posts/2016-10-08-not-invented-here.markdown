---
layout: post
title:  "Not Invented Here"
date:   2016-10-08
---
I have many times encountered developers that think they can solve problems better than anyone else before them. In many cases they end up with reinventing the wheel. Instead of using off-the-shelf open source or commercial software, they insist on doing their own implementation. This is commonly know as the Not Invented Here syndrome.

For instance, some people might implement there own HTTP cache instead of using well-known, high-performant open source products like Varnish or Nginx. Another example is when people don’t want to use an SDK that is provided by a service vendor such as AWS, but instead use the HTTP API and thus have to implement error handling, retries and authentication on their own instead of relying on a ready-made implementation by the service vendor.

This fallacy leads to several problems. First of all the initial effort to develop the software is wasted, especially if there are free (as in free beer) alternatives. Secondly, the custom solution needs to be maintained. The belief that software is “done” after the initial release is another fallacy. Software that you build is a liability. The third, and probably most severe problem is that the software built in-house is most likely less reliable and performant than a proven, battle-tested piece of software.

There are multiple explanations for this (in my eyes) irrational behaviour:

* Lack of trust in off-the-shelf software
* Underestimation of the complexity of the problem at hand
* Exaggerated trust in their own abilities and competence
* Unwillingness to try to understand how to use the off-the-shelf software

## What can we do to fight this?

In my experience, this problem takes time and effort to tackle. One approach that might work is to try to convince people that you should at least give the off-the-shelf software a try. Just as an experiment before you start coding. Try it out for a short period of time to see if it fulfils your needs. If you still decide to go for a custom implementation, you have a baseline to benchmark against.


