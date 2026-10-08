---
layout: post
title: "Your Payslip Is Not Their Business"
date: 2026-07-14
categories: [blockchain, privacy, identity]
tags: [zero-knowledge-proofs, privacy, digital-identity, verifiable-credentials, proptech]
author: Philippe Meyer
description: "To rent a flat, you hand over your passport, payslips, bank statements and employer details. The landlord's actual question is simpler: can this person pay the rent? Zero-knowledge proofs let you answer just that."
image: /docs/assets/images/payslip-not-their-business.png
excerpt: >
  To rent a flat, you hand over your passport, payslips, bank statements and employer details. The landlord's actual question is simpler: can this person pay the rent? Zero-knowledge proofs let you answer just that.
---

![Your Payslip Is Not Their Business](/docs/assets/images/payslip-not-their-business.png)

Here is what renting a flat currently requires in most cities: a copy of your passport, two or three months of payslips, a bank statement, your employer's contact details, references from previous landlords, and in many cases the same documentation again for a guarantor. That is if you are a straightforward salaried employee. If you are self-employed, freelance, or earn in a non-standard way, add several more steps and a higher chance of rejection.

The landlord's actual question is simple: can this person reliably pay the rent? Everything else, the payslip, the bank statement, the employer's letter, is just documentary evidence assembled to answer that one question. But the process hands over far more than the answer. It hands over the raw materials: exact salary, employer name, account balances, transaction history, address history, and in the case of guarantors, someone else's entire financial picture, because the applicant is not considered trustworthy enough on their own.

This is not a landlord problem specifically. It is a structural problem with how verification works: because we have no way to prove a fact without showing the document it came from, every verification request becomes a data dump.

Zero-knowledge proofs change that equation.

## Proving the fact, not the file

Zero-knowledge proof is a cryptographic method that lets one party prove a statement is true to another party without revealing anything beyond the truth of the statement itself. A zero-knowledge proof satisfies three properties: completeness (an honest prover always convinces the verifier), soundness (a dishonest prover cannot fake it), and zero-knowledge (the verifier learns nothing beyond the fact being proven).

Applied to rental verification, this looks like the following. A trusted third party, a bank, a payroll provider, a government income database, attests to a fact about you: your monthly income exceeds a certain threshold, you have held continuous employment for more than twelve months, you have no county court judgments or eviction history. That attestation is cryptographically signed and stored, either on-chain or in a portable credential. You then generate a proof from that credential and share it with the landlord. The landlord's system checks the proof and receives a binary confirmation: yes, the income condition is met. No figure. No employer name. No bank account number. Just the answer to the question that was actually being asked.

The same mechanic applies to employment verification for jobs, confirming a degree was awarded by a given institution without revealing grades, or confirming professional accreditation without exposing license numbers that could be misused. In each case, the verifier gets the answer they need, and the applicant retains control over everything else.

## Why this matters more than it sounds

The standard response to privacy concerns about document sharing is "well, landlords and employers have always done this." That is true, but it ignores what has changed. In 2026, a copy of your payslip sent by email to a letting agency sits in an inbox, potentially shared with third-party referencing services, stored on servers with unknown retention policies, and accessible to staff you will never meet. The data exposure of a traditional rental application is not the same as handing a paper document to a person across a desk, as it once was. The surface area is far larger, and the consequences of a breach are more significant.

There is also a fairness dimension: the evolution of income verification from document collection to direct, permissioned data sharing represents more than a technological upgrade, it is a fundamental shift from a system that assumes potential deception to one built on secure, permissioned data sharing, with the premise that the initial screening interaction sets the tone for the entire tenancy relationship. Privacy-preserving verification does not just protect applicants. It removes the adversarial dynamic from an interaction that should not be adversarial in the first place.

## Where this is already moving

The regulatory direction is increasingly supportive. The EU Digital Identity framework, due for full release by the end of 2026, is being built around selective disclosure, the ability to share only the specific attributes a verifier needs rather than a full identity document. Several EU member states are already developing zero-knowledge-based age verification for compliance purposes under this framework, with the same cryptographic principle: prove a threshold is met without exposing the underlying data. The EU Digital Identity Wallet, once rolled out, will make portable, privacy-preserving credentials available to hundreds of millions of people for exactly these kinds of verification use cases, including tenancy, employment, and professional licensing.

On the blockchain side, decentralized identity standards like Verifiable Credentials and the W3C DID specification are designed precisely for this: issuing signed, portable attestations that the holder can selectively disclose to any verifier, without the issuer being in the loop for every check. Smart contracts can act as the verification layer, confirming that a credential was issued by a trusted authority and has not been revoked, without ever seeing the underlying data.

## The practical implication

The question worth asking is not "should tenants have more privacy." It is narrower and more actionable: how much of what we currently collect do we actually need, and what happens to it after we have checked it?

For letting agencies, employers, and anyone else currently sitting on folders of scanned documents from applicants they never selected, the answer to that second question is often unclear. Privacy-preserving verification does not just solve an applicant's problem. It solves the data liability problem on the other side of the table too.

*This is the fourth in a [twelve-part series on smart contract use cases](/blockchain/smart-contracts/2026/06/16/smart-contracts-beyond-defi-nfts.html) beyond the well-known examples of DeFi and NFTs. Previous: [Insurance Without the Argument](/blockchain/insurtech/smart-contracts/2026/07/07/insurance-without-argument.html). Next: [The Crowd Knows First](/blockchain/prediction-markets/decision-making/2026/07/21/crowd-knows-first.html).*
