---
layout: post
title: "Mob Programming: Two Months In"
date: 2017-05-03 06:16:14 -0700
tags: dev agile mob
---

![Team Mobbing]({{site.url}}/assets/mobbing.jpg)

About two months ago our team jumped from doing all work individually in a scrum team to mob programming in a scrum team. Now, I broke the 'rules' here a bit. From what I've read, general recommendation is to gradually introduce mob programming to a team by doing sessions for a couple hours each week.  We didn't do this.  We tried it for 8hrs one day, liked it, and as Kent Beck says 'Turned Up the Good' to making the de facto way of work for the last two months.

Mob Programming is where whole team works on the same thing, at the same time, in the same space, and at the same computer.  It is pair programming, super sized.  It is not immediately intuitive in how it could make sense from a cost and efficiency perspective.  But after trying it, the results are surprising. We are delivering positive outcomes at higher than previous average sprint velocities, and are having a good time doing it.  Here are some of the successes and challenges I've seen in our team working in a mob.  I think it's worth pointing out that with so many variables at play (team dynamics, corporate culture, domain of work, agile maturity, etc) the successes and challenges I'm sure will be unique to each team.  

Here are some things I've noticed.

## Excess Work Goes Away
One of the most satisfying pieces of mob programming I've seen is how much simpler the final designs are that get merged into our master branch.  Many a times in code review have I seen the comment "This widget could be refactored in *this way* to provide *this benefit*.. **but** it's OK how it is, we can **do it later**".  And then the code gets merged, the comment is lost for ever, the refactor never happens and there continues to be a sore spot in that component whenever someone works on it.  Rather than wait for feedback in code review on how a design might be better and risk not being able to implement it due to the higher cost of rework, the design gets simplified on the fly through all the unique and brilliant people on the team at the earliest possible moment.  

> "Simple can be harder than complex: You have to work hard to get your thinking clean to make it simple. But it's worth it in the end because once you get there, you can move mountains." -- Steve Jobs

## Cycle Times are Reduced
In Lean manufacturing inventory is a form of waste as it is not yet providing any value.  By maximizing the single piece flow of getting a work item from idea to a state where it is done and it's value can be quantified the system health improves. In addition to the simpler design (less code, less tests, less opportunity for defects) that contribute to a reduced cycle time, we also see a reduction in what Woody Zuill calls the Question Queue Time: "The amount of time that we must wait before we get an answer to a question that is blocking us". Chances are someone in the mob knows the answer and progress can march on.  

In traditional software development when a blocker arises there is usually a context switch to another work item until the blocker goes away (response in email, next standup meeting, etc).  The effect of this though is just an increase in inventory.  Woody says it beautifully in his Mob Programming book:

> "In other words, we've HIDDEN the queuing problem by masking it with an inventory problem".  --Woody

## Team is happy
Happy teams are productive teams.  The energy of all the team solving a problem together, learning together, and deploying together has been really positive.  We recently had some travel that broke up the mob for a short time and we all came back together missing it and feeling its absence.  I do believe we all are more creative, engaged and committed to maximizing value for the business when the team is gelling and happiness abounds.  Mob programming I find fuels this team happiness.

## Continuous Improvement Is Needed
We still have a ways to improve in how we can maximize the benefit of mob programming for the business.  Some of the challenges I've noticed are:
1. **Email.**  The team still gets bombarded with emails (one of the least effective forms of communication in a corporate setting).  This distracts myself and others from being fully engaged in the mob when not driving.  I'm looking for a way to obtain a shared email address for all members of the mob where inquiries can be sent to and responded from a single team email address.  This way we can schedule a mob slot 1/day for responding to inquires.  
2. **Driver doing double duty.**  It is easy for the driver to just start coding.  I'm looking for a way to better adhere to the rule 'For an idea to go from your head into the computer, it must go through someone else's hands'.  Perhaps if the driver has a good idea, the driver skips or ends their turn in the driver seat in order to get back navigating.
3. **Demonstrating the value of the mob to managers** I'm grateful for the opportunity to work in an environment where I'm given the autonomy and freedom to experiment and push the boundaries of agile software development.  I recognize that not all managers may feel comfortable with this way of working.  How to demonstrate the value with data beyond anecdotal evidence?
4. **Product owner not co-located with team** The 'Question Queue Time' can start ticking when the product owner can't be reached.  Perhaps, setting up a daily office hour with the PO where we know he will be available if needed will enable the team to demonstrate work done, get feedback, and talk about the upcoming work as needed.
