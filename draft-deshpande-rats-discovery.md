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

...

--- abstract

RATS Architecture defines various roles such as Attesters, Endorsers and Verifiers.
These roles are performed by RATS Entities. When there are multiple entities in the ecosystem, they need to be discovered.
This document specifies the problem space of RATS Entity discovery and provides solutions that can be applied to entities performing specific RATS roles.


--- middle

# Introduction

Verifiers, Endorsers, and Attesters are roles defined in the RATS Architecture [RFC9334].
One or more entities undertake these roles to fulfil the functions mandated by these roles.
For example when Mulitple Verifiers are required to perform the appraisal of a composite attester,
then these Verifiers needs to be discovered before such trustworthy appraisal can be completed.
Similarly, when Attesters are composite, the Verifier may need to obtain the Endorsements from multiple sources before performing the appraisal.
Then Endorsement entity discovery is required to fulfil the requirement for Endorsements.

## Need for RATS Discovery
Composite Attesters come with a varying degree of heterogeneity of Evidence formats, depending on the type of Attesting Environments that come with each Component Attester, for example, CPU variants or GPU/FPGA variants. When Attesters are composite, they needed to be appraised by Multiple Verifiers.
These Verifier may not always be colocated. Similarly the Endorsements for such Attesters may not come from a single authoritative source.
For example, CPU Endorsements come from the premise of CPU Manufactuerer, while GPU Endorsements may come from a trusted GPU Supply Chain.
In order to conduct appraisal, one needs to discover the entities capable of providing the required information to fulfil the desired role.


## Discovery requirements
The discovery brings many aspects into consideration.

1. Capability

2. Protocol

3. Geographical location

4. Availability

## Proposed Solution

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
