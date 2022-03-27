---
layout: post
title: Seamless integration from token to accounting?
date: '2019-04-28T20:14:49.938+02:00'
author: Philippe Meyer
categories: blockchain
tags: #blockchain, #dvp, #ethereum, #smartcontract 
modified_time: '2019-04-28T20:14:49.938+02:00'
---
![token to accounting](https://PhilippeMeyer.github.io/docs/assets/images/tokenToAccounting.png)
<br />
<br />  
The so-called **smart contracts** have been around for quite a while with the first global public implementation made available with Ethereum 2015. This technology is a real breakthrough and proved to be very disruptive over several use cases.

# Smart contracts #

By the way do you know what a smart contract is? Well to start with, it is **neither smart nor a binding legal contract!** It is rather a piece of code running on a blockchain which implements agreed business rules between two or multiple parties.
How can this distributed piece of code be useful for a business? One example which has been very popular over the last year is **asset tokenisation:** the sudden emergence of the ICO (which are represented by tokens) phenomenon has enabled start-ups to get funding directly from investors disrupting the venture capital market. Out of this fast development, a categorization of three main tokens depending on their use has emerged:
* **Payment token:** tokens used as a mean of payment. Cryptocurrencies like bitcoin are typical payment tokens.
* **Security token:** tokens that are like traditional securities, ICO have been the first popular example of this kind of tokens.
* **Utility token:** those tokens are meant to be used to buy a service provided by the issuer. This is like selling forward goods or services that are going to be provided in the future.

# Utility token #

We’ll concentrate here on the utility token and its potential deep impact on how corporate systems are designed.
  
  
In the first place, one could consider a utility token as a **simple mean of exchange.**
  
The customer buys in advance a service he will later use. Conceptually nothing new there: these mechanisms have been used in structured financing.
For example, in large projects like power plans, the banks financing the plans are buying the future power production as part of the structured financing.
Same concept with crowdfunding with platforms like kickstarter where the buyers are paying now for a product or a service they will get (hopefully) some time later. 
The token which has been bought can then **be used when** the good or the service is **made available** by the provider.
  
The breakthrough is not in the concept itself but more in the impact of having these tokens in a digitalised form: those **forward agreements are not any more sitting on piece of paper** but on a public platform like Ethereum stored in normalised way. 
The first consequence of the radical difference is that those tokens can be exchanged creating a potential secondary market. Compared to the current world, this would mean that not only commodities but also **all kind of goods or services could made available on a secondary market.** 

# Invoicing tokens  #
  
But an even more interesting impact of storing those agreements in a digital form is that they can be made directly actionable (at least whilst we stay in a pure digital world). 
In essence, the details of the services to be provided could be stored in a smart contract and upon the reception of a token the agreed services could be provided without any form of transformation. **No invoicing anymore, no payment recovery…**
Of course, this is not yet possible as most corporations as well as the authorities are expecting regular invoices to be accounted properly. We are not yet ready for a **seamless digital supply chain down to accounting**, but this is coming.
  
A side point to mention in that respect is that to the contrary of money, **transactions are not fungible**. This means that each type token can embed its own business rules which would be then made immutable.
This is can be a great advantage when business rules change overtime but should not been changed retroactively. 

The operational costs of this technology are considerably lower compared to the current solutions. As an example, a **manual invoice costs in average 20 EUR to be processed**, whereas such an automated system costs much less to operate (depending on the complexity of the contract though). 
This means that businesses could invoice in a more granular way, limiting the credit risk they take servicing their customers without being paid.
  
This is also true for pre-paid services: the transaction costs being low and the chain fully automated, the pre-paid tokens may not need to be worth a lot of money.

# A concrete example #

A data provider company named “MoveData” which is distributing different types of data to its customers decides to automate their whole value chain. 
They then create a utility token ‘MDTA’ which is going to be used by the customers to pay for the data they get. The purpose of that token is that it can be **denominated in a fiat currency avoiding the price volatility normally affecting the crypto currencies**. 
They setup a straightforward pricing model: 1 MDTA = 1 EUR = 1 Data Point.
“MoveData” has also created a smart contract for each customer which represents the data each customer has subscribed to. 
The purpose of storing this information in a blockchain instead of doing this off chain is that this information is made fully transparent and auditable to the customer. The customer then credits this smart contract with the MDTA tokens he has purchased.
  
At that point the system is basically ready to operate based on the information stored in the blockchain: a scheduler would look on a regular basis at all the contracts to be served, would generate, most likely off-chain, the data files to be pushed to the customers. 
A proof of this file generation would be stored in the payment transaction moving the MDTA tokens from the customers to “MoveData”.
  
In this simplistic example, we foresee how core a blockchain implementation could be for a company, enabling **frictionless interactions with its customers. This basic example could easily be extended to the providers of “MoveData” which could be managed as well thanks to Blockchain based information.
A side note, considering the cost of storing data on a Blockchain we have not considered an on-chain solution for distributing the data which could also be feasible if the volume and the nature of data are appropriate.
  
**As this example like many others show, using the utility token technology, the whole value chain gets seamless and automated from the service description to the payment. A new SAP Blockchain based?**
<br />
<br />  
>[Also published on Medium](https://medium.com/@philippe.famille.meyer/seamless-integration-from-tokens-to-accounting-eea4569ed6af)
>
