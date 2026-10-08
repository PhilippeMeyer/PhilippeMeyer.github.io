---
layout: post
title: "Resilient by Design: Why IT Systems Must Be Built to Fail"
date: 2026-05-26
categories: [software-architecture, systems-design]
tags: [resilience, reliability, system-design, batch-processing, engineering-leadership]
author: Philippe Meyer
description: "Reliability asks: does the system work? Resilience asks: how does it behave when something goes wrong? The systems that last are not the ones built to be perfect, they're the ones built to fail gracefully."
image: /docs/assets/images/resilientByDesign.png
excerpt: >
  Reliability asks: does the system work? Resilience asks: how does it behave when something goes wrong? The systems that last are not the ones built to be perfect, they're the ones built to fail gracefully.
---

![Resilient by Design: Why IT Systems Must Be Built to Fail](/docs/assets/images/resilientByDesign.png)

Modern IT systems are rarely monolithic. They are intricate ecosystems, webs of APIs, microservices, scheduled jobs, data pipelines, and third-party integrations, all collaborating in long, interdependent chains. In this context, reliability is rightly treated as a primary engineering goal. But there is a subtler, often overlooked concept that underlies true reliability: resilience.

Reliability asks: does the system work? Resilience asks: how does it behave when something goes wrong?

The distinction matters enormously. A system can be composed of individually reliable components and still collapse spectacularly at the seams, because nobody designed for the inevitable moment when one link in the chain fails.

## The Optimism Trap

There is a pervasive, implicit assumption baked into many IT designs: that everything will work. Data will arrive on time. Services will respond. Currency tables will be populated. Network latency will be negligible. This optimism is understandable, it simplifies design, speeds up delivery, and feels rational when each individual component performs well in isolation.

But here is the uncomfortable truth: what holds for each part rarely holds for the whole.

A chain of ten systems, each with 99.9% individual availability, delivers a theoretical combined uptime of only ~99%. In practice, the compounded fragility is often far worse, because failures rarely affect just one component, they cascade. When upstream systems fail ungracefully, they don't just fail themselves; they corrupt, stall, and destabilize everything downstream.

The solution is not to demand perfection from every component. The solution is to design systems that expect imperfection and degrade gracefully when it arrives.

## What Graceful Degradation Looks Like in Practice

### The Missing Data Problem

Consider a deceptively simple scenario: a required piece of data, a file, a record, a value, is missing. What should the system do?

Option A (the common choice): Block the entire process. Raise an alert. Wait for a human to intervene and re-run everything from scratch once the issue is resolved.

Option B (the resilient choice): Skip the missing item, process everything else, log the gap clearly, and perform a targeted partial re-run once the missing data becomes available.

Option B seems obvious in hindsight, yet Option A is implemented far more often. The reason is that designing for Option B requires upfront effort: you must think about what "partial success" means, how to track and resume incomplete work, and how to communicate a degraded state to downstream consumers. It is harder to design. It is also far more valuable in production.

### An Illustrative Anecdote

Consider a real-world example that captures this perfectly. An accounting system was processing millions of transactions for end-of-month close when it ground to a halt, blocked because a single currency exchange rate was undefined in its reference table.

The situation could have been catastrophic. But because the process was flagged as business-critical, a manual monitoring chain was in place. An on-call manager was paged in the middle of the night. With no way to look up the correct value and no time to wait, they made a judgment call: set the rate to 1€ and restart the process.

Was it perfect? No. But by morning, accountants could identify and manually correct the handful of impacted transactions. More than 99.99% of the month-end processing completed successfully and on schedule.

The lesson is not that guessing currency values is acceptable practice. The lesson is that a system with a sensible fallback, even an imperfect one, is orders of magnitude more valuable than a system that refuses to continue at all.

## The "Cron Syndrome": When Scheduling Becomes a Liability

One of the most widespread sources of systemic fragility is what might be called the "cron syndrome", a pattern that emerges when developers with limited experience in enterprise batch management implement scheduling using primitive tooling.

Enterprise-grade schedulers offer powerful capabilities: event-driven triggers, dependency management, rich return code handling, conditional branching, and automatic retry logic. Unix cron offers none of these. Yet cron, or cron-equivalent simplistic scheduling, remains the default choice for many teams.

The consequences are predictable:

Time-based triggers instead of condition-based ones. A job fires at 02:00, regardless of whether its upstream data is ready. If a feed is delayed by 90 minutes, the downstream job either picks up stale data, crashes on missing input, or silently produces incorrect results, none of which are acceptable.

Return codes treated as decorative. A job exits with code 0 whether it processed 10,000 records successfully or zero records because of a silent failure. Downstream jobs proceed as if nothing is wrong. The defect surfaces hours or days later, in a context far removed from its origin.

No restart points. A six-hour batch job fails at hour five. The entire run must be discarded and restarted from scratch. Not only is this wasteful, it may mean missing business deadlines entirely.

The fix is not always to replace the scheduler. It is to change the philosophy: trigger on conditions, not just clocks; implement and honour meaningful return codes; design batch jobs with checkpoints and restart capabilities so that reruns pick up from the point of failure, not from the beginning.

## Black-and-White Batch Thinking

Related to the cron syndrome is a binary mindset around batch outcomes: either the job completes fully, or it fails entirely and produces nothing. This binary view maps onto simple, small jobs that run in seconds. It becomes dangerous for large, long-running processes.

Consider a nightly batch that aggregates data from 200 source systems and takes four hours to complete. If one source feed is malformed, the sensible response is to flag that feed, exclude it from the aggregation, complete the remaining 199 sources, and produce a result annotated with a quality indicator. The unsensible, but common, response is to abort the entire run.

Resilient batch design requires three things: granular error handling, where individual failures are caught, logged, and isolated rather than bubbling up to abort the whole job; restart points (checkpointing), where the job records its progress so re-runs skip already-completed work; and partial output with quality indicators, where downstream consumers receive data with metadata describing its completeness and reliability.

## Data Quality as a First-Class Concern

Consolidation systems, reporting engines, financial aggregators, data warehouses, face a specific and under-appreciated challenge. By design, they consume inputs from tens, hundreds, or even thousands of upstream sources. Statistically, perfect input is not a realistic expectation on any given day.

A single missing feed should not invalidate an entire consolidated report. Yet many systems treat any missing input as a hard blocker.

A more resilient approach involves estimation and substitution, where a missing data source is replaced with an estimate (the previous day's value, a rolling average, or a known baseline) rather than failing; quality flags, attaching metadata to every output indicating which inputs were actual versus estimated, and what confidence level the figure carries; and downstream transparency, making quality indicators visible to consumers so they can make informed decisions about how to use the data.

This approach mirrors how robust financial and statistical systems have operated for decades. A weather forecast does not refuse to run because one sensor is offline. It uses available data, applies estimation for gaps, and presents results with appropriate confidence intervals. IT systems should do the same.

## Designing for Failure: A Practical Checklist

For teams ready to move beyond optimistic design, the shift is consistent across every concern area. Missing input data moves from "block and alert" to "skip, estimate, or substitute; flag the gap." Batch scheduling moves from time-triggered to condition- and dependency-triggered. Return codes move from binary success/fail to granular status with meaningful codes. Long-running jobs move from all-or-nothing to checkpointed with partial-run capability. Data quality moves from assumed perfect to tracked, flagged, and communicated. Downstream failure moves from propagated to isolated and handled gracefully.

## Closing Argument: Build Systems That Are Ready to Fail

Resilience is not pessimism. It is engineering maturity.

The systems that survive and serve their organisations best are not the ones that assume nothing will go wrong, they are the ones built with the quiet acknowledgement that something always will. Graceful degradation, partial output, meaningful fallbacks, and transparent quality signals are not edge-case features. They are the foundation of systems that can be trusted.

The goal is not to build systems that never fail. The goal is to build systems where failure is bounded, visible, and recoverable, where a missing currency rate at 2 AM becomes a minor footnote, not a business crisis.

Design for imperfection. Build for resilience. Start from day one.
