skeleton: NAFATH-V3
Track: AI

## Overview
A trustworthy digital government service depends on six connected areas of information technology: software, artificial intelligence (AI), mobile technology, networking, cybersecurity, and data. Software provides the applications and systems that deliver services, while AI can help users find information and complete tasks more efficiently. Mobile technology makes services accessible through smartphones, and networking connects users, systems, and government platforms. Cybersecurity protects systems and users from threats and unauthorized access, while data supports accurate information, reliable decisions, and personalized services. These areas depend on one another: AI needs software and data, mobile services rely on networks, and all six areas require appropriate security and responsible management. Understanding how they work together helps explain how digital government services can become more accessible, reliable, secure, and effective.
## Software
Under Semantic Versioning, a MAJOR version increases when an incompatible public API change is introduced. A MINOR version increases when functionality is added in a backward-compatible way. A PATCH version increases for backward-compatible bug fixes. For the government assistant, changing or removing an API field that existing app versions rely on may require a MAJOR release. Teams should document changes and test compatibility before deployment.

Resource: Semantic Versioning 2.0.0 - https://semver.org/
## AI
Retrieval-Augmented Generation (RAG) combines a language model with a retrieval system that searches an external knowledge source before an answer is generated. For a government assistant, the system could retrieve relevant passages from approved service descriptions and use them to formulate a response. This can improve factual accuracy and make answers easier to verify, but it does not guarantee correctness; retrieval quality and the model’s use of evidence still need evaluation.

Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks - https://arxiv.org/abs/2005.11401
## Mobile
Apple’s App Transport Security (ATS) requires connections made through the URL Loading System, typically using URLSession, to use HTTPS and meet additional security requirements. If an app attempts an ordinary HTTP connection, ATS generally blocks it unless an applicable exception is configured. The preferred solution is to secure the server with HTTPS rather than broadly weakening ATS, because insecure connections can expose information to interception or modification.

Resource: NSAppTransportSecurity - https://developer.apple.com/documentation/BundleResources/Information-Property-List/NSAppTransportSecurity
## Networking
IPv4 uses 32-bit addresses, whereas IPv6 uses 128-bit addresses, providing a vastly larger address space. IPv6 supports the growing number of addressable devices and offers updated mechanisms for addressing and network configuration. For a government service used by many phones and connected devices, IPv6 support can help accommodate long-term growth. However, deploying IPv6 does not automatically solve every connectivity or security problem; networks and services must be configured and tested appropriately.

Resource: RFC 8200 - Internet Protocol, Version 6 (IPv6) Specification - https://www.rfc-editor.org/rfc/rfc8200
## Cybersecurity
Prompt injection occurs when crafted input manipulates a language model into behaving in unintended ways. Direct injection comes from instructions supplied by a user; indirect injection may be embedded in content the model retrieves or reads, such as a webpage or document. Risk can be reduced by treating retrieved content as untrusted and separating it from trusted instructions, and by limiting the model’s permissions to the minimum required. No single control eliminates the risk.

Resource: OWASP Top 10 for LLM Applications - Prompt Injection - https://genai.owasp.org/llmrisk/llm01-prompt-injection/

## Data
Anonymization removes identifying information so that a person is no longer identifiable by means reasonably likely to be used. Pseudonymization replaces direct identifiers with codes or other values, but additional information may still allow re-identification. Under the GDPR, genuinely anonymous information falls outside the regulation’s scope, whereas pseudonymized personal data remains personal data. Government chat logs should therefore be assessed carefully before being treated as anonymous, especially when other datasets could enable linkage.

Resource: General Data Protection Regulation (GDPR), Recital 26 and Article 4(5) - https://eur-lex.europa.eu/eli/reg/2016/679/oj
## Misconception in My Track
A common misconception is that adding Retrieval-Augmented Generation (RAG) automatically prevents a language model from producing unsafe or manipulated answers. RAG can help the model use relevant external information, but retrieved documents may themselves contain malicious instructions. OWASP explains that RAG and fine-tuning do not fully mitigate prompt injection vulnerabilities. Retrieval must therefore be combined with security controls and testing, especially when a government assistant uses external documents to answer citizens’ questions.
## Open Question
How can we evaluate whether a RAG-based government assistant consistently answers from current, approved service documents and safely handles malicious instructions embedded in retrieved content?
