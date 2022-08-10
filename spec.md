# Trust over IP (ToIP) Technology Architecture Specification

#### Revision History
#### Editors:
#### Contributors:

*Copyright: *

## 1. Introduction

The mission of the Trust over IP (ToIP) Foundation is to define an overall architecture for Internet-scale digital trust that combines cryptographic assurance at the machine layers (technology) with human accountability at the business, legal, and social layers (governance). Together these two halves form a complete four-layer architecture for decentralized digital trust infrastructure known as the [ToIP stack](https://trustoverip.github.io/toip/glossary#toip-stack), illustrated in Figure 1.

<img src="/images/ToIPDualStack.jpeg" alt="ToIP Dual Stack" style="width:800px;"/>

**Figure 1: Conceptial diagram of the ToIP stack**

This document is the normative specification for the high level architecture of the ToIP technology stack (the left half of Figure 1).  It is a deliverable of the [Technology Stack Working Group](https://wiki.trustoverip.org/display/HOME/Technology+Stack+Working+Group) at the [ToIP Foundation](https://www.trustoverip.org/). It is recommended to read this document in conjunction with three other deliverables from the ToIP Foundation:

1. [Introduction to ToIP](https://www.trustoverip.org/wp-content/uploads/Introduction-to-ToIP-V2.0-2021-11-17.pdf) is our white paper that provides an overall introduction to the market needs leading to the emergence of decentralized digital trust infrastructure. It explains the origin and basic structure of the ToIP stack together with the mission and activities of the ToIP Foundation.

1. [Design Principles for the ToIP Stack](https://www.trustoverip.org/wp-content/uploads/Design-Principles-for-the-ToIP-Stack-V1.0-2022-01-17.pdf) enumerates the set of design principles informing, guiding, and constraining the design of the ToIP stack.

1. [ToIP Governance Architecture Specification](https://wiki.trustoverip.org/pages/viewpage.action?pageId=71241) defines the overall requirements for ToIP-compliant governance frameworks.

As with all ToIP deliverables, the ToIP Foundation invites your feedback and suggestions. Please contact us via any of the channels listed on the [ToIP Foundation](https://www.trustoverip.org/) website.

## 2. Terminology

In this document, the key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL", when appearing in ALL CAPITALS, are to be interpreted as described in [IETF RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119).

All other defined terms are linked to their definitions in the applicable [ToIP glossary](https://trustoverip.github.io/toip/glossary) following the process defined by the [ToIP Concepts and Terminology Working Group](https://wiki.trustoverip.org/pages/viewpage.action?pageId=65700).

## 3. Motivations

*This section is informative.*

The goal of this specification is to define the overall requirements for a layered system architecture that enables interoperable trust relationships between any two peers on the Internet. This is directly analogous to the role the TCP/IP stack plays in enabling interoperable data exchange between any two peers on the Internet. The design patterns applicable to solving these interoperability challenges, and the motivations for each, are detailed at length in [Design Principles for the ToIP Stack](https://trustoverip.org/permalink/Design-Principles-for-the-ToIP-Stack-V1.0-2022-11-17.pdf).

Whether from the perspective of an implementer, a customer, or a policymaker, there are many benefits to a well-defined layered architecture:

- **Engineering stability.** The abstraction of bundling technologies and policies within distinct layers isolates changes within a layer from interactions and dependencies between layers. The result is a framework more resilient to structural changes in other parts of the stack.

- **Wide adoption through a principled trust spanning layer.** Achieving universal interoperable trust relationships between any two peers on the Internet is very challenging because we have a wide range of different understandings of the meaning of trust. The example of the TCP/IP stack offers a principled design pattern based on a simple minimalistic protocol (i.e. IP) as a common spanning layer, and more diverse task specific protocols on top of this common layer (e.g. TCP for connection-oriented, UDP for connectionless). Such a principled *trust* spanning layer can maximize adoption, interoperability and reachability in a similar way.

- **Consistency.** A well-defined architecture enables the development of software components and applications that can be trusted to act in predictable, consistent ways—and that can trust other components and applications to do the same.

- **Interoperability and vendor independence.** As with the TCP/IP stack, the Bluetooth stack, the NFC stack, or other protocol stacks, implementations from multiple vendors can and should be interoperable, and customers should be able to switch between them without major loss of functionality.  In addition, we want the TOIP stack to be as interoperable as is practical with existing internet technologies that may not embody TOIP goals, as long as the guiding principles of Trust Over IP are not frustrated.

- **Development communities.** As with each of the examples named above, a well-designed architecture stack helps spawn a robust, diverse community of developers building solutions whose interoperability depends on the core stack. More development attracts more customers, producing a network effect benefiting the entire ecosystem.

- **Commoditization.** Standardization of a stack for mass adoption helps turn it into a commodity, reducing both the cost of implementation and the time to market. It also frees vendors to focus on strategic differentiation in their service offerings.

- **Public policy.** A well-defined architecture with clear and concise terminology helps policymakers and legal experts define coherent policies and regulations in a manner that serves the needs of society without constraining technical innovation and competition. 

## 4. Audience and Scope

*This section is informative.*

The audience for this specification is protocol designers, system architects, software developers and product managers. The purpose of the reference architecture defined in this specification is to guide them in the development of protocols, system architectures, and software products that meet two key types of interoperability requirements:

1. **System-to-system interoperability requirements**: the architectural components and the interactions between those components necessary for interoperability of all systems acting within a ToIP digital trust ecosystem.
1. **Functional interoperability requirements**: the software functions required for each of the four layers including:
     - What each layer must do.
     - What each layer should do.
     - What behaviors are expected to support interoperability.
     - What interactions each layer supports for other layers on which it depends, or which depend on it.

Upon reading this specification, the intended audience should have a better understanding of the implications of their protocol design, system architecture, or product architecture with regard to interoperability between multiple implementations.

The scope of this specification is limited to defining the architectural requirements for each layer in the ToIP stack. The following are explicitly out-of-scope:
- The definition of specific protocols or interfaces at each layer.
- The definition of specific supporting systems or intermediary systems for any layer.
- The definition of specific test cases or interoperability profiles—including both vertical and horizontal interoperability—that can be used for test harnesses.
- The definition of applications (and their user interfaces) that run on top of the ToIP stack.
- The definition of trust frameworks or governance frameworks for usage of the ToIP stack within specific digital trust ecosystems.

The ToIP Technology Stack Working Group has committed to producing two additional documents addressing some of these needs:
1. **ToIP Interoperability Test Cases** will specify interoperability profiles that can be implemented by commercial-grade test harnesses and testing labs.
1. **ToIP Primer for Policymakers** will guide policymakers, governing authorities, analysts, and other non-technical audiences who need to deeply understand the purpose, uses, and implications of the ToIP stack but do not need (or want) to dive into technical details.

The rest of the specifications and guides necessary to develop, test, and deploy interoperable implementations of the ToIP stack are expected to be developed by the ToIP Technology Stack Working Group, other ToIP Working Groups, other standards development organizations, independent governing authorities, and independent developers.

## 5. Example Use Cases

*This section is informative.*

## 6. Reference Architecture Overview

*This section is informative.*

### 6.1 Design Goals

A reference architecture of a complex system is an abstract framework consisting of a list of component subsystems (or functions) and the interfaces of interactions with each other and external systems. 

Such a reference architecture is an exercise in design guided by a set of most significant goals or principles. Our overarching goals are twofold:

1. Defining a general means of establishing trust between any two endpoint systems over the Internet,
1. Achieving universal interoperability among implementations.

These twin objectives lead us to a set of design principles that influence the design choices presented in this document. These design principles are further discussed in the [Design Principles for the ToIP Stack](https://www.trustoverip.org/wp-content/uploads/Design-Principles-for-the-ToIP-Stack-V1.0-2022-01-17.pdf). 

On the first goal, establishing trust between parties requires that each party develop confidence in the following properties of their relationship:

1. **Authenticity:** is each party who the other party believes it to be?
1. **Confidentiality:** are the communications between the parties only accessible by the parties?
1. **Privacy:** will the expectations of each party—with respect to usage of the information communicated between the parties—be upheld by the other party?

These three properties of trust relationships are ordered, meaning each one depends on the one before it. Furthermore, in some trust relationships, confidentiality and privacy are optional. Thus our design goal with the ToIP stack is to achieve authenticity first, then confidentiality, then privacy. 

On the second goal, we share the same goal of global scalability as the original Internet architecture. This involves several intertwined considerations that overlap and reinforce each other as summarized by the first four [Design Principles for the ToIP Stack](https://www.trustoverip.org/wp-content/uploads/Design-Principles-for-the-ToIP-Stack-V1.0-2022-01-17.pdf):

- The End-to-End Principle
- Connectivity Is Its Own Reward (Universal Interoperability)
- The Hourglass Model
- Decentralization

### 6.2 The Four Layer Pattern

Together these considerations lead to the general four-layer pattern summarized in Table 1.

| Leyer # | Generic Name | ToIP Name |
|---------|--------------|-----------|
| 4       | Application. | Trust Application |
| 3       | Supported protocols | Trust Tasks |
| 2       | Spanning Protocol | Trust Spanning Protocol |
| 1       | Supporting Protocols | Trust support |

**Table 1: The four layer pattern of large-scale protocol stacks**

The keystone to this pattern is the role of the spanning layer at Layer 2. Much of the success of the Internet is attributed to its “hourglass” design in which a single spanning layer protocol—the IP protocol—is supported by a variety of lower-level protocols below it. The spanning layer in turn supports a variety of higher-level protocols above it. How this hourglass design applies to the four ToIP layers is illustrated in Figure 2.

<img src="/images/Fourlayerpattern.jpeg" alt="Four layer pattern" style="width:800px;"/>

**Figure 2: How the four layer pattern fits the Hourglass Model**

The spanning layer protocol maximizes interoperability because it provides a common way for all the higher level protocols to communicate via all the lower level protocols. This is why the design of the spanning layer protocol must be “as simple as possible but no simpler”. It should support only the minimal foundational functions needed by the supported protocols. 
In terms of our specific design goals, this means the ToIP trust spanning layer must only satisfy our first goal. All other goals can be accomplished by protocols and functions at other layers. 



### 6.3 High-Level System Architecture

This section describes a reference architecture for ToIP that provides a generalization of various viable solutions for trust establishment over the Internet. It provides the common concepts and vocabulary with which to discuss implementations of each component, the protocols or interfaces between these components, and interoperability among different implementations. Subsequent sections will describe these components and protocols in more detail.

At the highest level, a ToIP system consists of three base types of component systems that together all interact using the common infrastructure of the Internet:

1. At least two Endpoint Systems (often simply referred to as Endpoints).
1. A set of zero or more Supporting Systems that support trust establishment among the Endpoint Systems.
1. A set of zero or more Intermediary Systems that may be employed to assist the interactions between the Endpoint Systems. 

This high level view is depicted in Figure 3.

<img src="/images/Highlevelreferencearchitecture.jpeg" alt="High level view of the ToIP Reference Architecture" style="width:800px;"/>

**Figure 3: High Level View of the ToIP Reference Architecture**

The first level of decomposition is based on the locus of control. This is a critical decision because the locus of control determines the chains of dependencies as we construct end-to-end trust between any two Endpoint Systems. Each subsystem, whether it is classified as an Endpoint System, Supporting System, or Intermediary System, is its own locus of control. An Endpoint System, for example, may be a tiny IoT device, a personal smartphone, or a large capacity service hosted in a cloud. What matters to the architecture is that it exhibits a consistent locus of control with respect to other subsystems.

These subsystems collaborate with each other through three types of interactions:
- Endpoint System to Endpoint System
- Endpoint System to Supporting Systems
- Endpoint System to Intermediary Systems

The ToIP Endpoint Systems follow a 4-layered design pattern. As we move up the stack, roles played by an Endpoint System are often given more context specific names. For example, a credential exchange Trust Task in layer 3 may use terms such as issuers, holders, and verifiers to describe such roles played by the Endpoint Systems and the interactions among them in that context. These higher layer terms are specific to that context and must be consistent with the abstract and general terms used in this Reference Architecture.

The normative requirements for each type of subsystem and interaction across the ToIP layers are specified in the following sections.


## 7. Endpoint Systems and the Layered Stack
### 7.1 Endpoint Systems
### 7.2 Layer 1 (Infrastructures)
### 7.3 Layer 2 (Trust Spanning)
### 7.4 Layer 3 (Trust Tasks)
### 7.5 Layer 4 (Applications)

## 8. The End System to End System Trust Spanning Protocol
### 8.1 Overview
### 8.2 Identifier
### 8.3 Messages
### 8.4 Routing
### 8.5 Interface to Layer 1

## 9. Supporting Systems
### 9.1 Overview
### 9.2 Example 1
### 9.3 Example 2
### 9.4 Generalization

## 10. Intermediary Systems

## 11. Endpoint System Interoperability
### 11.1 Interoperability between Endpoints with Decentralized Identifiers
### 11.2 Interoperability between Endpoints with Decentralized and Other Identifiers


## 12. Integration with the ToIP Governance Stack

## 13. References


## About the ToIP Foundation

