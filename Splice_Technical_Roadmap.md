# Splice Developer Ecosystem Roadmap

This document outlines a comparison of Splice’s developer ecosystem with other blockchain platforms, identifies key pain points for onboarding developers, and proposes a first-draft technical roadmap to enhance Splice’s appeal to developers from ecosystems like Ethereum, Solana, and Aptos. The goal is to create a robust environment that simplifies onboarding and enables meaningful contributions to Splice, a set of reference applications for the Canton Network built using Daml.

## 1. Comparison with Other Blockchain Ecosystems

The following table compares Splice and the Canton Network’s developer ecosystem with those of Ethereum, Solana, and Aptos, focusing on documentation, SDKs, libraries, tools, community support, and additional resources.

| **Feature** | **Ethereum** | **Solana** | **Aptos** | **Splice/Canton** |
| --- | --- | --- | --- | --- |
| **Documentation** | Comprehensive, community-driven guides and tutorials covering all skill levels (Ethereum Developer Resources). | Detailed guides with API references and beginner-friendly tutorials (Solana Developer Resources). | Extensive, well-structured documentation for Move programming and dApp development (Aptos Developer Documentation). | Limited, deployment-focused with troubleshooting guides but lacks beginner-friendly tutorials (Splice Documentation). |
| **SDKs/Libraries** | Web3.js, Ethers.js for node interaction; OpenZeppelin for secure smart contract templates; Chainlink for oracles. | Solana CLI, web3.js, Anchor framework for Rust programs; Solana Program Library (SPL) for reusable components. | Official SDKs for Python, Go, TypeScript; Move standard library for reusable modules. | Daml SDK for smart contract development; `@daml/react` for front-end; limited community libraries like DAZL (Python). |
| **Tools** | Truffle, Hardhat, Foundry for development; Remix (web IDE); Metamask for wallets; Alchemy for node infrastructure. | Solana CLI, Anchor for testing; Solana Explorer; browser-based IDEs; Phantom wallet integration. | Aptos CLI for setup; language servers for IDEs; indexer APIs; browser-based tools. | Daml Studio (VS Code-based IDE); Canton Network Quickstart with Docker; DABL for deployment; no comprehensive CLI. |
| **Community Support** | Active forums, Discord, Stack Exchange; Ethereum Foundation grants and hackathons. | Solana Stack Exchange, Discord, forums; regular hackathons and grants from Solana Foundation. | Active Discord, forums; grants from Aptos Foundation. | Limited to Hyperledger Labs and Daml Developers Community Forum; no dedicated Splice channels (Daml Developers Community). |
| **Templates/Resources** | OpenZeppelin Starter Kits, Uniswap SDK, 0x protocol for reusable components. | SPL, token extensions, pre-built infrastructure components. | Move templates, AptosKit for iOS, Unity SDKs. | Amulet reference application; limited Daml templates for financial workflows. |

**Key Observations**:

- **Ethereum** leads with a mature ecosystem, offering extensive tools, libraries, and community support, including Metamask for seamless wallet integration.
- **Solana** emphasizes performance with tools like Anchor and Phantom wallet, appealing to developers seeking scalability.
- **Aptos** leverages Move and Petra wallet, focusing on developer experience and interoperability.
- **Splice/Canton** lags in beginner-friendly documentation, language diversity, and wallet solutions, with a steep learning curve due to Daml’s niche usage.

## 2. Splice’s Pain Points

Splice’s current developer ecosystem presents several challenges for attracting developers from other blockchain platforms:

1. **Limited Documentation**: The Splice Documentation focuses on deployment and operations, lacking beginner-friendly tutorials or guides that compare Daml and Canton workflows to familiar platforms like Ethereum or Solana.
2. **Niche Language (Daml)**: Daml is less widely known compared to Solidity, Rust, or Move, creating a barrier for developers unfamiliar with its syntax.
3. **Sparse Tooling**: While the Daml SDK and Canton Network Quickstart provide a foundation, there’s no equivalent to frameworks like Truffle or Anchor, nor a user-friendly CLI or web-based IDE.
4. **Limited Community Support**: The absence of a dedicated Splice community channel and limited activity on the Daml Developers Community Forum hinder peer support.
5. **Few Reusable Resources**: Beyond the Amulet reference application, Splice lacks extensive smart contract templates or starter kits.
6. **No Native Wallet Solution**: Unlike Metamask, Petra, or Phantom, Splice lacks a browser-based wallet for easy asset management and transaction signing, complicating user and developer interaction with the Canton Network.
7. **Complex Setup**: The Canton Network Quickstart requires tools like Docker, direnv, and nix, which may be unfamiliar to developers accustomed to simpler setups.

## 3. First-Draft Plan for Splice Technical Roadmap

To address these pain points and attract developers from Ethereum, Solana, and Aptos, the following technical roadmap is proposed to enhance Splice’s developer ecosystem, including the development of a native Canton wallet as a browser extension.

### 3.1 Enhance Documentation

- **Objective**: Create accessible, comparative guides to reduce the learning curve.
- **Actions**:
  - Develop tutorials comparing Daml workflows to Solidity, Rust, and Move, covering tasks like token creation, wallet integration, and governance.
  - Create a “Splice Developer Portal” with beginner-friendly guides, API references, and troubleshooting tips.
  - Enable community contributions to documentation via GitHub.
- **Expected Outcome**: Developers from other platforms can quickly grasp Splice concepts.

### 3.2 Develop SDKs for Popular Languages

- **Objective**: Enable interaction with Canton without requiring Daml expertise.
- **Actions**:
  - Build SDKs/client libraries for JavaScript/TypeScripts, Python, and Rust, providing APIs for querying Canton Coin balances and submitting transactions.
  - Ensure SDKs/libraries are interoperable with existing libraries (e.g., Web3.js).
  - Example: A JavaScript/TypeScript SDK for integrating Splice wallets into dApps.
- **Expected Outcome**: Broadened appeal through familiar languages.

### 3.3 Build Development Frameworks and Tools

- **Objective**: Simplify Daml app/smart contract development, testing, and deployment.
- **Actions**:
  - Develop a Daml framework (“SpliceForge”) inspired by Hardhat, Foundry or Anchor for project scaffolding and testing.
  - Create a Splice CLI with commands like `splice init` or `splice deploy`.
  - Build a web-based IDE for Daml, integrated with Canton’s TestNet (Canton Network TestNet).
- **Expected Outcome**: Familiar, efficient workflows for developers.

### 3.4 Strengthen Community Engagement

- **Objective**: Foster a vibrant community for support and contributions.
- **Actions**:
  - Launch a Splice-specific Discord or Slack channel.
  - Organize quarterly hackathons, workshops, and AMAs.
  - Offer grants through Hyperledger Labs for contributions like templates or SDKs.
- **Expected Outcome**: Increased developer participation and peer support.

### 3.5 Expand Reference Applications and Templates

- **Objective**: Provide reusable components to accelerate development.
- **Actions**:
  - Develop additional reference applications for governance, lending, and asset tokenization, building on Amulet.
  - Create a library of Daml templates for financial workflows (e.g., tokenization, escrow), hosted on the Splice GitHub Repository.
  - Build a React-based UI component library with `@daml/react` for wallet interfaces and dashboards.
  - **Develop a Native Canton Wallet Browser Extension**:
    - Create a browser extension (e.g., “Canton Wallet”) similar to Metamask, Petra, or Phantom, enabling users and developers to manage assets, sign transactions, and interact with Splice applications on the Canton Network.
    - Features: Account creation, transaction signing, integration with Daml contracts, and support for Canton Coin and other assets.
    - Provide an SDK for developers to integrate the wallet into dApps, with documentation and examples for common use cases (e.g., transferring assets via `Splice.Wallet.TransferOffer`).
    - Ensure compatibility with major browsers (Chrome, Firefox, Edge) and include a user-friendly interface for non-technical users.
- **Expected Outcome**: Faster development with reusable components and a familiar wallet interface for seamless interaction.

### 3.6 Integrate with Existing Development Tools

- **Objective**: Enhance compatibility with standard workflows.
- **Actions**:
  - Visual Studio Code/Cursor: Develop plugins (or enhance the existing [Daml Studio and DAML plugin](https://docs.daml.com/daml/daml-studio.html)) for Daml syntax highlighting and debugging.
  - Support CI/CD pipelines with GitHub Actions or Jenkins.
  - Provide templates for Git workflows.
- **Expected Outcome**: Improved productivity with familiar tools.

### 3.7 Create Educational Resources

- **Objective**: Provide structured learning paths for Daml and Canton.
- **Actions**:
  - Partner with Coursera or Udemy for Daml and Canton courses.
  - Develop interactive tutorials bridging Ethereum, Solana, and Aptos concepts to Canton.
  - Offer certification programs to recognize skilled developers.
- **Expected Outcome**: Increased developer skills and contributions.

### Implementation Timeline

| **Phase** | **Actions** | **Duration** |
| --- | --- | --- |
| **Phase 1: Foundation** | Enhance documentation, launch Splice Developer Portal, create tutorials | 3 months |
| **Phase 2: Tools** | Develop JavaScript SDK, Splice CLI, web-based IDE prototype, start Canton Wallet extension | 6 months |
| **Phase 3: Frameworks** | Build SpliceForge, expand Daml templates, create UI and wallet libraries | 9 months |
| **Phase 4: Community** | Launch Discord channel, host hackathon, offer grants | 12 months |
| **Phase 5: Education** | Partner for online courses, develop certifications, expand tutorials | 18 months |

### Expected Impact

- **Short-Term**: Improved documentation, SDKs, and wallet extension reduce onboarding time.
- **Medium-Term**: Frameworks, tools, and wallet integration streamline development.
- **Long-Term**: Vibrant community and educational resources establish Splice as a competitive ecosystem.

## Conclusion

By addressing Splice’s pain points, including the lack of a native wallet, and implementing this roadmap, Splice can attract developers from Ethereum, Solana, and Aptos. The addition of a Canton Wallet browser extension will provide a familiar interface, enhancing user and developer experience. This strategic path will foster growth in the Canton Network ecosystem as of June 19, 2025.

## Key Citations

- [Ethereum Developer Resources](https://ethereum.org/en/developers/)
- [Solana Developer Resources](https://solana.com/developers)
- [Aptos Developer Documentation](https://aptos.dev/en)
- [Splice Documentation](https://docs.sync.global/)
- [Daml SDK Documentation](https://docs.daml.com/)
- [Canton Network Quickstart](https://github.com/digital-asset/cn-quickstart/)
- [Splice GitHub Repository](https://github.com/hyperledger-labs/splice)
- [Daml Developers Community](https://www.digitalasset.com/developers)
- [Canton Network TestNet](https://blog.digitalasset.com/blog/canton-network-gains-momentum-testnet-now-live)
- [Write: Daml Studio](https://docs.daml.com/daml/daml-studio.html)