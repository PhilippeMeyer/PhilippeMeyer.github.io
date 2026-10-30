---
layout: post
title: "Incident Management: Don't Just Restore Service, Understand It"
date: 2026-10-30 09:30:00 +0100
categories: field-notes
tags: [incident-management, root-cause-analysis, itil, blameless-culture, safety-culture, it-operations]
image: /docs/assets/images/From Blame to System Understanding.png
description: "An update of my 2012 article on incident management: why understanding root causes matters more than restoring service, and what aviation teaches IT operations."
---
![Technicians do not make error on purpose](/docs/assets/images/From Blame to System Understanding.png)

*Updated October 2026. Originally published on [meyer.today]({{ site.baseurl }}/2012/12/02/incident-management.html) on December 2, 2012.*

Enterprise IT systems are complex, and reliability is a daily fight. Frameworks like ITIL gave us proven processes to wage it. But a process is only as good as the thinking behind it.

## Best practices are not recipes

Incident management is often implemented like a recipe. Steps are followed and tickets are closed, yet nobody can say why the process was designed that way. Best practices are a valuable shortcut, but they must not stop us from thinking about the essence of what we do: restore service quickly, and learn so the same failure doesn't return.

## The trap of the invisible department

For IT Operations, the best possible result is to be invisible. When everything works, users never see the effort behind it. Every outage, by contrast, is pure downside. So incident reports and KPIs become a shield, a way to prove the system runs better than anyone imagines, and ITIL becomes the label on that defensive strategy.

## From defense to understanding

There is another way: use the same processes and tools proactively, to understand what is really happening. The KPI matters less than the comment that comes with it. The incident matters less than making sure it doesn't happen again because its root cause was ignored.

## Root cause analysis pays off

Real improvement comes from deep analysis. It is hard, sometimes impossible, and it slows other work down, but it pays off. The natural reflex of Operations is to restart the system as fast as possible and move on. Management should counter that reflex: no significant incident is closed without a review, an action plan and an owner who executes it.

**Facing an error once can be acceptable. Facing the same error again is not.** In complex systems, a first failure is information: it shows us something we didn't know. A repeat is a verdict on our learning process, because the lesson was available and we didn't act on it. This is the real measure of incident management: not how few incidents we have, but how few of them are repeats.

## Firing the person who made the mistake fixes nothing

When an incident hits, the temptation is to find the person who made the mistake and make an example of them. It feels decisive, but it is counterproductive. It doesn't remove the conditions that allowed the error, so the next person in the same seat will probably make the same one.

Worse, it creates a culture of hiding. If admitting a mistake means losing your job, everyone learns to protect themselves: details are left out, logs are "cleaned up", near misses are never reported. That lack of transparency makes the search for root causes impossible, and without root causes there is no improvement process. **Blame buys a scapegoat and costs you the truth.**

The goal is the opposite: a climate where the person closest to the error is the first to speak up, because they know the question will be "how did the system allow this?" and not "who is to blame?". That does not mean no accountability. It means accountability for acting on what was learned, rather than for having been the one in the wrong place at the wrong time.

## What aviation teaches us

A recent [LinkedIn post](https://www.linkedin.com/feed/update/urn:li:activity:7521481758517678082/) by ["Até" Chuet](https://www.linkedin.com/in/dbrief/) revisits the 1990 BAC 1-11 windscreen accident, in which a cockpit window blew out at altitude and the captain survived. What struck me is how the investigation was framed. The maintenance manager had made a mistake, but investigators also found procedures that required no independent check, and local supervision that never looked at how the work was really done.

The post links this to Boeing's MEDA investigation method, which rests on one idea: *"les techniciens ne font pas d'erreurs exprès"* (technicians don't make errors on purpose). Its conclusion is that the single culprit is, in the author's words, *"un artefact de la façon dont on enquête"* (an artefact of how we investigate).

This is the same trap I described in 2012. Restarting fast and closing the ticket stops the analysis at the first convenient answer. When you look for a name, you find a name, and you stop there.

The post suggests three rules that transfer directly to IT, and I would add a fourth:

1. **Keep personal names out of the report.** Describe a function and a sequence of events, not a person. This also protects the transparency that root cause analysis depends on.
2. **Don't close an investigation with fewer than three contributing factors.** If you have only one, you haven't finished.
3. **Require a traced second-person check on irreversible tasks.** It should be a cross-check, not a hierarchical one. In IT terms, this is the four-eyes principle on production changes.
4. **Treat a repeat incident as a process failure.** The first occurrence is the price of learning. If the same error comes back, the question is no longer "what went wrong?" but "why didn't the fix hold?", and the answer usually sits in follow-up, ownership or knowledge sharing.

## Reports are communication

Commented incident reports and monthly KPIs that mix technical and business impact show users that IT takes responsibility. This kind of transparency only exists if people feel safe telling the truth. A useful addition is to track repeat incidents explicitly, as a KPI of its own. IT stops being the invisible department that is easy to outsource and becomes a visible contributor to the business.

---

*This article builds on my original post, [Incident management]({{ site.baseurl }}/2012/12/02/incident-management.html) (meyer.today, December 2012), and on the aviation case shared by ["Até" Chuet](https://www.linkedin.com/in/dbrief/) on LinkedIn.*
