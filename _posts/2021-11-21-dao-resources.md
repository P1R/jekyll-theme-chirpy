---
title: Maxcoin DAO resources
author: PIRO
date: 2021-11-21 17:10:00 +0800
categories: [Research, Resources]
tags: [DAO, Aragon, Governance, Resources, Research]
render_with_liquid: false
---

## About DAOs

DAOs are an effective and safe way to work with like-minded folks around the globe.

Think of them like an internet-native business that's collectively owned and managed by its members. They have built-in treasuries that no one has the authority to access without the approval of the group. Decisions are governed by proposals and voting to ensure everyone in the organisation has a voice.

There's no CEO who can authorise spending based on their own whims and no chance of a dodgy CFO manipulating the books. Everything is out in the open and the rules around spending are baked into the DAO via its code.[1]

Starting an organisation with someone that involves funding and money requires a lot of trust in the people you're working with. But it’s hard to trust someone you’ve only ever interacted with on the internet. With DAOs you don’t need to trust anyone else in the group, just the DAO’s code, which is 100% transparent and verifiable by anyone.

This opens up so many new opportunities for global collaboration and coordination.[2]

### Autonomy 

DAOs are autonomous in the sense that they are immune to third parties’ actions. Thanks to the public blockchain networks they run on, DAOs control their own capital and allocate it according to self-enforcing, tamper-resistant rules. This is why TheDAO in 2016 was presented as “unstoppable”, meaning that nobody could change its behavior nor pull the plug of the computer it was running on.

That’s what autonomy means here. The funds of a DAO are controlled by its code, and only by its code.[1]

*What have we learned?*
Using blockchain-based, autonomous code artifacts was quickly found to be problematic, and not only for DAOs. As individuals as well as organizations, we expect to have a recourse when something goes awry. If we make a mistake in bank transfer instructions, it is assumed that the bank will fix it and that our money will be returned. When two companies disagree over the execution of a contract, they might plead their cases before a court.
Immutability and censorship resistance are valued by those who want to protect their assets and their independence from corrupt judges or failed states. The autonomy of the code is a way to set personal and collective arrangements out of reach of any third party, regardless of how powerful or wealthy they are. But it’s worth emphasizing here that the autonomy that we really crave is for the people (as individuals or as collectives), and that the autonomy of the code is a means rather than an end. 
Balancing code vs. community

One way to approach such a combination is to make room for subjectivity in automated processes. Kleros and Aragon pioneered decentralized arbitration services that can be used today to make DAOs more flexible. Aragon Agreements, for instance, enable organizations to define human-readable agreements that can be enforced by a decentralized court of jurors when a dispute is raised.
Another way to protect people from blind application of automated rules is to provide them with a way to escape a system before being harmed. This is the idea behind the ragequit mechanism offered by Moloch DAO: any investor in the DAO’s fund can withdraw their investment when they disagree with a decision voted by a majority of members. 


> Note: Do a DFO vs Courts vs ragequit mechanism 

The focus has shifted from the absolute autonomy of the code praised by cypherpunks to the relative autonomy of a combination of dry code and human judgment.

One way to approach such a combination is to make room for subjectivity in automated processes. Kleros and Aragon pioneered decentralized arbitration services that can be used today to make DAOs more flexible. Aragon Agreements, for instance, enable organizations to define human-readable agreements that can be enforced by a decentralized court of jurors when a dispute is raised.

Lastly, we’re seeing mounting concern regarding legal risks for DAO members, which can be addressed by wrapping a DAO in a legal form such as an LLC. Several jurisdictions now offer such legal vehicles so that DAOs as well as their members are protected from legal uncertainties that may lead to unlimited personal liability. Examples include dOrg, a cooperative of developers that incorporated as a Vermont registered Blockchain-Based Limited Liability Company, and The LAO, a venture fund organized as a Delaware LLC.

In each of these cases, the ideal of a pure cyberspace solely determined by code is balanced with the legitimate concern of protecting the people for whom such space has been built in the first place. Decentralized courts make it possible to protect communities from rogue individuals. Ragequitting prevents majorities from exerting excessive power upon minorities. Legal wrappers offer protection against threats to DAO members via regulations and applicable laws.

### Decentralization

Decentralization can be understood as the process of reducing or avoiding the concentration of power within organizations. In decentralized structures, resources and decision-making power cannot be seized by a small number of parties.
Reality check: Put aside the decentralization razzle-dazzle, and have a look at real projects in the crypto space. All of them are under the control of their founders, and most of the significant ones are organized according to the traditional corporate governance system, with shareholders and accountable executives. Cooperative and meritocratic communities like dOrg, Metagame or LeapDAO are still an exception and have yet to prove themselves.
More options to effectively decentralize
Decentralization is hard, but there have never been so many ideas to make it real! Here are some of the most interesting approaches we’ve seen recently.

Token-based voting has been the main instrument for collective decision-making in DAOs since it’s the easiest way to prevent Sybil attacks, i.e., voting with multiple identities. Sybil attacks have always been a headache in the crypto space, which is essentially pseudonymous. People do not need to have their identity verified in order to participate in a public crypto-network such as Bitcoin or Ethereum, they just need a pair of cryptographic keys, and anyone can create an arbitrary number of keys at no cost. Token-based voting is an efficient way to be Sybil resistant since tokens are crypto-assets that cannot be created at will. However, token-based voting is also criticized because of its adverse effects on decentralization. As mentioned previously, most crypto-networks are imperfectly decentralized, precisely because a small number of addresses control a majority of the tokens.

Conviction voting enables the preferences of a community to be continuously captured over time instead of organizing votes within a narrow time period, and to let stakeholders choose where they put their influence. It makes Sybill attacks and vote-buying harder, and it can also help to fight voter apathy. 1Hive has delivered an implementation of conviction voting, available as an Aragon app.[1]

Conviction Voting offers a novel decision making process that funds proposals based on the aggregated preference of community members, expressed continuously. In other words, voters are always asserting their preference for which proposals they would like to see approved, rather than casting votes in a single time-boxed session. A member can change their preference at any time, but the longer they keep their preference for the same proposal, the “stronger” their conviction gets. This added conviction gives long standing community members with consistent preferences more influence than short term participants merely trying to influence a vote. Conviction Voting sidesteps sybil attacks, provides collusion resistance, and mitigates many of the attack vectors of time-boxed voting mechanisms.[2]

Quadratic voting is also a way to limit the plutocratic effects of token-based voting, while still giving people with more skin in the game a way to signal their preferences. It has been successfully experimented with by Gitcoin for funding public goods.[1]

Quadratic voting is a collective decision-making procedure which involves individuals allocating votes to express the degree of their preferences, rather than just the direction of their preferences.[1] By doing so, quadratic voting seeks to address issues of voting paradox and majority rule. Quadratic voting works by allowing users to "pay" for additional votes on a given matter to express their support for given issues more strongly, resulting in voting outcomes that are aligned with the highest willingness to pay outcome, rather than just the outcome preferred by the majority regardless of the intensity of individual preferences. The payment for votes may be through either artificial or real currencies (e.g. with tokens distributed equally among voting members or with real money).[2] 

Quadratic voting is a variant of cumulative voting in the class of cardinal voting. It differs from cumulative voting by altering "the cost" and "the vote" relation from linear to quadratic.

Quadratic voting is based upon market principles, where each voter is given a budget of vote credits that they have the personal decisions and delegation to spend in order to influence the outcome of a range of decisions. If a participant has a strong support for or against a specific decision, additional votes could be allocated to proportionally demonstrate the voter's support. A vote pricing rule determines the cost of additional votes, with each vote becoming increasingly more expensive. By increasing voter credit costs, this demonstrates an individual's support and interests toward the particular decision.

If money is used, it is eventually cycled back to the voters based upon per capita. Both E Glen Weyl and Steven Lalley conducted research in which they claim to demonstrate that this decision-making policy expedites efficiency as the number of voters increases.The simplified formula on how quadratic voting functions is

cost to the voter = (number of votes)2.[3]

the allocation of decision-making power to the people who contribute to the network. When the voting power of DAO members is based on their actual contributions and cannot be transferred to others, power asymmetries tend to be much less acute. Various reputation systems have been designed to that end, for instance by DAOstack, Colony, or SourceCred.
Finally, it’s worth mentioning that communities can be decentralized not only because of institutional or crypto-economic incentives, but also because they want to be. Decentralization is an ethos. MetaCartel, MetaGame, 1Hive or the Commons Stack all use tokenized instruments for measuring value and weighing voting power, but they also cultivate a participatory culture that is the most authentic and resilient way to embody decentralization.[1]


### Organization

The “O” of DAO points to the seemingly simplest term: “Organization”. It’s also the most deceitful. When one thinks about an organization, the image of a firm comes to mind. But it’s hard to picture a firm that would be decentralized and autonomous. Firms’ structures are hierarchical — even cooperatives appoint executives. And firms transact between each other thanks to contractual relationships that heavily rely on the rule of law, so they can hardly be considered autonomous.

Therefore, we still need to question the nature of DAOs as organizational structures.
The creators of TheDAO claim that it was a decentralized fund, controlled by a crowd of investors, without any corporate structure in the traditional sense: no shareholders, no executives, no management. Corporations have sometimes been defined as a collection of contracts between different parties (shareholders, directors, employees, customers, suppliers, etc).

*DAOs might be seen as organized economies, rather than automated organizations.*


Collectives are closer to traditional organizations: They have a smaller number of active members and a wider range of activities than protocol DAOs. 1Hive, dOrg, or MetaGame are examples of collectives that use DAOs to be more transparent, more open, more flexible and fairer towards their members than usual corporations. DXDao is worth a special mention, as a hybrid DAO that gathers an open collective to govern multiple DeFi protocols.

 Not a thing, but a dynamic process
It is now pretty obvious that there is no such thing as a pure “Decentralized Autonomous Organization”. DAOs are imperfectly decentralized, very moderately autonomous, and hardly comparable to organizations in the traditional sense.
In 2020, it’s time to acknowledge the fact that most DAOs are actually associated with firms or foundations. In most cases, it is not a problem but a necessity. DAOs are less a thing than a gradual, dynamic process. It is possible to “daoify” organizations, firms, markets, and protocols, i.e., to use blockchain technologies to transform these entities into transparent, rent-free networks owned by their members.

#### Author Conclusions

So what can we do with a DAO in 2020? It’s not prime time yet. I don’t think that we’re close to seeing mass adoption. DAOs are still a weird name for an obscure concept, only known by a tiny group of people, even compared to the number of people interested in cryptocurrencies and blockchain technologies in general.

It may seem paradoxical. A lot of people today are interested in self-organization, collectives, and cooperatives. Many appreciate the shortcomings of both free markets and political institutions with respect to the mounting social and environmental challenges of our time. One might think that a technology designed to help communities to govern and decide by themselves, to produce and share value together, would raise more interest from the general public.

My personal belief is that DAOs are poised to succeed once “crypto” itself becomes mainstream. DAOs suffer from the same plague as Dapps in general: user experience is simply unbearable to people unfamiliar with crypto. I appreciate the efforts made by Aragon, Colony, Abridged, and others to make things prettier, faster, and simpler. We’re just not on par yet with Web 2 applications. As long as this is the case, there will only be a handful of people willing to use DAOs.
Bonus points for taking care of externalities as well. The environment and society at large are the invisible contributors that we all benefit from and rely upon. DAOs help to create inclusive economies, through transparency and cooperation incentives.
When the year of the DAOs eventually happens, it will be because they serve the common good, rather than the limited interests of the crypto community.[1]

## Aragon

Aragon is a suite of applications and services that enable new forms of global communities.

Communities can organize around capital assets, currency, or tokens, which will increase in value as more people hold and use that asset to participate in the community.

By providing the tools for people to turn a community, cause, or even a meme into its own economy, we can unlock a long-tail of DAOs that are not limited just to protocols like Ethereum or Bitcoin.

Aragon not only provides basic financial tools like tokenization but can create reproducible and broadly applicable templates for defining the boundaries of a community and flowing value to contributors over the internet without traditional intermediaries.

But this isn't science fiction, it's happening now, and you can be a part of it.[3]

### Aragon Client

Aragon Client, regarded as Aragon v1, is the first generation protocol to create DAOs. It was initially launched in 2019 and became the dominant solution on the market. You can check the organizations powered by Aragon here.

As Aragon is looking to replace Aragon Client (v1) with new and better Aragon Govern (v2) it should not be used for any new DAOs. However, it is still a valid tool to test your MVP.

#### Anatomy

Aragon Client DAOs are made up of tiny independent software programs, known as “smart contracts”. Together they build up an operating system that runs the DAOs. It is called aragonOS and is similar to MacOS or Linux. 

The core of aragonOS is the Kernel, a brain of the DAO. There is also ACL, which ensures that only authorized accounts (People) and contracts (Programs) have permission to perform specific actions in an organization. For example it can enforce that only ANT token holders can vote on a proposal.

To expand functionality, DAO can install apps, developed for aragonOS. They will expand functionality and allow new actions for the members. You can add pre-built apps from Aragon or develop your custom applications. 

Some examples of available applications that can be added to Aragon Client DAOs are Token, Voting or Finance apps. Yet there are many more available.[4]


### Usefull Aragon Apps for Devs:

#### DAO management with a MultiSig (Decentralized)
Assign the desired permissions in the Client DAO to the MultiSig

Aragon Client DAOs have an access control system, where each action is protected by a set of permission records. Only someone who has specific permission can perform the action. You can read more about permissions here.

That is why we need to assign the MultiSig wallet to a range of permissions that correspond to the actions we want it to be able to perform.[5]

#### Agent App

The Agent app enables Aragon organizations to interact directly with any other smart contract on Ethereum. Before Agent, an organization would have to nominate a trusted party to interact with an Ethereum smart contract on its behalf: for example, an organization would send some Dai to one of its employees, who would then be trusted to lend the Dai on Compound, earn interest, and then send the interest plus the principle back to the organization. Now with Agent, an organization can (for example) lend its Dai out on Compound directly, without having to trust any intermediaries.[6]

#### Permissions Setting

The Permissions app is used to view all of the current permissions that have been set in an organization and add or remove permissions as needed. The permissions set by the Permissions app define which entities have what permissions to perform various actions in an organization. For example, any account may have permission to create a vote but only tokenholders in an organization may have permission to cast a vote.[7]

### Optimistic Governance
Optimistic Governance?
Sometimes called 'lazy' consensus, Optimistic Governance assumes that all actions are legitimate unless proven otherwise. In practice, this means that governance becomes a perpetual-motion machine of proposals that are scheduled as on-chain transactions to execute by default unless they are specifically challenged in Aragon Court during a Dispute Time Delay set by the DAO.
How exactly is my DAO protected from malicious actors?
First, every DAO must have a DAO Agreement that defines the purpose and parameters of the community. Any transaction that deviates from this document may be challenged in Aragon Court and have its collateral slashed.

![](/assets/img/posts/optimistic-dao.png)


Second, for more community control, Govern DAOs may restrict executive power to a whitelist of selected addresses so only they may schedule the transfer of funds.

‍Third, DAO transactions cannot be executed immediately. Instead, these are delayed by a period of time set by the DAO. This assumes 'optimistically' that all transactions are legitimate but gives any DAO member the opportunity to challenge the transaction in our decentralized dispute resolution system, Aragon Court. A successful challenge will cancel the transaction.

‍Fourth, a collateral deposit set by the DAO is required to schedule a transfer of DAO funds. This is refunded at the close of the execution window unless someone has successfully challenged the transaction in Aragon Court, in which case it will be forfeited to the Court Guardians.[8]


>NOTE: Is it possible to to do an optimistic govern that verifies from Maxcoin as mainchain the DAO address in a decentralized way?, and so that all transactions que aproved but only if there is no difference of the amount of maxcoin on the maxcoin net vs the wrapped version? 
>
### Aragon Voice
Aragon Voice is a key component of the voting infrastructure we are building for Web 3.0, powering unstoppable decentralized governance with zero voting costs. For the first time ever, anyone with an Ethereum address can design and implement On-Chain Proposals for their ERC20 project, where votes can be cast without gas fees, and are recorded as metadata both to Ethereum and IPFS, or Signaling Proposals that use a centralized backend but are universally verifiable on our custom vote-counting blockchain, Vochain. Only On-Chain Proposal creators need to pay the gas costs of deploying the information to mainnet.
 
Aragon Voice will be released as a standalone tool before later being integrated into all Decentralized Autonomous Organizations (DAOs) on the Aragon v2 OpenStack along with Aragon Govern and Aragon Court. At this early stage, we see Aragon Voice as being used primarily as a signaling tool for ERC20 tokens including, naturally, our own ANT token. In the future we are planning to extend functionality to other standards, such as ERC721 - the Non-Fungible Token standard - as well as trustlessly binding votes to transaction executions on the Ethereum mainnet.

Built on the Vocdoni OpenStack. To power Aragon Voice, we are using the Vocdoni OpenStack: a fully anonymous voting protocol by design, ensuring data availability and censorship-resistant protocol communication. This technology is also the base for layer-2 (L2), a voting-specific blockchain named Vochain, used for accounting ballots transparently. *The protocol can be configured to represent nearly all ballot types, including simple voting, quadratic, weighted, ranked-choice, multiple-choice, plus options such as whether the results are revealed in real-time or locked until the process concludes.* Vocdoni’s voting technology has already been used to secure votes of organizations with hundreds of thousands of members, including most recently, a pilot project of digital voting with a survey during the last Catalonia elections.[9]

![](/assets/img/posts/aragon-voice.png)

#### Supported voting

##### Weighted Voting
Weighted voting can exist in a policy or law making body in which each representative has a variable voting power (weighted vote) as determined by the number principals who have made that person their proxy, or the population or the electorate they serve.

By contrast weighted preference/preferential voting typically amasses a qualitative verdict of the voters. Within this form of ranked voting, a few advanced proportional voting methods ask each voter to grade the suitability for office of as many candidates as they wish. For example, the merit of each candidate to be graded Excellent, Very Good, Good, Acceptable, Poor, or Reject (and where all these grade count, assigned values such as 5 to 0). Under this, each member can by chosen by and/or could exercise a different weighted vote. In this way, each and every voting citizen is represented proportionately. No citizen's vote is "wasted".

A third definition is weighted bias voting. This exists in an electoral system in which not all the votes inherently vary in strength depending on the voter. Some voters, perhaps based on expertise, are given more weight than others. This is directly analogous to some preference shares. Listing Rules, the risk of a derivative suit, and of misrepresentation action may impose a cap on any enhanced voting rights attached, or to be attached, to preference shares. In the same way the existence of Unreformed House of Commons franchise-appointing small municipal corporations, was among injustices partly addressed by the Reform Act 1832 (widely known as the First Great Reform Act) in the United Kingdom. Being in the financial pocket of a sponsor, these were rebuked as pocket boroughs. [10]

##### Quadratic
>  its best function is with a Mutiple Choise but based on a
>Note: Is this the same as Convition Voting?

Quadratic voting is a collective decision-making procedure which involves individuals allocating votes to express the degree of their preferences, rather than just the direction of their preferences. By doing so, quadratic voting seeks to address issues of voting paradox and majority rule. Quadratic voting works by allowing users to "pay" for additional votes on a given matter to express their support for given issues more strongly, resulting in voting outcomes that are aligned with the highest willingness to pay outcome, rather than just the outcome preferred by the majority regardless of the intensity of individual preferences. The payment for votes may be through either artificial or real currencies (e.g. with tokens distributed equally among voting members or with real money). Quadratic voting is a variant of cumulative voting in the class of cardinal voting. It differs from cumulative voting by altering "the cost" and "the vote" relation from linear to quadratic.

Quadratic voting is based upon market principles, where each voter is given a budget of vote credits that they have the personal decisions and delegation to spend in order to influence the outcome of a range of decisions. If a participant has a strong support for or against a specific decision, additional votes could be allocated to proportionally demonstrate the voter's support. A vote pricing rule determines the cost of additional votes, with each vote becoming increasingly more expensive. By increasing voter credit costs, this demonstrates an individual's support and interests toward the particular decision. If money is used, it is eventually cycled back to the voters based upon per capita. Both E Glen Weyl and Steven Lalley conducted research in which they claim to demonstrate that this decision-making policy expedites efficiency as the number of voters increases. The simplified formula on how quadratic voting functions is

cost to the voter = (number of votes)^2. [11]

##### Ranked-choice

A ranked-choice voting system (RCV) is an electoral system in which voters rank candidates by preference on their ballots. If a candidate wins a majority of first-preference votes, he or she is declared the winner. If no candidate wins a majority of first-preference votes, the candidate with the fewest first-preference votes is eliminated. First-preference votes cast for the failed candidate are eliminated, lifting the second-preference choices indicated on those ballots. A new tally is conducted to determine whether any candidate has won a majority of the adjusted votes. The process is repeated until a candidate wins an outright majority.[12]

##### Multiple-choice 

> must verify it is correct one

Multiple non-transferable vote (MNTV), also known as plurality-at-large voting, block vote, block voting, or party block voting is a non-proportional voting system for electing several representatives from a single multi-member electoral district using a series of check boxes and tallying votes similar to a plurality election. Multiple winners are elected simultaneously to serve the district. Block voting is not a system for obtaining proportional representation; instead the usual result is that where the candidates divide into definitive parties (especially for example where those parties have party lines which are whipped) the most popular party in the district sees its full slate of candidates elected, resulting in a landslide.

The term "plurality at-large" is in common usage in elections for representative members of a body who are elected or appointed to represent the whole membership of the body (for example, a city, state or province, nation, club or association). Where the system is used in a territory divided into multi-member electoral districts the system is commonly referred to as "block voting" or the "bloc vote". Block voting as described in this article is "unlimited voting", unlike "limited voting", where a voter has fewer votes than the number of seats contested.

This system is usually based on a single round of voting, but it can sometimes appear in a runoff (two-round) version, as in some local elections in France, where candidates who do not receive an absolute majority must compete in a second round. In these cases, it is more accurately called "majority-at-large voting".

The term "block voting" sometimes means simple plurality election of slates in multi-member districts. In such a system, each party puts forward a slate of candidates, a voter casts just one vote, and the party winning a plurality of votes sees its whole slate elected, winning all the seats.[13]

##### Insured binding execution using Aragon Court*

##### Free proposal creation*

> ToDo : Search * ones

###### What is Vocdoni? (Paid)
Vocdoni is a project inside of the Aragon ecosystem, which is aimed at developing secure digital voting and governance solutions using decentralized technologies.

The main product is the eponymous governance platform, which allows participation in conventional organizations with the maximum guarantees of security and privacy. The platform is formed by a set of tools that not only serves for digital voting but also covers all other management aspects of an organization, such as membership management, dues payments and fundraising, as well as verifiable communication.

The voting protocol that powers the platform is designed to be universally verifiable, secure, and resistant to attack and censorship through the use of blockchain technology, together with decentralized technologies and cryptographic mechanisms, such as zero-knowledge proofs.[14]

### Aragon Court

Aragon Court is one of the core components of the Aragon OpenStack. It is a dispute resolution protocol that handles subjective disputes that cannot be solved by smart contracts. This is achieved by having a set of guardians drafted for each dispute who will vote to guarantee a certain ruling.
Aragon Court fundamentals

Guardians sign up to get drafted into the court by activating ANT tokens in Aragon Court's smart contract. The more tokens a guardian has activated, the higher the probability of getting drafted. 
Plurality rule

Unlike traditional courts, Aragon Court guardians are not asked to rule impartially on disputes but instead are asked to rule the way they expect the plurality of guardians to rule. Aragon Court attempts to find what the subjective truth is (i.e. the most correct outcome of a dispute) with a Schelling point. Every time a guardian is drafted for a dispute, a portion of their activated tokens is locked until the dispute is finalized. To incentivize consensus, guardians who don’t vote in favor of the final ruling have their locked tokens slashed. Guardians who vote in favor of the final ruling are rewarded with dispute fees and tokens from any guardians who voted for a minority ruling.

"Proof of stake"
The Aragon Court is a permissionless protocol where any participant can come and go without asking for anyone's authorization. Therefore, the protocol must function with integrity even in the presence of malicious actors, who may pose as multiple guardians at once to "Sybil attack" the Court. The defense against these attacks begins with a simple staking system where guardian impact is weighted by their active stake of tokens.

You may be thinking that if a cartel gets a majority of tokens, they'll have a majority weight and attack the system unopposed since they'll influence more than 50% of the decisions. However, Aragon Court uses multiple countermeasures including iterative appeals, commit and reveal voting, and locked withdrawal periods that are designed to dissuade a cartel from acquiring and misusing a majority of tokens.

Guardian responsibilities, Guardians are expected to perform certain duties and responsibilities, like reviewing arguments for a dispute and casting a vote. In order to help guardians properly execute their tasks, the Aragon Court Dashboard is available and provides all the tools they need.[15]

## References
[1] https://ethereum.org/en/dao/ 

[2] https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475

[3] https://aragon.org/about-aragon

[4] https://help.aragon.org/category/12-templates

[5] https://help.aragon.org/article/100-dao-management-with-multisig

[6] https://help.aragon.org/article/21-permissions

[7] https://help.aragon.org/article/37-agent

[8] https://aragon.org/aragon-govern#use-aragon-govern

[9] https://blog.aragon.org/introducing-aragon-voice/

[10] https://en.wikipedia.org/wiki/Weighted_voting

[11]https://en.wikipedia.org/wiki/Quadratic_voting

[12] https://ballotpedia.org/Ranked-choice_voting_(RCV)

[13] https://en.wikipedia.org/wiki/Multiple_non-transferable_vote

[14] https://help.aragon.org/article/59-what-is-vocdoni

[15] https://help.aragon.org/article/41-aragon-court

## ToDo

#### Check Developer notes:

Getting Started: https://hack.aragon.org/docs/getting-started
Aragon app framework: https://hack.aragon.org/docs/tutorial

## Contact.

***Developers***
- [David Serrano](https://twitter.com/getmaxcoin)
- [p1r0](mailto:p1r0@nethunters.xyz)

