---
layout: post
title: "Distributed Retrospectives with Slack"
date: 2017-07-15 04:22:14 -0700
tags: agile retrospective
---

The most rewarding meeting for me is by far the team retrospective. It is the opportunity to pause, express gratitude, and look collaboratively for ways to continuously improve as a team.  It builds trust, it removes bottlenecks, it provides learnings, and it accelerates positive outcomes for the company.  It's a great meeting.   

Recently, I've switched projects to join a team with locations in Oregon, San Jose, Paris, and Hong Kong.  There is no good time for us to meet.  Asking people to arrive early or stay late would be especially counterintuitive to the spirit of the Retrospective. Is it possible to hold an effective Retrospective without everyone in a reasonably overlapping timezone?

Our team already uses Slack for the majority of all communication.  IMO, Slack has 2 killer features.  
1. It's awesome UX.  
2. It's marketplace of integrations.  

Since we already use a Slack bot ([GeekBot](http://geekbot.io)) to conduct our daily standups it got me thinking it may be possible to conduct a distributed retrospective via Slack.  The result would be an asynchronous retrospective spread across multiple days in order for the team to collaboratively build off each others ideas and eventually come to an action plan without requiring anyone to wake up in the middle of the night to participate.  

## Monday: Gather Data
Using Geekbot I wrote up the typical retrospective questions scheduled to ping everyone at 9am in their local timezone.  

![Slack Retro]({{site.url}}/assets/slack-retro.png)

After 9am hits around the globe the bot kindly asks users the retrospective questions (with reminders if they miss the message) and consolidates the answers into a #retrospective channel.  A day later we had lots of rich commentary and data points flowing in.  This allows everyone to comfortably answer the retrospective questions in their own timezone.  

## Tuesday: Generate Insights
If we were all in the same room I would have liked to do an [affinity mapping](http://gamestorming.com/core-games/affinity-map/) exercise to start pulling out common themes in order to have some focused conversations.  Since I couldn't think of a whole team approach to efficiently do this asynchronously, I just did it myself. Oh well.  I consolidated a list of 10 pain points, doing my best to not reinterpret or significantly alter the original feedback, and shared them in our #retrospective channel.  

![Part 2]({{site.url}}/assets/slack-part2.png)

In order for the team to come together and focus on a couple pain points I pulled out another Slack integration: [Simple Poll](https://simplepoll.rocks).  I Created a poll with the list of 10 pain points I curated in order for the team to vote on what to address.  Another day goes by to give everyone a voice.

![Identify focus points]({{site.url}}/assets/slack-poll.png)

## Wednesday: Decide What To Do
With polling results in the goal was now to come up with proposals for action.  For each of the 3 top voted pain points I configured our slack bot to ask the question "What is something actionable we can do to change this?". This gives everyone the space to think and respond to actionable next steps for the top pain points the team identified.  Another day go by to let the results come in.

![Actions]({{site.url}}/assets/slack-results.png)

## Thursday: Commit and close
By the fourth day we have a pretty good list of team generated proposals for the top team voted pain points.  In order to commit to take action I created one last poll.  Summarizing the list of action proposals the team generated I created a final poll asking "Which action(s) from our retrospective will you do in the next 2 weeks?".

![Commit and Close]({{site.url}}/assets/slack-commit.png)

The polling results stay live on the #retrospective channel so we can check back to see who is working on improving what.

## Final thoughts
It's hard creating a unified, collaborative, self-organizing team culture with a distributed team across multiple timezones. An asynchronous chat based retrospective is of course not ideal as the empathy from being face to face can be lost, the persistent nature of the chat logs may discourage vulnerability, and the synergy of building off each others ideas in a dedicated meeting can be harder to achieve when spreading out the conversation across multiple days.  It also takes extra time to curate and guide the retrospective across multiple days.  

Despite the challenges, the effort to create a healthy, collaborative, full team retrospective when working closely with teammates across the globe is well worth it.   Is your team distributed across timezones and doing regular retrospectives?  If so, how do you perform your retrospectives?  
