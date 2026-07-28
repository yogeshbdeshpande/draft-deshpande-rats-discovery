---

title: "Remote Attestation Entity Discovery"
abbrev: "RED"
category: info

docname: draft-deshpande-rats-discovery-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: "Security"
workgroup: "Remote ATtestation ProcedureS"
keyword:
 - next generation
 - unicorn
 - AI-native
venue:
  group: "Remote ATtestation ProcedureS"
  type: "Working Group"
  mail: "rats@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/rats/"
  github: "yogeshbdeshpande/draft-deshpande-rats-discovery"
  latest: "https://yogeshbdeshpande.github.io/draft-deshpande-rats-discovery/draft-deshpande-rats-discovery.html"

author:
 -
    fullname: Yogesh Deshpande
    organization: Arm
    email: Yogesh.Deshpande@arm.com

normative:

informative:
  RFC9334: rats-arch

...

--- abstract

RATS Architecture defines various roles such as Attesters, Endorsers and Verifiers.
These roles are performed by RATS Entities. When there are multiple entities in the ecosystem, they need to be discovered.
This document specifies the problem space of RATS Entity discovery and provides solutions that can be applied to entities performing specific RATS roles.


--- middle

# Introduction

Verifiers, Endorsers, and Attesters are roles defined in the RATS Architecture [RFC9334].
One or more entities undertake these roles to fulfil the functions mandated by these roles.
For example Mulitple Verifiers may be required to perform the appraisal of a composite attester.
When there are multiple Verifiers they need to be discovered before trustworthy appraisal can be completed.
Similarly, when Attesters are composite, the Verifier or an Aggregator in CoServ may need to obtain the Endorsements
from multiple sources, to perform the respective functions. These sources may need to be discovered to fetch the desired Endorsements.

This document provides a generic architecture of discovery for RATS Entities and defines a framework and protocols required to accomplish
discovery.


# Need for RATS Discovery
Composite Attesters come with a varying degree of heterogeneity of Evidence formats, depending on the type of Attesting Environments that come with each Component Attester, for example, CPU variants or GPU/FPGA variants. When Attesters are composite, they needed to be appraised by Multiple Verifiers.
These Verifier may not always be colocated. Similarly the Endorsements for such Attesters may not come from a single authoritative source.
For example, CPU Endorsements come from the premise of CPU Manufactuerer, while GPU Endorsements may come from a trusted GPU Supply Chain.
In order to conduct appraisal, one needs to discover the entities capable of providing the required information to fulfil the desired role.


# Conventions and Definitions

{::boilerplate bcp14}

This document uses terms and concepts defined by the RATS architecture. For a complete glossary, see {{Section 4 of -rats-arch}}.

## Glossary
{: #sec-glossary }

This document uses the following terms:

RATS Entity:

: A RATS Entity is an end point performing a specific RATS Role, such as an Endorser or a Verifier.

Composite Attester:

A RATS Attester, which comprises of multiple components, which are individual Component Attesters.

Component Attester:

: A Component Attester is a single Attester of a Composite Attester.
For this document, a Component Attester is an entity which produces a single Evidence which can be appraised by a Component Verifier.

Composite Evidence:

: Evidence produced by a Composite Attester.
Also referred to as CE in the document.

# Discovery requirements
The discovery of any RATS Entity is built on the following fundamental aspects.

1. Capability

Entities have varying degree of capabilities. For an Attester, its shape and form is heavily dependent on the underlying technology it supports.
For example a Confidential Computing Attester from a specific Vendor will have a capability to produce Attestation Evidence pertaining to that technology.
Similarly, a Verifier capable of Appraising an Evidence for a specific Attestation Scheme can ONLY perform Attestation Verification for a specific Evidence.
Likewise an Endorsement Service from a specific Vendor may be capable of providing Endorsements pertaining to Attesters it manufactures.

2. Trust relationships
Entities need to establish trust prior to exchanging RATS Conceptual Messages, For example, a Lead Verifier may need to establish trust in the Component Verifier, prior to exchanging Component Evidence.  Similarly an CoServ Aggrgator may need to establish trust in an Endorsement service, before it can obtain the Endorsements.


3. Policy Evaluation
Entity Discovery MUST fulfil policy requirements prior to conclusion of a successful discovery.
For example, Entities may be handling PII information in their processing and hence due to Legal and Governance restrictions, processing MAY only be allowed in certain geographical boundaries.

4. Protocol Requirements
In order to discover correct Entities, the communicating parties MUST establish a common protocol. The protocol must represent the essential discovery claims (such as capability information), upon whose processing a discovery match can be obtained.

# Proposed Solution

// TO DO Specifcy Common Capability protocol that can be applied here


# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

Discovery intersection with Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
