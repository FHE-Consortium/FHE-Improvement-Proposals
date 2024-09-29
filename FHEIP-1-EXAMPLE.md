## FHEIP-01: FHEIP Purpose and Guidelines
| FHEIP | Title | Description | Author | Discussion | Status | Type | Date | 
|------|-------|-------------|--------|------------|--------|------|------|
| 1 | FFHEIP Purpose and Guidelines | Describes community standards for EVM-compatible blockchains implementing FHE functionality | [Your Name] | [Forum Link] | Draft | Informational | [Date] |

### Abstract

Fully Homomorphic Encryption Improvement Proposals (FHEIPs) describe community standards for EVM-compatible blockchain ecosystems implementing Fully Homomorphic Encryption (FHE) functionalities, including core protocol specifications, contract standards, and client APIs.

### What is a FHEIP?

FHEIP stands for Homomorphic Encryption Improvement Proposal. A FHEIP is a design document providing information to the community or describing a new feature for any EVM-compatible blockchain that supports FHE functionalities. FHEIPs are used by authors to measure, document, and build community consensus while providing technical specifications and motivation behind a specific feature proposal.

### FHEIP Rationale

In a decentralized and self-governed system, a framework is necessary for the developer community to inform, propose, and gather feedback on new features or changes. By introducing a transparent and versioned repository, the community maintains a historical record of all feature proposals, including their revision history and implementation progress. The main discussion space for all FHEIPs is a dedicated community forum, and feedback will be incorporated into the documented FHEIPs housed in the GitHub repository.

### FHEIP Principles

In order to ensure FHEIPs can serve their intended purpose, a FHEIP author should check that the FHEIP content is consistent with the principles below:
- **Uniqueness:** Ensure the proposal is the first of its kind. If an existing proposal is found, collaborate with the previous author to modify/extend the proposal.
- **Understandability:** The content should be clear and understandable without oversimplification, ensuring there is only one possible interpretation of proposed changes.
- **Conciseness:** Content must be as short as possible while maintaining focus.
- **Precision:** Content must reflect a narrowly-defined subject. Complex subjects should be split into complementary FHEIPs.
- **Thoroughness:** Address or reference all relevant aspects with regard to implementation and existing FHEIPs.

### FHEIP Types

The general categories for FHEIPs include:
- **Contracts:** Enhancements to smart contracts that leverage FHE capabilities.
- **Interface:** Improvements related to client API/RPC specifications and standards, ensuring interoperability across various blockchain implementations.
- **Informational:** Recommendations, information, or general discussions on relevant issues presented to the community.

## FHEIP Flow

### Idea
1. Initial post on Github discussions _or some other forum_.
2. Authors clarify their idea to reviewers and interested parties, inviting feedback from editors, developers, and the community.

### Draft
3. Assemble the FHEIP using the suggested template. Content should adhere to FHEIP principles. Editors will assist in amending any required changes.

### Review
4. Once ready, the author marks the FHEIP for peer review. It can be discussed and announced in relevant channels.

### Last Call
5. A PIP Editor assigns "Last Call" status for final review before finalization. Necessary changes revert the FHEIP back to Peer Review.

### Final
Once feedback is addressed and content is finalized, the FHEIP becomes an issue on GitHub. This represents the final standard and should only be updated for errata and non-normative clarifications. FHEIPs that have been live on the mainnet receive 'final' status.

## FHEIP Body

### Title
The title of the FHEIP should be concise and accurately explain its purpose.

### Status
One of the following statuses:
- **Draft:** Initial submission and discussion stage.
- **Review:** Author requests peer review.
- **Last Call:** Final review window before final status.
- **Final:** Represents the final standard.
- **Continuous:** For FHEIPs designed for ongoing updates.
- **Withdrawn:** The proposal is permanently withdrawn.

### Abstract
A short description (~200 words) of the technical issue being addressed.

### Motivation
Clearly explain why the existing protocol specification is inadequate and any potential self-interest.

### Specification
Describe the syntax and semantics of any new feature, detailed enough to allow interoperable implementations.

### Rationale
Describe the motivation behind design decisions and any alternative designs considered.

### Backwards Compatibility
Describe any backwards incompatibilities and how they are addressed.

### Reference Implementation
Optional section containing a reference implementation.

### Security Considerations
Discuss relevant security implications. Proposals without this section may be rejected outright.

### Copyright
Provide a license compatible with the original code or make available under CC0 1.0 Universal.

## FHEIP Editor Responsibilities

Editors review new FHEIPs to ensure readiness, soundness, and completeness, checking for technical sense, accuracy, and language correctness. If not ready, authors receive specific feedback for revisions. Once approved, editors upload the proposal to GitHub.

### FHEIP Editors

TBD

### References

The FHEIP framework, and in particular FHEIP-01 was heavily derived from the [Polygon Improvement Proposal-01], which was derived from [Ethereum EIP-1](https://eips.ethereum.org/EIPS/eip-1) document [Martin Becze, Hudson Jameson, et al., "EIP-1: EIP Purpose and Guidelines," Ethereum Improvement Proposals, no. 1, October 2015. [Online serial] Available: https://eips.ethereum.org/EIPS/eip-1.], which was derived from [Bitcoin's BIP-0001](https://github.com/bitcoin/bips) (written by Amir Taaki) which in turn was derived from [Python's PEP-0001](https://peps.python.org/) (written by Barry Warsaw, Jeremy Hylton, David Goodger, and Nick Coghlan)

### Copyright

All copyrights and related rights are waived under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/legalcode).
