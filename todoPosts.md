Illustrating the Blockchain superior level of service

# Improving transactions efficiency

## Pledging an NFT

Pledging an asset when it cannot be handed over to the creditor is rather costly. It has to involve a third party like for example a nortar.
Using the unique source of truth attribute of blockchain technology helps tremendously to solve efficiently this use case
For an NFT for example, it is trivial to block any transfer performed by the owner of a token if the token has been pledged. 
And only the creditor can remove the pledge

## Consign of an artwork

When a piece of art is exposed in a gallery, there is an agreement between the artist and the gallery which gives to the gallery the exclusivity of the sale for
a period of time. This is trivial to implement in a smart contract: the artist is not allowed to perform a transfer until the end of the exclusivity period.

## Making a document actionable

Processes have been improved thanks to digitazation. In particular, digital signatures improve significantly the processes avoiding some manual steps and
cumbersome verifications. Nevertheless, the digitally signed document is still outside the process, it is not by it self actionable. Blockchain to the countrary, 
does not store the signature in the document but can store the signature of a document that is uniquely referenced (off-chain). This makes a significant difference, 
as the validation of the document is a blockchain transaction which can be used to trigger atomically some further actions. 

## Atomic swap between assets

One big expectation from the blockchain technology applied to the securities industry is to reduce the reconciliation effort which is currently huge. 
The need of reconciling comes from the fact that the two legs (security and cash) of the transactions are independent and send through messages. Therefore it is important to verify the correct execution of those two legs and their synchronizaton.
Having both the cash and the security represented on the same transactional network completly irradicates the need for reconciliation: the whole transaction is performed as an indivisible swap between the security and a stable coin representing the cash

# Introducing fairer financial rules

## Voting rights based on the time a stock has been hold

Some raiders spotting opportunities buy a lot of stocks before a GA to influence the decisions to their will. There is no easy way to prevent this behavior in the
traditional finance. Using a smart contract, it is trivial to correlate the voting power to the time the stock has been hold by the owner. With this comapnies
willing to favour long term investors have the proper tools implementing their desired policy in the smart contract.

## Stacking vs Dividends

curve is a good example of this type of arbitrage: the revenues genrerated by the curve transactions are distributed for 50% at the stakers and 50% to the holders 
of the coins. If not all the holders stake their coins, the ones staking will get more than the ones not staking their coins.
This creates an incitive for staking over dividends

# Digital assets: still a long way to go

## Isin equivalent?

It took sometime for the securities industry to come with a unified identifier for the securities around the world. What is the equivalent for tokens?
How to manage multiple chains? Yes, there are some initiatives like ITAN but there is not yet a central reference which is needed up font as the blockchain 
market is by nature global

## Which stable coin?

Having a stable coin to settle the trades on-chain is a must. It reveals the blockchain full potential. But which stable coin? We have seen that there are 
different stable coins around and they are not fungible. This is an obstacle for the mass adoption, not talking about the associated credit risk

## Corporate actions

The success of the ERC20 comes from a minimal interface which has been standardised enabling transfers accross the different owners. We also need a standard 
interface to perform corporate actions on those securities. Another concern is the volumes: currently the corporate action computation is performed at two 
different levels: the CSD level which computes thos corporate action for each custodian and then this is distributed at custodian level, each custodian 
performing the same computation for their customers. Waht about haveing this done for millions of shareholders on-chain?
