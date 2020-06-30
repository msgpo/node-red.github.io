---
layout: blog
title: Going beyond Node-RED 1.x
author: nick
description: With the 1.1.0 release done, its time to think about what comes next for the project. Find out how we're proposing to approach future releases of Node-RED and what that means for longer term support.
---

With the 1.1.0 release done, our attention turns to the next release. But before
we push ahead with the next item on the backlog, it's a good moment to think about
the bigger picture

We reached our 1.0 milestone last October. This was a major point for us to reach
and it took quite a while to get there. And it has taken us 9 months to get to the
this latest release. That delay was not ideal as it has meant many new features
have been sat around for months, waiting to be released.

This is an unfortunate result of being an open-source project that cannot take
for granted anyone's involvement. Whilst I am in a fortunate position to be able
to dedicate a very large part of my day job working on the project, that is not
the case for many of the other contributors who help out.

Our approach to scheduling releases has been fairly relaxed. We haven't set
target dates too far in advance and at some point we would decide we have 'enough'
new content to warrant publishing a new release.

Prior to the 1.0 release, we would also, on occassion, make a change that shouldn't
be made in a minor-version number release. For example, dropping support for older
versions of Node. You can just about get away with that when you are a 0.x versioned
project, but now we are a 1.x versioned project, we need to take more care.

As it stands, we still technically support running on Node.js 8.x - even though
that version of Node stopped being maintained at the start of this year. And we certainly
have an eye on the fact that Node 10.x drops out of maintenance at the end of April
next year.

Whilst we certainly wouldn't recommend it, we understand some users are stuck on
older versions, and we don't want to needlessly break them if we can avoid it.

But nor can we continually hold ourselves back from being able to make use of new
Node.js features in the core runtime.

We also recognise that for the companies who have adopted Node-RED into their own
commercial solutions, they need a degree of confidence in how long any particular
version of Node-RED will be supported.

So with all of that in mind, here is the current *proposal* for how we manage
releases in the future.

![](/blog/content/images/2020/06/release-plan.png)

At the bottom, the chart shows the [published dates](https://nodejs.org/en/about/releases/)
for the current Node.js releases.

The top shows the proposed release schedule for Node-RED.

In summary, we aim to do a minor version release (for example, 1.1 &rarr; 1.2)
every three months.

At the end of April 2021, when Node 10.x reaches its end-of-life, we will publish
Node-RED 2.x that will *drop* support for both Node 8.x and Node 10.x.

The 1.x stream will then enter maintenance mode for the rest of the year. It will
only receive bug fixes, but with room for new features to be back-ported from 2.x
if there is a very good reason to do so.

The 2.x stream will contine in active development with a minor release every three months
until Apil 2022 when Node 12.x reaches its end-of-life, we publish Node-RED 3.x and
the cycle continues.

This proposal means:

 - We have a regular cycle of releases - getting new features into the hands of users.
 - We have a plan that enables us to make potentially breaking changes once a year.
 - We have a schedule to help us prioritise and plan backlog items.


It is important to remember this plan is not risk-free. It assumes, in good
faith, that the project has enough contributors to help deliver it. We're hopeful
that having a published schedule of releases will help encourage people to contribute,
whether in code, documentation, testing or just general feedback.

We will see how it goes over the next few months. If something isn't working and
we have to rethink this plan, then we will.

But for now, we make a start on getting 1.2 ready for the end of September.

