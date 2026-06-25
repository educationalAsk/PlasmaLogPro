Contributing to PlasmaLog Pro 🧬

Thank you for your interest in contributing to PlasmaLog Pro! By contributing, you are helping build an open-source, privacy-preserving, and self-sovereign financial and biometric ecosystem for plasma donors worldwide.

We welcome contributions from developers, designers, writers, and biometric data enthusiasts.

🗺️ Code Architecture & Core Philosophy

PlasmaLog Pro is engineered under a "Zero-Infrastructure" / serverless philosophy. To preserve the portability and immediate deployability of this tool:

The Single-File Mandate: The primary interface, core cryptographic blockchain, Chart.js visualizations, and local OCR parsing engine must remain bundled within a single, highly optimized index.html file.

CDN-Based Dependencies: We prioritize locked CDN imports over heavy node_modules configurations to allow immediate local execution via simple static servers.

Data Sovereignty First: No code should ever introduce automatic, unconsented transmission of raw medical records or financial balances to third-party endpoints.

⛓️ Cryptographic & Math Standards

Any pull requests modifying the block validation layer or parsing engine must respect the local Proof-of-Authority chain dynamics.

For any block $i$ within the ledger, its cryptographic hash $H_i$ must adhere strictly to:

$$H_i = \text{SHA-256}(i + H_{i-1} + T_i + \text{stringify}(D_i))$$

Where:

$i$ is the chronological block index.

$H_{i-1}$ is the signature of the preceding block (genesis hash is initialized if $i = 0$).

$T_i$ is the ISO-8601 UTC timestamp of creation.

$D_i$ represents the complete, structured biometric payload including the recently integrated day-of-visit bank balance and earnings data.

Your code must fail gracefully and notify the user using a custom UI toast wrapper if any validation check fails. Do not use browser alert() or confirm() modals.

🚀 Step-by-Step Contribution Workflow

1. Set Up Your Environment

Fork the repository to your own account and clone it locally:

git clone [https://github.com/your-username/plasmalog-pro.git](https://github.com/your-username/plasmalog-pro.git)
cd plasmalog-pro


Run a simple local server to avoid CORS bottlenecks when uploading local .json files:

# Python 3
python3 -m http.server 8000


Open your browser to http://localhost:8000.

2. Branch Guidelines

Create a branch specifically dedicated to your issue or feature. Use descriptive naming structures:

feature/web3-wallet-auth (for Milestone 1 target features)

fix/ocr-null-values (for bug fixes)

docs/update-grant-milestones (for documentation)

3. Coding & UI Guidelines

Responsive Layouts: Ensure any changes to the bento-grid layout scale beautifully on small screens (minimum mobile viewport of $360\text{px}$ width) as well as wide desktops.

Cubic Splines: When customizing chart plots in Chart.js, maintain the smooth cubic-spline tension configurations ($0.4 \le \text{tension} \le 0.45$) to emulate organic biological curves.

Code Style: Use semantic HTML5 elements, modular JavaScript, and consistent variable declarations. Fully comment all block-building and data-portability parsing scripts.

4. Verification Checklists

Before opening your Pull Request, verify that:

[ ] Direct manual data entry correctly appends an immutable block to the local ledger.

[ ] Entering Correction Mode (clicking an entry row) successfully overwrites the intended target date without breaking the SHA-256 block hash chain.

[ ] Local JSON loading parses both full state backups and sequential raw data arrays without throwing fatal runtime errors.

[ ] The browser console is free of layout warnings, uncaught exceptions, or failed cryptographic signatures.

5. Submit Your Pull Request

Commit your changes with clear, descriptive commit messages:

git commit -m "feat: integrate Web3 signed message verification logic"


Push your changes to your fork and submit a Pull Request to the main branch of our central repository.

Be ready to answer questions or implement feedback from reviewers during the community-led vetting stage.

💬 Community & Help

If you run into issues or have questions regarding our implementation plan for Ocean Protocol's Compute-to-Data engine, feel free to coordinate with us directly:

Post in the active Ocean Protocol Discord workspace (#shipyard / #grants).

Open a GitHub Issue for structured feature discussion.

Thank you for contributing to decentralized biological sovereignty! 🚀
