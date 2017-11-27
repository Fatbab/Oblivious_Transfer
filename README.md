# Oblivious Transfer -- TBC

## Intro:
Oblivious Transfer (OT) protocols study the exchange of information between an inquirer and database where the inquirer will correctly get the result of their query (and nothing else) while database will not be able to distinguish which part of thier content was in fact queried. 

For an intuitive application of these protocols, consider a fictional example: you're going to attend an auction. But before arriving at the venue, you're trying to get an idea on the market value of the items you're going to bet on. You decide to stop by an antique shop to inquire about the price. But then suddenly you notice one of the auctioneers in the shop chatting with the shop owner. That makes you wonder if your inquiry about specific items will be passed on to the auctioneer and results in some price fixing later. On the other hand unless you specifically ask, altough the information is available, you won't learn the price of other items.     
An OT in this case would have met your needs suitably.     

## Protocol
As a first step to see how mathematics can help fulfill these requirements, here I share two basic methods: with and without trusted authority. Trusted Authority (TA) is nearly as famous as Alice and Bob in Cryptography. It is an entity that all parties involved in a protocol fully trust. It's important to understand that in many protocols, TA is able to access all private inofrmation and recover all encrypted messages. Establishing full trust in TA from all parties is often an essential requirement. One example of TA in real-life applications is the financial institution who issues your credit card. They preload the chip with keys that later on will be used for generating Message Authentication Codes, etc.    

TA's are usually only involved in the initialization phase and after that they go offline.    

### 1-out-2 OT w/ TA
Let Alice be the database and Bob the inquirer. In the most simple case of OT, Alice holds two pieces of informatio, say _m0_ and _m1_ both from _{0,1}^k_. Bob is interested in knowing only one of _m0_ or _m1_, hence 1-out-2 OT. 

__Initialization Phase__:    
a. TA generates random values _r0_ and _r1_ from _{0, 1}^k_ and sends them to Alice.    
b. TA randomly selects _i_ from {0, 1} and sends (_i_, _ri_) to Bob.   

__Interaction Phase__:     
i. Bob intends to inquire about _mj_ where _j in {0,1}_ and so sends _i + j_  to Alice.    
ii. Alice publishes two values: <_m0 + r(i+j)_> and <_m1 + r1-(i+j)_>.         

#### Why this works:


### 1-out-2 OT w/o TA

#### What's missing: 
We have not considered adversarial behaviour in this protocols, either an external or internal.

## References
[Cryto StackOverflow](https://crypto.stackexchange.com/questions/8839/simple-protocol-for-1-out-of-2-oblivious-transfer)
