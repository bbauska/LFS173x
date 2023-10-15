---
LFS173x: Linux FoundationX -- Becoming a Hyperledger Aries Developer
---

![](images/image001.png){width="4.0in"
height="1.4208191163604549in"}

**Becoming a Hyperledger Aries Developer**

![lfs171x - hyperledger
blockchain](images/image002.png){width="5.0in"
height="2.962648731408574in"}

Welcome to LFS173x: Becoming a Hyperledger Aries Developer

The four Hyperledger Identity projects, Indy, Aries, AnonCreds, and
Ursa, provide a foundation for building distributed applications using
authentic data. Together, the projects include protocol specifications
and open-source tools, libraries, and reusable components for
establishing secure, peer-to-peer messaging channels that can be used
for issuing, receiving, holding, presenting and verifying verifiable
credentials. These capabilities enable the creation and use of
independent digital identities rooted on blockchains or other
distributed ledgers that are interoperable across administrative
domains, applications, and any other data silo.

While this course will mention Ursa and dive a bit into Indy and
AnonCreds, its main focus is on Aries, and the possibilities Aries
brings for building applications on a solid foundation of digital trust.
This focus will be explained further in the course but for now, rest
assured: if you want to start developing applications that are identity
focused and using the blockchain, this is where you need to be.

### Chapter 1.

#### 

#### 

#### 

#### 

#### 

#### 

#### 

#### 

### Chapter 2.

#### 

#### 

#### 

### Chapter 3.

#### 

#### 

#### 

### Chapter 4.

#### 

#### 

### Chapter 5.

#### 

#### 

### Chapter 6.

#### 

#### 

### Chapter 7.

## Course Learning Objectives

This course is designed to get students from the basics of Trust over IP
(ToIP) and self-sovereign identity (SSI), what you learned about in the
last course---[\"Introduction to Hyperledger Self-Sovereign Identity
Blockchain Solutions\"
(LFS172x)](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa)---to
developing code for issuing, presenting, and verifying credentials with
your own Aries agent or wallet.

By the end of this course, you should be able to:

-   Build Trust over IP (ToIP) applications for a variety of use cases
    in the real world.

-   Develop Aries agent code for issuing, presenting, and verifying
    AnonCreds and other types of credentials.

-   Understand the basics of how Hyperledger Indy and other ledgers are
    used by Aries agents.

-   Understand the architecture and components of Aries agents.

-   Understand the data exchange protocols that are the core of
    Hyperledger Aries, particularly those involving establishing
    peer-to-peer connections, and exchanging verifiable credentials and
    presentations.

-   Learn about the mechanisms and tools used in the broad and diverse
    Aries community to enable interoperability.

-   Understand DIDComm routing, mediators and relays, their
    applicability in the Aries general case, and why routing is required
    for mobile agents.

-   Get started with your own Aries mobile wallet.

-   Understand the requirements in moving to production in an Aries
    environment.

-   Learn about current happenings in Aries and how you can join and
    contribute to this amazing community!

## Terminology

We use the terms blockchain, ledger, decentralized ledger technology
(DLT) and decentralized ledger (DL) interchangeably in this course.
While there are precise meanings for each of those terms, in the context
of the material covered in this course the differences are not
meaningful.

For more definitions, take a look at our
course [Glossary](https://courses.edx.org/courses/course-v1:LinuxFoundationX+LFS173x+1T2020/65cfba99617340f39051f7c6f839bf85/) section.

## Labs and Demos

Throughout this course there will be labs and demos that are a key part
of the content and that you are strongly advised to complete. The labs
and demos are hosted on GitHub so that we can maintain them easily as
the underlying technology evolves. Many will be short interactions
between agents. In all cases, you will have access to the underlying
code to dig into, run and alter.

For some labs, you won't need anything on your computer except your
browser (and perhaps your mobile phone). For others, you may have the
option of running the labs in your browser or locally on your own
system. For the \"in browser\" option, we use a service called [*\"Play
with Docker\"*](https://labs.play-with-docker.com/) that allows you to
access a terminal command line environment in your browser so you don't
have to install everything locally. The downside of using Play with
Docker is that you don't have all the code locally to review and update
in your local code editor. If you want that, stick with running the labs
locally.

When you run the labs locally, you need the following prerequisites
installed on your system:

-   A terminal command line interface running bash shell.\
    - This is built-in for Mac and Linux, and on Windows,
    the **git-bash** shell comes with git (see installation instructions
    below).

-   Docker, including Docker Compose - Community Edition is fine.\
    - If you do not already have Docker installed, go to [the Docker
    Documentation](https://docs.docker.com/get-docker/#supported-platforms) and
    then click the link for the installation instructions for your
    platform.\
    - New and up to date installations of Docker include an integrated
    Docker Compose plugin. If your version of Docker does not include
    Compose, please update your Docker installation. To verify, run from
    the command line **docker compose ---help** and you should see help
    information specific to Compose.

-   git\
    - The following article [*\"Installing Git on Linux, Mac or
    Windows\"*](https://www.linode.com/docs/guides/how-to-install-git-on-linux-mac-and-windows/) provides
    installation instructions for Mac, Linux (including if you are
    running Linux using VirtualBox) and native Windows (without
    VirtualBox).

All of the labs that you can run locally use Docker. You can run the
labs directly on your own system without Docker, but we don't provide
instructions for doing that, and we highly recommend you not try that
until you have run through them with Docker. We recommend this because
of the differences across systems. It's difficult to provide universal
instructions; we've seen many developers spend too much time trying to
get everything installed and working right and losing focus on what
matters: learning Aries.

**NOTE**: The teams we work with only use Docker/containers for
development and production deployment. In other cases, developers
unfamiliar with (or not interested in) Docker set up their own native
development environment. Doing so is outside the scope of the labs in
this course.

## Chapter 1 Overview - Overview

*Data breaches. Identity theft. Companies exploiting our personal
information.* We read about these Internet issues all the time. Simply
put, trust on the Internet is broken and it needs to be fixed.

![No Shortage of Headlines About Internet
Issues](images/image003.png){width="4.0in"
height="3.02958552055993in"}

**No shortage of headlines about Internet issues**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

This is where the Hyperledger Indy, Aries, AnonCreds, and Ursa projects
come in and, we assume, the main reason you are taking this course. The
Indy, Aries, AnonCreds, and Ursa tools, libraries and reusable
components provide a foundation for distributed applications built on
authentic data using distributed ledgers, purpose-built for
decentralized trust.

![The Hyperledger Foundation
Projects](images/image004.jpeg){width="6.0in"
height="3.1781517935258092in"}

**The Hyperledger Foundation projects\
Licensed under [CC BY
4.0](https://creativecommons.org/licenses/by/4.0/)**

**NOTE**: This course is called \"Becoming a Hyperledger Aries
Developer\" because it focuses on building applications on top of
Hyperledger Aries components---the area where you, a (soon to be!)
verifiable credentials application developer, can have the most impact.
In the process, you will use and learn about using AnonCreds, and other
types of verifiable credentials. We'll also go over Indy and other types
of ledgers useful for verifiable data. And underneath it all is the
cryptography from Ursa. But to build digital trust applications, Aries
is where you need to dig in.

##  Learning Objectives

By the end of this chapter, you should:

-   Understand why this course focuses more on Aries (and AnonCreds),
    and less on Indy or Ursa.

-   Understand the issues that Aries is trying to address.

-   Know the core concepts behind self-sovereign identity.

## Advantages of Hyperledger Aries

Hyperledger Aries, AnonCreds, Indy, and Ursa make it possible to:

-   Establish a secure, private channel with another person,
    organization, or IoT thing---like authentication plus a virtual
    private network---but with no central server and no login.

-   Send and receive arbitrary messages with high security and privacy.

-   Use messaging to issue and receive verifiable data---signed data
    that can be presented by the holder to others without needing to
    call back to the issuer.

-   Present data that you hold, and verify the signed data presented to
    you from others.

-   Create an Aries agent with business logic specific to your needs
    that acts on your behalf, be it on a server or on a mobile device.

The vast majority of that list is about Aries. You will need to
understand verifiable credentials, and we'll (mostly) use AnonCreds.
However, you will have relatively little interaction with Indy---and
almost none with Ursa---as the vast majority of those working with the
Hyperledger identity project set build on top of Aries. Only those
directly contributing code into Indy, Aries, AnonCreds, and Ursa, are
likely to have significant interactions with Indy and Ursa. And here's
another big takeaway: while all four of the Hyperledger identity
projects are focused on decentralized identity, Indy is a specific
blockchain implementation, whereas both Aries and AnonCreds are
blockchain-agnostic. With Aries, you aren't limited to Indy.

## Why We Need Identity Solutions

In today\'s world, we are often issued *credentials* as paper documents
(for example, our driver\'s license or passport). When we need to prove
things from those paper documents, such as our name, we hand over the
document. The *verifier* looks at the document and attempts to ascertain
who issued the document, whether it is valid or is a forgery, whether it
belongs to you, and whether it satisfies the purpose for which it was
requested. The *holder* of the document cannot choose to only hand over
a certain piece of the document but must hand over the entire thing.

A driver's license is typically issued by a government authority
(an *issuer*) after you prove to them who you are (usually in person,
using other paper credentials such as a passport and/or birth
certificate) and that you are qualified to drive. You then hold this
paper credential (usually in your wallet) and can show it to others
whenever you want---for example, when renting a car, in a bank, when
opening an account or in a bar, to prove that you are old enough to
drink. When you are doing that you are *presenting* the credential.
That's the *paper credential model*.

![Examples of Paper Credentials](images/image005.png){width="4.0in"
height="1.4140627734033246in"}

**Examples of paper credentials**\
By Peter Stokyo\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

 The paper credential model (ideally) *proves*:

-   Who issued the credential.

-   Who holds the credential.

-   The claims have not been altered.

The caveat \"ideally\" is included because of the possibility of forgery
in the use of paper credentials. As many university students know, it's
pretty easy to get a fake driver's license that can be used when needed
to \"prove\" those same things.

All that works pretty well in person, but what happens when we have the
same needs online? So far, the most common approach has been to try to
replicate the in person process with decidedly mixed results! We take a
picture of our identification documents, and submit them via email or a
web form to the requesting party. If forgeries were a problem in a paper
world, what about when we are taking pictures of those documents? And,
where are those documents going after they are submitted? It's one thing
to have them reviewed in person, but emailing core identity documents
about yourself does not feel very safe!

## Verifiable Credentials (1)

Enter the VC model, the bread and butter behind authentic data and
decentralized identity. The VC model brings about the possibility of
building applications with a solid digital foundation of trust.

The verifiable credentials model is the digital version of the paper
credentials model. That is:

-   An authority decides you are eligible to receive a credential and
    issues you one.

-   You hold your credential in your (digital) wallet.

-   At some point, you are asked to prove the claims from the
    credential. You may even be asked to prove claims from multiple
    credentials in a single step.

-   You provide a verifiable presentation to the verifier, proving the
    same things as with a paper credential (or several).

Plus,

-   In some cases, you can prove one more thing---that the issued
    credential has not been revoked.

As we'll see, verifiable credentials and presentations are not simple
documents that anyone can create and use. They are cryptographically
constructed so that a presentation proves the four key attributes of all
credentials:

1.  Who issued the credential.

2.  The credential was issued to the entity presenting it.

3.  The claims were not tampered with.

4.  The credential has not been revoked.

A quick caveat here. There are multiple kinds of verifiable credentials,
and with some kinds, the second item is not always a part of the
presentation. It is with Hyperledger AnonCreds, but we'll cover other
kinds as well in this course.

Unlike a paper credential, those four attributes are evaluated not based
on the judgment and expertise of the person looking at the credential,
but rather online using cryptographic algorithms that are extremely
difficult to forge. When a verifier receives a presentation from a
holder, they use information from a decentralized source, often a
distributed ledger (shown as the *verifiable data registry* in the image
presented on the next page) to perform the cryptographic calculations
necessary to prove the four attributes. Forgeries become much (MUCH!)
harder with verifiable credentials!

## Verifiable Credentials (2)

Why does this matter for an Aries developer? When you are developing
applications on top of Aries, you don't have to worry about the
cryptographic nuts and bolts of issuing, holding, presenting and
verifying---all of that is handled for you. So too are the exchanges of
data between the issuer and holder, and the holder and verifier. Rather,
your focus is on business logic.

-   What credentials is your organization going to issue?

-   How do I create a great mobile wallet user experience for holders?

-   What credentials should we be asking our users to present?

-   How can I extend our core business applications to issue credentials
    and verify presentations?

In this course, we'll show you how to use Aries to solve all those
challenges---and more!

![The W3C Verifiable Credentials
Model](images/image006.png){width="4.0in"
height="1.9290387139107612in"}

**The W3C Verifiable Credentials Model**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

 The prerequisite course, [*\"Introduction to Hyperledger Self-Sovereign
Identity Blockchain Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa),
more than covers the reasons why we need a better identity model on the
Internet so we won't go into it too much here. Suffice to say, the
availability of distributed ledgers (such as those based on Hyperledger
Indy) has enabled a better way to build solutions using verifiable
credentials for exchanging authentic data, and in doing so, enables the
creation of a more trusted Internet.

## Terms to Remember

In the remainder of this opening chapter, we'll review some important
concepts that you'll need for this course. In the following sections,
we\'ll provide short introductions on this list of topics:

-   self-sovereign identity

-   trust over IP

-   decentralized identifiers

-   zero-knowledge proofs

-   selective disclosure

-   revocation

-   secure storage

-   verifiable credential formats

-   agent

If you are not familiar or comfortable with these concepts and
terminology after reviewing these (re)introductions, you want to review
them in greater depth in this course: [*\"Introduction to Hyperledger
Self-Sovereign Identity Blockchain Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa)!

## Self-Sovereign Identity (SSI)

Self-sovereign identity is one of the most important concepts discussed
in the prerequisite course and it is what you should keep in mind at all
times as you dig into the world of Aries development. SSI is the idea
that you control your own data and you control when and how it is
provided to others, and that when it is shared, it is done so in a
trusted way with your consent. With SSI, there is no central authority
holding your data that passes it on to others upon request. Authorities
provide your data to you, you hold on to it, and you share it directly
with whom and when you want. The underlying cryptography and the use of
verifiable data registries enable you to independently present claims
about your identity to others who can verify those claims with
cryptographic certainty.

## Trust Over IP (ToIP)

Along with SSI, another term we use in this course is Trust over IP
(ToIP). ToIP is a Linux Foundation organization that (per the ToIP
website) is defining a complete architecture for Internet-scale digital
trust that combines both cryptographic trust at the machine layer and
human trust at the business, legal, and social layers. The technical
capabilities embodied in Indy, Aries, AnonCreds, and Ursa enable the
\"trust at the machine layer.\" ToIP includes self-sovereign identity in
that it covers identity, but also goes beyond identity (attributes about
you) to cover any type of authentic data. Authentic data, in this
context, is a set of claims (assertions) stated by the issuer to the
holder (in the form of a verifiable credential), that the holder can
later prove were said by the issuer to the holder, were not tampered
with and have not been revoked. ToIP's dual focus on both the technical
and governance aspects of authentic data is encapsulated in the \"Trust
over IP Stacks,\" as represented in this image from the [Trust over IP
Foundation](https://trustoverip.org/):

![Trust over IP (ToIP) Technology
Stacks](images/image007.png){width="7.5in"
height="4.5777318460192475in"}

**Trust over IP (ToIP) technology stack**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

As shown, there are two stacks in ToIP: a governance stack and a
technology stack. The technology stack is a typical layered stack,
driven by technical components at each level. In parallel, the
governance stack defines the information to govern each layer of the
stack. For example, at Layer 3, where verifiable credentials are
exchanged, governance defines how a verifier might come to trust the
issuer of a credential---not the cryptography (that can be verified
using technology), but what the information in the credential means.
That is, under whose authority and using what processes did the issuer
come to issue the credential being proven?

## Trust Over IP (ToIP): Aries in the ToIP Stack

The core of Aries implements Layer Two (peer-to-peer protocol) and Layer
Three (Data Exchange, including verifiable credentials) capabilities of
the ToIP stack. Aries implements DIDComm, a secure, transport-agnostic
mechanism for sending messages based on DIDs (decentralized identifiers)
and a set of data exchange protocols built on top of DIDComm. Aries
enables the use of Layer 1 DID utility mechanisms, such as Hyperledger
Indy. Hyperledger AnonCreds is a privacy-preserving kind of Layer 3
verifiable credential. Although Aries works really well with Indy and
AnonCreds, it can also be used with other Layer 1 utilities, and other
verifiable credential formats, including JSON-LD-based W3C Standard
Verifiable Credential signature schemes.

As an Aries developer, you will spend most of your time at Layer
4---building business applications on top of Aries frameworks that
interact with other Aries agents using secure messaging to exchange
verifiable data. You'll be harnessing a lot of power in the apps you
build!

## Trust Over IP (ToIP): Decentralized Governance

While Aries is on the technical stack side of the ToIP model, you will
discover that in building decentralized systems, you will have to deal
with decentralized governance issues. As a developer, you may not deal
with it directly (let the business folks do that!), but here is a quick
summary of the types of ToIP governance stack issues that your
organization will encounter.

Suppose you are a potential issuer, and your organization wants to issue
a credential. You need to make some decisions. What data elements should
go in that credential? Who should be eligible to receive the
credentials? What verification should be done before issuing a
credential? In the centralized world, you would do an analysis of what
your customers (holders) and verifiers need, make decisions and that
would be that. You have made a set of necessary governance decisions.
However, as soon as your customers want to share the credentials you
issue outside of your known ecosystem (which they can do---they control
when and to whom to present the credentials), another issue comes
up---interoperability. Verifiers want to use the credentials your
organization issues, and similar credentials issued for similar
(identical?) purposes from other organizations. How do we achieve such
interoperability? That's where decentralized governance comes in.

In a decentralized world with interoperability, your organization is
likely part of a formal or informal set of issuers of similar
credentials, and for the benefit of customers and shared verifiers, it
would be better if all of the issuers agreed on those governance
decisions. In that world, issues around governance change from one
entity making internal decisions to a set of entities making decisions
(ideally) for the common good of those in the ecosystem. If the set of
issuers have a formal entity that all issuers are members (such as a
medical \"College of Physicians and Surgeons\" in a region), you can go
back to the \"centralized\" model, albeit with a committee making the
decisions. But of course, as soon as everyone wants medical
professionals to be able to have their credentials checked in another
region, you have another set of participants---a new, informal set of
issuers. How do you make decisions then?

Understanding decentralized governance is a journey. Organizations
becoming issuers must first realize that it is in their own best
interest to \"decentralize the governance\" (which could take a while!),
and then learn how to contribute to a useful community to achieve the
goals. If there is a formal organization available, use that. If not,
attempt to build such an entity to make the decisions. Of course, in
order to make any progress, you have to decide how decentralized it
makes sense to be. Requiring worldwide agreement on the format of a
credential will ensure that a credential will never be issued! For your
organization, what is the right level of governance to strive for? First
movers will have a good chance (but not a guarantee) of having their
decisions applied more broadly, giving them a lead in deploying the
approaches and reaping the benefits. The chances of that are improved if
consideration is given from the start about the needs of the broader
community, and not just thinking about the organization's needs. We know
from experience that even having just two independent entities
discussing, analyzing and together making ToIP governance decisions will
be better than just one.

Governance is not a technical concern that developers normally deal
with, but it is a part of building ToIP-based solutions to keep in mind!
Enough of that for now---back to the technical pieces.

## Decentralized Identifiers (DIDs)

A decentralized identifier (DID) is a self-generated universally unique
identifier (uuid) with some added power. DIDs are resolvable into a DID
Document (DIDDoc) that contains (at least) cryptographic public keys
owned by the controller of the DID that allow them to prove control over
the DID. Per the [W3C DID
Specification](https://www.w3.org/TR/did-core/), a specific DID is
defined by its DID method---a specification that defines how to create,
resolve (read), update and delete such a DID. Resolving a DID is like
resolving a URL in a browser, but instead of returning an HTML page, a
resolved DID returns the DID's associated DIDDoc.

Let\'s look at an Indy DID as an example. An Indy DID looks like this:

**did:indy:sovrin:CYQLsccvwhMTowprMjGjQ6**

That DID is published on the Sovrin Indy network, and was created by
first generating an Ed25519 cryptographic public/private key pair. From
the public key is derived the namespace identifier---the part of the DID
after **\"sov:\"** in the example above). We're assuming in this course
that you know what cryptographic key pairs are (at a high level, at
least), but if you need a quick refresher, here is the [Wikipedia
definition](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography).
The DID and related content for the DIDDoc is published by its
controller (often an Aries agent) to an Indy ledger. Once done, anyone
that has access to DID Resolver software (such as this [Universal
Resolver website from the Decentralized Identity
Foundation](https://dev.uniresolver.io/)) that supports Indy can resolve
the DID and get back the DID Doc for that DID.

An Aries agent can publish an issuer's public DID on a publically
accessible Verifiable Data Registry (VDR), and will include the DID, a
public key and a DIDComm **service** containing physical endpoint (such
as a URL) to which messages can be sent to the Aries agent. Aries
holders and verifiers generally do not publish a DID on a VDR because
they don't need a public DID to participate in the verifiable credential
model. Of course, any specific Aries agent may be any or all of an
Issuer, Holder and Verifier. On most public Indy ledgers, such as the
Sovrin Network (the oldest public Indy network), only organizational
DIDs can be published. DIDs for people may **[not]{.underline}** be
published, blocked by GDPR-type legal agreements that ledger writers
must accept before writing to the ledger. Such agreements prevent a
person from issuing verifiable credentials rooted in most public Indy
networks.

Peer DIDs are created and exchanged peer-to-peer between pairs of
messaging agents. Such DIDs are shared directly with the paired agent
and so do not need to be published on a distributed ledger. Such DIDs
are used only for messaging; they are not used in the signing and
issuing of verifiable credentials or in presenting proofs of claims from
verifiable credentials.

## Zero-Knowledge Proof (ZKP)

A [zero-knowledge proof
(ZKP)](https://en.wikipedia.org/wiki/Zero-knowledge_proof) is a
cryptographic method of proving (as in mathematically prove, not just
claim) to someone that you know the value of an attribute without
sharing the value of the attribute itself. Hyperledger AnonCreds uses
several ZKPs in a variety of ways to enable important privacy preserving
verifiable credential features.

A (super cool) use of a ZKP in AnonCreds is a \"predicate ZKP.\" A
predicate ZKP is a true/false expression proven (with cryptography) to a
verifier based on a claim from an issued credential without sharing the
underlying claim. For example, proving based on a \"date of birth\"
claim that a person is older than a given age (e.g., older than 18)
without providing the date of birth itself. The cryptography is pretty
neat, although left up to you to dig into. In this course, we'll just
cover enough to show how it is used.

**NOTE**: Although powerful and certainly privacy preserving, the
application of predicates in Hyperledger AnonCreds is limited to
situations where the underlying data is a number. As such, to prove \"an
older than\" predicate, the \"date of birth\" in the credential MUST be
a number (such as the integer \"20221205\" for December 5, 2022), not a
string (such as \"2022-12-05\"). The expression from the verifier must
also use a date represented as a number in the same way.

A second important use of ZKPs in AnonCreds is in demonstrating that the
holder presenting data to a verifier was the holder to which the
credentials were issued. Such a demonstration is the same reason you
have photo identification cards, so that a verifier can look at you and
the photo and decide if it is your photo. The neat part of AnonCreds is
that this demonstration is done with a ZKP, without sharing a
correlatable identifier that can be used to track you. We've talked
about the importance of reducing the amount of data that can be used to
track you, and this is one important way AnonCreds enables that.

How does it work? Without going too into the weeds, when you are issued
a credential, you have the issuer insert a value into the credential (a
\"blinded link secret\"), that makes the issued credential uniquely
yours. When you present the credential, you provide a proof (containing
a ZKP) that your blinded link secret was put into the credential by the
issuer without revealing its value. Your proof is unique with every
presentation---it is non-correlatable. A presentation using a blinded
link secret still exposes the claims (the data) asked for by the
verifier (which may uniquely identify the prover), but a unique
identifier for the holder is **[not]{.underline}** automatically
provided as part of the process of presenting a proof.

AnonCreds uses additional ZKPs to prevent verifiers receiving
correlatable identifiers, including (as we'll see shortly) for proving
the revocation status of a credential.

## Selective Disclosure

A key capability of Hyperledger AnonCreds (and some other kinds of
verifiable credentials) is selective disclosure; being able to share
just a selection of claims issued in a verifiable credential rather than
being forced to share all of them in a presentation. With selective
disclosure, an issuer can put all of the claims that might be needed for
a range of use cases, and the holder/prover and the verifier can limit
the information shared in a presentation for a specific use case. In the
example pictured below, a holder with a \"driver's license\" type
verifiable credential can share just their picture and that they are old
enough to drink (using a ZKP predicate) to a bartender at a pub. The
rest (name, address, driver's license number, birth date, etc.) can be
held back---it's not needed by the pub. Selective disclosure is an
important privacy capability with verifiable credentials!

![An Example of Selective Disclosure---Person is verified as "old
enough" to enter the bar but no other data is
revealed](images/image008.png){width="4.0in"
height="2.208030402449694in"}

**An example of selective disclosure---person is verified as**\
**\"old enough\" to enter the bar but no other data is revealed**\
By Peter Stokyo\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## Revocation

Verifiable credential revocation is the capability for an issuer to
publish (to everyone) that an issued verifiable credential is no longer
active. This action is done unilaterally by the issuer, although they
might inform the holder that their credential has been revoked. While
many think that revocation is always the result of something \"bad\"
done by the holder (e.g., the \"revoking a driver's license\" because of
too many driving violations scenario), there are many other business
reasons for revoking a credential, the most common being that
information in the credential is changed (e.g., change of address). When
something changes, it's easy with Aries for an issuer to notify the
holder about the availability of a new credential, and to revoke the old
credential. Once revoked, the verifiable presentation process makes it
easy for a verifier to know if a holder uses a credential that has been
revoked, and hence (in most use cases), should not be accepted.

For verifiable credential formats like AnonCreds that support ZKP
capabilities (and require non-correlation), revocation is a bit more
complex than one might assume. In a simple revocation approach, the
issuer might include a unique ID for the credential, and to revoke it,
add the ID to a published list of revoked credential IDs. The holder
shares the credential ID with the verifier, who can use the credential
ID to check the registry and see if the credential has been revoked. The
problem with that approach for a ZKP-enabled verifiable credential like
AnonCreds is that the credential ID given to the verifier is a unique,
correlatable identifier. That's exactly what we want to avoid! With a
ZKP revocation scheme, a credential ID is shared by the issuer to the
holder, and there is a published revocation registry. However, the
prover does not give the credential ID to the verifier. Instead, the
prover generates a ZKP \"non-revocation proof\" that the verifier can
check using the data in the published revocation registry without the
holder sharing their credential ID. ZKPs are powerful, and useful!

## Verifiable Credential Formats

Aries agents support several verifiable credentials formats and
cryptographic signatures today, and allows for adding more, as new
credential types become important.

Most Aries frameworks support the privacy-preserving Hyperledger
AnonCreds verifiable credentials that use a number of capabilities that
we've outlined in this section, including support for ZKPs, selective
disclosure and ZKP revocation. While simple to use in Aries and
functionally complete, the AnonCreds data format predates the publishing
of the W3C Verifiable Credential Standard, and as such, does not (yet!)
use that standard.

To align with other verifiable credential communities that don't use
Hyperledger AnonCreds, several Aries projects have implemented support
for JSON-LD W3C Standard Verifiable Credentials signature suites,
including:

-   LD Signatures (JSON-LD signed with an Ed25519 key), or

-   BBS+ Signatures for JSON-LD.

With LD Signatures, a verifiable presentation includes the entire
verifiable credential, lacking selective disclosure and any form of ZKP.
Using BBS+ Signatures, a verifiable presentation supports selective
disclosure. BBS+ Signatures can be implemented to support other ZKP
capabilities---e.g., not exposing a unique identifier for a prover as
part of a verifiable presentation. However, the BBS+ Signatures for
JSON-LD implementation does not use other ZKP capabilities. Further,
there is not yet support for either ZKP predicates or a ZKP revocation
capability for BBS+ Signatures. Selective disclosure is very important,
but BBS+ Signatures for JSON-LD lacks the other features of AnonCreds.

When looking at different Aries agents, verifiable credential format
support is an important differentiating factor. Want all the
privacy-preserving features available today? AnonCreds is the way to go.
Want W3C Standard Verifiable Credentials? JSON-LD credentials and
signatures are your best bet, ideally using BBS+ so you get selective
disclosure. Want it all? Well that might be possible as well. As of the
writing of this course (January 2023), there is a lot happening in the
Hyperledger AnonCreds project, and in particular around the idea of
enabling AnonCreds verifiable credentials to be issued in W3C Verifiable
Credentials Data Model Standard format. In fact, it may soon be possible
to issue a credential with both an AnonCreds and LD Signature such that
a holder can present a proof with AnonCreds privacy preserving
capabilities or (if necessary) using a \"show everything\" LD Signature
proof. It's something to keep an eye on when looking at what's new in
Aries!

## Secure Storage

Every Aries agent includes some kind of secure storage to hold its
secrets. Most important of those secrets are the private keys that the
agent creates and uses to sign data and decrypt messages from other
agents. The creation and use of private keys is generally handled within
a key management service (KMS) that is within or associated with the
agent's secure storage. The KMS makes sure that private keys are used
appropriately, and are not ever available to the Aries application code.
Ideally, the KMS is a hardware component or a software secure enclave.
For an Aries Developer (like you!) that is good news as it means that
you don't have to write any software that accesses those important
secrets.

Along with the Aries agent created keys, the secure storage holds other
data that you don't want others to access but need as an operational
agent, such as data about connections with other agents (peer DIDs and
connection metadata), verifiable credentials issued to you, cached
ledger objects, and the state of protocols that are currently \"in
flight\" (e.g., while your agent is being issued a credential). All of
the data in Aries secure storage is encrypted, with the decryption keys
carefully managed. While this is absolutely necessary for the security
of Aries, at some point when you are debugging your Aries application,
you will likely become annoyed that all secure storage is encrypted,
inaccessible even in a developer sandbox.

Most Aries implementations provide a way for \"other data\" to be stored
in the Aries agent secure storage, but we usually discourage such use of
Aries' persistence. Our recommendation is that any business data not
needed for the operation of the agent itself be stored in a separate
\"business\" database. We'll talk more about this when we talk about
Aries controllers, starting in Chapter 4.

## Agent

Hyperledger Aries uses the term agent to mean the software that is
operated by an entity (e.g., person, organization or thing) that
interacts with other agents. For example, a person might have a mobile
agent wallet application on their smart device, while an organization
might have an enterprise agent running on a server, perhaps in the
cloud. All agents (with rare exceptions) have secure storage for
securing identity-related data including DIDs, keys and verifiable
credentials. As well, all agents are controlled by their owner,
sometimes with direct control such as with a mobile wallet and sometimes
with automated workflows and business logic, such as an agent for a
bank. We're going to be talking a lot about agents in this course. As an
Aries developer, you'll spend most of your time building agents for
specific use cases.

## Chapter 1 Summary

This chapter has largely been a review of the concepts introduced in the
previous course. Its purpose is to provide context for why you want to
become an Aries developer and recaps some of the terminology and
concepts behind decentralized identity solutions that were discussed in
the prerequisite course: [*\"Introduction to Hyperledger Self-Sovereign
Identity Blockchain Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa).

## Chapter 2 Overview -- Exploring Aries and Aries Agents

As you learned in the prerequisite course, [*\"Introduction to
Hyperledger Self-Sovereign Identity Blockchain Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa)---which
you took, right?---Hyperledger Aries is a set of messaging protocols and
implementations of those protocols for enabling secure peer-to-peer
messaging that can be used for creating, transmitting, storing,
presenting and verifying digital credentials. Aries agents are software
components that act on behalf of entities---people, organizations and
things. Aries agents enable decentralized, self-sovereign identity based
on a secure, peer-to-peer communications channel. The Aries project
includes the definition of versioned, community-wide interoperability
profiles, and a test capability that allow Aries component builders to
continuously demonstrate their implementation's adherence to the
protocols and their interoperability with other implementations.

![Hyperledger Aries logo](images/image009.png){width="4.0in"
height="1.1294116360454942in"}

In this chapter, we'll try to convert all the buzzwords in the previous
paragraph into practical knowledge about Aries that you will use when
developing your own applications. We'll look at the architecture of an
Aries agent through some hands-on labs. Specifically, we look at what
parts of an agent come from Aries, and what parts you, an Aries
developer-to-be, are going to have to build. We will also look at the
interfaces that exist to allow Aries agents to talk to one another and
to distributed ledgers such as instances of Hyperledger Indy.

## Learning Objectives

By the end of this chapter (2), you should:

-   Be familiar with the Aries ecosystem consisting of wallet agents for
    people and organizations, server-based agents for enterprises and
    agents for IoT devices.

-   Know the concepts behind issuing, holding/proving and verifying
    agents.

-   Understand the internal components of an Aries agent.

-   Know what Aries interoperability means and how it is achieved with
    the Aries Agent Test Harness (AATH).

-   Learn about tools for testing Aries mobile wallet interoperability.

## Examples of Aries Agents

Let's first look at a couple of examples to remind us of what Aries
agents can do. We'll also use this as a chance to introduce some
characters that the Aries community has adopted for many Aries
proof-of-concept implementations. You first met these characters in the
LFS172x course.

![](images/image010.png){width="4.0in"
height="2.122876202974628in"}

-   Alice is a person who has a mobile wallet that uses Aries protocols
    running on her smartphone. She uses it to receive credentials from
    various entities, and uses those credentials to prove things about
    herself online.

-   Alice's smartphone wallet connects with a specialized agent that
    does nothing except routes messages to her. It too is an Aries agent
    (called a *mediator*, as we'll see) that is (most likely) run by a
    vendor. We'll learn more about these cloud services when we get to
    the Aries routing and mobile wallets chapters.

-   Alice is a graduate of Faber College (of Animal House fame), where
    the school slogan is \"Knowledge is Good\" (we think the slogan
    should really be \"Zero Knowledge is Good.\") Faber College has an
    Aries agent that issues verifiable credentials to the college's
    students. It issues student ID cards as verifiable credentials to
    students, and digital diplomas to graduates.

-   Faber has agents that verify presentations of claims from students
    when their student ID is needed around campus---joining classes,
    writing exams, getting food at campus eateries and so on.

-   Businesses in and around Faber College have agents that verify
    presentations of claims from students and staff at the college to
    allow them to easily offer discounts to students. For example, Alice
    proves the claims from her \"Faber College Student ID\" credential
    to get a discount every Tuesday night when she goes to (and wins)
    Trivia Night at a nearby pub.

-   Faber also has an Aries agent that receives, holds and proves claims
    from credentials about the college itself. For example, Faber's
    agent might hold a credential that it is authorized to grant degrees
    to its graduates from the jurisdiction (perhaps the US state) in
    which it is registered.

-   ACME is a company for whom Alice wants to work. As part of their
    application process, ACME's Aries agent requests proof of Alice's
    educational qualifications. Alice's Aries agent can provide proof
    using the credential issued by Faber to Alice.

-   Since Alice is the first Faber College student to ever apply to
    ACME, ACME doesn't know if they can trust Faber. An ACME agent might
    connect to Faber's agent (using the DID in the verifiable credential
    that Alice presented) to get a proof from Faber that it is a
    credentialed academic institution from an authorized regulator.

## Lab: Issuing, Holding, Proving and Verifying

In this first lab, we'll walk through the interactions of three Aries
agents:

-   A mobile agent to hold a credential and prove claims from that
    credential.

-   An issuing agent.

-   A verifying agent.

The instructions for running the lab can be found
on [GitHub](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/IssuingHoldingProving.md).

## More on the Aries Ecosystem (1)

All of the examples of Aries agents in the previous section can be built
and operated independently by different organizations because of the
common protocols upon which Aries agents communicate, as pictured below.

-   Some of the Aries agents are run by large enterprises (such as Faber
    College) that have a publicly accessible endpoint to which other
    agents can initiate connections. Such enterprise agents might be to
    verify credentials, or issue them---which usually involves verifying
    credentials before issuing.

-   Some enterprise agents might be the organizational equivalent of
    personal wallets, receiving, holding and presenting credentials
    about the organization itself. Of course, somewhere behind such an
    organizational wallet are the people in charge of the organization.

-   Other agents are owned by small businesses (such as the pub where
    Alice goes for Trivia Night) that might not be sufficiently IT-savvy
    to run their own agents. They might use an Aries Agency-as-a-Service
    offered by a vendor that allows them to, for example, use a mobile
    verifier app preconfigured for requesting certain types of
    credentials.

-   Mobile wallet apps, such as the one you used in the first lab.

-   Since mobile apps cannot have their own physical endpoint, it is not
    possible for an enterprise agent (such as Faber's enterprise agent)
    to send a message directly to a mobile wallet. Rather, each mobile
    wallet must have a routing agent that gives other agents a physical
    endpoint to which they can send messages destined for the wallet.
    We'll cover this in detail in the chapters on routing and mobile
    wallets.

An Aries ecosystem consists of both the Aries agents that message one
another to exchange verifiable credentials and an (ever expanding) set
of verifiable credential types that are issued, held, proven and
verified. The off-campus store that is providing discounts to students
because they have a student ID verifiable credential must know that
Faber College is issuing the credential and the meaning of the various
data elements (\"claims\") in the credential. To put that into Trust
over IP (ToIP) terms, all the participants have to know both the
technical and governance elements of the ecosystem---the ToIP Dual
Stack.

The agents in an Aries ecosystem share many attributes:

-   They all have secure storage for keys.

-   They all have some secure storage for other data related to their
    role as an agent.

-   Each interacts with other agents using secure, peer-to-peer
    messaging protocols.

-   Most connect with ledger(s) to write (issuers) and read (holders and
    verifiers) decentralized identifiers (DIDs) and verifiable
    credential metadata.

-   Most process (issue, hold, prove and verify) verifiable credentials.
    An exception might be specialized routing agents.

-   They all have an associated mechanism to provide \"business rules\"
    to control the behavior of the agent:\
    - Often a person (via a user interface) for phone, tablet, laptop,
    etc.-based wallet agents.\
    - Often a backend enterprise system for enterprise agents. The
    backend system may in turn have request handling workflows that
    include people.\
    - For routing agents the \"rules\" are usually limited to the
    forwarding of messages to other agents. Such routing agents are
    usually fully automated.

## More on the Aries Ecosystem (2)

While there can be many agent variations, the most common ones are:

-   Agents for people.

-   Agents for organizations.

-   Agents for routing messages to and from agents for people and
    organizations.

![Phone, car, cloud, screen,
home](images/image011.png){width="2.0in"
height="2.1996270778652667in"}

But let's not leave out agents for things! A significant emerging use
case that we've not covered in this section are agents embedded within
or associated with IoT devices. In the common IoT case, IoT device
agents are just variants of other agents, connected to the rest of the
ecosystem through a server-based agent. All the same principles apply.
For example, IoT devices might include a sensor to measure something
(such as greenhouse gas emissions at a factory) and emit the data by
issuing verifiable credentials, ensuring that the data cannot be
tampered with after generation. This provides a foundation of trust
about the captured data---if the device itself can be trusted. Such
trust might be accomplished by third-party auditors or government
regulators certifying the operation of the device, and hence the
validity of the issued verifiable credentials.

## Ledgers and Verifiable Credential Formats in an Aries Ecosystem 

The vast majority of Aries agents connect with a public ledger (and
sometimes several) to read and write the data necessary to share
verifiable credentials and presentations. In the diagram below, the
issuer, holder and verifier use the *verifiable data registry* (as
defined in the W3C Verifiable Credential standard), which is often
implemented as a distributed ledger as the basis for issuing and
presenting verifiable data. Aries agents can be configured to interact
with a variety of ledgers, including Hyperledger Indy ledgers (such as
the Sovrin Foundation's MainNet) and other types of networks, such as
Microsoft's Ion that is rooted on Bitcoin. Aries Agents can also use a
variety of verifiable credential schemes including privacy-preserving
AnonCreds credentials and Linked Data Signatures (LD-Signatures) and
BBS+ Signatures for JSON-LD. Well-defined protocols for issuing and
presenting verifiable data make it (relatively) easy to add other
verifiable credential formats and to interact with other credential
issuance/presentation approaches such as Open ID Connect.

![The Verifiable Credential Trust
Triangle](images/image012.png){width="6.0in"
height="3.374790026246719in"}

**The verifiable credential trust triangle**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

In this course, we will mostly use the more mature Aries+Indy
combination using AnonCreds in the labs as we establish the foundational
concepts. However, we'll also point out where other ledgers can be used
and highlight the differences in using other verifiable credential
formats. There is also a lab or two where you get hands-on with non-Indy
use cases.

## The Logical Components of an Aries Agent

All Aries agent deployments have two logical components:
a *framework* and a *controller*.

![The Logical Components of an Aries
Agent](images/image013.png){width="4.0in"
height="2.8892629046369205in"}

**The Logical Components of an Aries Agent**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

The framework contains the standard capabilities that enable an Aries
agent to interact with its surroundings---ledgers, storage, verifiable
credentials, presentations and other agents. As an Aries application
developer, a framework is an artifact of Aries that you don't have to
create or maintain, you just embed it in your solution. An Aries
framework knows how to initiate connections, respond to requests, send
messages, manage secure storage and more. However, a framework needs to
be told *when* to initiate a connection or to send a request. It doesn't
know *what* response should be sent to a given request. A deployed
framework just sits there until it's told what to do.

The controller is the component that, well, controls the behavior of an
instance of an Aries framework---the business rules for that particular
agent instance. The controller is the part of a deployment that you, an
Aries developer, build to create an Aries agent that handles your use
case. For example:

-   In a mobile application, the controller is the user interface that
    enables a person to interact in an Aries ecosystem. As events come
    into the application, the user interface shows the person their
    options, and after input from the user, tells the framework how to
    respond to the event.

-   An issuer, such as Faber College's agent, has a controller that
    integrates agent capabilities (requesting proofs, verifying them,
    issuing credentials and so on) with enterprise systems, such as a
    \"Student Information System\" that tracks students and their
    grades. When Faber's agent is interacting with Alice's, and Alice
    requests an \"I am a Faber Graduate\" credential, it's the
    controller that figures out if Alice has earned the right to receive
    such a credential, and if so, what claims (data) should be put into
    Alice's credential. The controller also directs the agent to issue
    the credential.

## Aries Agent Architecture (ACA-Py) (1)

The diagram below is an example of an Aries agent architecture, as
exemplified by Aries Cloud Agent-Python (ACA-Py):

![Aries Agent Architecture
(ACA-Py)](images/image014.png){width="4.0in"
height="4.585994094488189in"}

**Aries agent architecture (ACA-Py)**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

The framework provides all of the core Aries functionality such as
interacting with other agents and the ledger, managing secure storage,
sending event notifications to, and receiving instructions from the
controller. The controller executes the business logic that defines how
a particular agent instance behaves---how it responds to the events it
receives, and when to initiate events. The controller might be a web or
native user interface for a person or it might be coded business rules
driven by an enterprise system. Between the framework and the controller
is a pair of interfaces:

-   When the framework receives a message (an event) from the outside
    world, it sends a *webhook* (a notification) about the event to the
    controller so the controller can decide what to do.

-   In turn, the controller sends a *request* to the framework to tell
    the framework how to respond to the event.\
    - The same controller-to-framework request interface is used when
    the controller wants the framework to initiate an action, such as
    sending a message to another agent.

## Aries Agent Architecture (ACA-Py) (2)

What that means for an Aries developer is that the framework you use is
a complete dependency that you include in your application. You don't
have to build it yourself. It is the controller that gives your agent
its unique personality. Thus, the vast majority of Aries developers
focus only on building controllers, while paying little attention to the
internals of the Aries framework they are using.

Further easing the learning curve for Aries controller development is
that its event driven processing is almost identical to web development.
The controller sits waiting for an event. When received, the event type
is determined, it is dispatched for processing, and back into the event
loop we go.

![](images/image015.jpeg){width="4.0in"
height="2.6666666666666665in"}

**My Aries controller\
**Photo by [Danial Igdery](https://unsplash.com/@ricaros) on Unsplash

Of course, since Aries frameworks are both evolving and open source, if
your agent needs a feature that is not in the framework you are using,
you are welcome to do some Aries framework development and contribute
the feature to Hyperledger. We'd really like it if you did!

## Agent Terminology Confusion

In many places in the Aries community, the \"agent framework\" term we
are using here is shortened to \"agent.\" That creates some confusion as
you can say \"an Aries agent consists of an agent and a controller.\"
Ugh... Throughout the course we have tried to make it clear when we are
talking about the whole agent versus just the framework. Often, we will
use the name of a specific framework (e.g., Aries Cloud Agent Python or
Aries Framework JavaScript) to make it clear the context of the term.
However, as a developer, you should be aware that in the community, the
term \"agent\" is sometimes used just for the agent framework component
and sometimes for the combined framework+controller. Naming is hard\...
🤦

## Aries Agent Internals and Protocols

Below, we'll cover, at a high level, the internals of Aries agents and
how Aries agent messaging protocols are handled. Aries uses DIDComm
protocols for messaging, which are analogous to other messaging
protocols like Signal.

The most basic function of an Aries agent is to enable (on behalf of its
controlling entity) secure, encrypted messaging with other agents.
Here's an overview of how that happens:

1.  Faber and Alice have running agents.

2.  Somehow (we'll get to that) Faber's agent discovers Alice's agent
    and sends it an invitation (yes, we'll get to that too!) to
    connect.\
    - The invitation from Faber is in plaintext (often presented as a QR
    code) and includes information on how a message can be encrypted and
    securely sent by Alice's agent to Faber's.

3.  Alice's agent (perhaps after conferring with Alice---\"Hey, do you
    want to do this?\") creates a new private DID for the relationship
    and embeds it in a \"request to connect\" message it sends to
    Faber's agent.\
    - This message is not plaintext. It uses information from the
    invitation to securely encrypt and send the message back to Faber's
    agent.

4.  Faber's agent framework associates the message from Alice with the
    invitation that was sent earlier, and confers (via a webhook) with
    Faber's controller about what to do with the request.

5.  Assuming Faber's controller agrees, its agent framework stores
    Alice's connection information, creates a new private DID for the
    relationship, and sends a response message to Alice's agent using
    the public key and endpoint information from Alice's DID.\
    - Whoohoo! The agents are connected.

6.  Faber and Alice can now send messages to one another (via their
    agents, of course). The messages use the newly established encrypted
    communication channel and so are both private and secure.

## Lab: Agents Connecting

Let's run through a live code example of two Aries agents using a
protocol to connect and send messages to one another.

Follow
this [link](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/agentsConnecting.md) to
GitHub to try it yourself and explore the code in the example.

## Aries RFCs, Interoperability and Aries Interop Profiles (1)

While we'll be digging into Aries protocols a lot more in this course
(especially in Chapters 4 and 5), we want to cover something right up
front that is crucial in any software component built to run protocols:
interoperability. A core part of Aries are the protocols that have been
defined to exchange messages between agents to accomplish shared goals,
such as issuing a verifiable credential and presenting a proof. Inherent
in the use of protocols is that they evolve over time as implementations
are completed (\"wait, we missed this piece of data!\"), as new use
cases come up (\"if we add this to the protocol, we can do these other
use cases\"), and as the need for new protocols are discovered. In
Aries, the [\"Aries
RFCs\"](https://github.com/hyperledger/aries-rfcs) GitHub repository
contains the full set of community-created protocols that enable
software components to be Aries agents. Pull Requests for that
repository are constantly being submitted, reviewed and merged (or
rejected) to add, extend and remove (archive) the protocols. With Aries
protocols ever changing, how can a developer build something that works
reliably with things that are being built by others?

The challenge of independently building components based on shared,
changing protocols is enabling interoperability. How can we get all of
the teams of developers using a common set of protocols? What version of
the protocols should they be using? Are all the teams interpreting the
protocols in the same way? This is a common problem in many technical
communities building products based on protocols---WiFi makers,
Bluetooth, OAuth and more have all faced this challenge.

The Hyperledger Aries project encountered this challenge after the first
few Aries agents were successfully demonstrated at a hackathon in Provo,
Utah in 2019. Leading up to, and at the hackathon, the teams building
Aries implementations regularly tested with one another and things
worked pretty well---the hackathon was a success! However, once the
hackathon ended, the teams went back to focusing on their own use cases,
their own deployments, and cross implementation testing and
communication fell away. New teams joined the community and built their
own implementations without the benefit of the hackathon interop focus.
And with a lack of focus on interoperability came frustration... no one
could be certain that the agents that worked together yesterday would
still be working together tomorrow.

## Aries RFCs, Interoperability and Aries Interop Profiles (2)

The solution for the Aries community was the definition of Aries Interop
Profiles (AIPs). The concept of Aries Interop Profiles is formally
defined in [Aries RFC
0302](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0302-aries-interop-profile).
Here is a quick summary of the key points:

-   Each AIP has a version number, starting with 1.0.\
    - AIP versions are much like the various published WiFi standards
    (e.g., 802.11a, 802.11b/g/n and 802.11ac, and so on).

-   Each AIP has a mission, a set of goals that Aries implementations
    will be able to accomplish if they are compliant with that AIP
    version.

-   Each AIP defines a set of Aries RFCs that all compliant
    implementations will support.\
    - And if necessary, a standard that is outside of Aries.

-   For each included RFC, a link in the AIP goes to a specific version
    (a literal GitHub commit) of the RFC or external standard.

-   An RFC-driven suite of tests enables demonstrating interoperability
    across Aries implementations.

The Aries community defined AIP 1.0 in February 2020, selecting 19 RFCs,
and (per the AIP process) identifying a specific version of each of
those RFCs. The AIP 1.0 mission was based on the **[de
facto]{.underline}** standard Aries agents of the time, particularly as
it related to the use of establishing connections and the use of
AnonCreds verifiable credentials. One thing that AIP 1.0 did not include
at the time it was created, was an effective test suite for
demonstrating either compliance or interoperability. As we'll see later
in this chapter, such a test capability came later (and spoiler, it's
pretty great!).

AIP 1.0 has proven to be quite successful in enabling (pretty) reliable
interoperability across many Aries implementations. It has been
demonstrated repeatedly that it is relatively easy to build
interoperable Aries agents from scratch or based on existing frameworks.

In 2021, an effort was begun to define AIP 2.0, with final approval
occurring on May 26, 2021. AIP 2.0's mission is much the same as AIP
1.0, but extended to add support for ledgers other than Indy and
verifiable credential formats other than AnonCreds. Throughout the
course, we'll highlight places where the differences between AIP 1.0 and
2.0 are most relevant. As we've mentioned before, the core concepts of
Aries remain the same across implementations, and that's also true with
AIP 1.0 and 2.0.

And as this is written (January 2023), there are rumblings of an AIP 3.0
that will include a new version of DIDComm (V2), and the protocol
updates necessary to use DIDComm V2. Given the progress being made in
Aries since AIP 2.0 was declared, AIP 3.0 will likely include a number
of powerful new capabilities.

## Exploring Aries Frameworks

Next, we provide a summary of the four open source Aries frameworks, in
alphabetical order. Although several frameworks include their language
of implementation in the name, none are restricted to deployments in
that language, as we will see.

## Aries Cloud Agent Python

[Aries Cloud Agent
Python](https://github.com/hyperledger/aries-cloudagent-python) (ACA-Py)
is a mature, purely cloud-based agent, suitable for deployment as an
enterprise issuer/verifier or an organizational holder (or all three at
once!). It supports robust, scalable enterprise deployments with
features like:

-   Full AIP 1.0 and near complete (as of this writing, January 2023)
    support for AIP 2.0.

-   Support for multiple verifiable credential formats including
    AnonCreds and JSON-LD using LD-Signatures and BBS+ Signatures.

-   Scalable cloud native support, for use on container environments
    like Kubernetes.

-   Multi-tenant support, allowing many identity owners to use a single
    scaled instance.

-   Enterprise database support using Postgres or Clustered Postgres.

-   Integration with persistent queue and shared caching, such as Redis.

-   Issuer support for AnonCreds Revocation, including automated
    handling of multiple registries.

While developed in Python, ACA-Py exposes an HTTP API for controllers to
use, so applications can be developed in any language/stack. ACA-Py has
even been deployed on Raspberry Pi's and so can be used in IoT
scenarios. The Hyperledger Aries project includes services such as
an [Aries
Mediator](https://github.com/hyperledger/aries-mediator-service) and
an [Aries
Endorser](https://github.com/hyperledger/aries-endorser-service) that
are pre-configured, purpose-built instances of ACA-Py suitable for
immediate deployment.

## Aries Framework Go

[Aries Framework
Go](https://github.com/hyperledger/aries-framework-go) (AF-Go) is a
mature, Aries framework implemented in pure Golang that can be deployed
in many environments, enterprise, browser and mobile. AF-Go supports
JSON-LD verifiable credentials using LD-Signatures and BBS+ Signatures,
on VDRs other than Indy. AF-Go was implemented to support the TrustBloc
and did:orb VDRs, but also includes an extensible DID resolver that
allows the use of many other DID methods. Work has been happening
recently to also add support for AnonCreds into the framework. AF-Go was
started as the community neared the completion of defining AIP 2.0, and
as such only supports AIP 2.0. The benefit of being a pure Golang
implementation is that the library can be compiled to WASM for use
within a browser, opening up the possibility of browser-based Aries
wallets.

## Aries Framework JavaScript

[Aries Framework
JavaScript](https://github.com/hyperledger/aries-framework-javascript) (AFJ)
is a relative newcomer to the Aries family, that has an extremely active
developer community, and a full feature set. The AFJ team's initial
focus was on building a framework to be embedded in a mobile wallet app,
but features are rapidly being added to support the server-side use case
as well. AFJ has AIP 1.0 and AIP 2.0 support, mediator capabilities and
support for both AnonCreds and JSON-LD (using LD-Signatures and BBS+
Signatures) verifiable credentials. AFJ is the basis for [Aries
Bifold](https://github.com/hyperledger/aries-mobile-agent-react-native),
a complete, open source Aries wallet that can be customized for
publishing to the Apple and Google app stores in hours. We'll cover
Aries Bifold when we dive into mobile wallets later in the course.

## Aries VCX

[Aries VCX](https://github.com/hyperledger/aries-vcx) (for Verifiable
Credential eXchange) derives directly from the Agent work started in the
Hyperledger Indy project. Aries VCX is implemented in Rust with a
C-callable interface, and official wrappers for Java (including
Android), iOS, and NodeJS. Aries VCX requires the use of a mediator
(included), whether used with mobile or not, and has rich support for
AIP 1.0, with (as of January 2023) AIP 2.0 support in progress. Aries
VCX has an extremely active contributor community, led by a team
at [ABSA Bank](https://www.absa.co.za/personal/) (South Africa).

## Other Aries Frameworks

Within Hyperledger, there is one more framework, [Aries Framework
.NET](https://github.com/hyperledger/aries-framework-dotnet), however,
as of this writing, contributions to that repository have slowed to a
trickle. The framework is still in use, but the open source version is
getting only a minimum of updates. That may change, so if you are a .NET
developer, you might want to see the current state of the framework.

Outside of the Hyperledger Aries project itself, there are a number of
open and closed source implementations of Aries, and a large number of
commercial products built on top of different Aries frameworks and
deployed in the cloud (as a service) or on premise. There are far too
many to list here!

In the open-source category, the Findy Agency project has a number of
great tools and capabilities for deploying your own open source agency.
The project, implemented in Golang, uses Google's gRPC integration
layer, and implements a single instance, multi-tenant Aries agency. It
supports AIP 1.0 protocols using AnonCreds verifiable credentials. The
Aries agency can be used for cloud-hosted wallets, and the Findy Agency
supports a mobile interface for accessing agency-hosted wallets. The
implementation is extremely fast and includes a number of novel
capabilities.

## How to Ensure Interoperability

Now we know that there are lots of Aries frameworks, and lots of
organizations out there building applications based on those frameworks.
And we also know that in the Aries world there are Aries Interop
Profiles (AIPs) that define how Aries agents should behave. How do we
know that all of those Aries frameworks are following the AIPs? How do
we know that the different Aries frameworks are actually interoperable?
Wouldn't it be great to know that not only does an Aries framework
comply with AIP 1.0 and/or AIP 2.0, but that it is demonstrably (and
continuously) tested to ensure interoperability with other Aries
components---that ACA-Py, Aries Framework JavaScript, Aries VCX, and
Aries Framework Go really are interoperable?

To prove an agent or agent framework's support for a given AIP version
and that it plays well with other agents, we need a test suite that lets
us execute tests using agents created from one or more Aries frameworks.
The tests must be defined to exercise the RFCs, and must make it easy to
mix and match the agents being tested. Further, we don't want to run
that test suite just once---we want to run the tests continuously
against the latest codebases so that as the frameworks evolve, they
continue to be interoperable. This is where the Aries Agent Test Harness
comes in. It's an incredibly powerful and useful resource for the Aries
community.

## Aries Agent Test Harness (1)

The vision for the Aries Agent Test Harness (AATH) comes from the
physical labs that the big telecommunication companies use to test their
products. In those labs (like the [UNH InterOperability
Lab](https://www.iol.unh.edu/)), a telecom company brings their
networking products, new and old, plugs them into the lab network, and
sees if they work with products from all of the other participating
companies. Networking products that don't interoperate with the rest of
the network ecosystem create problems for everyone. It's the same with
Aries components in a ToIP ecosystem!

AATH works by having each \"component-under-test\" (e.g., ACA-Py, AFJ,
etc.) packaged as a test agent that looks identical (from the outside)
as all other test agents. In AATH, a component-under-test is usually an
Aries framework, although in theory it could be a full agent (e.g., a
framework plus a controller). Each test agent implements a
\"backchannel\" component that responds to requests from the test
harness that is orchestrating the tests. The backchannel is an Aries
controller that receives test harness requests, and does whatever it
needs to do to cause the component-under-test to execute the request.
Since all the test agents look the same to the test harness, AATH tests
can be run using any combination of test agents.

Each AATH test involves four test agents (called ACME, Bob, Faber, and
Mallory), as shown in the picture below. The test agents are driven by
a [\"Behavior Driven
Development\"](https://www.agilealliance.org/glossary/bdd/) (BDD) engine
(specifically,
the [Behave](https://behave.readthedocs.io/en/latest/) engine) that
orchestrates the test executions. Each test script implements some AIP
capability---a combination of Aries protocols. As noted, since all of
the test agents are (more or less) identical, any test agent can play
any role---limited of course by the capabilities of the
\"component-under-test.\" To make everything easy to run, the test
agents are all packaged into Docker containers.

## Aries Agent Test Harness (2)

The names of the participants in the test scripts imply their usual role
in a verifiable credential ecosystem, although they may perform
activities other than their usual role in some tests.

-   ACME is an issuer

-   Bob is a holder/prover

-   Faber is a verifier

-   Mallory is holder/prover that is sometime malicious

When AATH tests are run, the test agents and BDD engine are deployed and
a list of test scripts to execute is passed into the engine. As
necessary, some supporting services are also started; perhaps a local
instance of an Indy network, or an external universal resolver. Driven
by the test scripts, the BDD engine makes calls (using HTTP) to the test
agent backchannels, triggering interactions between the components under
test using the DIDComm agent-to-agent interface. Progress and results
are reported from the backchannels to the BDD engine, and optionally, to
a test suite execution report tool.

The BDD tests themselves are quite readable and so provide a good
example of the business flows involved in Aries agent interactions. For
example, the following is a test script that executes the \"present
proof\" protocol:

Scenario Outline: Present Proof where the prover does not propose a
presentation of the proof and is acknowledged\
      Given \"2\" agents\
         \| name \| role \|\
         \| Faber \| verifier \|\
         \| Bob \| prover \|\
      And \"Faber\" and \"Bob\" have an existing connection\
      And \"Bob\" has an issued credential from When \"Faber\" sends a
request for proof presentation to \"Bob\"\
      And \"Bob\" makes the presentation of the proof\
      And \"Faber\" acknowledges the proof\
      Then \"Bob\" has the proof verified

      Examples:\
         \| issuer \|\
         \| Acme \|\
         \| Faber \|

The AATH scripts are organized around a protocol that is part of a
particular AIP. Tags are used on tests to both indicate the topic of the
tests (e.g., what RFC, what AIP version, etc.) and to select what tests
are to be executed on a given run.

The AATH approach of using a backchannel to control the
component-under-test should be familiar to you. The backchannel is just
another Aries controller! Each test agent is just a bundling into a
Docker container of a controller (the backchannel) that responds to HTTP
requests from the test harness, and an Aries component-under-test
(usually an Aries framework) that the controller controls.

## Lab: Aries Agent Test Harness

In this lab, we'll look at the Aries Agent Test Harness that can be used
to test the interoperability of two Aries agents.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/AriesTestHarness.md) to
run the lab in GitHub.

## Visualizing Aries Interoperability

While the Aries Agent Test Harness is interesting to know about, how
does it help an Aries developer? Why is it important?

One obvious benefit is that the tests provide a good way to see how
Aries agent interactions occur (by looking at the BDD test scripts) and
how controllers are implemented (by looking at the backchannels). But
other than that, the internals of the AATH is really focused on the
developers of Aries frameworks. Helpful, but
not **[too]{.underline}** helpful.

A second thing you might consider is creating a backchannel for your
full Aries agent. We've not had anyone in the community do this yet, but
it has been considered. It would give you a lot of runnable tests and a
way to run them against other implementations. Interesting, but if you
are building on an existing Aries framework, there shouldn't be any
surprises.

However, there is one absolutely critical output of AATH that is a
must-use resource for all Aries developers. The AATH repo has a series
of automated test sets (via GitHub actions) that are executed daily for
all of the available backchannels using (usually) the latest code merged
into the \"main\" branch of each \"component-under-test.\" The results
of those runs are collected using a BDD test reporting tool
([Allure](https://github.com/allure-framework/allure2) --- pretty neat!)
and a summary report is generated that is published on the [Aries
Interoperability Test Results](https://aries-interop.info/) website
every few days (whenever the results change).

![](images/image016.png){width="7.0in"
height="5.210457130358705in"}

**Screenshot of
the [https://aries-interop.info](https://aries-interop.info/) website**\
Licensed under [CC By 4.0](https://creativecommons.org/licenses/by/4.0/)

By monitoring the Aries Interoperability Test Results website, you can
track:

-   Current state of interoperability across a number of Aries
    frameworks (most importantly, the current state of interoperability
    of the Aries framework that you are using).

-   You can see what specific tests are passing and failing. Are they
    going to impact you?

-   You can drill into the test results and see exactly where the
    failures are occurring. Perhaps you can contribute a fix?

-   You can see areas that are *not* being tested. Perhaps you could
    contribute some test cases to AATH!

-   You can see how new protocols and AIP versions are progressing
    across Aries implementations. This will tell you, for example, is
    AIP 2.0 ready to use in the wild?

## Lab: The Aries Interop Info Website

In this lab, you will check out the Aries Interop Info website, learn
how to navigate beyond the front page and use the Allure reports to
drill into specific test cases. We'll try to find some test failures and
see exactly where and why they are failing.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/AATHInfo.md) to
see instructions for this lab in GitHub.

## The Mobile Backchannel

The last thing we'll mention about the AATH is a cool backchannel that
can be used to test mobile wallet apps. The \"mobile\" backchannel
operates the same as all of the other backchannels, except the
\"component-under-test\" is intended to be an Aries mobile wallet
running on a physical phone. The backchannel is limited, as the only way
the backchannel can "control" the mobile wallet is by printing
directions for you (the person holding the phone) and displaying QR
codes for connecting the mobile wallet to the other test agents being
run. Once connections are made, the actions of the other agents drive
the behavior of the mobile wallet. Only some of the AATH tests can be
run, and the mobile agent is \"Bob\" in all the tests.

The beauty of the \"mobile\" backchannel is that you can download a
mobile wallet app onto your phone and immediately run it against issuers
and verifiers using different Aries frameworks, no muss, no fuss! It's
also pretty cool how the QR codes are displayed on a terminal screen. Of
course, they are pretty low resolution, so if the mobile wallet's scan
feature can't handle the QR code, you are pretty well stuck.

On the next page, you will find a quick lab to give that a try.

## Lab: The AATH Mobile Backchannel

In this lab, you will use AATH, the mobile backchannel and one of the
other backchannels to test the interoperability of an Aries mobile
wallet. Get out your favorite mobile wallet app and give it a try!

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/AATHMobileBackchannel.md) to
see instructions for this lab in GitHub.

## Aries Mobile Test Harness

One more thing about mobile wallet testing. In addition to the mobile
backchannel in the Aries Agent Test Harness, the Aries community has
also built the [Aries Mobile Test
Harness](https://github.com/hyperledger/aries-mobile-test-harness) (AMTH).
AMTH is conceptually similar to AATH and even uses AATH Test Agents in
executing tests. However, it is focused entirely on automating the
testing of Aries mobile wallets and for that, it uses a 3rd party mobile
device testing service that enables access to hundreds of mobile
devices. If you are building and publishing an Aries mobile wallet,
you'll want to check it out!

## Chapter 2 Summary

This chapter focused on the Aries ecosystem (the way Aries is used in
the real world), the Aries agent architecture (the components that make
up an Aries agent), and how an Aries agent functions. We looked at
examples of Aries agents, namely Alice and Faber College, and you
stepped through a demo to verify, hold and issue verifiable credentials.
We mentioned, but didn't spend a lot of time on routing agents
(mediators and relays). We'll cover them in more detail later in the
course. Next, we described the Aries agent architecture, discussing
an agent framework, its controller and how the two work together.

We looked at the core of Aries, the protocols, and how Aries Interop
Profiles are used to provide certainty for developers looking to build
Aries agents that will interoperate with Aries agents built by others.
We surveyed the current landscape of open source Aries frameworks, and
the range of approaches that are available to Aries developers. There
are lots of options! We also showed you the Aries Agent Test Harness
that is executed daily by the community and whose output you can review
to see the evolving state of Aries interoperability across the
frameworks.

The main takeaway from this chapter is that as a developer, you will
most likely be building your own controller, which will give your agent
the business rules it needs to follow depending on your agent
implementation. This is true regardless of the Aries framework upon
which you plan to build your controller.

You might have noticed in the \"Agents Connecting\" lab, there was no
mention of a distributed ledger. That's right, Aries agents can provide
messaging capabilities without any ledger at all! Of course, since the
main reason for using an Aries agent is to exchange verifiable
credentials, and verifiable credential exchange requires a ledger, we'll
look at ledgers in the next section.

## Chapter 3 Overview -- Running a Network for Aries Development

In the last chapter, we learned all about the Aries agent architecture
and the key components of an agent: the controller and framework. We
also discussed common setups of agents and some basics about messaging
protocols used for peer-to-peer communication. The labs in Chapter 2
demonstrated connecting two agents that didn't use a ledger. Now that
you're getting comfortable with what an agent does and how it does
it---and have seen agents that work off-ledger---let's set the
groundwork for using a distributed ledger for your development needs.
We'll even look at some alternatives to using a ledger.

## Learning Objectives

In this chapter, we will describe:

-   What you need to know and *not* *know* about ledgers in order to
    build an SSI application.

-   How to get a local Indy network up and running, plus other options
    for getting started.

-   The ledger's genesis file---the file that contains the information
    necessary for an agent to connect to a specific ledger.

## What You Don't Need to Know

Many people come to the Hyperledger Aries and Indy communities thinking
that because the projects are \"based on blockchain,\" that the most
important thing to learn first is about the underlying blockchain. Even
though their goal is to build an application for their use case, they
dive into Indy, finding the guide on starting an Indy network and off
they go---bumping their heads a few times on the way. Later, when they
discover Aries and what they really need to do (build a controller,
which is really, just an app with APIs), they discover they've wasted a
lot of time.

Don't get us wrong. The ledger is important, and the attributes
(robustness, decentralized control, transaction speed) are all key
factors in making sure that the ledger your application will use is
sufficient. It's just that as an Aries agent application developer, the
details of the ledger are *someone else's problem*. There are three
situations in which an organization producing self-sovereign identity
solutions will need to know about ledgers:

-   If your organization is going to operate a ledger node (for example,
    a steward on the Sovrin network), the operations team needs to know
    how to install and maintain that node. There is no development
    involved in that work, just the operation of a software artifact.

-   If you are a developer who is going to contribute code to a ledger
    project (such as Indy) or contribute an interface to a ledger not
    yet supported by Aries, you need to know about the development
    details of that ledger.

-   If you are building a product for a specific use case, the business
    team must select a ledger that is capable of supporting that use
    case. Although there is some technical knowledge required for that,
    there is little developer knowledge needed---it's more of a business
    question.

So, assuming you are here because you are building an application, the
less time you spend on ledgers, the sooner you can get to work on
developing that application. For now, skip diving into Indy and use the
tools and techniques outlined here. We'll also cover some additional
details about integrating with ledgers in Chapter 8, \"Planning for
Production\", later in this course.

With that, we'll get on with the minimum you have to know about ledgers
to get started with Aries development. In the following, we assume you
are building an application for running based on a Hyperledger Indy
ledger.

## Distributed Ledgers (1)

Before we go further in this chapter, let's go back to the basics and
cover the purpose of a distributed ledger when using Aries. For Aries
agents that comply with Aries Interop Profile (AIP) 1.0 and 2.0, the
primary purpose of the ledger is a place for a verifiable credential
issuer to publish cryptographic keys and credential metadata so that a
holder can produce a presentation that a verifier can cryptographically
verify. In theory, such information could be digitally published in
other ways, but the attributes of a ledger are ideal for this purpose:

-   Data written to a distributed ledger is immutable---it can't ever be
    changed.

-   Ledger data can't be removed, so, for example, the issuer cannot
    remove the data (public keys and credential metadata) and \"break\"
    (make unverifiable) credentials issued to holders.

-   Multiple parties (that is, validators or miners) reach consensus on
    what is to be written to a ledger, preventing the data from being
    maliciously altered before writing.

-   The data is replicated across a set of independent parties and as
    such is highly available.

**NOTE:** Always remember that with verifiable credentials in general,
and specifically with Aries, no private data goes on the ledger, and the
data written to the ledger is extremely limited to the verifiable
credential use case. Credentials are NEVER written to the ledger.

That discussion covers why distributed ledgers are commonly used for
verifiable credential implementations such as Aries. However, publishing
DIDs and other data for issuing credentials need not always be to a
distributed ledger. There are DID methods that publish to other than
distributed ledgers that could also be used, such as did:web (publishing
files to a web server) or did:dns (publishing DID data to DNS records).
They too can be used as verifiable data registries---albeit with a loss
of some of the important characteristics of ledgers listed above. The
important point is that the objects (DIDs, and AnonCreds objects) must
be resolvable by anyone that might receive the URL for the object. It's
not enough that the object is published somewhere, it is also required
that the object be resolvable given just the URL for the object.

The following are some methods for publishing DIDs that you might run
into when doing Aries development:

-   The [\"did:web\" DID
    method](https://w3c-ccg.github.io/did-method-web/) is a non-ledger
    alternative for an organization to publish DIDs at a known place on
    their web server. Publishing things like public keys on a web server
    is a [common
    practice](https://en.wikipedia.org/wiki/Well-known_URI), with
    organizations often putting the files in the path **/.well-known/**.
    Almost every organization has a web server, so using it as a place
    to store DIDDocs that can be resolved is a pretty logical approach.\
    - The problem with this approach is that it is easy for the
    organization to remove the data at any time, breaking the
    \"immutability\" goal for verifiable credentials. Once the data is
    removed, any presentations referencing that data can no longer be
    verified.

-   A developer might use the [\"did:github\" DID
    method](https://github.com/decentralized-identity/github-did/blob/master/docs/did-method-spec/index.md) as
    a quick'n'dirty way to publish a DID for development purposes.\
    - Like \"did:web,\" the DID is not immutable and implies even less
    trust than \"did:web,\" but for development purposes it might be
    useful.

-   A DID method developed by Gen Digital (formerly SecureKey), the
    maintainers of [Aries Framework
    Go](https://github.com/hyperledger/aries-framework-go), is
    the [\"did:orb\" DID
    method](https://trustbloc.github.io/did-method-orb/) which uses a
    protocol called ActivityPub (and other technologies) to enable an
    entity to publish their DIDs in a trusted way without requiring a
    distributed ledger. ActivityPub is the protocol that drives
    Mastodon, so you know it's rock solid.

You will also run into Indy DIDs, did:key and did:peer both during
development and elsewhere in this course.

## Distributed Ledgers (2)

There are a lot of other DID methods defined in the W3C DID Standard
registry. In theory, for verifiable credential purposes, any of them
could be used, but we recommend when deciding what DID methods to use,
you do some research on the DID methods to gain confidence that they
will still be around in a few years. Some of the more interesting DID
methods (beyond Hyperledger Indy) are ones that are rooted in the major
permissionless blockchains such as Bitcoin and Ethereum, as well as ones
built on private blockchains such as Hyperledger Fabric.

If you are using AnonCreds verifiable credentials, there is another
caveat. With AnonCreds it is not (currently) enough that DIDs be
published by issuers. Issuers also need to have a way to publish
AnonCreds objects. As of this writing (January 2023), the concept of
\"AnonCreds methods\" (analogous to \"DID methods\") is beginning, and
there are only a couple of implementations, such as one using
the [cheqd.io](https://cheqd.io/) network. We expect that in 2023 more
will be added, and when you are researching, you'll want to find out
what your options are.

While the published DIDs and other objects on a ledger are mostly used
for the processing of verifiable credentials and verifiable
presentations, the public DIDs can also be used for connecting and
messaging with an organizational Aries agent. Some organizations use a
public DID as the basis for all their connections with other agents,
instead of using peer DIDs for that purpose.

We'll touch on the use of other DID methods later in this chapter. For
now though, we'll focus on running (or not) an Indy network that we'll
use for labs in the later chapters.

## Using von-network

The easiest way to get a local sandbox Indy network running is to
use [von-network](https://github.com/bcgov/von-network), a pre-packaged
Indy network built by the Government of British Columbia's (BC) [Digital
Identity and Trust](https://digital.gov.bc.ca/digital-trust/) team. In
addition to providing a way to run a minimal four-node Indy network
using Docker containers with just two commands, von-network includes:

-   A well maintained set of versioned Indy container images.

-   A web interface allowing you to browse the transactions on the
    ledger.

-   An API for accessing the network's genesis file (see **[\"The Indy
    Genesis File\"]{.underline}** section later in the chapter).

-   A web form for registering DIDs on the network.

-   Guidance for running a network instance in a cloud service such as
    Amazon Web Service or Digital Ocean.

The [VON container
images](https://hub.docker.com/r/bcgovimages/von-image/) maintained by
the BC Gov team are updated with each release of Indy, saving others the
trouble of having to do that packaging themselves. A lab focused on
running a von-network instance will be provided at the end of this
chapter.

## Or, Don't Run a Network for Aries Development

What is easier than running a local network with von-network? How about
not running a local network at all!

Another way to do development with Indy is to use a public Indy network
sandbox. When using that model, each developer doesn't run their own
local network, they access one that is running remotely. Using this
approach, you can run your own, or even easier, use someone else's, such
as the BC Government's BCovrin (pronounced \"Be Sovereign\") networks
(dev and test). As of writing this course, the networks are open to
anyone to use and are pretty reliable (although no guarantees!). They
are rarely reset, so even long lasting tests can use a BCovrin network.
They are only for testing---definitely don't rely on them for production
work!

![Bulb](images/image017.png){width="1.0in"
height="1.2834787839020123in"}

An important thing that an Aries developer needs to know about using a
public sandbox network is to make sure you create unique objects
on *every* run by making sure issuer DIDs are different on every run. To
get into the weeds a little:

-   Indy DIDs are created from a seed, an arbitrary 32-character string.
    A given seed passed to Indy for creating a DID will always return
    the same DID, public key and private key.

-   Historically, Indy/Aries developers have configured their apps to
    use the same seeds in development so that the resulting DIDs are the
    same every time. This works if you restart (delete and start fresh)
    the ledger and your agent storage on every run, but causes problems
    when using a long lasting ledger.\
    - Specifically, a duplicate credential definition (same DID, name
    and version) to one already on a ledger will fail to be written to
    the ledger, causing your application to fail.

-   The best solution is to configure your app so a randomly generated
    seed is used in development such that the issuer's DID is unique on
    every run. That way the credential definition name and version can
    remain the same on every run, but the DID and credential definition
    identifier will always be different.

**NOTE**: This is important for development. We'll talk about some
issues related to going to production in Chapter 8, Planning for
Production, where the problem is reversed---we MUST use the same DID and
credential definition every time we start an issuer agent.

In the labs in this course, you will see examples of development agents
running against both local and remote sandbox Indy networks.

## Proof of Concept Networks

When you get to the point of releasing a proof of concept (PoC)
application \"into the wild\" for multiple users to try, you will want
to use an Indy network that all of your PoC participants can access,
including those using third party mobile wallet apps. You will also want
that environment to be stable such that it is always available when it's
needed---we all know about how mean the demo gods can be---and
comparable to the production environment you plan to use.

Some of the factors related to production applications (covered
in **[Chapter 8, Planning for Production]{.underline}**) will be
important for a PoC. A locally running network is not really viable, so
you best run a publicly accessible network. For that, you have three
choices:

1.  The BCovrin sandbox test network is available for long term testing
    and is supported by many of the better known mobile wallet apps.

2.  Operators of public Indy networks (such as Sovrin and Indicio) offer
    production and pre-production networks for testing, proof of
    concepts, demos, and other non-production use cases.

3.  You may choose to run your own network on something like Amazon Web
    Service or Azure. Basically, you would be running your own version
    of \"BCovrin.\"

We've used the term \"sandbox\" a few times above. An Indy sandbox
network is one that is wide open such that everyone can write to it.
When you transition from using a sandbox to permissioned Indy test and
production networks, you will have two additional requirements.

-   As a transaction author, you indicate in your transactions that you
    agree to a legal agreement (much like an End User License Agreement)
    posted by the network owner.

-   Your DID on the network must either be a permissioned \"Endorser\"
    DID, or you must find an Endorser that will sign (\"endorse\") your
    transactions for you.

We'll cover these issues a bit in the next section of this chapter and
in **[Chapter 8, Planning for Production]{.underline}**.

Running your own network gives you the most control (and is pretty easy
if you use [von-network](https://github.com/bcgov/von-network)), so that
might seem at first glance to be the preferred option. However, that
means extra work for you in maintaining the network. If you need to
interoperate with agents from other vendors (such as mobile wallet
apps), the distributed ledger you choose must be one that is supported
by those other agents. Those requirements often make either or both of
the BCovrin and public networks as the best/only options.

## What Is a Genesis File?

In working with an Indy network, the ledger's **[genesis
file]{.underline}** contains the information necessary for an agent to
connect to that ledger. Developers new to Indy, particularly those who
try to run their own network, often have trouble with the genesis file,
so we'll cover it here.

The genesis file contains information about the physical endpoints (IP
addresses and ports) for some or all of the nodes in the ledger pool, as
well as the cryptographic material necessary to securely communicate
with those nodes. Each genesis file is unique to its associated ledger
and must be available to an agent that wants to connect to the ledger.
It is called the genesis file because it has information about the
genesis (first) transactions on the ledger. Recall that a core concept
of blockchain is that the blocks of the chain are cryptographically tied
to all the blocks that came before it, right back to the first (genesis)
block on the chain.

The genesis file for Indy **[sandbox]{.underline}** ledgers is (usually)
identical, with the exception of the endpoints for the ledger---the
endpoints must match where the nodes of the ledger are physically
running. The cryptographic material is the same for all sandbox ledgers
because the genesis transactions are all the same, generated from the
same seeds. Those transactions:

-   Create a trustee **[endorser]{.underline}** DID on the ledger that
    has full write permission on the ledger.

-   Permission the nodes of the ledger to process transactions.

Thus, if you get the genesis file for a ledger and you know the
\"magic\" seed for the DID of
the [**[trustee]{.underline}**](https://docs.google.com/document/d/1gfIz5TT0cNp2kxGMLFXr19x1uoZsruUe_0glHst2fZ8/edit#heading=h.xs7z6weav1fw) (the
identity owner entrusted with specific identity control responsibilities
by another identity owner or with specific governance responsibilities
by a governance framework), you can access and write to that ledger.
That's great for development and it makes deploying proof of concepts
easy. Configurations such as von-network take advantage of that
consistency, using the "magic" seed to bootstrap the agent. For agents
that need to write to the network (at least credential issuers, and
possibly others), there is usually an agent provisioning step where the
endorser DID is used to write a DID for the issuer that has sufficient
write capabilities to do whatever else it needs to do. This is possible
because the seed used to create the endorser DID is well known. In case
you are wondering, the magic seed is:

**000000000000000000000000Trustee1**

***NOTE***: For information about this, see this [***great
answer***](https://stackoverflow.com/questions/59089178/hypelerdger-indy-node-seed-value) on
Stack Overflow about where it comes from.

![Bulb](images/image017.png){width="1.0in"
height="1.2834787839020123in"}

By the way, the typical problems that developers have with genesis files
is either they try to run an agent without a genesis file, or they use a
default genesis file that has not had the endpoints updated to match the
location of the nodes in their network. It's part of why using
von-network is so helpful; it takes care of those details for you,
dynamically making the genesis file available to you based on how the
network was started.

As we'll see in *Chapter 8, Preparing for Production*, the steps are
conceptually the same when you go to production---you use a *transaction
endorser* that has network write permissions to create your DID.
However, you'll need to take additional steps when using a permissioned
test or production ledger (such as the Sovrin Foundation's TestNet or
MainNet) because you won't know the seed of any endorsers on the
network. Connecting to and reading from a production ledger is just as
easy as a sandbox ledger---you get the network's genesis file and pass
that to your agent. However, being able to write to the network is more
complicated because you don't know the \"magic DID\" that enables full
write access.

## Genesis File Handling in Aries Frameworks

Most Aries frameworks make it easy to pass to the agent the genesis file
for the network to which it will connect. For example, we'll see from
the labs in the next chapter that to connect an instance of an ACA-Py
agent to a ledger you use command line parameters to specify either a
file name for a local copy of the genesis file, or a URL that is
resolved to fetch the genesis file. The latter is often used by
developers that use the von-network because each von-network instance
has a web server deployed with the network and provides the URL for the
network's genesis file. The file is always generated after deployment,
so the endpoints in the file are always accurate for that network.

## Lab: Running a von-network Instance

Please follow this [GitHub
link](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/vonNetwork.md) to
run a lab in which you will start a von-network, browse the ledger, look
at the genesis file and create a DID.

## Accessing Multiple Indy Networks

In the \"genesis file\" discussions before the lab we talked about
loading *\"the\"* genesis file for an Aries agent deployment, allowing
the agent to connect with, read and possibly write to a single Indy
ledger instance. However, as more production networks become available,
and Aries agents (especially Aries mobile wallet apps) are used in
different use cases, it is obvious that Aries agents must be able to
access more than one ledger at a time. A person might be issued
verifiable credentials from a university using the Sovrin MainNet, and a
government using a government managed network, and it all has to work
smoothly.

There are two solutions to this. Aries frameworks support the idea of
using multiple ledgers. For issuers agents one of those ledgers can also
be designated for writing. Aries agents can be configured to load
genesis files for, and connect to, all needed Indy networks. While an
issuer agent will likely only write to one of the networks, when
resolving a given Indy identifier (a DID or ledger object ID), the agent
will check for the object on each of the connected networks. The process
has proven to work pretty well, with the caveat that the resolver might
find the same object on multiple networks and so need some form of
collision handling if the object is on more than one ledger.

A future evolution of this approach has been defined that uses a new
did:indy DID method (covering AnonCreds objects as well) that embeds in
all Indy identifiers (DIDs and AnonCreds objects) a reference to the
ledger on which the object resides, eliminating both the need to check
on multiple ledgers and the possibility of a collision (the same object
on multiple ledgers).

The good news for you, the Aries developer, is that for the most part,
the complexity of connecting to and resolving objects on multiple Indy
ledgers will be handled by the Aries framework you are using. You have
to decide what ledgers you want to use, but all the details about using
the ledgers after that are handled by Aries.

## The DID Resolution Process

As discussed earlier in this chapter, Indy is not the only ledger around
and Indy DIDs are not the only DIDs used in Aries. In this section,
we'll cover how Aries handles other ledgers and DID methods.

As you (should) know by now, DIDs are resolved in a similar fashion to
web URLs, returning a DID document (DIDDoc) instead of a web page.
Rather than a single DNS-based process for finding the resource
associated with a URL, DID identifiers embed a reference to a *DID
method* in each DID. In turn, each DID method has an associated
specification that is implemented in software to resolve the DID and
find the associated DIDDoc. This picture below shows the DID resolution
process.

An application (such as an Aries agent) needs to resolve a DID. They
call a resolver (\"Universal Resolver\" in the picture below), which
figures out what DID method is being used. Remember that the DID method
is included as part of the DID, right after the \"did:\" prefix. From
that, the resolver decides on the driver to use---there's usually a
driver per DID method---and the selected DID method knows how to
interact with the distributed ledger (or other storage location) to get
and return the DIDDoc associated with the DID.

![The DID Resolution Process](images/image018.png){width="5.0in"
height="2.812325021872266in"}

**The DID Resolution Process**\
Licensed under [CC BY
4.0](https://courses.edx.org/xblock/%E2%80%9Chttps:/creativecommons.org/licenses/by/4.0/%E2%80%9D)

This all sounds good, until you realize that the current (January
2023) [W3C DID
Registry](https://w3c.github.io/did-spec-registries/#did-methods) contains
158 DID methods and the list may still grow. With each having their own
DID method specification, that means a **[universal DID
resolver]{.underline}** that can resolve every DID method must support
158 drivers. This is exactly what the open source **[DIF universal
resolver]{.underline}** does (more or less). Each organization that adds
a DID method to W3C DID Method Registry may also implement a driver for
their DID method and add it to the DIF universal resolver. An instance
of the universal resolver is deployed by DIF as a central web service
with APIs that can be used for resolving (in theory, at least) any DID
that has been published. And anyone else can deploy their own version of
a universal resolver.

That paragraph leads us to a couple of editorial comments:

-   First, not all 158 (and counting!) DID methods will last. The
    general expectation of the community is that a handful of DID
    methods will survive and the rest will quietly fade away.

-   Second, while an interesting and useful tool for developers,
    a **[centralized]{.underline}** web service such as the DIF
    universal resolver is not a particularly strong foundation on which
    to build a scalable, production layer of trust for the Internet.
    What if that central service is hacked? There's a safer way.

Let's look at how DID resolution is handled in Aries.

## Aries DID Resolvers

Within Aries frameworks is a generic \"resolveDID\" call that takes DIDs
of any method and returns (if available) a DIDDoc for the DID via a set
of resolver plugins. The call determines the DID's method and checks if
there is a resolver plugin available for that DID method. If so, the
resolver plugin is called and the result returned; if not, the
resolution fails. The term \"plugin\" is used loosely here; plugins
might be either added at compile time or loaded at runtime depending on
the framework. Either way, a generic interface to the resolver is used.
Each supported DID method is handled in one of two ways:

-   The resolver may be a local plugin run within the Aries deployment.

-   The resolver might be part of an external \"universal resolver.\"

![Aries Agent DID Resolution: Local and
External](images/image019.png){width="5.0in"
height="3.792250656167979in"}

**Aries agent DID resolution: local and external**\
Licensed under [CC BY
4.0](https://courses.edx.org/xblock/%E2%80%9Chttps:/creativecommons.org/licenses/by/4.0/%E2%80%9D)

 The idea (shown in the diagram above) is that an Aries implementation
will have a number of fast, local instances for commonly used DIDs (in
this case, \"did:sov\", \"did:peer\", \"did:key,\" and \"did:web\") and
fallback to a universal resolver for \"obscure\" DIDs that it might need
to support. The fallback \"universal resolver\" could be the public DIF
universal resolver (although that's not recommended for production), or
more likely, a local deployment of the DIF universal resolver, including
only the drivers needed for DID methods of interest.

Using such an approach, an Aries deployment can have an easily
configured policy on what DIDs to resolve (or not) and how---via a
built-in plugin and external resolver.

The built in DID resolvers in Aries are likely \"did:peer,\" \"did:key\"
and the ledger that the Aries deployment writes to, such as an Indy
ledger. Aries implementations that don't support Indy, such as those
based on Aries Framework Go, will likely have favored DID methods and
use an external DID resolver for Indy DIDs.

## The did:key DID Method

A special DID method that we haven't talked about yet but that deserves
mention is \"did:key.\" did:key is similar to did:peer in that it is not
a DID that is published on a ledger. Rather, it is a way to represent a
single, public key as a DID. It's not as capable as a did:peer (for
example, a did:key cannot have an endpoint, and its key cannot be
rotated), but it is useful in a number of Aries RFCs.

The details of using the did:key method are provided in the did:key
specification, but the quick version is as follow:

-   Create a key pair of a known key type (e.g., Ed25519).

-   Encode (using standards \"multibase\" and \"multicodec\" per the
    did:key specification) the public key and its type, and then prefix
    the result with \"did:key:\" to create a DID that looks like
    this: **did:key:z6MkpTHR8VNsBxYAAWHut2Geadd9jSwuBV8xRoAnwWsdvktH**

-   To \"resolve\" the DID, reverse the encoding (e.g., remove the
    \"did:key:\" prefix and decode the multibase/multicodec string) to
    get back the public key and its type.

-   Generate a DIDDoc by merging the three data values (the DID, public
    key and signature type) into a fixed template.\
    - Where possible, such as with an Ed25519 verification key, generate
    a key agreement key (for encryption) from the verification key and
    include in the DIDDoc a key agreement block.\
    - Here's a link to a [sample did:key
    DIDDoc](https://dev.uniresolver.io/#did:key:zDnaerDaTF5BXEavCrfRZEk316dpbLsfPDZ3WJ5hRTPFU2169).

Although the did:key template process is based on some pretty simple
text processing, the representation is powerful, allowing an otherwise
plain old public key string to be handled in the same way as any other
DID.

## Lab: Aries and Universal DID Resolvers

Enough on DID resolution, let\'s try some hands-on resolving.

Please follow
this [link](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/didResolvers.md) to
run a lab in which you try out a couple of DID resolvers, including one
built into an instance of ACA-Py.

## DID Registration

Before we wrap up DID resolving, we need to briefly mention DID
registration, the operation of creating and publishing a DID. While each
Aries deployment will generally only publish DIDs to one place,
different deployments will choose to publish to different places, and
Aries frameworks need to enable such diversity. As such, the approach
taken in Aries frameworks for DID registration is conceptually the same
as for DID resolution. A generic \"registerDID\" call is made that in
turns determines what type of DID is to be registered and uses a plugin
to actually create and publish the DID. The interface and plugin are
more complicated to register a DID vs. resolving because of the extra
information needed for the registration, information that might be DID
method specific. However, the concept is the same.

## Writing and Reading the AnonCreds Objects

With the creation of the Hyperledger AnonCreds project in late 2022, and
its focus on creating an implementation of AnonCreds that is not
dependent on Hyperledger Indy, but instead is ledger-agnostic (or more
precisely, VDR-agnostic), the same resolver and registrars' capabilities
are needed for AnonCreds methods as are needed for DID methods. Aries
agents using AnonCreds must be able to write (register) and read
(resolve) the four AnonCreds objects (schemas, credential definitions,
revocation registry definitions and revocation registry entries) based
on their identifiers. The goal in the Aries frameworks is to create the
same abstract interfaces for resolving and registering AnonCreds
objects, with implementation of specific AnonCreds methods, and
possibly, a call out to a universal AnonCreds resolver and/or registrar.

From the Aries developer perspective, you will be able to configure your
Aries issuer agent to use a specific AnonCreds registrar, that creates
the AnonCreds objects on your ledger of choice. Further, you will be
able to configure your Aries issuer, holder, and verifier agents to
resolve AnonCreds objects based on the object identifiers embedded in
the data (credentials, presentations, etc.) that your agent processes.
Your configuration will likely have one or more local AnonCreds methods
for commonly handled/expected VDRs, and perhaps a callout to an
external, universal resolver for retrieving other AnonCreds object
identifiers.

## Chapter 3 Summary

The main point of this chapter is to get you started in the right spot:
you don't need to dig deep into distributed ledger technology in order
to develop SSI applications. By now, you should be aware of the options
for running an Indy network and know the importance of the genesis file
for your particular network. We also covered some of the new options for
publishing DIDs to other than a Hyperledger Indy network. If you are
using AnonCreds, you may want to stick to using an Indy network, but
other options are on the way for that as well. Finally, we went over a
powerful DID method that doesn't use a ledger at all and makes plain
public keys way more useful, the \"did:key\" DID method.

In the last chapter, we covered the architecture of an agent and
demonstrated connecting two agents that didn't use a ledger. In this
chapter, we covered running a ledger. So, in the next chapter, let's
combine the two and look at running agents that connect to a ledger.

## Chapter 4 Overview -- Developing Aries Controllers

In the second chapter, we ran two simple command line agents that
connected and communicated with one another. In the third chapter, we
went over running (or not) a local ledger for development. In this
chapter, we'll go into details about how you can build a controller by
running agents that connect, communicate and use a ledger to enable the
issuing of credentials and the presentation of proofs. For developers
wanting to build applications on top of Aries and Indy, this chapter is
the core of what you need to know and is presented mostly as a series of
labs.

We will learn about controllers by looking at [Aries Cloud Agent
Python](https://github.com/hyperledger/aries-cloudagent-python) (ACA-Py)
in all the examples. Don't worry if you are not a Python guru as with
ACA-Py, a controller can be written in any language. ACA-Py is not
suitable for use as a mobile wallet app, so we'll leave the wallet
discussion until Chapter 7. In the last section of this chapter, we'll
cover controllers for other Aries open-source frameworks. As you'll
discover, the concepts are pretty much the same across the frameworks.

## Learning Objectives

In this chapter (4), you will learn:

-   What an agent needs to know at startup.

-   How protocols impact the structure and role of controllers.

-   About the aries-cloudagent-python (ACA-Py) framework versus other
    Aries frameworks (such as aries-framework-javascript and aries-vcx).

The goal of this chapter is to give you the knowledge you'll need to
build your own controller using the framework of your choice. Succeed
and you'll be an Aries developer!

## Defining \"Wallet\"

In the prerequisite course, [*\"Introduction to Hyperledger
Self-Sovereign Identity Blockchain Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa),
we defined the term \"wallet\" to be a mobile application that is like a
physical wallet, holding money, verifiable credentials and important
papers. This is the definition the Aries
community **[mostly]{.underline}** uses. Unfortunately, the term has
historically had a second meaning in the Indy community, and it's a term
to which developers in Aries (and Indy) are still exposed. In Indy
source code, the term \"wallet\" refers to the secure storage
(introduced in Chapter 1) part of any agent, the place where DIDs, keys,
ledger objects and credentials are stored.

So, while the old Indy definition of wallet is being eliminated in
Aries, its use in some existing Indy components that are called from
current Aries code means that as an Aries developer, you will sometimes
see the word \"wallet\" used to mean \"secure storage.\" In the course
materials, we'll always use the term \"secure storage\", and reserve
\"wallet\" for a mobile application for holding verifiable credentials
and other things. However, be aware that in some of the labs, Aries
documentation and source code, you might see the old meaning used in
places.

## What Configuration Information Is Needed

An Aries agent needs to know a lot of configuration information as it
starts up. For example, it needs to know:

-   The location of the genesis file(s) for the ledger(s) it will use
    (if any).

-   If it needs objects (DIDs, schema, etc.) on the ledger, checking
    that they exist on ledger and in secure storage, and creating those
    objects if they don't exist.

-   Transport (such as HTTP or web sockets) endpoints for messaging
    other agents.

-   Storage options for keys and other data.

-   Interface details between the agent framework and the controller for
    events and requests.

These are concepts we've talked about earlier and that you should
recognize. Need a reminder? Checkout the \"Aries Agent Architecture\"
section of Chapter 2. We'll talk about these and other configuration
items in this chapter and the next.

## Command Line Parameters

All Aries agent frameworks will have a number of configuration options
that must be set to deploy an instance in a specific scenario. At
minimum, the agent must know about things such as how to access a
database for secure storage, how to connect to ledgers, the HTTP
addresses for interacting with the controller, and so on. One of the
first things you'll need to know is how to set the configuration options
for your agent, and unfortunately, it can be daunting! As of this
writing (January 2023), there are 112 ACA-Py startup options! So getting
a handle on startup options is your first Aries developer task. Let's
look at how ACA-Py deals with agent configuration and try to make sense
of the options.

We'll start with a bit of good news. Most of the configuration settings
have default values, so that if you don't set the options, reasonable
defaults get set in the code. As such, many of the settings need not be
set at all.

ACA-Py can be configured via command line options in the form
of **\--option \<extra info\>**. For example, to specify the name of the
genesis file the agent is to use, the command line option
is **\--genesis-file \<genesis-file\>**. The number (oh, so many!!!) of
startup options and the frequency with which new options are added
require that ACA-Py be self-documenting---you run ACA-Py to get its list
of options. In fact, ACA-Py must be self-documenting, since plugins to
ACA-Py (added via command line options, of course!!) can add new
configuration options at runtime. As such, the **\--help** option is
your friend! Use it to get the list of all of the startup options for
running the instance of ACA-Py you are using.

In addition to using command options, ACA-Py provides two other ways to
configure an instance:

-   Each command line option has a corresponding environment variable
    that can be used for configuring ACA-Py. For example, instead of
    using the command line option, **\--genesis-file \<genesis-file\>**,
    the environment variable **ACAPY_GENESIS_FILE** can be set
    to **\<genesis-file\>** before running the command to have the same
    effect. The **\--help** information lists the environment variable
    to use for each option. Thus, a way to configure an ACA-Py instance
    is to create a shell script that sets environment variables as
    needed and then invokes ACA-Py. To start an instance of ACA-Py, run
    the shell script.

-   A YAML configuration file can also be used to set any and all of the
    command line options. The following is a minimal YAML file that sets
    the genesis file for an instance of ACA-Py, including a comment to
    document why the option is being used: **\# Use the Indy BCovrin
    Test genesis file: genesis-file:
    http://test.bcovrin.vonx.io/genesis**. When starting ACA-Py, use the
    command line option **\--arg-file \<yaml-file-name\>** and the
    entries in the YAML file will be processed as their command line
    option equivalents. YAML files are usually the best way to manage
    and centrally document the settings being used for an ACA-Py
    instance, perhaps combined with a simple shell script that wraps the
    instance invocation.

You can mix and match the configuration settings using all three of the
techniques. If you do, the order of precedence is command line options
override environment variables override YAML file values override code
defaults. This is shown in the image below. ACA-Py uses the (pretty
cool!) ConfigArgParse library to handle arguments.

![Override Order When Specifying
Options](images/image020.png){width="2.0in"
height="2.827225503062117in"}

**Override order when specifying options**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## The provision and start Options

A basic ACA-Py agent is a stateful component that persists data in its
secure storage and as needed, to a ledger. When an agent starts up for
the first time, it has no persistent storage and so it must create a
secure storage database, and then any ledger objects it will need to
fulfill its role. When we're developing an agent, we can do that over
and over: start an agent, create its state, test it, stop it and delete
it. However, when an agent is put into production, we only initialize
its state once. We must be able to stop and restart it such that it
finds its existing state, without having to recreate its secure storage
database and content from scratch.

Because of this requirement for a one time \"start from scratch\" and a
many times \"start with data,\" ACA-Py provides two major modes of
operation: \"provision\" and \"start.\" \"provision\" is intended to be
used one time per agent deployment to establish its secure storage
database and the required ledger objects. This mode may also be used
later when something new needs to be added to the secure storage and
ledger, such as an issuer deciding to add a new type of credential they
will be issuing. \"start\" is used for normal operations and assumes
that everything is in place in secure storage and on ledger. If it finds
things aren't as expected, it should error and stop---an indicator that
something is wrong.

![Cook](images/image021.png){width="2.0in"
height="2.17872375328084in"}

The \"provision\" and \"start\" separation is done for security and
ledger management reasons. Provisioning a new secure storage database
often (depending on the technical environment) requires higher authority
(for example, root) database credentials. Likewise, creating objects on
a ledger may require the use of a DID with more access permissions. By
separating out provisioning from normal operations, those higher
authority credentials do not need to be available on an ongoing
basis---which improves security.

We recommend the pattern of having separate provisioning and operational
versions of an application, with the operational app treating the ledger
as (mostly) read-only. When initializing the operational app, it should
verify that all the needed objects are available in secure storage and
ledger, but should error and stop if they don't exist. At minimum, care
must be taken to make sure that the same object is not created by
multiple parallel running instances. During development, we recommend
using a script to make it easy to run the two steps in sequence whenever
they start an environment from scratch (a fresh ledger and empty secure
storage database).

The exception to the \"no ledger writes in start mode\" method is the
handling of AnonCreds credential revocations, which involve ledger
writes. However, that's pretty deep into the weeds of credential
management, so we won't go further with that here. Better yet, in ACA-Py
at least, AnonCreds revocation handling is done entirely within ACA-Py,
and Aries controller developers don't really have to worry too much
about it.

## Startup Option Groups

The ACA-Py startup options are divided into a number of categories, as
outlined in the following:

-   **Admin**: Options to configure the connection between ACA-Py and
    its controller, such as on what endpoint and port the controller
    should send requests. Important required parameters include if and
    how the ACA-Py/controller interface is secured.

-   **Debug**: Options for development and debugging. Most (those
    prefixed with \"auto-\") implement default controller behaviors so
    an ACA-Py deployment can run without a controller. Several options
    enable extra logging around specific events, such as when
    establishing a connection with another agent.

-   **Discover Features**: Mechanisms to control what the deployment
    will disclose to other agents when asked what features it supports.
    For details of why this protocol is configurable, see [Aries RFC
    0557 Discover
    Features](https://github.com/hyperledger/aries-rfcs/blob/main/features/0557-discover-features-v2/README.md).

-   **General**: A catch-all category of options, including defining
    YAML config files to be used, adding and blocking plugins, setting
    plugin options and general configuration settings about how other
    agents connect to this agent, and how DIDs can be resolved.

-   **Revocation**: Options related to AnonCreds revocation. In the
    future, other revocation schemes might be added to ACA-Py, and their
    options added in this category.

-   **Ledger**: Options that provide different ways for the agent to
    connect to a ledger. As of this writing, all the options relate to
    Indy ledgers, but that is expected to change as other ledgers become
    easily used with ACA-Py.

-   **Logging**: Options for setting the level of logging for the agent
    and to where the logging information is to be stored.

-   **Protocol**: Options for special handling of several of the core
    protocols. We'll be going into a deeper discussion of protocols in
    the next chapter.

-   **Start-up**: Options about provisioning during start-up.

-   **Transport**: Options about the interfaces (such as HTTP and web
    sockets) that are to be used for connections and messaging with
    other agents.

-   **Mediation Invitation**: Options related to configuring an ACA-Py
    instance to use a specified mediator. We'll cover mediators in
    Chapter 6 and 7, when we talk about DIDComm message routing and
    mobile wallets.

-   **Mediation**: Options related to configuring an ACA-Py instance
    that is being used as an Aries mediator agent. We'll cover mediators
    in Chapter 6 and 7, when we talk about DIDComm message routing and
    mobile wallets.

-   **Wallet**: Options related to the storage of keys, DIDs, Indy
    ledger objects and credentials. This includes the type of database
    (e.g., SQLite or PostgreSQL) and credentials for accessing the
    database. This is a case of the term \"Wallet\" being used in the
    old Indy way. This category should be called \"Secure Storage.\"

-   **Multi-tenant**: Options for configuring ACA-Py to run in
    multi-tenant mode, where a single instance of ACA-Py acts as an
    agent for multiple entities.

-   **Endorsement**: Options related to the use of an Indy
    ledger's **[Endorser]{.underline}** features for writing
    transactions to the ledger.

**NOTE**: While the naming and activation method of the options are
specific to ACA-Py, few are exclusive to ACA-Py. Any agent, even those
from other Aries frameworks, likely provide many of these options.

## Lab: Agent Startup Options

Here is a [short
lab](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/ACA-PyStartup.md) to
show you how you can see all of the ACA-Py startup options.

The many (many!) ACA-Py startup options can be overwhelming. We'll
address that in this course by pointing out which options are used by
the different sample agents.

## Exploring Aries Protocols (1)

Before we get into the internals of controllers, we need to talk about
Aries protocols, introduced in Chapter 5 of the prerequisite
course---[*\"Introduction to Hyperledger Self-Sovereign Identity
Blockchain Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa)---and
a subject we'll go deep into next chapter. For now, we'll cover just
enough to understand how protocols impact the structure and role of
controllers.

As noted earlier, Aries agents communicate with each other via a
messaging mechanism called DIDComm (DID Communication). DIDComm uses
DIDs (usually private, pairwise DIDs) to enable secure, asynchronous,
end-to-end encrypted messaging between agents, including the option of
routing messages through a configuration of mediator agents. Aries
agents commonly use peer-to-peer DID methods that do not publish DIDs to
a ledger, but instead share them privately between the communicating
parties, usually just two agents.

The caveats in the above paragraph:

-   Some enterprises choose to deploy their agents with public DIDs for
    all peer-to-peer messaging.

-   Agents may directly message one another without any mediator agents.

-   Most current Aries implementations using peer-to-peer DID methods do
    not support rotating keys of the DID.

-   Aries AIP 1.0 and 2.0 agents use what has become known as \"DIDComm
    V1\". The ***DIDComm Messaging V2*** specification has been
    completed at the Decentralized Identity Foundation. At the time of
    writing (January 2023), the Aries community has started to work on
    defining AIP 3.0 with the primary goal of adding support for DIDComm
    Messaging V2.

Given the underlying DIDComm secure messaging layer (routing and
encryption are covered in Chapter 7), Aries protocols are standard
sequences of messages communicated on the messaging layer to accomplish
a task. For example:

-   The [**[Out of
    Band]{.underline}**](https://github.com/hyperledger/aries-rfcs/blob/main/features/0434-outofband/README.md) and [*DID
    Exchange*](https://github.com/hyperledger/aries-rfcs/blob/main/features/0023-did-exchange/README.md)**[ protocols]{.underline}** enable
    two agents to establish a connection (or reuse an existing
    connection) through a series of messages---an invitation, a
    connection request (or reuse connection), and a connection response.

-   The [*Issue
    Credential*](https://github.com/hyperledger/aries-rfcs/blob/main/features/0453-issue-credential-v2/README.md)**[ protocol]{.underline}** enables
    an agent to issue a credential to another agent.

-   The [*Present
    Proof*](https://github.com/hyperledger/aries-rfcs/blob/main/features/0454-present-proof-v2/README.md)**[ protocol]{.underline}** enables
    an agent to request and receive a proof from another agent.

Each protocol has a specification that describes and defines the
protocol (an Aries RFC). Included

-   a series of messages

-   one or more roles for the different participants

-   a series of named states for each role

-   a state machine per role that defines the state transitions
    triggered by messages/events

## Exploring Aries Protocols (2)

For example, the following table shows the messages, roles and states
for the connection protocol. Each participant in an instance of a
protocol tracks its state based on the messages they\'ve seen. An
agent's state depends on its role and the most recent message received
or sent by/to that agent. The details of the elements of all protocols
are covered in Aries [RFC
0003](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0003-protocols).

![](images/image022.png){width="6.0in"
height="2.7910367454068243in"}

In ACA-Py, the code for protocols is implemented as (possibly
externalized) Python modules. All of the core (AIP 1.0 and AIP 2.0)
protocols are in the [ACA-Py code
base](https://github.com/hyperledger/aries-cloudagent-python/tree/main/aries_cloudagent/protocols) itself.
External modules are not in the ACA-Py code base, but are written in
such a way that they can be loaded by an ACA-Py instance at run time,
allowing organizations to extend ACA-Py (and Aries) with their own
protocols. Protocols implemented as external modules can be included (or
not) in any given agent deployment. All protocol modules include:

-   The definition of a state object for the protocol.\
    - The protocol state object gets saved in secure storage while an
    instance of a protocol is in flight and waiting for the next event.

-   The handlers for the protocol messages.

-   The events sent to the controller on receipt of messages that are
    part of the protocol.

-   Administrative endpoints that are available to the controller to
    direct ACA-Py on what to do next for a given protocol.

-   Command line options for configuring the protocol, if any.

Each administrative endpoint becomes part of the HTTP API exposed by the
agent instance, and is visible by the OpenAPI/Swagger generated user
interface. More on that later in this chapter.

## Protocol Versions, AIP 1.0 and AIP 2.0

As we start to get into Aries protocols, we need to talk about instances
of protocols in terms of version and whether or not the protocol is part
of AIP 1.0 or 2.0. In fact, in mentioning \"connections,\" issuing
credentials and presenting proofs in the last section, we hit on some of
the biggest changes between AIP 1.0 and 2.0.

All Aries protocols are versioned, generally starting with 1.0. Although
a protocol is versioned, you can tell the version in a running Aries
agent by the \"type\" field in messages, which includes the version, as
shown in these examples:

-   v1.0: https://didcomm.org/issue-credential/1.0/offer-credential

-   v2.0: https://didcomm.org/issue-credential/2.0/offer-credential

Protocols are versioned using the \"semver\" (semantic versioning)
scheme that allows for major and minor version changes based on whether
the changes are only additions (minor) or removals and/or changes in
meaning (major). In Aries, major protocol versions are generally treated
as entirely new protocols, usually with a new RFC and, within
frameworks, by copying and pasting the code for the old version as a
starting point for the new version. Clarifications to an RFC that don't
require a change in the technical implementation of a protocol are
permitted without changing the protocol version.

As a reminder from Chapter 2, each AIP version is:

-   a specific list of RFCs (many of which are protocols)

-   a link for each RFC to a specific GitHub commit of the RFC

In transitioning from AIP 1.0 to AIP 2.0, RFCs were dropped, kept and
added, resulting in some protocols being updated to new major protocols
versions, including the most fundamental protocols---those used for
connecting agents, issuing credentials and presenting proofs. Note that
the version of any particular protocol (such as issue-credential) does
not indicate if it is part of AIP version 1.0 or 2.0. What matters for
an AIP is what GitHub commit is used for the link from the AIP RFC to
the specific protocol.

As of this writing (January 2023), most Aries frameworks support AIP 2.0
and the use of AIP 1.0 is fading away. The roadblock to eliminating AIP
1.0 are the mobile wallets that are available, most of which are in
transition from AIP 1.0 to 2.0. We expect that in 2023, there will be a
concerted effort to update all deployments to AIP 2.0, and to drop the
use of any mobile wallets that don't update.

The impact of the AIP 1.0 to 2.0 transition on this course is that we'll
have places in the rest of the content where we'll need to indicate
whether we're using/talking about AIP 1.0 or AIP 2.0 RFCs. At key
points, we'll add a paragraph that references the RFC(s) from the other
AIP version and the differences between the protocols. As you'll see,
for the protocols that changed from AIP 1.0 to 2.0, the changes are
relatively subtle. The concepts are (for the most part) still the same.

## Coming Soon: Aries Interop Protocol 3.0

As we are writing this course (January 2023), the Aries community has
started to talk about AIP 3.0. The primary motivation (at least right
now) for AIP 3.0 is to add support for DIDComm Messaging V2. Recall that
AIP 1.0 and 2.0 are both based on the DIDComm V1. From a developer
perspective, the biggest difference between DIDComm V1 and V2 is the
JSON structure---DIDComm V2 handles the protocol-specific message body
and attachments differently from DIDComm V1. In some cases, those
differences require that a new major (breaking) version of the DIDComm
protocol be defined, in other cases, an Aries Framework can simply move
the JSON around---no need to define a new major version of the protocol.
As such, at least some of the protocol specific changes from AIP 2.0 to
AIP 3.0 will be new major protocol versions.

What else will be in AIP 3.0? Time will tell---as the community
discussions continue. Since AIP 2.0, there has been a lot of progress
made on Aries mobile wallets, and especially the wallet user experience.
We think that will be an area where there are new and useful protocols
added to AIP 3.0.

Want to know more and help set the contents of AIP 3.0? Join the
weekly [Aries Working Group
calls](https://wiki.hyperledger.org/display/ARIES/Aries+Working+Group) and
see what is happening with AIP 3.0. As well, keep an eye on [Aries RFC
0302 Aries Interop
Profiles](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0302-aries-interop-profile).

## Aries Protocols: The Controller Perspective (1)

We've defined all of the pieces of a protocol as well as where the code
lives in an Aries framework such as ACA-Py. Let's take a look at a
protocol from the controller's perspective.

Our agent has started up (an ACA-Py instance and its controller), and
everything has been initialized. Perhaps some connections have been
established, but not much is going on. The controller is bored, ACA-Py
is bored. Suddenly, a DIDComm message is received from another agent.
It's a credential offer message! ACA-Py starts a new instance of the
\"issue credential\" protocol (either [RFC
0036](https://github.com/hyperledger/aries-rfcs/tree/main/features/0036-issue-credential) V1
in AIP 1.0 or [RFC
0453](https://github.com/hyperledger/aries-rfcs/tree/main/features/0453-issue-credential-v2) V2
in AIP 2.0) and we're off and running!

Here's what happens:

-   The ACA-Py instance figures out what connection is involved and
    creates a protocol state object. It sets some data in the object
    based on what it received in the message and sends a webhook event
    (HTTP request) to the controller with information about the message
    and the protocol state object.\
    - This assumes that the ACA-Py instance is **[not]{.underline}** set
    up to automatically process the offer (e.g., the
    option **\--auto-respond-credential-offer** is not set). If that
    option is set, the ACA-Py instance would just handle the whole thing
    and the controller would just get an \"all done!\" webhook event,
    but not have to do anything else. Sigh\... back to waiting.\
    - Since the ACA-Py instance doesn't know how long the controller
    will take to tell it what to do next, the ACA-Py instance saves the
    protocol state object in its secure storage and moves on to do other
    things---like waiting for more agent messages.\
    - A piece of data that is included in every message called the
    thread identifier (**thid**) is used to index the protocol state
    object so it can be found when it is needed again. We'll dig into
    that in the next chapter.

-   The controller receives the webhook and panics (OK, it doesn't...).
    The controller code (that you wrote!) figures out what the business
    rules are for handling credential offers. Perhaps it just accepts
    (or rejects) them, no questions asked. Perhaps it puts the offer
    into a queue for a legacy app to process and tells it what to do.
    Perhaps it opens up a user interface screen, and waits for a person
    to tell it what to do. That is usually what happens in an Aries
    mobile wallet app.\
    - Depending on how long it will take to decide on the answer, the
    controller might also need to persist the state of the in-flight
    protocol in a database of its own.\
    - Again, the thread identifier will be used when saving the state
    and for retrieving it later.

-   When the controller decides (or is told) what to do with the
    credential offer, it retrieves (if necessary) its information about
    the in-flight protocol and constructs an HTTP request to send the
    answer to the appropriate ACA-Py administrative endpoint.\
    - In this example, the controller might use the
    \"credential_request\" endpoint to request the offered credential.

![Aries Protocols in ACA-Py from the Controller's
Perspective](images/image023.png){width="5.0in"
height="4.166666666666667in"}

**Aries protocols in ACA-Py from the controller's perspective**\
Licensed under [CC BY
4.0](https://courses.edx.org/xblock/%E2%80%9Chttps:/creativecommons.org/licenses/by/4.0/%E2%80%9D)

-   Once it has sent the request to the ACA-Py instance, the controller
    might persist the data about the interaction and then go back to
    lounging around, waiting for something else to happen.

-   The ACA-Py instance receives the request from the controller and
    gets busy. It retrieves the corresponding protocol state object from
    its secure storage and constructs and sends a properly crafted
    \"credential request\" message in a DIDComm message to the other
    agent, the one that sent the credential offer.\
    - The ACA-Py agent then saves the protocol state object in its
    wallet again as it has no idea how long it will take for the other
    agent to respond. Then it returns to waiting for more stuff to do.

## Aries Protocols: The Controller Perspective (2)

That describes what happens when a protocol is triggered by a message
from another agent. A controller might also decide it needs to initiate
a protocol. In that case, the protocol starts with the controller
sending an initial request to the appropriate endpoint of the ACA-Py
instance's HTTP API. In either case, the behavior of the controller is
the same:

-   Wait for an event to happen.

-   Get notified of an event either by the ACA-Py instance (via a
    webhook) or perhaps by some non-Aries event from, for example, a
    legacy enterprise app.

-   If necessary, retrieve saved information about the related business
    process.

-   Figure out what to do with the event:\
    - Perhaps the event ends the business process.\
    - Perhaps by asking some other software or a person to do
    something.\
    - Perhaps by sending a response to the event to the ACA-Py instance
    via the administrative API.

-   If necessary, save the state of the business process.

-   Return to waiting for the next event to come along.

As we've discussed previously, developers building Aries agents for
particular use cases focus on building controllers. As such, the event
loop above describes the work of a controller and the code to be
developed. If you have ever done any web development, that event loop is
going to look mighty familiar! It's exactly the same.

Aries agent controller developers must understand the Aries protocols
that they are going to use (the hard part!), including the webhook
events the controller will receive and the protocol\'s administrative
messages exposed via the HTTP API. Then, they write controllers that
loop waiting for events, deciding what to do with each event,
responding, and returning to the waiting state. The events might come
from ACA-Py when a message is received, or from the business needing to
initiate the execution of protocol.

And that's it! We've covered the basics of protocols from the
perspective of the controller. Let's see controllers in action!

## Lab: Alice Gets a Credential

In this section, we'll start up two command line agents, much as we did
in Chapter 2. However, this time, one of the participants, Faber
College, will carry out the steps to become an issuer (including
creating objects on the ledger) and issue a credential to the other
participant, Alice. As a holder/prover, Alice must also connect to the
ledger. Later, Faber will request a proof from Alice for claims from the
credential and Alice will oblige.

We'll do a couple more versions of this interaction in subsequent labs.
There is not much content to see in this chapter of the course, but
there is lots in the labs themselves. ***Don't skip them!***

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/AliceGetsCredential.md) to
access the lab.

## Links to Code

There are a number of important things to highlight in the code from the
previous lab---and in the ones to come. Make sure when you did the
previous lab, that you followed the links to the key parts of the
controller code. For example, in the previous lab, Alice and Faber
ACA-Py agents were started and it's helpful to know for each what ACA-Py
command line parameters were used. Several of the labs that follow will
include a comparable list of links that you can use to inspect and
understand the code.

## Learning the ACA-Py Controller API using OpenAPI (aka Swagger)

Now that you have seen some examples of a running controller, let's get
minimal. As noted earlier, ACA-Py has been implemented to expose an HTTP
interface to the controller---the \"Admin\" interface. To make it easy
(well\... easier) for you to understand the Admin interface, ACA-Py
automatically generates an industry standard OpenAPI (also called
Swagger) configuration. In turn, that provides a web page that
developers (you!) can use to see all the calls exposed by a running
instance of ACA-Py, with examples and the ability to \"try it\"---that
is, execute the available HTTP endpoints. Having an OpenAPI/Swagger
definition for ACA-Py also lets you do cool things such as generate code
(in your favorite language) to create a skeleton controller without any
coding. The OpenAPI/Swagger definition also provides a level of runtime
verification of the parameters passed in via the Admin API endpoints. If
you are new to OpenAPI/Swagger, here's a [link to what it
is](https://swagger.io/docs/specification/about/) and how you can use
it. The most important use: being able to quickly test something out
just by spinning up an agent or two and using OpenAPI/Swagger.

With ACA-Py, the exposed API is dynamic for the running instance. If you
start an instance of ACA-Py with one or more external Python modules
loaded (using the **\--plugin \<module\>** command line parameter),
those modules must add administrative endpoints to the OpenAPI/Swagger
definition so that they are visible in the OpenAPI/Swagger interface.

## Lab: Using ACA-Py's OpenAPI/Swagger Interface

In this lab, we'll introduce you to the OpenAPI/Swagger interface for
interacting with a running ACA-Py instance, covering how to do some
querying of ACA-Py state information. In the next chapter, after we
learn a little more about protocols, we'll use the OpenAPI/Swagger
interface to carry out the Faber and Alice use case.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/OpenAPIIntroduction.md) to
run the OpenAPI/Swagger introduction lab.

## Lab: Help Alice Get a Job

Time to do a little Python controller development. The next assignment
is to extend the command line lab with Alice and Faber to include ACME
Corporation. Alice wants to apply for a job at ACME. As part of the
application process, Alice needs to prove that she has a degree.
Unfortunately, the person writing the ACME agent's controller quit just
after getting started building it. Your job is to finish building the
controller, deploy the agent and then walk through the steps that Alice
needs to do to prove she's qualified to work at ACME.

Alice needs your help. Are you up for it?
Click [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/HelpAliceGetAJob.md) to
run the lab.

## Lab: Python Not for You?

The last lab in this section provides examples of controllers written in
other languages. GitHub user amanji (Akiff Manji) has taken the agents
that are deployed in the command line version of the demo and written a
graphical user interface (GUI) controller for each participant using a
different language/tech stack. Specifically:

-   Alice's controller is written in Angular.

-   Faber's controller is written in C#/.NET.

-   ACME's controller is written in NodeJS/Express.

To run the lab, go to the
instructions [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/AriesACAPyControllers.md).

As an aside, Akiff decided to make these controllers based on [an issue
posted in the
ACA-Py](https://github.com/hyperledger/aries-cloudagent-python/issues/93) repo.
The issue was labelled \"Help Wanted\" and \"Good First Issue.\" If you
are looking to contribute to some of the Aries projects, look in the
repos for those labels on open issues. Contributions are always welcome!

## Optional Exercise

Want to go further? This is optional, but we recommend doing this as an
exercise to solidify your knowledge. Build your own \"Alice\" controller
in the language of your choice. Use the pattern found in the two other
Alice controllers ([command line
Python](https://github.com/hyperledger/aries-cloudagent-python/blob/master/demo/runners/alice.py) and [Angular](https://github.com/petridishdev/aries-acapy-controllers/tree/master/AliceFaberAcmeDemo/controllers/alice-controller))
and write your own. You might start by generating a skeleton using the
OpenAPI/Swagger tools, or just by building the app from scratch. No link
to a lab or an answer for this one. It's all up to you!

If you build something cool, let us know by [clicking here and
submitting an issue](https://github.com/cloudcompass/ToIPLabs/issues).
If you want, we might be able to help you package up your work and
create a pull request (PR) to the aries-acapy-controllers repo.

## Discussing Additional Frameworks

In this chapter we have focused on understanding controllers for Aries
Cloud Agent Python (ACA-Py). The Aries project has several frameworks
other than ACA-Py. In this section, we'll cover how controllers work
with those frameworks.

## Aries Framework JavaScript

Aries Framework JavaScript (AFJ) is a relatively new framework, but one
that is getting lots of contributions, capabilities and use. It is the
basis of the newer open source Aries mobile wallets (that we'll get to
in Chapter 7), but can also be run with NodeJS on the server side. The
architecture for the controller and framework with AFJ is a little
different from ACA-Py. Instead of embedding the framework in a web
server and exposing an HTTP interface for the controller, AFJ is built
as a library, and the library is embedded in an application---the
controller---that you create. As such, the equivalent to the ACA-Py HTTP
Admin API in AFJ is the API between the application and the embedded
library that is the framework. This architecture is illustrated below.
Since both ACA-Py and AFJ do the same things, the two styles of API are
conceptually the same. All of the same requests and events occur, with
the details about how the requests and events are handled that differ
between the two.

![Aries Agent Architecture---Aries Framework
JavaScript](images/image024.png){width="4.0in"
height="4.3697473753280835in"}

**Aries agent architecture---Aries Framework JavaScript**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## Lab: Run Some Aries Framework JavaScript Agents

In this lab, we'll run an Alice/Faber demo with AFJ. In the lab, you
will deploy a couple of agents, connect them, issue a credential from
one to the other and do a presentation request.

To run the lab, go to the
instructions [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/AFJGettingStarted.md).

## Aries VCX

Aries VCX is architecturally similar to the Aries Framework JavaScript
(a library embedded in a controller application), but adds the need for
a language-specific wrapper around the C-language interface exposed by
Rust language of the framework. As of this writing, there are three
complete wrappers that are part of the framework, Java, Objective-C for
IOS and NodeJS. The Java wrapper enables the use of Aries VCX as the
basis for an Android mobile wallet.

**No**te that it would be possible to build Aries VCX (and AFJ, for that
matter) into a web server and expose an HTTP Admin API (and webhook
events) to match the ACA-Py architecture. That might be an approach for
supporting the use of any language controller with those Aries
frameworks.

## Lab: Getting Started with Aries VCX

In this lab, we'll run a simple demo with Aries VCX using the NodeJS
wrapper. As with the ACA-Py and AFJ labs, you will deploy a couple of
agents (yes, Alice and Faber again!), connect them, issue a credential
from one to the other and do a presentation request.

To run the lab, go to the
instructions [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/AriesVCXGettingStarted.md).

## Aries Framework Go

The Aries Framework Go (AFGo) takes the same approach to the
controller/framework architecture as ACA-Py---an HTTP interface between
the two. In fact, as the team building AFGo has created the framework,
they tried to use the same Admin interface calls as ACA-Py. As such, a
controller written for ACA-Py should work with an instance of AFGo with
relatively few changes.

What's unique about this framework is that it is written entirely in
Golang without any non-Golang dependencies. That means that the
framework can take advantage of the rich Golang ecosystem and
distribution mechanisms. That also means the framework does not use the
Indy and AnonCreds Rust language components, and so does not support
out-of-the-box writing Indy ledgers or the AnonCreds verifiable
credentials exchange model. AFGo supports using other types of ledgers,
W3C Verifiable Credentials Data Model Standard signatures, such as
LD-Signatures and BBS+ Signatures for JSON-LD.

## Optional Lab: Run the Aries-Framework-Go \"Getting Started\" Exercise

In this optional lab, we'll run the Aries Framework Go repository's
\"Getting Started\" exercise to learn a bit about aries-framework-go.

To run the lab, go to the
instructions [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/AFGoGettingStarted.md).

## Aries Framework .NET

The oldest of the other Aries frameworks supporting AIP 1.0 is Aries
Framework .NET (AF.Net) written in Microsoft's open-source C# language
on the .NET development platform. The architecture for the controller
and framework with AF.Net is the same as that of Aries Framework
JavaScript, with the framework built as a library and deployed inside
the controller application.

As we'll see in the chapter on mobile agents, AF.Net can be used as the
basis of a mobile agent. It can also be used as a full enterprise agent,
or as a more limited cloud routing agent. A jack-of-all-trades option!
The downside of using AF.Net is that it is currently still at AIP 1.0
and the open-source implementation has not had much attention recently.

## Chapter 4 Summary

We've covered an awful lot in this chapter! As we said at the beginning,
this is the core of the course, the hands-on part that will really get
you understanding Aries development and how you can use it in your use
cases. The rest of the course will be lighter on labs, but we'll refer
back to the labs from this chapter to put those capabilities into a
context with which you have experience.

## Chapter 5 Overview -- Digging Deeper-The Aries Protocols

In the last chapter, we focused on how a controller injects business
logic to control the agent and make it carry out its intended use cases.
In this chapter, we'll focus on what the controller is really
controlling---the messages being exchanged by agents. We'll look at the
format of the messages and the range of messages that have been defined
in the Aries protocols. Later in the course, when we're talking about
message routing and mobile agents, we'll look deeper into how messages
get from one agent to another.

Some of the topics in this chapter come under the heading of \"DIDComm
Protocol,\" where pairs (and perhaps in the future, groups) of agents
connect and securely exchange messages using DIDs each has created and
shared, usually privately. The initial draft and implementations of the
DIDComm V1 protocol described here was incubated first in the
Hyperledger Indy Agent Working Group, and later the Hyperledger Aries
Working Group. The DIDComm Messaging V2 specification was completed in
2022 by the DIDComm Working Group within the [Decentralized Identity
Foundation](https://identity.foundation/) (DIF).

## Learning Objectives

As we've just explained, this chapter is all about messaging and the
protocols that allow messaging to happen. We will discuss:

-   The aries-rfcs repository---the home of all the documents!

-   \"DIDComm 101,\" covering the two layers of Aries messaging
    protocols.

-   Which protocol layer a developer needs to worry about (hint: it's
    the Aries protocols layer).

-   The format of protocol messages.

-   Message processing in general.

-   A summary about the differences between AIP 1.0 and AIP 2.0.

## The Aries Project GitHub Repository

The concepts and features that make up the Aries project are documented
in the Hyperledger aries-rfcs GitHub repository. RFC stands for
\"request for comments\" and is a type of text document used by a wide
range of technical groups to create understanding towards defining and
evolving specifications and standards. RFCs are the documents that tell
developers how they MAY, SHOULD and MUST do things to meet a particular
standard. With Aries, the RFCs are defined into two groups, concepts
(specifications that cross protocols) and features (specific protocols).

The aries-rfcs repository is full of extremely detailed information
about exactly how each protocol is to be implemented. While the repo is
a crucial resource for developers, it is overwhelming for newcomers.
It's definitely not the best place to get started---kind of like
learning a language by reading the dictionary. It's important that you
are aware of the aries-rfcs repo so that when you are deep in the weeds
and need to know exactly what a certain protocol does, you know where to
look. For now though, follow along here and we'll get you going!

Throughout the course, we'll provide pointers into the aries-rfcs
repository for things we mention. That way, when you are on your own,
you'll know how to navigate the repository when you need to know the
crucial details it holds. Here's an example: the [Aries Interop Profile
(AIP) 2.0
section](https://github.com/hyperledger/aries-rfcs/blob/main/concepts/0302-aries-interop-profile/README.md#aries-interop-profile-version-20) of
the AIP RFC. It provides a list of the most important Aries RFCs that
you need to know about---the ones that you will use in building your AIP
2.0 controllers. Check it out!

**NOTE**: Hyperledger Indy has a comparable repository to aries-rfcs
called indy-hipe (for Hyperledger Indy Project Enhancement). Despite the
name difference, the purpose of the repository is the same. Likewise,
the DIDComm Messaging protocols that moved from Hyperledger Aries to the
Decentralized Identity Foundation (DIF) have a comparable home
there---although the format of the documents is a bit different.
Regardless of where the specification document resides, if it is
relevant to Aries protocols and interoperability, it will be covered in
aries-rfcs. A few of the HIPEs in the Indy repo are useful and so are
still referenced.

## DIDComm Concepts

We introduced the core concepts of DIDComm in Chapter 5
of [*\"Introduction to Hyperledger Self-Sovereign Identity Blockchain
Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa),
a prerequisite of this course. Here is a review of the key points
covered there to provide context as we move on to the developer's
details of Aries messaging.

The core capability of an Aries agent is peer-to-peer
messaging---connecting with other agents and sending and receiving
messages to and from those agents to accomplish some interaction. The
interaction might be as simple as sending a text message, or more
complex, such as negotiating the issuing of a verifiable credential or
the presentation of a proof.

Enabling both the exchange and use of messaging to accomplish higher
level transactions requires participants interact in pre-defined ways,
to interact by following mutually agreed upon protocols. Aries protocols
are just like human protocols, a sequence of events that are known by
the participants to accomplish some shared outcome. For example, going
out to a restaurant for a meal is a protocol, with both the guests and
the restaurant staff knowing the sequence of steps for their
roles---greeting, being seated, looking at menus, ordering food, etc.
Unlike human protocols (etiquette), Aries protocols need to be carefully
specified and then implemented by multiple participants.

![](images/image025.png){width="2.0in"
height="1.4923075240594925in"}

With Aries, there are two levels of messaging protocols.

![DIDComm](images/image026.png){width="3.0in"
height="3.3266108923884516in"}

**DIDComm**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

At the lower level is the *DIDComm protocol*, the method by which
messages are exchanged, irrespective of the message content. The
participants exchange DIDs, and the attributes of those DIDs---signing
and encryption keys, and service endpoint details---enabling end-to-end
secure messaging via DIDComm. You can think of the DIDComm protocol as
being like the postal service. You write a letter, place it into an
envelope, address it to a recipient, give it to the postal service and
magically, it appears at the recipient's door. And, just like the postal
service, there is a lot of complexity in the sending and receiving of a
message.

At a higher level are the *Aries protocols* we talked about in the last
chapter, the many protocols that define back-and-forth sequences of
specific messages (content) to accomplish some shared goal. The simplest
of these is one agent sending another agent a text message (\"Hi, how
are you?\"). A more complex protocol is issuing a verifiable credential,
where it takes three messages back and forth to offer, request and issue
an AnonCreds credential. Getting back to our postal system analogy,
Aries protocols deal with content that goes into the envelopes that are
delivered by DIDComm.

With the DIDComm protocol we don't care about the content of the
message, just the envelope and the method by which the message gets
delivered. With the Aries protocols, it's the reverse---we know that the
messages get delivered (we don't care how), and we only care about the
content of each message.

## What Protocols Matter for Controller Development?

While it's important to understand that both layers of protocols exist,
for the most part, Aries application developers (those building Aries
controllers) are really not exposed to the lower DIDComm layer at all.
The DIDComm layer is handled entirely in code provided by the Aries
frameworks.

On the other hand, Aries application developers do need to understand a
lot about the Aries protocols---the content of the messages delivered
via DIDComm. While the mechanics of receiving Aries protocol messages
and preparing and sending messages is handled by the code in the Aries
frameworks, the semantics (business processing) of what to do with those
messages is up to the controller. For example, when an enterprise agent
wants to issue a credential to another agent, the controller doesn't
have to get into the nitty-gritty of signing the verifiable
credential---the framework handles that. However, the controller does
have to figure out what data needs to go into the credential and pass
that data (via the controller-to-framework API) into the framework to be
signed.

For the remainder of this chapter, we will focus only on the
upper-level, Aries protocols (content). We will cover more about the
lower level DIDComm (envelope) protocol in Chapter 6 when we talk about
message routing.

## Understanding Aries Protocol Messages

As we saw in the labs in the previous chapter, the format of Aries
protocol messages is JSON. Let's start our look into Aries protocols by
considering an example of a simple message and going through each of the
JSON items. The following is the only message in the \"basic message\"
protocol defined in Aries [RFC
0095](https://github.com/hyperledger/aries-rfcs/tree/main/features/0095-basic-message).

**{**\
**    \"@id\": \"caec7c09-e0ef-4e2a-9708-e69316a0b73f\",**\
**    \"@type\": \"https://didcomm.org/basicmessage/1.0/message\",**\
**    \"\~l10n\": { \"locale\": \"en\" },**\
**    \"sent_time\": \"2023-01-15 18:42:01Z\",**\
**    \"content\": \"Your hovercraft is full of eels.\"**\
**}**

The purpose of the message is simple: to send some text content in a
message from one agent to another.

While the format is standard JSON, some conventions are used in messages
such that they are compatible with [JSON-LD (JSON Linked
Data)](https://json-ld.org/)---notably the **\@type** and **\@id** items
that are in every Aries protocol message. For those unfamiliar, JSON-LD
is based on JSON and enables semantic information (what the JSON data
items mean) to be associated with JSON. It is a W3C-standard way to
embed in the JSON itself a link to metadata about the items in the JSON
structure so that an application developer can know exactly how the data
is to be processed. \"Compatible with JSON-LD\" means that while the
JSON does not support all the features of JSON-LD, it respects JSON-LD
requirements such that JSON-LD tools can process the messages. It's not
crucial to know more about Aries messaging and JSON-LD at this point,
but if you are curious, you can read Aries [RFC
0047](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0047-json-ld-compatibility) about
support for JSON-LD in Aries messages.

Back to the message content. Every message in every protocol includes
the first two fields:

-   \@id is a unique identifier for the message, generated from a
    globally unique ID (GUID) library.

-   \@type is the type of the message. It is made up of the following
    parts:

1.  **[Namespace]{.underline}** (e.g., **https://didcomm.org**) is
    defined so that when appropriate, different groups (for example,
    companies, standards groups, etc.) can independently define
    protocols without conflicting with one another. All of the protocols
    defined by the Aries Working Group (and hence, documented in the
    aries-rfcs repo) use the same namespace, the one listed above
    (https://didcomm.org). By using a URL as the namespace, the Aries
    community hopes to one day make the message type a link to the human
    (and perhaps machine readable) specification for the message.

2.  Protocol (e.g., **basicmessage**)---the name of protocol to which
    the message type belongs.

3.  Message version (e.g., **1.0**)---Aries uses the semver versioning
    system, as defined [here](https://semver.org/), although with just
    MAJOR.MINOR version components.

4.  Message type (e.g., **message**)---the actual name of the message.

**NOTE**: When AIP 1.0 was defined, the \"Namespace\" prefix was a
specific DID (specifically this DID: *did:sov:BzCbsNYhMrjHiqZDTUASHg*).
The Aries community decided that since that DID was on a specific Indy
network, it was inappropriate to use for a \"blockchain-agnostic\"
project, and the transition was made to the new didcomm.org namespace.
You might still see some production Aries agents using the old-style DID
message type namespace. If you do, please tell them to change! Message
types in all AIP 2.0 RFCs require using the didcomm.org-style namespace.

The remaining items in the JSON example above are specific to the type
of the message. In our example, these are the items **\~l10n**, which
we'll talk about in the next section, **sent_time** (when the message
was sent, as defined by the sender) and **content** (the text of the
message). For each message type in each protocol, the protocol
specification defines all of the relevant information about the message
type specific item. This includes which items are required and which are
optional, the data format (such as the time format in
the **sent_time** field above), and any other details necessary for a
developer to implement the message type. That overview of message types
is all you really need to know. However, it's a good idea to get used to
going to the aries-rfcs repository to get all the details on a topic, so
please check out [RFC
0020](https://github.com/hyperledger/aries-rfcs/blob/main/concepts/0020-message-types/README.md) to
see the accepted information about message types.

## Message Decorators

In addition to protocol specific data elements in messages, messages can
include \"decorators,\" standardized message elements that define
cross-cutting behavior. \"Cross-cutting\" means the behavior is the same
when used in different protocols. Decorator items in messages are
indicated by a \"\~\" prefix. The **\~l10n** item in the previous
section is an example of a decorator. It is used to provide information
to enable the localization of the message---translations to other
languages. Decorators all have their own RFCs. In this case, the
localization decorator is specified
in [RFC 0043](https://github.com/hyperledger/aries-rfcs/blob/main/features/0043-l10n/README.md).

The most commonly used decorator is the **\~thread** ([RFC
0008](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0008-message-id-and-threading))
decorator, which is used to link the messages in a protocol instance. As
messages go back and forth between agents to complete an instance of a
protocol (for example, issuing a credential), **\~thread** decorator
data lets the agents know to which protocol instance the message belongs
and the ordering of the message in the overall flow. It's
the **\~thread** decorator that will let Faber College issue thousands
of credentials in parallel without losing track of which student is
supposed to get which verifiable credential. We'll talk later in this
chapter about the **\~thread** decorator when we go over the processing
of a message by an agent. You'll note that the example message in the
previous section doesn't have a **\~thread** decorator. That's because
it is the first message of that protocol instance. When a recipient
agent responds to a message, it takes the **\@id** of the first message
in the protocol instance and makes it the **thid** (thread id) of
the **\~thread** decorator. Want to know more? As always, the place to
look is in the aries-rfcs. Other currently defined examples of
decorators include **\~attachments** ([RFC
0017](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0017-attachments)), **\~tracing** ([RFC
0034](https://github.com/hyperledger/aries-rfcs/tree/main/features/0034-message-tracing))
and **\~timing** ([RFC
0032](https://github.com/hyperledger/aries-rfcs/blob/main/features/0032-message-timing/README.md)).

Decorators are often processed by the core of the agent, but some are
processed by the protocol message handlers. For example,
the **\~thread** decorator is processed by the core of the agent to
connect an incoming message with the state of a protocol that is
mid-flight. On the other hand, the **\~l10n** decorator (enabling text
display in multiple languages) is more likely to be handled by a
specific message type, as its purpose can't be understood except by the
handler of that particular type of message.

## Special Message Types: Ack and Problem Report

The Aries Working Group has defined two message types that deserve
special attention: ack (acknowledge) and problem_report. Much like
decorators, these are cross-cutting messages, used in the same way
across many protocols. In particular, these messages are for error
handling.

In executing an instance of a protocol, there are often times when one
agent wants to say to the other \"yup, I got your last message and all
is well.\" Likewise, if something goes wrong in a protocol, an agent
will want to notify the other \"uh-oh, something bad has happened!\"
Rather than having each protocol define their own special purpose
messages, the common ack and problem_report messages were defined so
that any protocol can **[adopt]{.underline}** those messages. When a
protocol adopts these messages, it means that there is a message type of
ack (and/or problem_report) in the protocol, even though there is not a
formal definition of the message type in the specification. The
definition is found in the respective RFCs: [RFC
0015](https://github.com/hyperledger/aries-rfcs/tree/main/features/0015-acks) for
ack, and [RFC
0035](https://github.com/hyperledger/aries-rfcs/tree/main/features/0035-report-problem) for
problem report.

![Bulb](images/image017.png){width="1.0in"
height="1.2834787839020123in"}

Remember that unlike HTTP requests, all DIDComm messages are
asynchronous. An agent sends off the message, doesn't immediately get a
response message, and continues doing other things until it receives the
next message of the protocol. Thus, a use case for problem_report is
when an agent sends off a message and doesn't hear back in a time it
thinks is reasonable, it can send a problem report message asking if the
previous message was received.

## Protocols and Messages: The Controller's Perspective

Since protocols enable the interactions between Aries agents, it's
important for you, the Aries developer, to know what the protocols do
and how to use them when coding your controller. However, as we'll see
soon, the controller does not handle all the nitty-gritty details of the
protocol messages directly. Rather, each Aries framework exposes a way
to use the protocols that minimizes what the controller has to do, thus
limiting the mistakes the controller can make. In ACA-Py, the endpoints
made available via the Admin HTTP API requires the controller to provide
the absolute minimum information necessary for ACA-Py to carry out an
action.

For example, let's look at the [\"request\" message in the RFC 0023 DID
Exchange
protocol](https://github.com/hyperledger/aries-rfcs/tree/main/features/0023-did-exchange#1-exchange-request).
The message has a lot of fields to complete. Fortunately, the controller
doesn't have to construct the actual message. All the controller does is
call the **/didexchange/{conn_id}/accept-invitation** Admin API
endpoint, using the ID of the connection (which it got from an earlier
webhook event), and ACA-Py takes care of the rest! Easy!

So, while it is important to know what's going on with the protocols
your controller needs to use, the details about what information the
controller needs to supply (and not supply) to the framework is in the
API exposed for controllers.

## Controller Perspective

Messages are sent between agents. Let's talk about the processing of
messages from the perspective of the controller. We'll start with a
controller initiating a message, and then move onto the receipt of a
response to the message.

![Bulb](images/image017.png){width="1.0in"
height="1.2834787839020123in"}

You should have noticed in looking at the ACA-Py startup parameters and
in the labs in the last chapter that ACA-Py can handle a number of
common interactions without involving a controller. For example, when
ACA-Py is started with the **\--auto-accept-invites** parameter, ACA-Py
will not wait on the controller to tell it what to do when it receives
an invitation---it will just accept it.

The **\--auto\*** parameters are to simplify getting started and
debugging ACA-Py itself. It is rare that those parameters would be used
in a production agent implementation. **Don't rely on those parameters
in your application!** In this section, we'll make sure those options
are off.

## Initiating a Protocol

We'll start with a protocol initiated by the controller. Assume that
Faber College and Alice have established a DIDComm connection and now
Faber College wants to offer Alice a verifiable credential about her
accomplishments at Faber. The Faber controller uses the administration
API to initiate the process by requesting the agent framework send a
message identifying the:

-   type of message to be sent

-   content of the message

-   connection to which the message is to be sent

In ACA-Py (and other Aries frameworks) the type of message to be sent is
implied by the API endpoint used by the controller. In general, there is
one API endpoint per message type. The content is provided as JSON data
as defined by the API endpoint. Sometimes, the JSON provided by the
controller corresponds to the content items of the message that is to be
sent---the JSON message fields except **\@id** and **\@type**. If the
controller request is to start a new protocol, it might need to pass in
the ID of an existing connection to use. Or, if the controller is
sending a request that tells ACA-Py what to do next in an in-flight
protocol, it might pass in the ID of the protocol state object (e.g.,
the **cred_ex_id** credential exchange ID in the issue credential
protocol).

In order to know the connection on which to initiate a protocol, the
controller must keep a record of the connections as they are
established, perhaps storing the relationship as an attribute of an
account it holds. For example, Faber College might keep the identifier
for the DIDComm connection it has established with Alice in the \"Alice
Record\" in its \"Student Information System.\" Alternatively, the
controller might have its own database, and create a record that has
both an identifier for Alice's DIDComm connection and an identifier for
her record in the \"Student Information System.\"

![](images/image027.png){width="2.7291666666666665in"
height="2.1979166666666665in"}

Armed with that information, agent framework code carries out the
details of:

-   Finding the connection for Alice.

-   Determining how to route messages to Alice's agent.

-   Generating an **\@id** for the message.

-   Packaging (including encrypting) the message.

-   Sending the credential offer message.

If the message requires any special processing, such as getting
information from a public ledger, or using a cryptographic primitive to
encrypt the message, the agent framework code handles that as well.
Since usually a first message is not going to be the only message of the
protocol (for example, Alice's agent is expected to reply to the
message), the agent framework also persists a protocol state object in
anticipation of the response to come. We'll talk more about that in the
next section.

## Receiving a Response

After the message is sent, the agent handles other work it needs to do.
For an enterprise agent such as Faber's, that might be hundreds or
hundreds of thousands of messages being exchanged with the agents of
other users. The message from Alice might take a long time to come back.
For example, the message might go to Alice's mobile agent while her
phone is not connected to the Internet because she is climbing a
mountain in the Andes. Alice won't receive the message until her phone
is back online, and even then, she won't respond until she's had a long
sleep to recover from her amazing mountain adventure. Plus she needs to
catch up on Instagram\...

Eventually, a response from Alice's agent is received---a credential
request message because Alice wants to be issued a credential about her
degree from Faber College. The agent framework code processes the
message (with help from the controller) as follows:

-   It uses the **\~thread** information to find the message's
    corresponding protocol state object and retrieves it from storage.
    In our example, the state object from the initial credential offer
    message.\
    - If it doesn't find the protocol state, there is an error in the
    message metadata, or if the message is found to be out of order, it
    will likely send an event to the controller to determine if it
    should send a problem report message back to Alice's agent.

-   It processes any other generic decorators, ones not intended to be
    processed by the message type handler, such as **\~tracing**.

-   It hands the message and the protocol state object to the
    appropriate message type handler. In this case, the credential
    request handler that is part of the issue credential protocol is
    invoked.

-   The message type handler processes the message, updates the protocol
    state object appropriately and (if needed) sends an HTTP request to
    the controller (a webhook) to provide info to the protocol state
    object.

-   The controller receives the information via the event webhook.

-   Since the agent framework code doesn't know how long it will take
    for the controller to respond to the event, it again persists the
    protocol state object and carries on with its other duties. Back to
    waiting for stuff to do\...\
    - Even some enterprise controllers might take a long time to
    respond. For example, perhaps the Faber College Student Information
    System is not connected to their Accounting System. Before they
    issue a credential, they have to email Accounting to see if Alice is
    fully paid up to the college and wait on a response. That could take
    hours...

-   The controller uses the information from the protocol state to
    figure out how it wants to respond to the message. In this case, it
    checks Alice's data in the Student Information System and decides if
    it's going to issue the credential and the claims that are to go in
    the credential.

-   The controller issues another call to the Aries administration API
    with information on how to respond to the previous message. It
    passes all the same types of information as with the first message
    (above), with the content including the claims to be put into
    Alice's verifiable credential. It also passes a reference to the
    protocol state object.

-   The agent framework code receives the request, retrieves the
    protocol state object, prepares and sends the message to Alice and
    updates and saves the protocol state object.

You're right---there's a lot going on there! The good news is the
sequence described above is the same for almost every request/response
transaction, and it is much like the processing of traditional web
servers---one layer handles the mechanics of receiving requests and
responding, and another layer figures out what the request is for and
how to respond. If you have done any web development, you've seen this
pattern before.

## Lab: Executing a Protocol

We only have one lab in this chapter, but it's a doozy! We're going to
use the OpenAPI/Swagger interface for ACA-Py that was introduced in the
last chapter to manually walk through a connection and credential
issuance process from Faber to Alice. There's no controller other than
you and OpenAPI/Swagger to receive and respond for each of the agents.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/OpenAPIController.md) to
jump into the lab.

## AIP's Impact on the Aries Developers Work

In Chapter 2, we talked about a key driver in the Hyperledger Aries
community---the Aries Interop Profile (AIP) ([RFC
0302](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0302-aries-interop-profile)),
and introduced the two AIP versions that have been defined to date, [AIP
1.0](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0302-aries-interop-profile#aries-interop-profile-version-10) and [AIP
2.0](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0302-aries-interop-profile#aries-interop-profile-version-20).
Let's talk about how AIPs and AIP versions impact you, an Aries
developer.

-   AIP versions reduce the number of protocols that you need to learn.
    AIP 1.0 includes just 19 RFCs and only six are Aries messaging
    protocols. AIP 2.0 increases the total RFC count to 34, but still
    includes just 10 protocol RFCs. In both versions, many of the
    non-protocol RFCs are addressed within the Aries framework and are
    not the concern of those building controllers. The bottom line?
    Despite the many RFCs in the aries-rfcs repo, the subset of
    \"getting started\" RFCs is really quite small.

-   As you select and configure an agent framework to use, you must be
    aware of the framework's AIP support and plans for supporting any
    upcoming AIP versions. As this course is being written
    (January 2023) that means focusing for the most part on AIP 2.0.

-   Another factor to consider in selecting and configuring your agent
    is what AIP versions are supported by other agents in the ecosystem
    in which you are participating. Building a \"latest and greatest\"
    issuer agent when there are no mobile wallets that support the
    \"latest and greatest\" is going to be frustrating.\
    - Of course, being stuck in \"old tech\" is also a problem.
    Encouraging and helping everyone move steadily forward is in all of
    our best interests.

-   Finally, while most of the hard work in supporting an AIP version is
    in the agent framework, controllers will be impacted in the form of
    changes and additions to the administrative API. Pay attention to
    the API endpoints you are using!

As a controller developer you should be aware of when AIP version
changes are coming and their potential impact on your controllers. That
means that you need to be plugged into the [Aries Working
Group](https://wiki.hyperledger.org/display/ARIES/Aries+Working+Group),
as that is the group that defines when new versions of AIPs will be
introduced. You also have to be aware of what's happening with the Aries
framework you are using. Chances are, there are community meetings and
regular updates for that.

## Lab: Executing Protocols Using JSON-LD Credentials

Remember when we said there is only one lab in this chapter? Well,
technically, we were telling the truth\... This lab is going to be
(almost) identical to the one you just finished, but this time instead
of using AnonCreds credentials, we'll be using W3C Standard JSON-LD
verifiable credentials using BBS+ signatures. So, the same lab, but
different! As you do this lab, note the differences (and similarities)
in issuing and presenting different format credentials. What would be
the impact on your controller in using the different types of
credentials?

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/OpenAPIControllerAIP2.md) to
jump into the lab.

## Reflections: New Protocols and Verifiable Credential Formats

All done? We think that's a pretty important lab for a couple of
reasons. Here are some things to reflect upon now that you've done the
lab. Twice.

The lab shows that the controller's job is pretty much the same,
regardless of whether you're using AIP 1.0 or AIP 2.0, or you are using
AnonCreds or JSON-LD credentials. Sure, there are some API differences
that have to be accounted for, but the core logic is pretty much the
same for the controller---get an event, decide what to do about it, do
it, and go back to waiting. And the events that are processed for AIP
1.0 and 2.0 are pretty much the same, even though they are using
different protocols.

The lab was also our first look at some of the differences between the
handling of Hyperledger AnonCreds and W3C Standard JSON-LD verifiable
credentials. AnonCreds schemas are simple (just a list of claims), so
managing them is pretty easy and AnonCreds credentials provide important
powerful privacy-protecting features. However, because their schema is
minimal, there is a lot of implied understanding between those issuing
the credentials and those holding and verifying them. The only built-in
information about how to use the claims in an AnonCreds credential is
the name of the claims. JSON-LD credentials provide the option to
create/use additional semantic information about the claims. Developers
for verifiers may find from the JSON-LD **\@context** links information
about the claims, their format, perhaps even localization information.
However, the additional Linked Data detail is a double-edged sword, as
it makes it harder for developers to write code for constructing and
managing them. Further, the currently available (January 2023) JSON-LD
verifiable credential signature schemes lack the privacy features of
AnonCreds.

Later in the course (in Chapter 7 which discusses mobile wallets), we'll
look at an emerging capability called Overlays Capture Architecture
(OCA) that provides a pretty simple way for issuers to provide a lot
more semantic information about AnonCreds credentials (or any other type
of credential), including a way for issuer to express their branding so
as to \"make credentials beautiful\" for users. We'll also briefly talk
about an initiative to format AnonCreds credentials in JSON-LD using the
W3C Verifiable Credentials Data Model Standard. That will eliminate both
the data model differences between AnonCreds and JSON-LD-based
credentials, and provide comparable access to the linked data semantic
data. In fact, the same JSON-LD credential can even have an AnonCreds
signature and a JSON-LD verifiable credential signature at the same
time.

## Chapter 5 Summary

We have covered a lot of information about the Aries protocols including
the details of the protocols you will use as you code them into your
controller. As you build your own application and need to know more
about the underlying details of the protocols, you know where to look,
right? Yup, the aries-rfcs repository!

Let's highlight the key takeaways from this chapter:

-   You need to know about the aries-rfcs repos but you don't need to do
    a deep dive (or even a shallow one) there until you have something
    specific to look up (for example, handling a particular protocol).

**NOTE**: Want to gain some points in the Aries community? If you find
something in an RFC that needs clarification, submit an issue or a pull
request to make things better. Such contributions
are **always** welcome.

-   With Aries, there are two levels of messaging protocols. Since all
    of the messaging is based on the exchange and use of DIDs, the
    overall messaging mechanism is called *DIDComm* (for DID
    communication).\
    - The DIDComm protocol handles the delivery of messages.

-   As an Aries application developer your focus is on the Aries
    protocols, the protocols that define back-and-forth sequences of
    specific messages to accomplish some shared goal. You don't need to
    know much about how the messages get delivered, just about the
    content of each message and the steps in the protocols.\
    - The Aries protocols define the content of the messages delivered.

-   As an Aries application developer, you also have to pay attention
    more to the APIs provided by the Aries framework you are using than
    to the nitty-gritty details of the protocols. You need to understand
    the protocols, but to use them, it's all in the API!

-   As a developer, you need to be aware of the Aries Interop Profile
    (AIP) to keep track of the versions of the Aries protocols that
    other developers and organizations are using so that your
    applications will be able to interoperate with theirs.

Easy, peasy, right?! You're well on your way to becoming a Hyperledger
Aries developer!

## Chapter 6 Overview -- DIDComm Message Router

So far in this course we have focused on how a controller injects
business logic to control the agent and make it carry out its intended
use cases. We have looked at how the controller manages the messages
being exchanged by agents and the format and range of the messages that
have been defined by the Aries Working Group. In this chapter, we'll
prepare you for the next chapter (\"Mobile Wallets\") by looking closely
at message routing---how messages get from one agent to another, and
especially the routing when a mobile wallet is involved. DIDComm routing
is applicable beyond mobile wallets, but it's required from mobile
wallets, so it is an important prerequisite for the next chapter.
Happily, a lot of what we cover in this chapter is important to know as
an Aries developer, but is largely just \"taken care of\" by the Aries
frameworks you will use.

## Learning Objectives

In this chapter (6), you will learn about:

-   Agent message routing, particularly the important roles of mediator
    and relay agents in DIDcomm messaging, and especially in the Aries
    mobile wallet use case.

-   What data about a message, its sender and its recipient is exposed
    to others as the message travels from one to the other.

-   What a mobile mediator is and why it is needed.

-   The role of the DIDDoc in message routing.

-   What happens when Aries agents establish a connection (in painful
    detail!).

## Delivering Messages from Sender to Recipient

Before we can cover mobile wallets in the next chapter, there is an
important digression we have to make in order to understand an important
requirement of mobile wallets. We need to cover the general topic of
Aries message routing---how a message gets from its sender agent to its
recipient.

Based on what we have covered in the course so far, it's easy to form a
mental model of agents interacting directly with one another; Faber
College has its enterprise agent, Alice has her mobile wallet app on her
smartphone and the two message one another whenever the need arises.
However, while two messaging agents appear to be directly connected,
they often are not. Mediator and relay (terms we will formalize shortly)
agents are often necessary to enable messages to be securely delivered
from the sender to recipient agent because:

-   Mobile wallets do not have an endpoint (a physical address) that
    other agents can use for sending messages. Thus, it is impossible
    for other agents to send messages directly to a mobile wallet app.

-   Entities may want to minimize correlation of their agent's messages
    across relationships and so instead of having a unique endpoint per
    agent, many agents share a common endpoint (for
    example, [https://agents-r-us.ca](https://agents-r-us.ca/)) such
    that their specific messages are \"hidden in a crowd\" of lots of
    other messages.

-   Entities may not want their inbound messages to be correlated to
    their outbound messages so they use different paths for sending and
    receiving messages.

-   An enterprise may want to have a single gateway agent for the use of
    the many enterprise agents they have in their organization. That
    way, only the gateway agent interacts with the big, bad Internet,
    and all the enterprise agents only talk to that gateway.

In the list above, the first one is a requirement, the others are
options. Happily, DIDComm was designed with these capabilities in mind.

When a DIDComm message is sent from one agent to another, it is routed
per the instructions provided by the receiver to the sender, and for the
outbound needs of the sender. For example, using the following picture,
Faber might be told by Alice to send messages to her phone (agent 5) via
agents 3 and 4, and Faber might always send out messages via agent 2.
That means a message from Faber to Alice actually involves 5 different
Aries agents, flowing from agents 1 to 5 via agents 2, 3 and then 4.

![Message flow from Faber to
Alice](images/image028.png){width="5.0in"
height="1.604575678040245in"}

**Message flow from Faber to Alice**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

When Faber and Alice communicate, they want their message to be
private---they don't want the routing agents to see the contents of
their message. So, when there are agents in the flow between the two,
Faber and Alice encrypt their messages with wrappers that provide only
enough information for each routing agent to send (route) the message
along on the next step of its end-to-end journey. These wrappers are the
equivalent to a postal service envelope with just a \"To\" address on
the outside of the envelope.

To carry the postal system analogy a bit further, suppose Alice and Bob
work in different offices of a corporation and need to send paper
messages to one another. Alice might write her message for Bob, put it
in an envelope for Bob, put that into an interoffice envelope addressed
to Bob, and then into a postal service envelope addressed to the office
in which Bob works. She mails the letter via the postal service and it
gets delivered to the mailroom at Bob's office. The postal envelope is
removed in the mailroom, and the interoffice envelope is used by the
internal mail system to get the letter to Bob. Bob takes the message out
of the interoffice envelope, and opens the inside envelope to read
Alice's message. This matches the DIDComm world exactly, with Alice
using encryption for the envelopes, and the postal service and mailroom
as routing agents to facilitate delivery.

## DIDComm Mediators and Relays

In DIDComm, the term **[mediator]{.underline}** is a routing agent that
the recipient has directed the sender to use when sending a message. In
our Faber-Alice example earlier, the mediators are the agents Alice
provides Faber through which Faber's message must be routed. If there
are no mediators, the message will go directly to Alice, so Faber's
agent need only encrypt the message for transporting the message to
Alice. For each mediator Alice adds, Faber explicitly adds another
envelope, another layer of encryption. Thus, Alice's \"list of agents\"
is just a list of encryption keys for Faber to use when preparing a
message for Alice.

**NOTE:** As an aside, the folks designing the DIDComm specification
have come up with some clever handling to prevent message bloat when
there are multiple encryption envelopes. When you repeatedly encrypt the
same content, the message can get quite large, and care has been taken
to prevent that.

The term **[relay]{.underline}** is used in DIDComm to indicate that the
message is being routed through one or more additional
agents **[without]{.underline}** the knowledge of the sender. The
important difference is that the sender must know about all recipient's
mediators and explicitly add envelope wrappers for each, whereas they
don't know (or care) about the recipient's relays. To stretch our Alice
and Bob paper message analogy a bit more, the mailroom in Bob's building
might deliver all the messages for Bob's floor to an assistant who then
distributes the messages to their intended recipients. Alice doesn't
know about that process, and doesn\'t add an envelope for the assistant.
The mailroom may add an envelope (encryption layer) around the message
for the assistant to open, so only they know the message is for Bob. And
since there is a final layer of encryption for Bob, none of the postal
service, mailroom or the assistant know what's in Alice's message for
Bob.

There is (of course!) an Aries RFC that covers mediators and relays in
more detail---[RFC
0046](https://github.com/hyperledger/aries-rfcs/blob/main/concepts/0046-mediators-and-relays/README.md).

To get back to our Faber and Alice picture, agents 3 and 4 are mediators
because Alice explicitly tells Faber, \"please send your messages to me
through those agents.\" Since Faber is sending its outbound messages via
agent 2, then agent 2 is acting as a mediator agent, but not because
Alice referenced, but rather because that's how Faber's agent is
configured.

## Mediators and Relays Are Agents Too!

An important item to underline here is that mediators and relays are
themselves DIDComm agents. They may only do routing activities, or they
may provide other services on behalf of their controlling entity. They
have a peer-to-peer relationship with other agents with which they
interact, and they use that channel to coordinate the routing they will
do on behalf of the sender and recipient agents, and to route the
messages.

## Message Encryption Handling

The DIDComm encryption handling is performed within the Aries
frameworks, and not really something a developer building applications
using an agent needs to worry about. Further, within an Aries agent, the
handling of the encryption is left to libraries---ultimately calling
dependencies from Hyperledger Ursa. To encrypt a message, the agent code
calls a **pack()** function to handle the encryption, and to decrypt a
message, the agent code calls a corresponding **unpack()** function. The
\"encryption envelope\" described in [RFC
0019](https://github.com/hyperledger/aries-rfcs/blob/main/features/0019-encryption-envelope/README.md) for
AIP 1.0 and [RFC
0587](https://github.com/hyperledger/aries-rfcs/tree/main/features/0587-encryption-envelope-v2) for
AIP 2.0 define variations for sender authenticated and anonymous
encrypting. With authenticated messages, the keys of the sender and
recipient are used together for the encryption, so the recipient knows
exactly who the sender is. With anonymous encryption, only the public
key of the recipient is used, so anyone who knows that key can send a
message. In DIDComm, authenticated encryption is generally used for all
\"sender-to-recipient\" message encryption, while anonymous encryption
is generally used only for messages to and from mediators and relays.
Much thought has also gone into repudiable and non-repudiable messaging,
as described in [RFC
0049](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0049-repudiation).

## Mediators, Relays and Privacy (1)

When messages pass through other agents there are some privacy
implications that need to be considered. It is tempting to simplify the
message handling as much as possible, but there are privacy reasons for
being careful about how to do that. In this section, we'll give you a
taste of the threats to privacy that are mitigated with DIDComm. Keep
these in mind as you think about deploying your DIDComm-based services.

Each time a mediator and relay agent receive a message and pass it on,
they can record information about the message---metadata. Even though
the agent can't see the content of the message, they know at least that
the message was sent, from where it was received, how big it is, when it
was sent and where it will go next. It is well known that with existing
communications systems, the collection of metadata can lead to major
invasions of privacy. Telephone metadata (who called who, when and for
how long), routinely collected by telcos, enables the detailed tracking
of an individual's social and business relationships. Facebook and
Google tracking your logins to other services provides them with
information on your interests and frequency of use of services. Internet
Service Provides (ISPs) can likewise learn about your interests by
tracking the websites you visit from your home computer and mobile
phone.

One of the goals in designing the DIDComm messaging protocol was to try
to limit the metadata exposed in passing messages. The use of encryption
for every wrapper and the minimal inclusion of information in the
envelope (just a \"To\" address for the next step in the route) limits
what metadata can be gathered. The use of multiple hops in the sequence
limits the agents from knowing the early and later steps in the flow.
From our Faber and Alice picture presented earlier in this chapter,
let's consider what *could* be collected by the agents. Assume messages
from all of Alice's connections come in via the agent 3 and 4 path, and
she sends all her outbound messages directly from her mobile wallet
(agent 5). Assume as well that agents 3 and 4 are used by many mobile
wallet users, in addition to Alice.

-   Every agent in the flow could try to decrypt the inner messages
    being passed along.\
    - As long as we are using updated, trusted encryption approaches
    this risk is mitigated---their decryption attempt would fail. That's
    covered by DIDComm messaging.

-   Agent 2 can see that messages are coming from Faber's agent and
    going to the physical address of agent 3. Again, as long as
    people/organizations other than just Alice are using agent 3 as a
    physical endpoint, agent 2 doesn't know who the ultimate message
    recipient is.\
    - This is a concept called \"lost in the crowd.\" Many people
    receive their messages at common physical endpoints, and the senders
    (and other Internet observers) don't learn anything about the
    ultimate sender or receiver (e.g., Faber or Alice).

-   Agent 3 can see the physical address from which a message came
    (e.g., from 2). However, it can't see from where agent 2 got the
    message, so unless all and only Faber's messages come from agent 2's
    physical IP address, it won't know the message is from Faber.

-   Since agent 3 routes lots of messages via the agent 4 mediator,
    agent 3 does not know the message from Faber is for Alice.

## Mediators, Relays and Privacy (2)

-   Agent 4 (Alice's mobile wallet mediator) knows every time Alice
    receives a message and when she picks up the messages.\
    - This is the same for almost any mobile application operating in
    conjunction with a cloud service.\
    - While not yet (as far as we know) implemented, in theory, Alice
    could have several mediators using different ones for different
    connections, reducing the overall picture each has of her
    activities.

-   Agent 4 does not know from whom the messages were received, since
    they all come from Agent 3. And, since Alice is only using Agent 4
    for inbound messages, agent 4 does not know anything about Alice's
    outbound activities.

-   For a mobile wallet, the data sent between the mediator and the
    mobile wallet flows through the mobile internet service provider
    (ISP) that Alice is using. The ISP likewise can know when all the
    messages are flowing (inbound and out), but cannot decrypt the
    content of the messages.

-   The recipient agent (mobile or otherwise) can see the decrypted,
    plaintext data of all of the messages so that data can be displayed
    for the user. Of course this is necessary and assumed, but from a
    privacy and security perspective, it should be considered as a risk.
    What if the Aries agent you are using is scraping the plaintext data
    presented on screen and sharing it with other parties?

Those are at least some of the privacy threats to consider. A
security/privacy maven would likely be able to find others. In
comparison with the examples we gave (telcos, \"login with\" services,
ISPs), the amount of exposed metadata is far less with DIDComm.

In theory, by using different vendors for different agents you could
further reduce the metadata each participant can gather. But that comes
with its own challenges---for example, the need to engage with each of
the different vendors. Other techniques have been suggested. These
include:

-   Randomly sending \"no-op\" messages to reduce the knowledge gained
    about when you send/receive messages.

-   Adding a chunk of throwaway data to messages to alter the size of
    the message.

However, these complicate the creation of controllers and frameworks and
few are doing that. It's all about tradeoffs.

In the remainder of this chapter, we'll focus on the mobile agent and
mediator use case, the only required use of a mediator in an ecosystem
of DIDComm agents.

## Lab: Using a Mediator

Enough theory. Let's see some routing agents in practice. The [Aries
Mediator
Service](https://github.com/hyperledger/aries-mediator-service) repository
implements an Aries mediator that you can deploy for testing and
ultimately for production use cases. Currently, the mediator service is
a configuration of an ACA-Py Aries framework as a mediator. In this lab,
we'll deploy our familiar Alice and Faber ACA-Py agents, but this time
with a mediator in front of each of them.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/MediatorLab.md) to
get started on the mediator lab.

## Things to Consider When Developing a Mobile Agent

It would be much more interesting to talk about Aries mobile wallets (as
we'll do in the next chapter---stay tuned!), so why the in-depth look
into message routing? While routing is an important thing to understand
about DIDComm and Aries agents in general, it is especially important
for mobile wallets---mediators are a requirement for using Aries
wallets.

As noted earlier in the chapter, other agents cannot send data directly
to mobile wallets. All data that gets to any mobile application
(wallets, games, email---any app) does so via the mobile app making a
request to receive the data. As such, Faber's agent cannot directly send
a message to Alice's mobile wallet.

In theory, Alice's wallet could directly ask Faber's agent for any
messages it is holding for Alice, but that's impractical. Alice's wallet
agent cannot be continuously sending requests to all of her connections
to ask \"Have you got a message for me?,\" on the off chance that they
do.

\"Wait!,\" you say, what about all those notifications I get on my
phone? Couldn't those be used to send DIDComm messages to mobile
wallets? While there is some ability to send notifications to a mobile
app, the use of notifications is restricted by mobile operating system
vendors (for example, Google and Apple). Only registered services may
send notifications to an app, so the many arbitrary agents that might
connect with a wallet can't use OS level notifications for messaging the
wallet. Further, mobile operating systems limit the volume of
notifications that can be sent, and require that notifications have an
associated message displayed to the user when sent. As such,
notifications cannot be used as a way to send Aries/DIDComm messages to
a mobile wallet.

The bottom line is that in order to operate, a mobile wallet *must* have
a mediator agent through which all inbound messages must flow. As a
result, if you are thinking about deploying a mobile wallet, you also
have to think about how you will deploy a cloud-based mediator agent,
how it will be architected and what features it will provide.

![Things to Consider When Developing a Mobile
Agent](images/image029.png){width="4.0in"
height="3.38300634295713in"}

**Things to consider when developing a mobile agent**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## Mobile Wallets and Trust

As mentioned in the earlier section on privacy, the mediator for a
mobile wallet will know more than any other about their clients
messaging activity---timing of inbound messages, when messages are
picked up, information about your mobile app (for example, the ISP and
other information to connect with your mobile wallet) and your use of
any other services it provides. This is the same for any mobile
application with an associated web service.

The difference between Aries agents and other mobile apps is that in
many cases, Aries agents hold cryptographic keys that should be tightly
controlled by the owner of those keys. Where those keys reside and how
they are accessed is therefore paramount in the client trusting the
agents. In particular, the private keys that enable Aries protocols such
as verifiable credential exchange, should be under the complete control
of the agent's owner, and ideally protected by a secure hardware enclave
such as is provided on mobile phones. That gives the owner confidence
(trust) that the wallet interface is the only way to access the agent
and all that it is protecting.

A suggestion we often hear from developers new to the community is about
making a mobile wallet that resides on the cloud as a web service and
has only the user interface on the mobile phone. This is easy to do with
(for example) ACA-Py since you would only be building an Aries
controller on the mobile device. The problem with that approach is that
all of the owner's keys would reside on the web service infrastructure
and would not be under the direct control of the owner. The owner would
have to trust that the web service would not do anything with the
private keys they are holding for the owner. That's a big leap compared
to having the keys locally, and not one we would recommend taking
lightly.

So, while it is tempting with Aries to build centralized components, as
is often effective in other business domains, be careful in doing that.
Make sure that the control, particularly of private keys and the use of
those private keys is as close to the owner as possible. Using cloud
services run by vendors that are just passing along encrypted messages
is likely safe enough and necessary. Using cloud services run by vendors
that are (for example) actually receiving credentials and proving claims
about an entity (a person or an organization) must be considered with
skepticism.

An alternative that some are looking at is keeping much of the secure
storage data in the cloud, but keeping certain private keys on (for
example) a mobile device (perhaps several!) such that the data in the
cloud cannot be used by anyone other than the owner of the data. It's an
interesting approach, and one that might be viable and useful!

## Adding a Mediator

To this point in the course when we've talked about establishing a
connection, we've assumed the two agents are able to talk *directly* to
one another. When we establish a connection from a mobile agent, we add
the need to include a mediator into the process. As you will see, this
process seems to be (ok, it *is*) pretty complicated, and it's useful to
understand what's happening. The good news is that for an Aries
developer building and deploying an Aries application, the details of
using a mediator is a deployment and configuration issue, and not a
coding issue. We'll cover some of the details at the end, but once you
configure your mobile wallet app (or cloud agent) to use a mediator, and
optionally, deploy your own mediator, everything else should be taken
care of automatically by the Aries framework. And for other agents
(issuers, verifiers) connecting to a mediator-using mobile wallet, there
is nothing to do. Everything needed for delivering messages to the
mobile wallet will be automatically handled by the Aries framework.

## The Scenario

Here is a picture of the scenario we're going to go through. Faber is an
enterprise agent (an issuer/verifier) and is establishing a connection
to Alice, who uses an Aries mobile wallet. The maker of Alice's mobile
wallet has deployed a mediator that is used by all of the mobile wallet
apps that have been installed on their customers' mobile phones. This is
the common case in use today, and makes our picture simpler than our
earlier example, as there are only 3 agents involved, and two hops for
the message to go from Faber to Alice. We'll keep the numbering from the
earlier image, so Alice's mediator is still agent 4.

![Faber Sending Messages to Alice --- Common
Case](images/image030.png){width="5.0in"
height="1.604575678040245in"}

**Faber sending messages to Alice --- common case**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## The Scenario: All the DIDs

DIDs and DIDDocs are generated by each participant for each relationship
they have. That includes:

-   Alice for Faber

-   Faber for Alice

-   Alice for the mediator

-   The mediator for Alice

That's a total of 4 DIDDocs that are needed. Note that only a single
Alice/mediator connection is needed, regardless of how many connections
Alice has with other agents. For example, if Acme and Alice connect,
only two additional DIDDocs are added (Alice for Acme, Acme for Alice).

## The Scenario: DIDDoc Data (1)

From a routing perspective, the important information in the DIDDoc is
the following (as defined in the DIDDoc Conventions [RFC
0067](https://github.com/hyperledger/aries-rfcs/blob/master/features/0067-didcomm-diddoc-conventions/README.md)).
Recall that a DIDDoc is what you get when you resolve a DID, regardless
of where that DID is published (and even if it is not published).

-   The public keys for agents referenced in the routing.

-   A service element of type did-communication, including:\
    - the one **serviceEndpoint**\
    - the **recipientKeys** array of referenced keys for the ultimate
    target(s) of the message\
    - the **routingKeys** array of referenced keys for the mediators

Shown below is an example of these elements of a **service** definition
section of a DIDDoc. We saw this in the mediators lab we did earlier. In
this example, there is one recipient of the message and one mediator.

**{**\
**  \"service\": \[{**\
**    \"id\": \"did:example:123456789abcdefghi#did-communication\",**\
**    \"type\": \"did-communication\",**\
**    \"priority\" : 0,**\
**    \"recipientKeys\" : \[ \"did:example:123456789abcdefghi#1\" \],**\
**    \"routingKeys\" : \[ \"did:key:98490275222\" \],**\
**    \"serviceEndpoint\": \"https://agent.example.com/\"**\
**  }\]**\
**}**

Let\'s look at the did-communication service data in the DIDDocs
generated by Bob\'s mobile and mediator agents for the set of
relationships involved. Recall that there are three relationships, and
with two DIDDocs per relationship, we have six(!) DIDDocs to look at.
Note the term \"key reference\" all through the following tables. In
most cases, that will be an instance of a \"did:key.\" Recall from our
discussion in Chapter 4 that \"did:key\" is a plain public key and key
type that is formatted as a DID. An example of a \"did:key\" is in the
JSON above.

![](images/image031.png){width="6.0in"
height="5.084033245844269in"}

## The Scenario: DIDDoc Data (2)

![](images/image032.png){width="6.0in"
height="2.6957983377077865in"}

![](images/image033.png){width="6.0in"
height="4.908683289588802in"}

![](images/image034.png){width="6.0in"
height="4.5198884514435695in"}

## The Scenario: The null ServiceEndpoint

The null **serviceEndpoint** for Alice\'s mobile wallet is worth a
comment. As discussed previously, mobile apps work by sending requests
to servers and receiving back data. The server has no way to directly
initiate sending data to the mobile app, and the mediator for a mobile
wallet is no different. So how does the wallet get its messages from the
mediator?

Two techniques are commonly used by Aries wallets to get messages from
the mediator. For mobile wallets, the most common is to open a [web
socket](https://www.wallarm.com/what/a-simple-explanation-of-what-a-websocket-is) with
the mediator, allowing the mediator and the wallet to send messages to
one another while the connection is open. This is a common technique in
messaging apps, and is equally appropriate for an Aries mobile wallet.
Alternatively, a DIDComm protocol called Transport Return Route ([RFC
0092](https://github.com/hyperledger/aries-rfcs/tree/main/features/0092-transport-return-route))
defines how a mediator can put DIDComm messages for its mediator clients
(including mobile wallets) into the response of an HTTP request from the
mobile wallet.

Either way, the flow of messages is the same.

-   When there is no connection to the wallet, the mediator queues up
    any message for that wallet.

-   A wallet uses either web sockets or DIDComm return route to initiate
    a connection.

-   While the connection is open, the mediator sends the queued up
    messages to the wallet.

With web sockets, the connection might remain for some time and after
all the queued up messages are sent, arriving messages can be sent right
along using the open connection.

With return route, the wallet sends an HTTP request with
the **\~transport** decorator specifying the use of **return_route**,
and the mediator uses the HTTP response to send one or a batch of
DIDComm messages from the queue to the wallet, and the connection ends.
Unlike with web sockets, the wallet must keep polling the
mediator---sending HTTP requests containing DIDComm messages---to
receive more messages from the mediator. There are messages
(**batch-pickup** and **noop**) defined in [RFC 0212
Pickup](https://github.com/hyperledger/aries-rfcs/tree/main/features/0212-pickup) specifically
defined for picking up messages using the return route protocol.

## The Scenario: Preparing Alice's DIDDoc for Faber

Given that background, let\'s go through the sequence of events and
messages that occur when Alice and Faber first connect so that Alice\'s
agent can construct the service element of the DIDDoc to send to Faber's
agent:

-   Initialization: Alice and the mediator

-   Connecting to Faber

-   Completing the connection

## Initialization: Alice and the Mediator

Before Alice's wallet can connect to Faber (or any other) Aries agent,
Alice's wallet must do a one-time setup of her inbound routing using a
mediator. To do that, Alice's wallet establishes a DIDComm connection
with the mediator, and asks it to mediate for her. A protocol called
\"coordinate-mediation\" ([RFC
0211](https://github.com/hyperledger/aries-rfcs/tree/main/features/0211-route-coordination))
is used to create the mediator relationship between a mediator and a
client of the mediator. The protocol has a few messages that we'll use
in the following processes:

-   **mediate-request**: An agent (e.g., Alice's mobile wallet) asks a
    mediator to provide mediator services such as forwarding messages to
    the requesting agent.

-   **mediate-grant**: The mediator agrees to provide mediation
    services, and gives a key reference (usually a \"did:key\") that the
    requesting agent can share with their connections in
    the **routingKeys** array.

-   **keylist-update**: While establishing a connection, the requesting
    agent sends a key reference to the mediator for the new connection
    to say in effect, \"when you see a message for this key, please send
    it to me\". The mediator maintains a routing table consisting of a
    list of all of its client wallets, and for each wallet, the set of
    keys it has registered. As messages are received, the mediator looks
    up the key from the message, finds the corresponding wallet, and
    delivers the message to the wallet.

Alice's agent and the mediator agent establish their relationship as
follows:

-   Alice's mobile wallet (somehow) connects using DIDComm to the
    mediator agent (agent 4 in our picture).\
    - We say \"somehow,\" because there are several ways to do this.
    Often the wallet maker will put a hard-coded DIDComm invitation into
    the wallet and the connection will happen automatically during the
    installation and initialization of the wallet. Alternatively, the
    connection might be triggered by a link in the app. Alice might even
    find and use a public mediator service, independent of the wallet
    makers, and use that as her mediator.

-   Once connected, Alice's mobile wallet sends a \"mediate-request\"
    message to the mediator agent.

-   The mediator agent (presumably) agrees, and sends back a
    \"mediate-grant\" message with a public key and endpoint for the
    mediator. Alice will use the public key in DIDDocs for her
    connections to other agents (such as Faber).

As previously mentioned, either web sockets (most likely) or [RFC 0092
Transport Return
Route](https://github.com/hyperledger/aries-rfcs/tree/main/features/0092-transport-return-route) protocol
will be used by Alice's mobile wallet to get messages from the mediator.

## Connecting to Faber

Let's assume that Alice\'s mobile wallet receives an out-of-band
connection invitation message from Faber---perhaps via a QR code or a
link in an email. The steps for Alice to follow to prepare her side of
the Alice-Faber connection is as follows:

-   Alice\'s mobile wallet generates a new DID for Faber and prepares
    and partially completes a DIDDoc, including the (new) public key(s)
    that she will use when sending messages to Faber.\
    - The **did-communication** service's **serviceEndpoint** is
    (usually) the mediator endpoint. See an alternate approach below.\
    - The **recipientKeys** array is populated with a DID containing
    Alice's public key(s) for Faber.\
    - The **routingKeys** array is populated with a DID referencing the
    public key that Alice received earlier from her mediator agent.

-   Before sending the response to Faber, Alice first lets the mediator
    know that messages using the new **recipientKeys** for Faber should
    be sent to Alice.\
    - To do this, Alice sends a \"keylist-update\" message to the
    mediator. The mediator is now routing messages sent by Faber to
    Alice's agent.

Faber, on receipt of the Alice-for-Faber DIDDoc, resolves the DIDs in
the DIDDoc. The mediator might use a did:key DID, and the mediator's
endpoint for receiving messages will be put in
the **serviceEndpoint** in the Alice-for-Faber DIDDoc. Alternatively,
the mediator might use a public DID and Faber will resolve that DID by
looking for it on a public ledger. Such a DID might have the endpoint
for the mediator in that DIDDoc's **serviceEndpoint**. By doing that,
the mediator, which presumably has many users, each with many
relationships, can just update its public DID information to, for
example, rotate its key, rather than having that done by every user of
the mediator, for every relationship they have. The downside of that is
that Faber has to regularly check the public ledger for changes to the
mediator's DIDDoc.

## Completing the Connection

With Alice's DIDDoc for Faber ready, Alice uses the endpoint provided in
Faber's invitation to send a connection-request message to Faber with
the new DID and DIDDoc. Faber now knows how to get any DIDComm message
to Alice in a secure, end-to-end encrypted manner. When Faber sends
messages to Alice\'s wallet, it uses the information in the DIDDoc to
securely send the message to the mediator endpoint, from which it is
retrieved by Alice\'s mobile wallet. Connection established!!

Based on the DIDDoc that Alice has sent Faber, the following are the
steps that Faber carries out in order to send a DIDComm message to
Alice:

-   Prepares the message for Alice\'s wallet.

-   Encrypts and places that message into a \"forward\" message for
    Alice\'s mediator.

-   Sends that message to the mediator endpoint.

## Adding Mediators and Relays (1)

Let's take a quick look at one more scenario, one that adds more steps
to the routing and the resulting privacy. Back to our original Faber and
Alice picture from the start of the chapter. We'll define the
relationships but not go into all of the details we've already covered
about initializing wallets, setting up the mediator relationships, and
so on. We do recommend you think about what those steps will be as we go
through the scenario. Back to this picture:

![Message flow from Faber to
Alice](images/image028.png){width="5.0in"
height="1.6045745844269466in"}

**Message flow from Faber to Alice**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

Faber is configured to use an outbound mediator (agent 2) to send
messages. In reality, there is not an implementation (of which we are
aware) of an outbound mediator, but it is conceptually even easier to
implement than an inbound one. We will not worry about Faber's inbound
message path. Alice's wallet (5) is going to use a mediator, agent 3 as
an agency endpoint, and agent 4 as the mediator we discussed in the
previous section. When the scenario is all set up, and all the
connections are established, here is what happens when Faber's agent (1)
sends a

-   Faber's wallet prepares and encrypts the message for Alice\'s
    wallet.

-   Faber's agent encrypts and places that message into a \"forward\"
    message for Alice's mediator.

-   Faber's agent encrypts and places that message into a \"forward\"
    message for Alice's agency endpoint mediator.

-   Faber then encrypts and places that message into a \"forward\"
    message for Faber's outbound mediator.

-   Faber's agent sends that message to the outbound mediator endpoint.

-   Faber's outbound mediator decrypts the message and using the \"to\"
    address on the decrypted message, sends it to Alice's agency
    endpoint.

-   The agency mediator decrypts the message and using the \"to\"
    address on the decrypted message, sends it to Alice's mediator.

-   The mediator decrypts the message and sees from the \"to\" address
    that it is a message for Alice.

-   If there is an active websocket connection available with Alice's
    wallet, the mediator immediately sends the message along. Otherwise,
    the mediator queues the message up, waiting for Alice to retrieve
    it.

-   Finally, once Alice's wallet has the message (!), it decrypts and
    processes it.

## Adding Mediators and Relays (2)

**NOTE**: The first two \"forward\" messages are required because of
what Alice put into her DIDDoc for Faber. The third is independent of
what Alice's wallet requires and is needed because of how Faber's agent
has decided its outbound messages should be handled.

Why would Faber want an outbound mediator, and Alice (or her wallet
maker) want an agency mediator? It's all about privacy. Suppose Faber's
outbound mediator was used by many other agents. No one observing the
outbound mediator's traffic would know which one sent any particular
message. Likewise, suppose many mediators (like Alice's mediator (agent
4) shared an agency mediator endpoint. No one observing messages going
into the agency endpoint would know for whom they were destined, and the
mediators would not know from whom the arriving message was from. Much
like a Tor network, privacy is added by configuring routes that make it
harder for observers to identify traffic going from any particular agent
to any other.

Wow... there is a lot to DIDComm messaging and routing! As mentioned
earlier, all of this complexity is hidden from the developer of Aries
applications so the use of mediators (or not) has little to no impact.
Those deploying Aries applications with mediators and relays need to
know how to configure their agents, but the Aries frameworks handle
everything after that. Finally, those deploying mediators and relays
need to know how to configure them, but again, that is mostly about
configuring the deployment rather than developing it.

## Chapter 6 Summary

What did we learn in this chapter? Lots about routing, including why it
is needed, how it is implemented, particularly in the mobile wallet use
case (where it is a requirement), and how connections are established
when mediators and relays are involved. Here are the key takeaways from
the chapter.

-   Agents are often not directly connected, and in fact,
    sometimes *cannot* be directly connected (for example, mobile
    wallets).

-   Mediator agents play a key role in Aries agent routing and are
    required for Aries mobile wallet apps. If you are developing mobile
    apps, you will need to consider how you will deploy your cloud-based
    mediator agent.

-   During connection establishment, each agent provides instructions
    (in DIDDocs) for how the other agent should prepare messages (how
    many encryption envelopes), and to what endpoint the message should
    be sent.

## Chapter 7 Overview -- Mobile Wallets

Mobile wallets are a crucial part of the Aries ecosystem, providing
people with a user-friendly, convenient way to receive credentials that
they can use by presenting authoritative data to verifiers. They are
also pretty fun to use, and extraordinarily helpful in understanding how
these new approaches to sharing data change everything. Aries mobile
wallets have been around since about 2018, and it's exciting to see how
the capabilities have evolved. As of writing this (January 2023), the
focus on mobile wallets is not about making them work (we're long past
that stage!) but rather about the user experience of wallets---how to
make the technology as accessible as possible for people to use in their
everyday lives.

## Learning Objectives

In this chapter (7), you will learn about:

-   The features of mobile wallets right now.

-   The features of mobile wallets that are in progress and soon to be
    available.

-   Open source Aries mobile wallets and especially, the Aries Bifold
    project.

-   How you can easily deploy a customized version of Aries Bifold, with
    your own unique features, without having to fork the Aries Bifold
    project.

-   Other open source mobile wallets.

Let's jump in!

## What Are the Aries Mobile Wallets Used For

Aries wallets are much like any other Aries agent we've talked about in
the course. They embed a framework that handles all of the core Aries
functionality---establishing connections, managing secure storage,
exchanging credentials, and so on. As wallets are people-centric, they
are also credential holder-centric, with the user experience currently
built around the idea of connections, receiving credentials, receiving
presentation requests and sending presentations. The following are a set
of approaches and capabilities that are in Aries wallets, being worked
on, or being considered as of this writing (January 2023).

## Basic Capabilities and User Experience

All Aries wallets support a common core set of capabilities.

On first startup, the wallet is initialized, setting up the wallet's
secure storage and setting up some sort of access security, either
mobile OS biometrics, an application PIN, or both. Terms and conditions
for use are usually presented. A \"getting started\" tutorial is often
offered, to help new users understand the wallet. A mediator connection
is established, either automatically, or with some input from the user.
The mediation initialization sequence we talked about in the last
chapter is completed.

![Screenshot from an open source Aries mobile wallet
application](images/image035.png){width="2.0in"
height="4.330103893263342in"}

**Screenshot from an open source Aries mobile wallet application**\
By [Government of British
Columbia](https://www2.gov.bc.ca/gov/content/governments/government-id/bc-wallet)

An important note about startup is that when the wallet is secured using
a biometric (fingerprint or face recognition), the operation is done
entirely on the device. The biometric is not stored by the wallet and is
not shared outside the wallet with anyone---the mobile OS maker, the
wallet maker, the issuer, holder or verifier, and it is definitely not
put on any sort of public ledger.

Once the wallet is initialized, users have a \"front and center\" button
to trigger the scanning of QR codes. QR codes are currently the favored
method of establishing connections and receiving credentials from
issuers, or to receive presentation requests and send presentations in
response. Once a connection has been established, the \"other side\" can
send other Aries messages without needing to reestablish the connection,
so an issuer might send presentation requests and get presentations as a
prelude to issuing a credential, all using the same connection.

As both credentials and connections are collected, corresponding lists
are created and made accessible to the wallet owner. We'll talk about
that next.

## Credential and Connection Lists

An interesting debate in the Aries wallet community is if either (or
both) of the lists of credentials or connections (aka \"contacts\")
should be a primary focus in wallets. As long as the use of the wallet
is driven by other agents (issuers and verifiers) and not the wallet, it
mostly doesn't matter.

-   The wallet's internal framework \"knows\" what connection is asking
    for something, and the wallet user interface lets the user know who
    it is. Users don\'t have to find for themselves who it is in their
    list of contacts.

-   When presentation requests are received, the wallet's internal
    framework looks up what credentials the user has to satisfy the
    request, shows them and asks for confirmation to respond with a
    presentation. The user doesn't have to rifle through their list of
    credentials manually to find the credentials needed.

Current uses of the credential and connections list in most Aries
wallets are to get a history of each. When was a connection established,
what interactions have occurred with it? When was a credential received,
and when has it been used, what data was shared, and with whom? Neither
connections nor credentials are needed for initiating actions, and so
far, most wallets have made scanning QR codes the main focus. Providing
a way to see the list of credentials, or connections is a secondary
action.

The debate will be settled by what features are added to the wallet, and
especially what capabilities can be initiated from individual
credentials or connections. Some of the wallet approaches and
capabilities in this section describe instances of both. As those
features are added, the \"credentials or connections\" debate will be
resolved, one way or the other. The answer might even be both, as we see
in this image from the [Lissi wallet](https://www.lissi.id/).

![Screenshot from the Lissi Aries Mobile Wallet
App](images/image036.png){width="2.0in"
height="4.330103893263342in"}

**Screenshot from the Lissi Aries mobile wallet application**\
By Neosfer

Which do you think is the right choice?

## Credential Types and Ledgers

All Aries wallets to this point (as far as we know) have used
exclusively AnonCreds credentials and Hyperledger Indy ledgers. This is
because of a combination of the project history (Aries roots in Indy),
its privacy-preserving features, and because AnonCreds are easier to use
(at least from a business and developer perspective) than other
credential types. The \"ease of use\" is because AnonCreds makes a lot
of decisions about how issuers, holders and verifiers interact that are
otherwise left up to implementers with other credential types. Support
in Aries wallets for other credential types will come over time, but
only after decisions are made or capabilities defined that enable
interoperability, at least within Aries, and ideally with non-Aries,
verifiable credential implementations.

For wallets using Indy, a second issue that Aries wallet deployments
must decide is which Indy ledgers they will support. The basic approach
most wallet deployments have taken is to support some common testing
ledgers (so experimenting, especially for developers, is easy) and the
production ledgers that are most likely to be used by their customers.
Some common test ledgers are the BCovrin Test ledger (a pure sandbox
ledger intended only for developers), the Indicio TestNet and DemoNet,
and the Sovrin TestNet. Once the more modern \"did:indy\" DID method is
in use that supports dynamically connecting to Indy ledgers as needed in
resolving DIDs, Aries wallets need not be so concerned about deciding up
front the networks they support; they can tell from the DID they are
resolving what ledger to read.

## Beautiful Credentials and OCA for Aries

As Aries wallets have matured, pressure was added by business users to
\"make credentials beautiful.\" Notably, they wanted issuers to have
some control over how their credentials looked like in wallets,
primarily for branding, and they wanted credential information displayed
in users native languages (English, French, Spanish, and so on), with no
\"techo-babble\" visible (e.g., \"given_name\"). As was once said at an
SSI-focused conference, \"if an end user ever sees a DID, we have
failed.\" The response of the Aries community to that challenge has been
to use a capability called [Overlays Capture
Architecture](https://humancolossus.foundation/blog/cjzegoi58xgpfzwxyrqlroy48dihwz) (OCA).
While we won't go into the OCA standard here, the use of OCA for the
Aries credential use case allows issuers to convey, in a nice,
well-defined and easy to create structure, the following items to
holders and verifiers.

-   The name of, and a description for, the credential and the issuer,
    in multiple languages.

-   Help/support information about the credential, in multiple
    languages.

-   Language specific links to website pages with information about the
    issuer, and how to get support about the issuance and use of the
    credential.

-   Labels for, and help information about, each claim (attribute) in
    the credential, in multiple languages.

-   The data type and format of each claim in the credential, so that
    the holder and verifier can properly render the attribute data on
    screen.

-   A series of branding elements (images, colors, etc.) that allow the
    issuer to convey both their brand identity and the important
    attributes in their credential.

The image below shows the same credential with no OCA support and with
OCA support, displayed first in English, and then in French. Note in the
image the different \"date\" renderings, the raw date in the first, and
then the user setting rendering in the next two.

![OCA for Aries in action!](images/image037.png){width="6.0in"
height="3.5535017497812773in"}

**OCA for Aries in action!**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

OCA is a powerful (and beautiful!) addition to Aries. We won't go deeper
into OCA for Aries in the course, and we don't have a lab for it, but if
you are interested in learning more, see [RFC 0755 OCA for
Aries](https://github.com/swcurran/aries-rfcs/tree/oca4aries/features/0755-oca-for-aries) and
its sibling, [RFC 0756 OCA for Aries Style
Guide](https://github.com/swcurran/aries-rfcs/tree/oca4aries/features/0756-oca-for-aries-style-guide).
It's fun stuff!

## Advanced Chat and Actions Menu

A powerful by-product of establishing a DIDComm connection with another
agent is the secure, private communications channel between the
participants that can be used for much more than just issuing
credentials and presenting proofs. In earlier times, the telephone was a
\"trusted\" channel between contacts, such as between you and your bank.
But now, numbers can be spoofed and there are more scam phone calls than
legitimate ones. Emails were, for a time, a trusted medium, but email
addresses can also be spoofed and phishing attacks are common. SMS
messages are the same. People are pleaded with to ignore/delete emails
and texts from supposed enterprise contacts, especially ones asking the
user to take some sort of action, such as clicking on a link. In 2023,
any attempt by an enterprise to initiate an unexpected, legitimate
interaction with you is very likely to be ignored because the trust in
the available communication channels is gone.

A DIDComm connection is a way to bring that trust back, giving both
parties a reliable way to initiate communications with one another. A
bank, wanting to warn you of potential fraud related to the use of your
credit card, can send you a DIDComm message that you will know came from
the bank. The driver's license authority can send you a DIDComm message
to notify you that your license (and related verifiable credential)
needs to be renewed. On the other side, you can initiate a message from
your wallet that goes directly to (for example) the call center of a
contact, with them knowing exactly who you are---no further verification
needed (no more being asked \"What is your mother's maiden name?\").
Some organizations, such as Bloqzone in the Netherlands have created an
SSI-powered customer contact framework so that your call center team
members can **[reliably]{.underline}** know the customer calling before
they say hello---no questions asked.

Another feature that is showing promise in the Aries community is one
called Action Menu ([RFC
0509](https://github.com/hyperledger/aries-rfcs/blob/main/features/0509-action-menu/README.md)).
Action Menu is kind of like a telephone Interactive Voice Response (IVR)
system, the \"Press 1 for order status information, press 2 to submit an
order and press 3 for any other issue.\" With Action Menu, one contact
sends a multiple choice menu of options, and the other side picks one of
the answers, either triggering an action or perhaps, triggering a
sub-menu of more options. Since your wallet is a much more powerful data
entry tool than a phone keypad, the action menu options can be more
sophisticated, but the concept is the same. In the screenshots below
from the [2060.io](https://2060.io/) wallet, you can see that the user
has clicked into a contact, requested their \"main menu,\" and is
showing the (important!) options.

![Aries DIDComm Wallet for Chat: Chat List, Chat, Action
Menu](images/image038.png){width="6.0in"
height="3.8588232720909885in"}

**Aries DIDComm wallet for chat: chat list, chat, action menu**\
By [2060.io](https://www.2060.io/)

Several companies in the Aries space,
including [2060.io](https://www.2060.io/) and RootsID, are building out
chat-centric Aries wallets that use DIDComm connectivity as the basis
for both identity capabilities and trusted messaging. It's a powerful
combination!

For wallets that embrace messaging, incorporate action menus into their
offering, and make it easier for you to initiate interactions with your
connections, it's likely that the credential- vs. connection-centric
wallet debate discussed earlier will lean towards connection-centric.

## Governance: Trust the Issuer, Trust the Verifier, Trust the Holder (1)

As we've seen with telephone, email, websites, SMS and other
communications systems, it can be easy to establish a communication
channel, but harder to know that the party on the other side of the
conversation is trustworthy. While a big part of SSI is enabling
decentralization, we also know that there needs to be mechanisms put in
place to enable human trust on top of the cryptographic verifications
enabled by the use of, for example, DIDComm and AnonCreds credentials.
The [Trust over IP governance
framework](https://trustoverip.org/news/2022/02/01/the-toip-foundation-releases-its-first-official-governance-specifications/) exists
to define ways to allow creating layers of trust. This image from
the [Trust over IP Trust Registries Task
Force](https://wiki.trustoverip.org/display/HOME/Trust+Registry+Task+Force) shows
the key questions that need to be asked by the participants in a Trust
ecosystem of issuers, holders and verifiers.

![Establishing Trust in an
Ecosystem](images/image039.png){width="6.0in"
height="3.374790026246719in"}

**Establishing trust in an Ecosystem**\
From [Trust over IP Foundation](https://trustoverip.org/)

For a wallet user, the big questions are about what issuers and
verifiers should be trusted. If I am offered a connection and to be
issued a credential, should I accept and trust the issuer? If I am given
a presentation request, should I trust the verifier? For the wallet
makers, the challenge is to add capabilities to the wallet to help the
user. This is a very large topic and we're just going to quickly skim
the surface.

The current (January 2023) method for deciding who you trust is mostly
about how you came to be interacting with the other agent. Specifically,
since QR codes are so prevalent in initiating connections and
presentation requests, in what context did the QR code appear? Chances
are, you initiated the interaction, likely on a website that you trust,
and so that trust transfers. That will work for the early days of
digital trust, but it is insufficient. It is purely a human trust, and
it would be better to have tools to help users make sure decisions.

We expect that new Aries capabilities will soon be available in wallets
to increase trust by using verifiable credentials to confirm the
identity of *both* contacts of a connection. That means that (for
example) your wallet will automatically request the other side of a
connection to prove who they are via verifiable credentials. That will
be an improvement, but still leaves everyone \"fending for themselves\"
in determining trust. They have better data, but it's still an effort.

## Governance: Trust the Issuer, Trust the Verifier, Trust the Holder (2)

Going further, we expect to see implementations of community managed
registries of trusted entities, a construct that Trust over IP
calls [Trust
Registries](https://wiki.trustoverip.org/display/HOME/ToIP+Trust+Registry+Protocol+Specification).
In those, an entity that you trust uses a process (that you also trust)
to populate a registry of entity identifiers (e.g., DIDs) that meet some
criteria for being included in the registry---for good or bad. For
example, a government might maintain a registry of all of the
identifiers used by sub-organizations within that government. A wallet
could be configured (by the user or the wallet maker) to trust a set of
trust registries. When a new DID (identifier) is encountered by the
wallet, the registries could be checked to see if that DID is found and
the user given information accordingly, such as green if found with a
positive reputation, yellow if not found and red if found with a
negative reputation.

Trust the holder reverses the questions of the previous topics. Why
should issuers and verifiers trust the wallet being used by the holder?
If anyone can create a wallet, how can issuers and verifiers be sure
that the wallet they are interacting with is not malicious. For example,
that the wallet is not secretly sending back information about the
holder and what the holder is doing to the wallet maker's server? Or
perhaps the user has altered the wallet and introduced capabilities that
bypass the wallets trust safeguards.

Using open source software is an important tool in building trust in a
wallet implementation. If the code for the wallet can be scrutinized,
backdoors from the wallet maker can be detected. The more open and
transparent the wallet, the better. Certification is a second mechanism
to engender trust. A trusted entity, perhaps a standards organization,
can define a \"wallet certification program,\" evaluate wallets and
issue \"trustmarks\" to say that a given wallet is certified. From a
technical perspective wallets can check that the phone on which it is
running is not rooted, which prevents a user from altering the wallet
code. A proposed addition to that is for the wallet maker to issue a
verifiable credential to the wallet asserting that the phone is not
rooted, the wallet is unaltered, the wallet is certified, and the wallet
is from the developer/organization that received the certification. The
latter can be verified through a mobile OS check, so it is not just a
\"self-asserted\" claim. With such a verifiable credential in place,
presentation requests can include both the necessary business
information and proof of the wallet security credential. As of January
2023, the most progress in the \"trust the holder\" area has been made
by the [Decentralized Identity Foundation's Wallet Security Working
Group](https://identity.foundation/working-groups/wallet-security.html),
where they have been both specifying and implementing some of the
concepts talked about here.

## Wallets as Verifiers

We've talked about wallets being designed to automatically request
presentations from other agents when forming a connection. When that is
done, the wallet is acting as a verifier. There are other use cases when
having either a verifier capability built into a wallet or a standalone
mobile verifier might be useful. In either case, the end user is
triggering an ad hoc presentation flow. Countless in person
verifications can be easily accommodated by just about anyone with a
mobile verifier. Age verification at pubs and restaurants is an obvious
one, as is proof-of-vaccine at a high-risk location such as a nursing
home. A potential home seller could verify that a real estate agent's
license is up to date, and the real-estate agent could verify that the
home seller is authorized (preventing disasters
like [this](https://www.cbc.ca/news/canada/toronto/fraudulent-home-sale-1.6710868)).
A care-giver providing in-home care can demonstrate their
certifications.

The big challenge in enabling mobile verification is how an end user
defines the presentation request they need. For developers it's not so
bad to construct the JSON, but even then, the developer has to know very
precise information about schemas, issuers and the credentials being
issued and that the verifier is willing to accept. Not feasible for
wallet users! For some very common use cases in specific countries or
regions, some stock presentation requests can be built into the wallet.
For example, proof of age requests based on government issued ID. With
built-for purpose mobile verifiers, makers could preload presentation
requests suitable for how and where the verifier app is to be used.

Another approach that might be useful is that a verifier (the person)
would verbally ask the holder to present a specific credential, and the
holder initiate the interaction by clicking on the credential. The click
would trigger the Aries present proof protocol's **propose** message.
The holder's wallet would display a QR code and the verifier's app would
scan it to trigger the required back and forth. While this is a
technically easy approach, the verifier would have to have some way of
determining if the issuer can be trusted, as discussed in the previous
section. The human verifier must not be put into the position of
deciding that question!

As an aside, we mentioned earlier about the display of a QR code on one
device, and the scanning of it by another. For in person interactions,
QR codes could be avoided by using [Bluetooth Low
Energy](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy) (BLE)
connections. In that scenario, the two devices \"bump\" and the
interaction is triggered---no QR code required! There is ongoing
research and development on the use of BLE for trusted messaging and
credential exchange, with early examples just now coming to light. Keep
an eye out for that feature!

## Mobile Application and Mobile Wallet Interactions

Let's cover one more interesting topic in the area of mobile wallets.
One of the goals every wallet community has is that we not wind up with
a proliferation of wallets, each holding some of the verifiable
credentials that we've been issued. A bank wallet with our banking
credentials, a government wallet with our government credentials, a
wallet from our company with our company credentials, and so on. We want
all of our credentials together so we don't have to remember in which
app we have the credential we need, and so that we can use a super power
of verifiable credentials---presenting multiple credentials in a single
transaction.

Further, we want to be able to present our credentials whenever they are
needed, including when we are in the middle of using another app or
browsing the web on our phone. The most common example is the scanning
of QR codes to initiate wallet interactions. QR codes work great if you
have two screens, such as your laptop showing the QR code and your phone
to scan it. But what do you do, if you're web browsing on the same
device as your wallet? Maybe use your front camera and a mirror? This
\"single screen\" issue doesn't just happen when you are browsing on
your phone. If you are on your banking app, and need to provide
authoritative information to, for example, prove you are authorized to
perform an escalated permission action, you want to do that on your
phone in a simple, straightforward way. Unfortunately, that has proven
easier said than done, and wallet communities such as Aries are working
on solutions.

The challenge is that apps on a mobile phone are (quite correctly!)
isolated (\"sandboxed\") from one another and cannot directly
communicate; it's a crucial security feature. But what capabilities are
there that would allow us to have one wallet app that can be used by
many apps? Here are a couple of possibilities.

Mobile apps support the concept
of [deep-links](https://www.adjust.com/glossary/deep-linking/), that
allow an app to trigger the opening of another application on the phone,
with a (relatively easy) mechanism to get back to the original
application. So a deep link using a protocol of, for
example, **didcomm://** could be used to open up any DIDComm-based
wallet app. Once the wallet interaction is complete, a link on the
screen allows a quick return to the original app. Unfortunately, that
relatively straightforward approach has problems. Notably, on Apple's
iOS there is a significant issue with deep links that makes them pretty
much unusable. The problem is that if you have more than one app on your
phone that handles a given protocol, iOS does not let you choose which
app to use when a deep-link is processed---it just picks one for you. On
Android, when you hit a deep-link with multiple handlers, a prompt
appears letting you select which app to use, and even letting you set a
default if you want. That missing interaction on iOS is a pain point, as
although we don't want users to have too many wallet apps, it\'s quite
often they will have more than one. It's unfortunate that such a feature
is not a part of iOS for the mobile wallet use case and many, many
others.

An alternative pattern that might be possible for apps that have a
server side component is for the calling app to reach out to its
server-side companion to initiate interactions with the wallet. The
initial establishment of a connection is needed (somehow---perhaps a QR
code on another device), but once that is done, the app, when it needs
to interact with the holder's wallet, can ask the server-side component
to handle the interaction. A notification on the mobile device would be
used to bring the wallet to the fore, and on completion of the wallet
interaction, a link on the screen allows a quick return to the original
app, just as with the deep-link design.

This is an important mobile wallet issue that needs to be addressed!

## Getting Hands On

As we talked about at the start when discussing mobile wallets, there is
a lot going on! The items in this section have covered lots of
capabilities and possibilities, all of them at some level of
implementation. As you get started as an Aries mobile wallet developer,
looking into the state of these capabilities is an important step.

Enough about possibilities---let's get hands on with a real Aries
wallet!

## Reasons to Have an Open Source Wallet

There are several reasons why open source mobile wallets are important
as the use of verifiable credentials goes mainstream.

Perhaps the most important reason to have an open source wallet is to
ensure that the code and functionality in the wallet is transparent and
auditable. Users are trusting their wallet apps to manage their keys and
credentials. No one wants a wallet that (for example) shares private
data about the user, or exploits that information for profit, such as
using the information to market to the user (\"Hey, I see you presented
your driver's license to the police. Do you want me to connect you to a
good lawyer?\"). We've seen this type of exploitation with web browsers,
and we definitely don't want a repeat of that, especially with an app
whose explicit purpose is to manage a user\'s private data.

Important issuers and verifiers, such as businesses and governments,
want to be certain that their users have wallets that are known to be
safe and secure. Open source is a great way to achieve such a certainty.
For the reasons outlined in the previous paragraph, the wallet
\"business model\" is tricky, with end users not wanting to pay for a
service, and issuers, verifiers and privacy regulators extremely leery
of any sort of \"user exploitation\"-based business model. As such,
collaborating on building a wallet and sharing the one-time engineering
costs, can result in a more capable wallet, while enabling the powerful,
verifiable credential-based use cases we all want to see.

The next reason played out in the initial wave of Aries wallets. At that
time, the wallet vendors were creating wallets for their specific use
cases, and didn't invest in adding features beyond their use cases, or
in evolving their wallets to add new Aries protocols. For example,
adding features such as internationalization, transitioning from AIP 1.0
to 2.0, adding new verifiable credential formats, using the wallet as a
verifier, and defining mechanisms to enable fantastic user interfaces.
Open source wallet projects allow organizations to collaborate on those
issues versus each spending the money working independently on their own
wallets, solving the same problems.

A final reason we'll mention that argues for open source collaborations
for wallets is the tendency for early players in the field to embed
wallet functionality in their existing apps, so their users have a
familiar (and branded) place to use their credentials. While this may
work for a user's first experience with verifiable credentials, it
precludes the ability to combine credentials into a single presentation,
and could make things confusing for users (\"which app is holding
credential x???\"). While we need ways to enable great user experiences
for the clients of businesses, we'd really like to do that with a single
credential and keys store.

Our advice if you are looking to provide a wallet for your business is
to join one of the open source wallet communities, and contribute to
what is being created there. Don't go it alone! That advice leads us to
Aries Bifold, an excellent React Native open source wallet that is easy
to customize and publish in mobile app stores.

## Aries Mobile Agent - React Native (\"Bifold\") {#aries-mobile-agent---react-native-bifold .unnumbered}

The most advanced Aries open source wallet project is known by its long
name (the one used for its GitHub repository) [Aries Mobile Agent React
Native](https://github.com/hyperledger/aries-mobile-agent-react-native),
and its short name \"Aries Bifold\" (as in the name for a type of
physical wallet). In this course, we'll go with the short name. Aries
Bifold is built on [Aries Framework
JavaScript](https://aries.js.org/) (AFJ), which makes sense given the
JavaScript basis of the [React Native](https://reactnative.dev/) mobile
framework in Aries Bifold. A nice benefit of using AFJ is that it has an
Aries Agent Test Harness backchannel, and so is being tested daily as it
evolves against other Aries frameworks. The AFJ library within Aries
Bifold includes any dependencies needed to use ledgers and verifiable
credentials needed for the wallet. As of writing this course (January
2023), support is limited to Indy ledgers and AnonCreds verifiable
credentials, but with AFJ evolving quickly to support other ledgers and
other verifiable credential formats, those capabilities will soon show
up in Aries Bifold. A related repository that also provides Aries Bifold
dependencies is Aries Framework JavaScript Extensions
(aries-framework-javascript-ext), which holds extensions to AFJ that are
useful in some cases, but not core to AFJ. Some of those extensions are
specifically useful in the Aries Bifold capabilities.

Aries Bifold itself is the source code for a complete react native
Aries-based mobile wallet application, including a user interface
capable of connecting to other agents, messaging, receiving verifiable
credentials, receiving presentation requests, providing presentations
and much more. The use of react native makes it possible to deploy Aries
Bifold to both Android and iOS from the same code base. That's a benefit
for some, but a showstopper for others. We'll look later at what options
are available if you require native Android and iOS Aries wallets.

## Making Aries Bifold Your Own {#making-aries-bifold-your-own .unnumbered}

To create your own mobile wallet suitable for publishing to the app
stores, one more repository is needed---the one for your own wallet.
Since Aries Bifold is \"just a user interface\" and could be considered
a reference implementation, one might be tempted to simply copy Aries
Bifold and evolve your own wallet from there. But that's not ideal. Any
features you add to your wallet aren\'t available for others unless you
reapply the changes into the Aries Bifold repository. As well, any
changes others make to Aries Bifold after you make your copy have to
be manually added by you to your copy. It's not a great situation.
Happily, for Aries Bifold, there is a better way.

The wallet team at the Government of British Columbia (BC Gov) came up
with a very clever continuous integration pipeline that allows them to
maintain the [BC Wallet
repository](https://github.com/bcgov/bc-wallet-mobile) that contains
only the overrides to Aries Bifold. When a build is triggered from the
override repository, the resulting application, ready for publishing to
the app stores is Aries Bifold overridden with changes made by the BC
Gov team. The figure below shows the flow. As a result, even though the
BC Wallet (Android, iOS) has a different look and feel from Aries
Bifold, and significant functional differences, the team estimates that
more than 80% of their work goes into Aries Bifold. Many of the
overrides are things that everyone will apply---\"skinning\" the
application to use your own colors, logos, language and translations.
Some are Aries configurations, such as the specific ledgers your wallet
supports. But others are significant functional differences---features
that are applicable to the BC Gov scenario, but not needed by others.
The good part is that while those are possible using this technique,
it's pretty rare they are needed. Much more often, new features are
commonly applicable, with just configurations needed that are specific
to each different wallet.

![The BC Gov Wallet Build/Publish
Pipeline](images/image040.png){width="5.0in"
height="3.5807655293088363in"}

**The BC Government Wallet build/publish pipeline**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

From an open source perspective, this \"override\" pipeline has
significant collaboration benefits. When teams define features to be
added to their wallet, they consider where is the best place (or

-   In Aries Framework JavaScript

-   In Aries Framework JavaScript Extensions

-   In Aries Bifold

-   In their own repository

Changes are made as high up in that list as makes sense, so the
contribution has the broadest impact. Of course, when such contributions
are to the open source components, they must be made in concert with the
community. Happily, in a collaborative community (such as we have in
Aries), the process for that is well-known:

-   Create a GitHub issue to announce the change you are going to make,
    and monitor the issue for feedback from the community.

-   Make the change in a pull request.

-   Have your pull request reviewed by the maintainers and others in the
    community.

-   Assuming you've assessed the applicability of the change correctly
    and applied any feedback you receive from the community along the
    way, the pull request is likely to be merged.

-   Everyone benefits!

If other teams are taking the same approach with their wallet, your
wallet will evolve much faster than if you were going it all on your
own. And assuming everyone is on the watch for vulnerabilities in the
code, your wallet is likely to be more secure than if you were
developing it from scratch on your own.

## Lab: Getting Started with the Aries Bifold Wallet {#lab-getting-started-with-the-aries-bifold-wallet .unnumbered}

In this lab, we'll go through an Aries Bifold wallet \"getting started\"
tutorial to set up a mobile app development environment and run Aries
Bifold. We'll also run the BC Gov wallet and see what overrides have
been applied to give that wallet its own personality.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/MobileAgentLab.md) to
go to the lab.

## So, What Else Is Out There? {#so-what-else-is-out-there .unnumbered}

While there is a lot of focus in the Aries community on Aries Bifold,
there are other options. Here is a summary of the Aries-based mobile
wallet options that you might consider.

The Aries Mobile Agent-Xamarin (\"Aries MAX\") was started by the teams
developing Aries Framework .NET (AF.NET) in 2019 (eons ago in SSI
time!). The repo for Aries MAX can be
found [here](https://github.com/hyperledger/aries-mobile-agent-xamarin).
Aries MAX wraps the AF.NET framework code
with [Xamarin](https://dotnet.microsoft.com/en-us/apps/xamarin),
Microsoft's open source development platform for creating mobile iOS and
Android applications, and includes a cloud mediator agent suitable for
local deployments. Aries-MAX is a complete open source component for
mobile wallet deployments, handling AIP 1.0 connections, receiving
credentials and proofing claims and more. While there has been much
closed source development with both AF.NET and Aries Max (including an
upgrade to [Microsoft's .NET
MAUI](https://dotnet.microsoft.com/en-us/apps/maui)), the open source
code bases are falling behind. There is talk of the upgrades to both the
AF.NET and Aries Max repositories, so if you are a .NET developer, take
a look at those two repositories to see if they have been brought up to
date.

The Rust-basis of the Aries VCX framework makes it a good candidate for
mobile development. Aries VCX has wrappers for both iOS and Java (that
can be used for Android development), as well as a generator for a Node
wrapper. As such, Aries VCX is a good candidate for native applications
for iOS and Android, rather than going down the React Native approach of
a single code base for iOS and Android.

A recent addition to Aries is the new [Aries Framework
Swift](https://github.com/hyperledger/aries-framework-swift) (AFS), a
new Aries framework built specifically for delivering an iOS
application. If you want to build an iOS native mobile application for
Aries, AFS might be just what you need!

## Chapter 7 Summary {#chapter-7-summary .unnumbered}

What did we learn in this chapter? We started with an overview of the
features and functionality of current Aries wallets, and a look at new
capabilities being created. We also got hands on with the open source
Aries Bifold, the current best choice foundation for Aries wallet
deployments. Here is a list of the key take-aways from this chapter:

-   Existing Aries mobile wallets have a common core set of features.

-   There are a number of organizations working on non-core mobile
    wallet features that just might become core.

-   The current most advanced open source Aries mobile wallet is Aries
    Bifold, a react native mobile wallet, suitable for producing both an
    iOS and Android app from the same code base.

-   While you might be tempted to build your own mobile wallet, before
    doing so consider instead sharing the effort, by contributing to and
    deploying an open source wallet. Aries Bifold mobile wallet is a
    great foundation for building your own wallet.

-   By using a pipeline that allows using Aries Bifold with your own
    overrides, you can have a custom, app-store publishable mobile
    wallet in hours. Further, by using the pipeline, you can easily
    collaborate with others, adding new features to the wallet at the
    appropriate level---specific to your wallet, or at a higher level
    such that the feature is available to others also using Aries
    Bifold.

-   In addition to Aries Bifold, there are other open source building
    blocks for getting started on building your own native mobile wallet
    for iOS or Android.

## Chapter 8 Overview -- Planning for Production {#chapter-8-overview-planning-for-production .unnumbered}

Now that you have explored building your own Aries controller or mobile
wallet, let's talk about actually getting it into production. This
chapter describes some of the things you need to be aware of in the
production context, things that are important in the Aries environment.
While the vast majority of the content of this chapter will be in the
context of enterprise versus mobile agents, we do touch on mobile agent
production as well. Useful stuff!

## Learning Objectives {#learning-objectives-7 .unnumbered}

In this chapter (8), you will learn about:

-   Mobile agent deployment challenges such as pushing an app to the app
    store.

-   Keeping ledgers and agent storage in sync.

-   Writing to a sandbox ledger versus a production one.

-   Managing writes to production ledgers, especially permissioned
    ledgers and those that charge for writes.

-   Considerations for the management of your agent, such as backup and
    restore.

-   Why getting good requirements for what should be in credentials and
    presentations is harder than it might seem.

-   Horizontal scaling of high-volume, enterprise issuer agents.

-   Running many logical agents in a single deployment---multi-tenant
    deployments.

## Production Challenges {#production-challenges .unnumbered}

The bulk of this chapter will be about production issues around
enterprise agents, particularly issuer agents. But we'll first touch
briefly on mobile wallets and the challenges they bring.

![Screen, laptop, tablet, phone](images/image041.png){width="4.0in"
height="2.5639588801399826in"}

**NOTE**: We are not experts in mobile development so these are based on
our observations and experiences only.

The biggest challenge with Aries mobile wallets is likely the same with
all mobile apps---agent distribution. In particular, there are two
issues related to the distribution of new versions:

-   Dealing with the app stores' release processes---getting each
    release of your app through the gates that Apple and Google define.

-   Getting users to upgrade to the latest version so that you can drop
    support for deprecated features in older versions.

For those of us that have grown comfortable (and complacent) in
deploying web services that have but a single deployment, having to
distribute and upgrade apps on (hopefully) millions of mobile phones
creates a much bigger backwards compatibility problem. Sure, with a web
service we have to make sure that the web API provides backward
compatibility, but that's a more manageable problem. As well, while
Google and Apple are aggressive in pushing users to update their apps on
a more or less continuous basis, it's still a challenge to keep things
working across a range of \"stable\" releases that users might be
running.

## Community Upgrade Process {#community-upgrade-process .unnumbered}

This backwards compatibility challenge is exacerbated in the Aries world
because you want your mobile wallets integrating with a range of other
agents. We've talked a lot about interoperability and the Aries Interop
Profile (AIP) in earlier chapters. Having agents (mobile and server
based) that align to AIP versions and are tested for interoperability is
crucial for the community of agent builders. For these applications to
succeed, they all have to be able to work together!

![People holding hands](images/image042.png){width="2.0in"
height="2.168627515310586in"}

An important mechanism for managing upgrades in Aries is described
in [RFC 0345: Community Coordinated
Update](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0345-community-coordinated-update).
This update process is used when the Aries community agrees on the need
to make a breaking change to a protocol agents are using. We want such
changes to be made carefully so that each agent maker can make the
changes independently, and all agents will continue to interoperate
throughout the transition. With RFC 0345, we have a template process
that coordinates a breaking change using a series of steps that gives
time for (hopefully) all deployed agents to be updated without breaking
agent-to-agent interoperability.

Mobile wallets makers have to be particularly aware of these community
coordinated updates because not only do they have to make the changes in
their code, but they have to get a new version with that code change
distributed to (hopefully!) millions of users. To enable global
interoperability, it's not sufficient that only creators of Aries
components (especially frameworks) communicate about updates, but for
mobile wallet operators to let the rest of the community know about
their status---what protocol changes they have made, what protocol
changes are in the works, and what's their latest on interoperability.

## Mobile Wallet Interoperability Testing {#mobile-wallet-interoperability-testing .unnumbered}

How can a wallet publisher let others know about their interoperability
profile? We've talked in Chapter 2 about the Aries Agent Test Harness
(AATH), an automated environment for testing the interoperability of
Aries Test Agents, such as Aries frameworks, and the special AATH Mobile
Backchannel. Although a manual process, it does let the maintainers of
the open source wallets determine their wallet's level of
interoperability, and lets users of deployed open source wallets see
that for themselves. Two things that would be really nice to have in
AATH are the following:

-   An extension to the Mobile Backchannel to allow formal reporting of
    tests that were run (what wallet was tested, and what tests
    passed/failed).

-   A way to run the tests automatically for a given mobile wallet on a
    periodic basis (e.g., daily).

If you have ideas on how to make that happen, please connect (on
Hyperledger Discord) with the AATH developers!

![Wallet](images/image043.png){width="2.0in"
height="2.7480916447944006in"}

## Deploying a Mediator (Or Not) {#deploying-a-mediator-or-not .unnumbered}

Beyond deploying the mobile agent to the mobile OS app stores, each
mobile wallet will need a mediator to at least serve as the target
physical endpoint for other agents sending messages to the wallet. The
mediator may do other things as well for the wallet, such as act as an
outbound relay, manage wallet backup and restore capabilities and so on.
It's up to you, the mobile wallet provider, what you want the mediator
service to do---beyond the minimum of routing messages. You have several
options for providing a mediator, so let's look at what's possible.

With the advent of the Aries mediation protocols RFCs linked above, an
extremely easy option becomes possible for at least getting started.
Using a third-party mediator that is managed by someone else. Anyone can
set up a mediator that uses the mediation protocols and serve as a
mediator for any mobile wallet that supports those protocols.
Indicio.tech has done just that. Check
out <https://indicio-tech.github.io/mediator/>, where a public mediator
has been made available that anyone can use. Your wallet app could use a
specific public mediator, or you could even make it possible for your
users to pick their own public mediator.

The next easiest option is to deploy an instance of [Aries Mediator
Service](https://github.com/hyperledger/aries-mediator-service) (AMS), a
mediator service ready to deploy in your environment. Under the covers,
AMS is (currently) Aries Cloud Agent Python wrapped in configuration
settings such that it is ready to function as a mediator. ACA-Py
supports the Aries mediation protocols, notably [RFC 0211: Route
Coordination](https://github.com/hyperledger/aries-rfcs/tree/main/features/0211-route-coordination) and [RFC
0212:
Pickup](https://github.com/hyperledger/aries-rfcs/tree/main/features/0212-pickup).
Your mobile wallet app must support those same Aries mediation protocols
as a client. You can deploy an instance of AMS as is, or add other
features to improve your app user's experience. Of course, while having
a configuration of an instance of ACA-Py to use for mediation is pretty
easy for testing, setting it up to support millions of mobile wallet
apps (because that's your goal, right?) is a little more challenging.
The good news is that we cover deploying scalable, server-side Aries
agents (which is what a mediator agent is) in the next section of this
chapter.

Another option is to write your own mediator \"agent\" that works with
the mobile wallet app you will deploy. Since a mediator doesn't do a lot
of agent-y things, using an Aries framework as the basis of a mediator
may not be a huge advantage, and it may make more sense to write your
own component that handles all the other features you want (perhaps some
services for which you can charge), and includes the minimum Aries
protocol support to be a mediator. The API between the wallet and the
mediator can be custom between the two, or you can implement the
mediator protocol RFCs referenced above. This \"custom mediator\"
approach was implemented successfully in the early AIP 1.0 Aries wallet
apps and is a viable strategy.

You have options! We recommend using the easiest option first, learning
more about the issue and then making a decision for the long term on the
best approach for your use case. We also recommend that you collaborate
with the Aries community to know what is the best current approach to
providing a mediator.

## Mobile Wrap Up {#mobile-wrap-up .unnumbered}

That's all we have about deploying production mobile wallets. The rest
of this chapter is largely focused around challenges with running
enterprise agents in production. We've had our fair amount of experience
(and battle scars) in dealing with production use cases and we hope the
things that we've learned along the way will make it easier for you.
Certainly this is not an exhaustive list, but it will give you a good
starting point. You'll know a lot more than we did when we got started!

## What's Coming in This Section? {#whats-coming-in-this-section .unnumbered}

This section mostly deals with working with Indy production ledgers,
such as Sovrin MainNet. Most of this section also applies to the test
networks made available by organizations such as Sovrin and Indicio that
operate production ledgers. While to this point in the evolution of
Aries, the focus has been on the use of Indy ledgers, we'll also touch
briefly on impacts of using non-Indy ledgers.

## Sandbox Versus Production-Secure Storage Handling {#sandbox-versus-production-secure-storage-handling .unnumbered}

As you develop your first Aries controllers and deploy your first
proof-of-concept using a sandbox ledger, you can get quite complacent in
managing the ledger and your agent's secure storage. If things aren't
working, it's easy to just entirely reset a local sandbox ledger, reset
your agent(s) secure storage, and start again. In fact, particularly
during development, it's often the case that things unintentionally get
out of sync between the objects on the ledger and what's in agent secure
storage. When that happens, you are forced to delete everything and
start again. That's OK during development, but in production, you won't
have that luxury---you can't afford to lose the data!

![Sandbox](images/image044.png){width="2.0in"
height="1.5835662729658793in"}

Some production ledgers (for example, Sovrin MainNet) there is a fee for
writing to the ledger and you don't want to pay more than you have to.
Even more important, if you are an issuer of credentials, if you lose
access to your secure storage, you won't be able to issue credentials
based on the objects you have already put on the ledger. The simple
reality is that once you are in production, you must remember that your
storage is a production database that must be handled
appropriately---back it up, be able to restore it and always, always
keep it secure. On that last part, security: you don't want someone to
steal the keys from your secure storage and be able to act in your
place!

## Agent Storage Backup and Restore {#agent-storage-backup-and-restore .unnumbered}

As was covered in the prerequisite for this course ([*\"Introduction to
Hyperledger Self-Sovereign Identity Blockchain Solutions\",
LFS172x*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa)**[)]{.underline}**,
backup and restore of agent secure storage is crucial to the long term
usefulness of this technology. While that may be less important in the
early days for mobile wallets (users do not write to a public ledger and
should be able to get credentials easily reissued), backup and restore
for enterprise Aries agents is crucial from day one.

![Cloud with an arrow pointing
up](images/image045.png){width="2.0in"
height="1.8351071741032372in"}

Fortunately, unlike the mobile use case, backup and restore for the
enterprise use case is a well understood problem. Enterprise agent
storage should use an enterprise database, such as PostgreSQL, and all
of the tools and techniques that have been developed over the years to
manage such an enterprise database. There should be nothing special
about enterprise agent secure storage from a database perspective than
any other enterprise database. As such, the following guidelines apply:

-   Backup the data regularly, either fully or incrementally using logs,
    depending on the use case.\
    - The specific approach taken depends on the answer to the question:
    how much data can you afford to lose if the operational database is
    lost and you must restore it from a backup?\
    - Consider using a cluster database with replicated storage to have
    continuous data redundancy.

-   Test the viability of the backups regularly.\
    - Run frequent test restores to verify the integrity of the backup.

-   Define and periodically execute a full agent disaster recovery plan.

-   Ensure that the backups are maintained in a secure location, and
    protect both the database and encryption keys for the secure
    storage.

**NOTE**: The vast majority of the data in the agent storage database is
encrypted and the encryption keys for the database must be appropriately
managed. This includes ensuring that the keys are stored separately from
the data, they are protected from accidental disclosure, and they are
accessible when necessary for starting the agent and after a database
restore. Techniques using tools like ***Hashicorp's Vault*** for
managing the agent storage keys might be a good approach. Again, none of
these requirements are different from any other enterprise database
system.

Regarding the \"how much data can you afford to lose\" question,
remember as you consider that question, that in addition to the ledger
objects, agent secure storage holds information about the connections
your agent has established (with your private key for each connection)
and about the protocols that are \"in-flight.\"

## Indy Ledger Writing: Legal and Technical Issues {#indy-ledger-writing-legal-and-technical-issues .unnumbered}

While Indy ledgers are pretty easy to write to (there\'s an API call for
that!), there are a couple of added governance related complications
that need to be handled in using most production and some test Indy
ledgers, the \"TAA\" and \"Endorsers.\" We'll go through each of them
next.

## The Indy Transaction Author Agreement (TAA) {#the-indy-transaction-author-agreement-taa .unnumbered}

The Indy Transaction Author Agreement (TAA) is an optional agreement
between a party that is writing a transaction to an Indy instance and
the operators of that instance. If the ledger is configured to use a
TAA, the API calls made to write to the ledger must include information
that amounts to the transaction author (you) saying \"I agree to the
TAA\"---just like the \"End User License Agreement\" (EULA) that most
software and websites require you to acknowledge. In the case of an Indy
write transaction, there are three fields that are added to each Indy
write transaction that the ledger will check before processing the
transaction if the TAA is enabled:

-   The time the TAA was accepted.

-   The hash of the current TAA.

-   An enumerated value indicating how the TAA was accepted.

From a legal perspective, your organization must review and accept the
TAA before writing to the ledger. That means, getting the TAA from the
ledger operator and making sure your organization understands the legal
implications of, and abides by, the agreement. The TAA can be retrieved
from the ledger (for Sovrin MainNet
it's [here](https://indyscan.io/tx/SOVRIN_MAINNET/config/9364) on
indyscan.io) and likely stored in a more readable form on the Indy
ledger operator's site, such
as [here](https://docs.google.com/document/d/1wcSESHbqU6OCOG1g1q5TrIkRehJZ38PtjWkFkLxg-Dc/edit) for
Sovrin MainNet.

From a technical perspective, an agent writing to the ledger that has an
active (non-empty) TAA needs to get the hash of the current TAA from the
ledger, and a list of configured values for how to accept the TAA. Once
again, that information is stored on the ledger, this time in
the **TXN_AUTHOR_AGREEMENT_AML** configuration transaction, such
as [here](https://indyscan.io/tx/SOVRIN_MAINNET/config/9362) for the
Sovrin MainNet. \"AML\" means \"Acceptance Mechanism List,\" and it's a
list of the name/value pairs for how an organization can accept the TAA,
plus the hash of the TAA. So, to write to the ledger, an agent must:

-   Get the AML transaction from the ledger.

-   Have the (human) controller select a method from the AML to use to
    accept the TAA.

-   Include the method selected, the hash from the AML data, and the
    current timestamp in any ledger write transaction.

Fortunately, most Aries frameworks make it easy for you to configure how
to accept the TAA on every write, and that\'s all you need to do. For
example, Aries Cloud Agent Python has an Admin API call to read the AML
data, and another, **/ledger​/taa​/accept**, that lets you indicate how
you accept the TAA from the list of options. After execution, ACA-Py
automatically adds TAA data to every write. By adding that call to the
controller initialization code, you no longer have to worry about the
TAA from a technical perspective.

However, remember that's only the technical handling. Your organization
should definitely do a legal review of the TAA itself and make sure that
it is willing to abide by the terms of the agreement before adding that
call to the controller. And of course, you must also be certain that
what you are writing to the ledger doesn't break the agreement that
you've agreed to.

## Lab: Handling the TAA In ACA-Py {#lab-handling-the-taa-in-aca-py .unnumbered}

In this lab, we'll activate the TAA on a local instance of the
VON-Network, and then run some API commands to retrieve the TAA
Agreement AML, and use it to accept the TAA.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/TAALab.md) to
run the lab.

## Endorsing Transactions {#endorsing-transactions .unnumbered}

The second governance challenge in writing to a production ledger is
having permission to do so. Not just anyone can write a transaction to
an instance of a ledger, even if they have agreed to the Transaction
Author Agreement. While the permission rules are configurable per Indy
instance, on the Sovrin ledgers at least, writing requires the
participation of a \"Transaction Endorser.\" An endorser is an
organization that has submitted and had accepted an application to be an
endorser, has signed legal agreements about being an endorser, and has
had a DID with the \"endorser\" role added for them on the ledger. Once
an organization is a transaction endorser, they can, using their
endorser DID:

-   Write objects on the ledger.

-   Create author DIDs on the ledger---DIDs with no permissions.

-   Sign (with the private key from their endorser DID) write object
    transactions created by author DIDs so that the author's
    transactions are accepted and written to the ledger.

The ability to sign transactions of others is an interesting capability
because it can be used in several ways.

-   An organization with just one issuer wouldn't use the signing
    capability, and it would just write any required transactions
    directly using its endorser DID.

-   For a large enterprise, like a government or multinational, the
    enterprise might have one endorser, and all other issuing agents in
    the organization have author DIDs that must request the endorser
    sign their transactions before submitting them for writing. That
    keeps both the control and billing for the writes centralized in the
    organization.

-   An \"SSI-as-a-Service\" (SSIaaS) company might provide services for
    other organizations that include creating author DIDs and signing
    any write transactions needed for their customers to be verifiable
    credential issuers. The SSIaaS company would have to pay the ledger
    operator (for example, the Sovrin Foundation) for the objects
    written to the ledger, and could charge their customers whatever
    makes sense. [Danube Tech](https://danubetech.com/) operates just
    such a service, called [godiddy.com](https://godiddy.com/), that
    supports Indy and other types of ledgers.

When transactions are written to the Sovrin ledger (for example), it's
not the author that has to pay for them, it's the endorser; the
organization that has the endorser legal agreement with the Sovrin
Foundation. And, while the author must still adhere to the TAA (above),
the endorser must ensure the endorser legal agreements are adhered to by
both the endorser and the author, if those are different entities.

Endorsing adds some complexity to the writing process. In order to write
a transaction to the ledger, a non-endorser must first get their DID
created by an endorser. Once they have an endorser DID, they use that
DID to write transactions using the following steps:

-   The author creates the transaction to be written, but does not send
    it to the ledger.

-   The author sends the transaction to the endorser.

-   If the endorser is willing, it signs the transaction---adding a
    signature item to the transaction.

-   The endorser sends the now endorsed transaction back to the author.

-   The author submits the endorsed transaction to the ledger.

-   The ledger verifies the signatures on the transaction, evaluates the
    permissions against the configured rules for writing the transaction
    and if all is well, writes the transaction to the ledger.

That's a lot! In the early days of Aries, those steps were done
manually, often by emailing (!!) the transactions back and forth between
those with an author DID and those with an endorser DID. Not a
sustainable practice by any means, especially if the issuer is regularly
revoking credentials.

Fortunately, Aries frameworks like ACA-Py have created a built-in
endorser flow, so that it is easy to spin up an endorser agent, and to
configure an ACA-Py issuer instance to use the endorser agent when
needed. When the issuer ACA-Py instance creates a transaction to be
written to a ledger, it contacts the endorser service to get the
transaction signed, and on receipt, the author sends the transaction to
the ledger. Likewise, when the endorser receives a request from an
author it is willing to endorse, it signs it and sends it back. The
Aries repository [Aries Endorser
Service](https://github.com/hyperledger/aries-endorser-service) contains
a pre-configured instance of ACA-Py suitable for use as an endorser.

Let's take a look at the details of endorsing a transaction both
manually and using a fully automated endorser flow in a couple of labs.
We think you will like the second lab a whole lot more than the first!

## Lab: Scripting Indy Production Writes {#lab-scripting-indy-production-writes .unnumbered}

In this lab, we'll look at the manual process (using the Indy CLI) for
authoring, endorsing and writing transactions to a ledger that is fully
permissioned, such as Sovrin MainNet.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/master/docs/LFS173xV2/ProductionWrites.md) to
run the lab.

## Lab: Using the Aries Endorser Service {#lab-using-the-aries-endorser-service .unnumbered}

In this lab, we'll look at a fully automated endorser service
deployment. It's our old favorite Alice and Faber demo, but this time
with Faber created as a simple author, needing the help of an endorser
to get its transaction written to the ledger.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/UsingAriesEndorserService.md) to
run the lab.

## Evolving the Endorser Service {#evolving-the-endorser-service .unnumbered}

Endorsing transactions is in much better shape now than previously, with
the capabilities built into Aries frameworks. There are a few things
that may need to evolve in the future, things that you should keep an
eye out for. Notably:

-   Aries endorser service does not have a set of business rules to
    decide if it should endorse a transaction or not. Thus, it is up to
    those deploying the service to make sure that only authors that are
    allowed to be endorsed can access the service. It would be nice to
    have that logic built in.

-   As implemented today (January 2023), an Aries Endorser Service
    deployment can only endorse transactions for one Indy network. If
    you want to support endorsing authors using multiple Indy networks,
    you will need multiple deployments of the endorser service.

-   The abstract concept of \"endorsing\" transactions is not limited to
    Indy. As Aries adds support for more and more types of ledgers
    (Verifiable Data Registries), the concept of signing a transaction
    will need to be pluggable, allowing different implementations for
    different networks.

## Summing Up {#summing-up .unnumbered}

The most important thing you need to take from this section is that if
you are using the Indy ledger, there will likely be legal and technical
requirements around writing data to the ledger. That means that you have
to investigate the governance around the ledger you are using to
understand that governance, and the legal and technical requirements you
will need to address. Once you know those requirements, look at the
Aries framework you are using and understand the features of the
framework that allow you to manage your Indy ledger writes.

That wraps up some of the special handling issues for Indy ledgers. Next
up---handling credential revocations.

## Challenges (1) {#challenges-1 .unnumbered}

Revocation is a surprisingly difficult challenge in software systems. A
unilateral revocation of a credential by its issuer such that everyone
that needs to (holder, verifiers) are notified of the revocation in a
timely manner is hard, especially if you don't want to create
undesirable side effects like tracking/monitoring of the holder and the
sharing of correlatable identifiers. Not surprisingly, issuer revocation
handling in AnonCreds is pretty tricky, with several extra challenges
over other ledger-related activities. The good news (at least if you are
using Aries Cloud Agent Python) is that ACA-Py takes care of most of
those extra challenges, leaving you, the Aries application developer,
with just some extra configuration and implementing the business logic
to do what is necessary---revoking credentials.

![](images/image046.png){width="5.0in"
height="1.6311854768153982in"}

We're not going to cover how AnonCreds revocation works, but rather
provide a little guidance on what extra things you, as an Aries
developer, need to do when including support for revocation, and what
support ACA-Py (and perhaps other Aries frameworks) provides for
handling revocation. If you are interested in the details of AnonCreds
revocation, please checkout
this [article](https://github.com/hyperledger/indy-hipe/tree/master/text/0011-cred-revocation).
The basic activities of an issuer of revocable AnonCreds credentials
are:

-   Setup for issuing credentials by publishing AnonCreds ledger objects
    and a tails file (details below).

-   Issue credentials, and as needed, create additional revocation
    registries (and tails files).

-   Track credentials pending revocation.

-   Revoke pending credentials by publishing impacted revocation
    registries to the ledger.\
    - The publication may be immediately after each pending revocation
    is identified or in a periodic batch, depending on the needs of the
    business.

These activities create some complications for the issuer.

The first complication with AnonCreds revocation is the need for the
issuer to generate and publish a tails file per revocation registry. A
tails file must be published by the credential issuer such that every
credential holder (such as a mobile wallet) can retrieve it. In theory,
it can be published anywhere (e.g., on a file server), but for it to be
read by a mobile wallet, the file must be retrieved from an SSL
certificate protected (https:) server. This is a restriction placed on
web apps by iOS and Android---apps can no longer use non-SSL protected
sites. To make it (relatively) easy to get started, the BC Gov team has
implemented a [\"Tails Server\" open source
repository](https://github.com/bcgov/indy-tails-server) that you can
deploy yourself, and they have also deployed a public instance of it
at <https://tails.vonx.io/>. The 404 you get from following that link is
expected, showing that the service exists, albeit with little fanfare.

A second complication is that AnonCreds revocation registries are pretty
small, limiting the number of credentials you can issue per revocation
registry (but not per type of credential!). When you run out, you have
to create a new registry. For example, if you have a revocation registry
size of 2000 credentials, when you go to issue your 2001st credential,
you must first create a new revocation registry. If you issue 100k
credentials, you will have 50 revocation registries for that credential.
What a pain!

Finally, every time you want to revoke a batch (1 or more) of
credentials, you have to write to the ledger. If the credentials to be
revoked are in different revocation registries, you have to write
multiple transactions to the ledger. As well, if you are using an Indy
network and you are not an endorser, you have to get each of those
transactions signed by an endorser.

It's a lot for a poor Aries controller to manage!

Fortunately, Aries Cloud Agent Python takes care of the complexity
around revocation registries for you, minimizing the work of the issuer
as much as possible. Here's how.

When the controller (your code) indicates that revocation will be used
when creating a credential definition, ACA-Py automatically creates two
revocation registries, and starts using one for issuing credentials. Why
two? So that when credentials are being issued, and we've used up all
the credentials in one registry, we don't have to stop issuing to create
a new revocation registry. When a registry runs out of credentials,
ACA-Py automatically switches to use the next one (no delay!), and
automatically and in the background creates another registry. This means
you, as a controller writer, don't have to worry about managing the
creation of revocation registries at all. ACA-Py makes sure there is
always an active and ready-to-go registry on hand!

## Challenges (2) {#challenges-2 .unnumbered}

Likewise, when you revoke a credential, your code just has to tell the
ACA-Py instance \"I want to revoke credential X.\" ACA-Py takes care of
tracking pending revocations from there. Your code must trigger the
publishing pending revocation updates, so that you can decide if you
want to publish revocations immediately or in a periodic batch (perhaps
daily). Publishing in batches might save money on ledgers where there is
a payment for each transaction written. Either way, when publishing is
requested, ACA-Py figures out which revocation registries have pending
revocations and writes a revocation registry entry transaction for each
to the ledger.

All that makes revocation handling pretty easy for a controller! From an
issuer controller perspective, here's what you have to do when using
AnonCreds revocation with ACA-Py:

-   Deploy your own, or use a public tails server.

-   When starting ACA-Py, pass in the URL of the tails server as a
    command line option. ACA-Py will take care of publishing the tails
    file for each revocation registry created and making sure that the
    location of the tails file is published as required to the ledger
    you are using.

-   When creating a credential definition, indicate (via a flag) that
    revocation is to be supported, and include the size (number of
    credentials) you want to have for each revocation registry. The size
    will be a tradeoff between the number of registries needed (fewer is
    better) and the tails file size (smaller is better).

-   When issuing a credential, save the ID of the credential
    (associating it with the holder) such that it can be used later for
    revoking the credential, if necessary.

-   When required, mark a credential as pending revocation using the
    saved ID for the credential. This marks the credential for
    revocation, but does not publish that information.

-   Trigger the publishing of revoked credentials. That can be done in
    conjunction with revoking a credential, or periodically, to publish
    all of the revoked credentials since the last publication.

**NOTE**: If the transaction(s) need to be endorsed, the ACA-Py endorser
configuration we covered earlier in this chapter will take care of that
as well. Nothing extra for the controller to do, other than to be sure
that everything is properly configured.

By the way, all of this complication is on the shoulders of the issuers.
A holder's job is much easier. As long as the ledger and the path to the
tails file is accessible, all of the revocation handling is within the
AnonCreds code, so there is little for the holder agent's controller
code to do. Oh wait, maybe one thing. After creating a presentation that
involves a revocable credential, the controller can check to see if
their credential has been revoked. If it has, perhaps the presentation
shouldn't be sent to the verifier\...

A last issuer concern to touch on is how often you should publish
revocations to the ledger. On public Indy ledgers such as Sovrin's
MainNet there is a cost associated with writing a revocation entry (as
they are called on Indy) to the ledger. It's not much, \$0.10US right
now, but it's something to consider. At the same time, your verifiers
may need to know as quickly as possible if a credential has been
revoked. What's the best approach? Well, it depends... Revocations could
be written as needed (whenever they occur), or written periodically. For
example, consider a government that issues driver's licenses as
verifiable credentials that needs to revoke existing credentials when
driver's license data changes---address, class of license, the right to
drive, etc. In that use case, it's likely acceptable to write an update
to the revocation registry daily that includes all the revocations that
have occurred since the last update. For a large population, the number
of daily revocations might number in the thousands. Such an issuer might
also define a class of \"high importance\" revocations (for example,
loss of right to drive) for which the issuer wants to support immediate
revocation. On the other hand, issuers that rarely revoke credentials
(for example, monthly) could work either way, revoking credentials as
they happen, or batching them into periodic writes to the ledger.

## Lab: Using Revocation {#lab-using-revocation .unnumbered}

In this lab, we\'ll return to our Alice-Faber demo, but this time with
the credential that Faber issues to Alice will be revocable. And we'll
revoke Alice's credential. Let's see what happens when Alice tries to
prove the credential.

Click [here](https://github.com/cloudcompass/ToIPLabs/blob/main/docs/LFS173xV2/FaberRevokesAliceCredential.md) to
run the lab.

## Summing Up Revocation {#summing-up-revocation .unnumbered}

We covered revocation with AnonCreds and the complications it brings.
Yuck! We also looked at the support that Aries frameworks provide to
hide those complications from controller software. They make your job of
developing Aries issuer applications a lot easier!

## Things to Consider {#things-to-consider .unnumbered}

This is a very short section that is not about development, but rather a
reminder about the challenges of getting requirements in order to do
development that enable going to production for the long term.

Way back in Chapter 1 we talked about \"Decentralized Governance,\" and
about the challenges in a group of peer organizations agreeing on things
like, what credentials to issue, when, and to whom. From a going to
production perspective, that leads to the following challenges. How do
you, the Aries developer for an issuer, get the requirements for the
credentials you are going to issue, the rules of how to populate those
credentials, and what your software needs to collect and verify from
users to know to whom those credentials should be issued? At first
glance, those will seem like easy questions, especially if you only
discuss those requirements inside your organization. However, we
recommend that your organization not limit itself to internal
discussions, but try to look at a larger context. Is there an existing
standard for the type of credential you want to issue? Are others
already issuing a similar credential? Are there potential issuers of the
type of credential you are going to issue with whom you could
collaborate? In a larger community, what would the \"ideal\" credential
of this type look like? Have conversations with peer organizations, and
with verifiers that are going to receive presentations of the
credentials you and others issue. Likewise for the Aries dDeveloper and
for a verifier. What credentials are out there that you will consume?
What potential issuers exist that you might want to work with in
changing them into active issuers? There are lots of collaborations that
a verifier can initiate with issuers to enable an interoperable
ecosystem of credential issuers, holders and verifiers.

Such discussions may trigger the need to create an \"industry
association\" to be the authority over the governance for that schema.
It might also trigger the need to create a formal standard. Such efforts
can be a lot of work, but that work may pay off in creating a better,
more stable trust ecosystem. Once you have the information in place,
publish that information for all to see. Publish what the credential
schema is, who should get the credential, and details about all of the
attributes. Have each issuer document details about their issuing of the
type of credential. How they do their pre-issuance verifications, are
there attributes that they don't populate and so on.

From an Aries developer perspective, it's not a hard technical problem
to create credentials. If someone tells you what should be in a
credential, it's easy to do the technical work to make it so. If they
tell you how to populate that credential, it's probably not too hard to
make it so. Although if your source of truth systems don't currently
have the data in the form that's needed, there might be some non-Aries
work to refactor those systems. Likewise for a presentation request. If
someone can give you some details about what is needed to be presented,
you can probably work out what the presentation request data structure
needs to look like. The hard part will be in doing the work to get good
requirements in the first place. Having the business analysts (and the
like) work on the governance issues will take time.

We recommend that as an Aries dDeveloper, you don't wait for that
governance work to be done, but make a \"best effort\" to define what
you think the credentials and presentations will need to look like and
do your development based on that. However, before you go to production,
make sure you get those important, good requirements that come from
effective collaborations amongst a community of issuers and verifiers.
Our best advice: don't go it alone!

Enough on governance. Let's get back to technical stuff!

## What Is Horizontal Scaling (1) {#what-is-horizontal-scaling-1 .unnumbered}

For enterprise agents, an important production issue to consider is
horizontal scaling---the ability to increase the capacity of an
enterprise agent by adding more agent instances. While your use cases
may start out small, it\'s a good idea to think about how you will scale
up your capacity as demand grows for the services offered by your agent.

This section draws on the experience of the Digital Identity and Trust
team at the Government of British Columbia running a service called
OrgBook BC, which uses a verifiable credential flow to publish open data
about all registered legal entities in BC. We won't go into the business
case behind OrgBook BC and its code base (you can read about it on
the OrgBook BC website), we'll just look at its verifiable credential
processing requirements.

The OrgBook BC team has implemented two generations of agents in
its OrgBook BC issuer and [Aries
VCR](https://github.com/bcgov/aries-vcr) community holder. When OrgBook
BC was initialized, an Aries issuer issued millions of credentials to a
single enterprise holder as quickly as possible. That sheer volume of
credential issue events requires the scaling of the solution to use as
much processing power as is available. The architecture of the solution
is pictured below.

![OrgBook BC Issuer-Holder Agents
Architecture](images/image047.png){width="2.0in"
height="4.130018591426071in"}

**OrgBook BC issuer-holder agents architecture**\
Licensed under [CC BY
4.0](https://courses.edx.org/xblock/%E2%80%9Chttps:/creativecommons.org/licenses/by/4.0/%E2%80%9D)

The following is a summary of the architecture:

-   ACA-Py instances are the orange boxes---issuer and holder agent
    frameworks.

-   The controllers are in green, each controlling one of the ACA-Py
    instances.

-   The databases labeled \"Secure Storage\" are agent secure storage,
    holding the keys, ledger data, connections, credentials and protocol
    state objects.

-   The issuer controller monitors the source system for \"events\" that
    trigger credential updates---issuing or re-issuing credentials. It
    invokes the issuer ACA-Py instance to issue the verifiable
    credentials to the Credential Registries agent using the \"Aries
    Issue Credential V2\" protocol ([RFC
    0453](https://github.com/hyperledger/aries-rfcs/tree/main/features/0453-issue-credential-v2)).
    The controller keeps track of the events processed and credentials
    issued in the Event Tracker database.

-   The holder ACA-Py agent framework instance receives issued
    credentials, stores them in its agent secure storage and notifies
    its controller about the credentials.

-   The holder controller extracts the claims from the credentials and
    stores some of the claims in the search database.

-   HTTP is used for transport between all of the controllers and ACA-Py
    instances.

-   All of the databases (both Secure Storage and the Search Database)
    are PostgreSQL instances.

## What Is Horizontal Scaling (2) {#what-is-horizontal-scaling-2 .unnumbered}

The design (hopefully) looks pretty straightforward, and the operation
is pretty simple: use Aries protocols to connect two agents during
startup, and then issue credentials from the issuer to the holder. The
challenge in first loading OrgBook BC was the volume of credentials to
be issued. For launching OrgBook BC, the requirement was to issue 2.5
million credentials as quickly as possible, ideally within hours, and
then continue to issue credentials at a steady pace of thousands per
week. Thus, we want to scale up for the initial load, using every bit of
computing resource we can find, and then scale down to a pretty low
steady state. After some experimentation, the results were satisfactory,
with the scaling working as expected.

The OrgBook BC use case is somewhat different than might be seen for any
high volume issuer. In a more typical case, instead of one holder, the
issuer would be connecting with tens to hundreds to thousands of holders
simultaneously, issuing credentials to each. Regardless, the need for
horizontal scaling to adapt to loads as they happen is needed in each
case.

For this scenario, we want to be able to run the agent on a platform
that supports high availability and (ideally automated) horizontal
scaling, such as [Kubernetes](https://kubernetes.io/). As the load on
the agent increases (more requests), more processes (containers) are
added so that we have more available issuing capacity. When requests
drop, some of the containers stop and capacity decreases. To enable
auto-scaling, [cloud
native](https://www.cncf.io/) [approaches](https://github.com/cncf/toc/blob/main/DEFINITION.md) must
be applied. In the case of Aries, that means the controllers and agent
framework components should be stateless---operating without holding
state in memory. The multiple agent (framework and controller) instances
operate as a single logical agent, with the combined capability of all
of the instances looking to the outside world as a single agent.

All of the agent framework (ACA-Py in this case) instances persist data
to a single logical secure storage instance; for example, a single
PostgreSQL database. Ideally, that database would be implemented as a
cluster, so it too supports high availability and scalability. Likewise,
the scalable controllers likely have their own persistence, separate
from the Aries secure storage.

As we have seen in this course, both Aries controllers and agent
frameworks (such as ACA-Py) operate an event loop (waiting for an event,
processing it, and responding to the event), just like any web service.
To make Aries components stateless, event state must not be held in
memory, but rather persisted to shared storage when completing the
processing of an event. With that, any number of instances of the agent
components can wait on events, retrieve the state information associated
with the event and process it. Since it is likely in enterprise
scenarios that all the transports to, from and within the agents are
HTTP, load balancers (often built into the container platform such as
Kubernetes) can be run in front of the components to distribute the load
across all available instances.

Agent frameworks such as ACA-Py have been built with scaling in mind. As
you build your controller, you should also try to meet this requirement.
Define a clean controller event loop that includes both retrieving state
from shared storage at the start of processing an event and persisting
state to that same shared storage at the end of processing. Minimize the
state outside of event processing.

## Making ACA-Py Stateless {#making-aca-py-stateless .unnumbered}

Making ACA-Py instances completely stateless has proven to be a
challenge that is still being worked on. ACA-Py defaults to having an
internal in-memory queue for processing requests. When ACA-Py instances
are loaded, they might queue up requests in memory. However, in-memory
queues represent state, and so problems can occur when ACA-Py instances
are shut down. When the instances are shut down gracefully (e.g., with
warning to stop accepting new requests), there could be a problem if the
instance is unable to complete its request processing before the
instance is forced to stop---some requests might be lost. Worse, if an
instance is terminated suddenly (such as when the power plug is pulled
on the server on which it is running) anything in the in-memory queue is
lost. The heavier the load, the more likely messages will be lost due to
shutdowns.

A lot of work has gone into making a stateless, scalable \"ACA-Py
Cluster\" using persistent queue and shared caching techniques based on
tools like Redis and Kafka. Implementations have been done by individual
teams. However, as of this writing (January 2023), a clean and simple
overview of a pluggable deployment is still a work in progress. DIDComm
brings some interesting challenges to ensure a deployment, especially
when connection-oriented transports, such as web sockets and [Aries RFC
0092: Transport Return
Route](https://github.com/hyperledger/aries-rfcs/blob/main/features/0092-transport-return-route/README.md) are
involved.

For many use cases, deploying a high availability, horizontal scaling
instance of ACA-Py on Kubernetes (or equivalent) is sufficient for many
use cases. We recommend over provisioning the solution so the load on
individual instances of ACA-Py are lightly loaded, to minimize the
impact of instance (containers) shutdown by Kubernetes. It is not a
great solution as we all know that Murphy's Law (\"Anything that can go
wrong will go wrong, and at the worst possible time.\") will no doubt
strike, but in our experience, it has been pretty successful.

However, don't settle for that. Keep an eye on the open-source
collaborations happening in clustering ACA-Py. If you have the
expertise, please contribute towards making that clean, elegant
deployment description we're all looking to create.

## Agent Instance Initialization {#agent-instance-initialization .unnumbered}

With horizontal scaling, you will have instances of the agent starting
and stopping regularly, and initializing those agents must be managed
properly, particularly as it relates to objects written to the ledger. A
naive approach to starting every instance of an agent might be to follow
the pattern in the image below.

![Initializing Aries Agents](images/image048.png){width="3.0in"
height="2.9137259405074367in"}

**Initializing Aries agents**\
Licensed under [CC BY
4.0](https://courses.edx.org/xblock/%E2%80%9Chttps:/creativecommons.org/licenses/by/4.0/%E2%80%9D)

While that will work in most cases, since there can be multiple agent
framework instances running concurrently, what happens if multiple
instances start up in parallel, each sees in step 2 that some ledger
objects don't exist, and each tries to create them?

The maintainers of ACA-Py have addressed this and related initialization
concurrency issues by having agents run in one of two modes:
provisioning and operational (called \"start\".) In provisioning mode,
the agent starts up, checks if all of the resources that an agent needs
have already been provisioned and if not, it creates them. This includes
creating and initializing secure storage, creating any ledger objects
required (for issuers), and writing them to the ledger. Once that is
done, the agent exits, its work done.

In ongoing operation, the operational mode is used. The agent starts up
checks if all of the resources that an agent needs have already been
provisioned and if not, exits immediately with an error. However, if the
provisioning has been done, off it goes to do its work.

We recommend that you stick with this pattern as you deploy your agents.
It allows you to limit the use of higher level permissions (e.g., to
create the secure storage database, and write to the ledger) to
provisioning mode and running agents with less authority in operational
mode. Note that if you are using revocation, your operational agents
likely will need the ability to write to the ledger, as new revocation
registries will need to be created from time to time.

We don't have a lab related to horizontal scaling, but if you think you
will need to know more about this topic, we recommend that you keep
handy this link to the [BC Gov's OpenShift Deployment
Configurations](https://github.com/bcgov/orgbook-configurations) repository
to use when you need it. OpenShift is Red Hat's distribution of
Kubernetes, and the repository will give you some guidance as you deploy
agents to a Kubernetes platform.

## Operating Agent Services with Multiple Agents (1) {#operating-agent-services-with-multiple-agents-1 .unnumbered}

We've covered how to deploy a single agent (one framework with one
controller) a number of times in this course---Faber the issuer and
verifier, Alice the holder, Acme the verifier. That's all good, but what
if you want to operate an agent service with thousands (or millions!) of
agents? For example, you want to empower many small businesses to become
verifiable credential issuers. Or perhaps you want to create \"custodial
wallets\" for lots of holders, wallets that aren't stored on a mobile
device, but that are accessed through a web app. As we've discussed
earlier in the course, it's not an ideal approach, but it may be the
\"best possible\" approach in some cases.

In the early days of ACA-Py the answer to that need wasn't great:
\"create a new deployment of a full agent using a different URL and use
different ports.\" What a pain! Fortunately, a better answer was
possible, and [SICPA](https://www.sicpa.com/) from Switzerland
contributed the code and documentation in ACA-Py to provide multi-tenant
mode.

In multi-tenant mode, a single instance of ACA-Py is deployed, usually
using the horizontal scaling techniques talked about in the previous
section. When the service starts, a base instance of secure storage is
created with limited agent capabilities, but with the added
administrative power to be able to dynamically create new \"tenants,\" a
new agent within the agency. A new tenant is really just three things:

-   A JWT authentication token given to the controller for the new
    tenant agent.

-   A new unit of secure storage (\"sub-wallet\"), a new database for
    the exclusive use of the new tenant.

-   This means that within the database server (e.g., Postgres) the
    \"CREATE DATABASE\" command is executed, and new tables are created
    within that new logical database.

-   An entry in the base secure storage (\"base wallet\") with
    information about the new agent.

**NOTE**: In the ACA-Py multi-tenant documentation, the term \"wallet\"
is used for what we call \"secure storage\" in this course.

Those three elements are sufficient to make an entirely new agent
framework within a single instance of ACA-Py. From outside of the
agency, tenants look exactly like any other Aries agent. Likewise, the
controller's administrative API for the tenant framework is exactly the
same as for a standalone agent framework, allowing the execution of all
of the same Aries protocols. Since the overhead for each tenant is
minimal, the solution can scale to the limits of the underlying platform
(compute and storage), supporting as many tenants as needed.

## Operating Agent Services with Multiple Agents (2) {#operating-agent-services-with-multiple-agents-2 .unnumbered}

The base secure storage plays an important role in multi-tenancy,
identifying for each request the tenant to which it applies and
providing access to the tenant's storage. In most cases, the base
storage holds the decryption key for the tenant storage, although the
multi-tenant capability can be configured such that the decryption key
must be passed in and thus never stored in the agency. The role of the
base storage can be seen from the drawing below, which shows how
messages from external agents are received by the base storage
(\"wallet\" in the drawing) and, based on the intended recipient, passed
on to the right tenant.

![External Agent Messaging in a Multi-Tenant ACA-Py
instance](images/image049.png){width="5.0in"
height="2.1223151793525807in"}

**External agent messaging in a multi-tenant ACA-Py instance**\
Licensed under [CC BY
4.0](https://courses.edx.org/xblock/%E2%80%9Chttps:/creativecommons.org/licenses/by/4.0/%E2%80%9D)

 Requests from the controller must include the issued JWT for the tenant
attached, allowing the ACA-Py instance to find and access the secure
storage for the tenant to process the request. Webhooks from the tenants
can be configured per tenant, allowing each to go to a different URL.

That's all we're going to cover about multi-tenant mode---a little taste
just to let you know the feature is available should you need it for
your use case. It's a pretty advanced feature, and many Aries developers
won't need it---until they do! Want more information about it right now?
Check out this document, [*\"Multi-tenancy in
ACA-Py,\"*](https://github.com/hyperledger/aries-cloudagent-python/blob/main/Multitenancy.md) in
the ACA-Py repository.

## Chapter 8 Summary {#chapter-8-summary .unnumbered}

In this chapter you learned about the challenges of production, covering
a little about mobile and a large amount about enterprise agents. This
chapter covered a lot of territory!

You learned about:

-   The issue of keeping ledgers and agent storage in sync---and the
    danger of losing your agent secure storage---not good.

-   The \"best practice\" pattern for managing ledger objects in
    production.

-   The current process for writing transactions to a ledger that is
    fully permissioned.

-   The need to collaborate in a community to develop the best
    requirements for defining credentials and presentations.

-   Deploying enterprise agents on scalable platforms such as
    Kubernetes.

-   How you can create an agent platform, an agency, running hundreds or
    thousands of agents within a single Aries deployment.

Don't worry, you won't need all of these features on day one of your
work as an Aries developer. But we did want you to know about some of
the more powerful features under the hood, as you get closer to
releasing your first Aries-based product.

## Chapter 9 Overview -- What to Do Next {#chapter-9-overview-what-to-do-next .unnumbered}

We've covered the core of the materials. Congratulations---you've made
it! We hope you are well on your way to becoming a Hyperledger Aries
developer.

With the heavy content and labs complete, this chapter provides a look
forward at what might be next on your journey. We have looked at agents
and controllers, agents and protocols, and agents and frameworks. We've
looked at testing, message routing, mobile agents and moving things into
production. Now it's time to consider what you want to do with Aries.

## Learning Objectives {#learning-objectives-8 .unnumbered}

In this chapter, you will learn about:

-   Where your development efforts might fit best and how they apply to
    the technical layers of the Trust over IP (ToIP) stack.

-   What Aries projects are active and where you can contribute.

-   Aries Working Group Calls and other ways to get involved.

## Next Steps {#next-steps .unnumbered}

Now that you have (almost) completed the course, consider what you want
to work on next:

-   Are you looking to build an application on top of Aries?

-   Do you want to add a new capability to Aries?

-   Do you want to contribute to an existing Aries project?

-   Do you want to contribute to the projects that are used in Aries,
    such as AnonCreds, Indy, and Ursa?

In the following, we go through the technical layers of the Trust over
IP (ToIP) stack from top to bottom and relate that to what you could
work on next. As you will recall, the Trust over IP stack was introduced
in the prerequisite course, [*\"Introduction to Hyperledger
Self-Sovereign Identity Blockchain Solutions\"
(LFS172x)*](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa) and
is represented in this image from the [Trust over IP
Foundation](https://trustoverip.org/).

![Trust over IP (ToIP) Technology
Stacks](images/image007.png){width="5.0in"
height="3.0518208661417323in"}

**Trust over IP (ToIP) Technology Stack**\
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

Our expectation is that the majority of developers will work on ToIP
applications---building Aries controllers at Layer 4, that run on top of
the Aries frameworks that occupy Layers 2 and 3 of the ToIP technical
stack. A minority of developers will become contributors to the open
source technologies at or below Aries frameworks. Given that, if you are
not going to contribute at the lower levels, it's OK that you don\'t
need to know everything about those layers. It\'s much like web
development---you don\'t need to know TCP/IP to build web apps.

## Developing Enterprise Applications {#developing-enterprise-applications .unnumbered}

If you just want to build enterprise applications on top of the
decentralized identity-related Hyperledger projects, you will be doing
exactly what we've discussed in this course, building cloud-based
controller apps using any language you want, based on an agent framework
such as [Aries Cloud Agent
Python](https://github.com/hyperledger/aries-cloudagent-python) (ACA-Py).
You can start by using the examples we have provided in the labs in this
course, from scratch, or look in the community for starter kits that are
available (such as this [Verifiable Credential Identity Starter
Kit](https://github.com/bcgov/issuer-kit) from the BC Government). As we
have seen throughout the course, developing enterprise issuer/verifier
Aries agents is much like building any web service: receive events,
process them and respond.

## Enterprise Agent Open Source Projects {#enterprise-agent-open-source-projects .unnumbered}

While most folks are building ToIP applications for their own needs,
here is an enterprise agent open source project that some might find
intriguing. One of the initiatives currently (January 2023) incubating
within the [Hyperledger
Labs](https://labs.hyperledger.org/) organization is the
interesting [Business Partner Agent (BPA) open-source
project](https://github.com/hyperledger-labs/business-partner-agent) that
was started by [Bosch](https://www.bosch.com/). A BPA is a Hyperledger
Aries agent for an organization that allows the organization to:

-   Receive verifiable credentials issued to it.

-   Share self-asserted data and data from the verifiable credentials it
    holds by responding to presentation requests.

-   Request presentations from partners and other organizations.

-   Issue verifiable credentials.

It's kind of like the organizational equivalent of a person's mobile
wallet, but intended for business-to-business use cases, ideal for
things such as controlled sharing of supply chain information to prove
the provenance of products, and the organizations that produced those
products.

In addition to its Aries DIDComm interface to interact with other
agents, a BPA exposes a web-based interface for authorized users within
the organization to see and respond to requests coming into their BPA,
and to initiate requests to other BPAs (or other Hyperledger Aries)
agents. Incoming requests are handled by configurable workflows that
might be as simple as an automatic response, to as complex as a
multi-person, multi-level approval business process. And of course, BPA
users present data from verifiable credentials they hold for BPA
authentication and authorization.

Just as almost all companies have a web presence today, we can see a
future where all companies have their own public BPA for exchanging
verifiable information to enable trusted business transactions. It's a
big project with a ton of potential!

## Mobile Hyperledger Aries Wallets {#mobile-hyperledger-aries-wallets .unnumbered}

As we covered in Chapter 7, if you want to build and deploy a mobile
wallet, there are open source options available to start with, such as
the [Aries
Bifold](https://github.com/hyperledger/aries-mobile-agent-react-native) project.
If you are going to build off of the source bases, we strongly recommend
you do most of the work within those projects, collaborating to
everyone's benefit. In the long run, we hope that there are a number of
Aries mobile agents in the app stores that offer users fantastic mobile
experiences. In the short run, we expect that some organizations will
want to issue companion mobile wallets that work closely with their
enterprise web services. Organizations may even extend their existing
mobile applications to include Aries agent/ToIP capabilities. Credit
Union tech company Bonifii has taken this path with its MemberPass
capability in its mobile app that makes verifying the user on support
calls way more secure.

## Collaborating in the Aries Community {#collaborating-in-the-aries-community .unnumbered}

As a developer building applications that use/embed Aries frameworks, we
recommend you join the regular [Aries Working Group
calls](https://wiki.hyperledger.org/display/ARIES/Aries+Working+Group) (see
the last section of this chapter) and Aries channels on the [Hyperledger
Discord Server](https://chat.hyperledger.org/home). The maintainers of
the Aries repositories often hold regular meetings about their project.
For example, ACA-Py holds [biweekly
ACA-Pug](https://wiki.hyperledger.org/pages/viewpage.action?pageId=24780322) (Aries
Cloud Agent Python Users Group) meetings to bring together the ACA-Py
developers and teams building applications on ACA-Py. Listed at the end
of this chapter are the links for all of the Aries project chat channels
and meeting pages.

![Aca Pug logo](images/image050.png){width="2.0in"
height="2.296551837270341in"}

Looking for Hyperledger Aries product ideas? The last chapter of the
prerequisite course
([LFS172x](https://www.edx.org/course/identity-in-hyperledger-aries-indy-and-ursa))
provided a list of areas where the verifiable credentials model could be
applied, ranging from identity to climate change. Jump back to that
chapter to remind yourself of just some of the many possibilities with
Aries technology. But realize that the possible applications are truly
endless. We hear of new ideas every day!

## Learning the Protocols {#learning-the-protocols .unnumbered}

As we've talked about a lot in the course, the [Aries
RFCs](https://github.com/hyperledger/aries-rfcs) repo is an important
resource. As you get started in building applications, we recommend you
review the Aries Interop Profiles (1.0 and 2.0) in [RFC
0302](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0302-aries-interop-profile),
where you will find links to the set of RFCs/protocols that many of the
existing agents and agent frameworks support. Sticking to these
protocols will ensure that your applications will interact with other
agent-based applications in the ecosystem. As well, you should look at
the state of the agents and agent frameworks that are available, and
choose the right one for your application.

**NOTE**: If building apps is what you want to do, you don\'t need to do
a deep dive into the Aries agent framework (beyond the API they expose),
the AnonCreds, Indy or Ursa repositories. You need to know the concepts
implemented by those projects, but it\'s not a requirement to know those
code bases intimately.

If we did our job right in building this course, you should now have all
the tools you need to get started!

## Helping the Community {#helping-the-community .unnumbered}

As you build controllers on top of the Aries projects, you may find
limitations in what is available today in Aries frameworks. When that
happens the community would love it if you made a contribution. A start
would be just to raise the topic on [Hyperledger
Discord](https://wiki.hyperledger.org/display/HYP/Our+chat+service) or
create an issue in GitHub that clearly outlines what you are trying to
do, and the limitations you have hit. From there, the community will be
more than willing to help you move forward. Perhaps you haven't yet
discovered the capability already exists, or perhaps it's a deficiency
that needs to be addressed. Either way, the community will help you find
a way to make progress.

The following are some ideas for some ways you can contribute to Aries
projects and the other open-source projects on which they are built.

## Extending the Aries Bifold Open-Source Mobile Wallet {#extending-the-aries-bifold-open-source-mobile-wallet .unnumbered}

We've noted Aries Bifold as being a rich, open-source mobile wallet. The
developers working on Aries Bifold welcome new contributors with mobile
expertise to enhance the product. Ultimately, all published (in the app
stores) mobile agents are by definition proprietary, but there is a lot
of shared work needed to make it easier for organizations to create
great mobile self-sovereign identity experiences. Join the user
experience group and help to make a beautiful wallet. Code the features
designed by the user experience team. Make it easier to customize Aries
Bifold without having to fork the repository. Update Aries Bifold to use
newly added features in Aries Framework JavaScript. Improve the
continuous integration/continuous delivery pipelines. There are lots of
places to help!

## Mobile Wallet Backup and Restore {#mobile-wallet-backup-and-restore .unnumbered}

As we discussed in both this course and its prerequisite, mobile agent
backup and restore is a crucial capability that must be both secure and
easy for users. Consider designing and building a backup and restore
capability for mobile agents that both automates the backup operation
(that's pretty easy) and provides a user-friendly, secure restore
operation (that's a bit more challenging!).

## Contributing to the Aries Agent Test Harness {#contributing-to-the-aries-agent-test-harness .unnumbered}

Embracing interoperability is a huge part of building a sustainable
ecosystem. The Hyperledger Aries community wants to empower creators of
Aries agents to build their applications with confidence that they will
work with all of the other agents in the community. As we talked about
in Chapter 2, the Aries Agent Test Harness is a crucial piece of the
interoperability puzzle, enabling continuous, automated testing of Aries
agent frameworks and agents. Here are some of the ways that you can
contribute to the [Aries Agent Test
Harness](https://github.com/hyperledger/aries-agent-test-harness) open
source project.

-   Add tests that expand the coverage of Aries Interop Profiles, such
    as additional AIP 2.0 tests, DIDComm V2 tests. We\'re even getting
    to the point that we can improve AATH by subtraction---removing some
    of the old AIP 1.0 tests.

-   Expand the scope of the tests supported by specific Aries frameworks
    or for the Mobile Backchannel. As different Aries frameworks add
    more features, they don't always add support for those new features
    in their AATH backchannel. Expand the backchannel and add the newly
    supported tests in the nightly runsets.

-   Develop backchannels to enable testing of specific, important Aries
    implementations (such as yours!).

-   Monitor the test runs and take ownership of failing tests to at
    least determine the faulty component, and ideally, drive a fix to
    it. The faulty component could be in a number of places and it's a
    challenge to figure out where the problem might be. Is it:

\- The RFC from which the test was defined?\
- The test itself?\
- One of the backchannels operating a component-under-test?\
- The functionality of a component-under-test?

Once you identify the problem, create an issue to get the right team to
fix it---or, fix it yourself!

## User Experience {#user-experience .unnumbered}

The focus of the Aries (and AnonCred, Indy, and Ursa) communities to
this point has definitely been on the underlying technology. The
majority of the community is technical and the focus has been more on
getting things working in a secure manner. However, as products based on
the technology begin to move into the mainstream, there is a need to
focus on user experience. How can we provide the benefits of this new
technology in ways that are easy for the majority of the population? In
2022 we saw the start of a shift to focus on user experience, especially
in the mobile wallet space. However, ease-of-use needs to be at the
core, and as such, we need more great designers to join the community to
make that happen. Projects such as the mobile agents and Business
Partner Agent on the enterprise side are great places to contribute.

## Aries Documentation {#aries-documentation .unnumbered}

That \"user experience\" focus also needs to extend to developers
joining the community, like you! For the first 5 years of the Aries,
AnonCreds, Indy, and Ursa projects, documentation was of technical
nature and targeting project contributors and maintainers. It was enough
to have a good **README.md** in the repository that was updated
periodically. Now, READMEs are not enough. We need to transition the
documentation to friendly, multi-audience, generated websites that make
it easy and interesting to bring new people into the projects. Aries
Framework JavaScript's recent launch of their [documentation
site](https://aries.js.org/) is a great example of this transition. We
need more of those! Highest priorities? Aries Cloud Agent Python and the
Aries RFCs site.

## Driving RFCs from Proposed to Accepted {#driving-rfcs-from-proposed-to-accepted .unnumbered}

As you begin to build your applications and discover features you wish
you had, ask in the community. You may find that an existing RFC covers
your needs. Is your idea new and you need other agents to support it?
Raise it in the community and if appropriate, contribute an RFC and
drive it with an implementation. In reviewing and contributing RFCs,
please make sure you look at the
main [README](https://github.com/hyperledger/aries-rfcs/blob/main/README.md) for
the repo, covering the RFC lifecycle, and
the [contribution](https://github.com/hyperledger/aries-rfcs/blob/main/contributing.md) guidance.

Also, when you are looking at the Aries RFCs, don't hesitate to add pull
requests to clarify existing RFCs. The Aries RFC process allows for the
addition of clarifying text without changing the major/minor version of
the protocol. Accurate, clarifying corrections are welcome!

## Creating a Scalable ZKP Revocation Scheme in AnonCreds {#creating-a-scalable-zkp-revocation-scheme-in-anoncreds .unnumbered}

The biggest challenge in using AnonCreds is the revocation scheme. The
great news is that it works and is reliable. The bad news is that it
really doesn't scale sufficiently. It's not going to work when there is
a holder population in the millions for a given verifiable credential
type. On a positive note, a [design has been
developed](https://docs.google.com/presentation/d/10dGC-qKU7XT2WRd_wTxK82u0FmvjJrfdXwFEiWGauE4/edit#slide=id.p) and
a proof-of-concept implemented for a replacement revocation scheme that
has the scalability we would love to see---1M credentials per revocation
registry! However, to this point (January 2023), we've not received
sufficient interest from an organization to create a complete,
AnonCreds-friendly version of the approach. It would be a huge
contribution to the AnonCreds community to develop an open-source
implementation of this scheme.

## Ledger-Agnostic and W3C Format AnonCreds {#ledger-agnostic-and-w3c-format-anoncreds .unnumbered}

As of this writing (January 2023), one of the biggest initiatives in the
Aries community is the definition and implementation of ledger-agnostic
AnonCreds---being able to use AnonCreds with ledgers other than Indy. In
addition to working on AnonCreds, updates are being made to the Aries
frameworks that will simplify using AnonCreds on other ledgers.

At the same time, a technique to put AnonCreds credentials into the W3C
Verifiable Credentials Data Model Standard format has been defined. Such
a deployment will reduce the friction in using AnonCreds with other
common W3C Data Model signature schemes. Such a change will even allow
attaching to a single credential and multiple credential signature
schemes, giving holders and verifiers choice in how they present and
verify a given credential.

Contributing to initiatives in and around privacy-preserving Hyperledger
AnonCreds is definitely worth looking into!

## Improving indy-node {#improving-indy-node .unnumbered}

If you are interested in getting into the public ledger part of Indy,
particularly if you are going to be a Sovrin or Indicio Steward, you
should take a deep look into indy-node. As with all of the original Indy
technology, indy-node is robust, of high quality and is well thought
out. As the network grows, use cases change and new cryptographic
primitives move into the mainstream, and thus, indy-node capabilities
will need to evolve. Indy-node is coded in Python. Indy-node is a great
place to contribute to the community!

## Working in Cryptography {#working-in-cryptography .unnumbered}

Finally, at the deepest level, and core to all of the projects is the
cryptography in [Hyperledger Ursa](https://github.com/hyperledger/ursa).
If you are a cryptographer, that\'s where you want to be---and we want
you there!

## Additional Resources {#additional-resources .unnumbered}

We've covered most of the ways to get involved in the content above, so
the following is just a list of those resources with links:

-   [Hyperledger Aries](https://www.hyperledger.org/use/aries) project
    page

-   The Aries Working Group [Wiki, and meetings
    schedule](https://wiki.hyperledger.org/display/ARIES/Aries+Working+Group)

-   [Hyperledger
    Discord](https://wiki.hyperledger.org/display/HYP/Our+chat+service) and
    the main [Aries
    channel](https://discord.com/login?redirect_to=%2Fchannels%2F905194001349627914%2F905206466410057728)

-   [Aries Cloud Agent - Python User
    Group](https://wiki.hyperledger.org/pages/viewpage.action?pageId=24780322), [meetings
    schedule](https://wiki.hyperledger.org/display/ARIES/ACA-Pug+Meetings),
    and [Discord
    channel](https://discord.com/login?redirect_to=%2Fchannels%2F905194001349627914%2F941706593739894804)

-   Aries Framework
    JavaScript, [Wiki](https://wiki.hyperledger.org/display/ARIES/Aries+Framework+JavaScript), [meetings
    schedule](https://wiki.hyperledger.org/display/ARIES/Framework+JS+Meetings),
    and [Discord
    channel](https://discord.com/login?redirect_to=%2Fchannels%2F905194001349627914%2F941708033434738768)

-   Aries Framework
    Bifold, [Wiki](https://wiki.hyperledger.org/display/ARIES/Aries+Bifold+User+Group), [meetings
    schedule](https://wiki.hyperledger.org/display/ARIES/Aries+Bifold+User+Group+Meetings),
    and [Discord
    channel](https://discord.com/login?redirect_to=%2Fchannels%2F905194001349627914%2F941708242030063656)

-   The [Hyperledger
    AnonCreds](https://www.hyperledger.org/use/anoncreds) project
    page, [Wiki](https://wiki.hyperledger.org/display/ANONCREDS), [meeting
    schedule](https://wiki.hyperledger.org/display/ANONCREDS/Meetings%3A+AnonCreds+Specification+Working+Group),
    and [Discord
    channel](https://discord.com/login?redirect_to=%2Fchannels%2F905194001349627914%2F1035263835449331793)

Starting from those links, you can learn anything more you need about
becoming a Hyperledger Aries developer! The Aries community is very
welcoming.

## Chapter Summary {#chapter-summary .unnumbered}

That's a wrap! Thank you for taking the course. We hope that you have
acquired a sound understanding of Aries agents and are ready to jump in,
contributing to this new and exciting technology.

...the end.
