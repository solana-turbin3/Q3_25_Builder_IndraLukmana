# Turbin3 Q3 Solana Builder Proof of Learn

Welcome to my proof-of-learning repository for the Turbin3 Solana Builders
cohort!

This repository serves as a collection of my work and progress throughout the
program. It's designed to showcase the concepts learned and projects built
during the program.

## Structure

This repository utilizes git submodules to organize the code and projects from
each week of the bootcamp. Each submodule points to a specific repository
containing the code for that week's module. If you are unfamiliar with git
submodules head into [Working with Git Submodules](#working-with-git-submodules)
section on the bottom for a quick guide on how to clone and update the
submodules.

## Capstone Project: Gamified SRS for Solana Developers - Proof of Discipline

The final project of the Turbin3 Q3 program, this is a Gamified Spaced
Repetition System (SRS) tailored for Solana developers. It features a unique
"Proof of Discipline" mechanism built on the Solana blockchain with Anchor.
Users commit SOL to a vault, perform daily on-chain check-ins to maintain a
learning streak, and upon completion, can withdraw their deposit and mint a
verifiable NFT credential.

**Link to the project: [Gamified SRS for Solana Developers](./capstone)**

### Highlights

- **Dual-Program Design:** A modular architecture featuring two distinct Anchor
  programs:
  - `srs-vault`: Manages the core "Proof of Discipline" logic, including SOL
    deposits, daily check-ins, and streak tracking.
  - `nft-minter`: A permissionless program that mints a verifiable NFT
    credential upon successful commitment completion, using the Metaplex Core
    standard.
- **Secure Cross-Program Invocation (CPI):** The `srs-vault` program securely
  invokes the `nft-minter` program to create a `MintPermit` PDA, ensuring that
  NFTs can only be minted after a user has fulfilled their on-chain commitment.
- **Comprehensive Test Suite:** Includes rigorous unit and integration tests
  built with `vitest`, `@solana/kit`, and `solana-kite`, integrated through
  `codama` covering the full end-to-end user lifecycle from vault initialization
  to NFT minting.
- **Detailed Documentation:** The project is supported by extensive
  documentation.
  - **[Project Brief](./capstone/docs/brief.md):** Outlines the project's
    vision, goals, and scope.
  - **[Product Requirements Document (PRD)](./capstone/docs/prd.md):** Defines
    the functional and non-functional requirements.
  - **[Architecture Document](./capstone/docs/architecture.md):** Provides a
    detailed technical blueprint of the system.

## Weekly Modules

The repository is also split into the following weekly modules:

- [`week0-typescript`](./week0-typescript): Prerequisite works for interacting
  with the Solana blockchain using TypeScript.
- [`week0-rust`](./week0-rust): Prerequisite works for building Solana programs
  using Rust.
- [`week1-spl`](./week1-spl): Working with the Solana Program Library (SPL),
  focusing on token programs.
- [`week1-nft`](./week1-nft): Exploring Non-Fungible Tokens (NFTs) on Solana.
- [`week2-vault`](./week2-vault): Building a secure vault program using the
  Anchor framework.
- [`week2-escrow`](./week2-escrow): Escrow program using Anchor framework.
- [`week2-amm`](./week2-amm): AMM (Automated Market Maker) program using Anchor
  framework.
- [`week3-marketplace`](./week3-marketplace): Marketplace program using Anchor
  framework.
- [`week3-staking`](./week3-staking): Staking program using Anchor framework.

Feel free to explore the individual module directories to see the code and
projects for each week!

---

## Working with Git Submodules

<details>
<summary>Git Submodules Guide</summary>

This repository uses git submodules to manage the code for each week of the
bootcamp. If you're new to git submodules, here's a quick guide on how to work
with them:

### Cloning the Repository (First Time)

When you clone this repository for the first time, the submodules are not
automatically initialized or updated. You need to do this separately:

1. **Clone the main repository:**

   ```bash
   git clone git@github.com:solana-turbin3/Q3_25_Builder_IndraLukmana.git
   ```

2. **Initialize and update submodules:** Navigate into the cloned directory:

   ```bash
   cd <repository_directory>
   ```

   Then, run the following command to initialize and update all submodules:

   ```bash
   git submodule update --init --recursive
   ```

   - `--init`: Initializes the submodule, registering the submodule's path and
     URL in the main repository's `.git/config`.
   - `--recursive`: Updates nested submodules as well, ensuring you get the
     correct versions of all dependencies.

### Updating the Local Repository and Submodules

To pull the latest changes from the main repository and update all submodules to
the versions specified by the main repository:

1. **Pull changes in the main repository:**

   ```bash
   git pull origin main
   ```

2. **Update submodules:** After pulling the main repository changes, update the
   submodules to match the commit specified in the main repository:

   ```bash
   git submodule update --recursive
   ```

   This command fetches the latest commits for each submodule and updates them
   to the commit recorded in the main repository.

### Handling Submodule Updates

If you make changes _within_ a submodule (e.g., inside one of the weekly code
directories) and push those changes to the submodule's remote repository, you
need to update the main repository to point to the new commit of that submodule:

1. **Navigate into the submodule directory:**

   ```bash
   cd path/to/submodule
   ```

2. **Make your changes, commit, and push in the submodule:**

   ```bash
   # Make changes...
   git add .
   git commit -m "Your commit message"
   git push origin main # Or the appropriate branch
   ```

3. **Navigate back to the main repository's root directory:**

   ```bash
   cd ../../ # Adjust path based on your location
   ```

4. **Commit the submodule update in the main repository:** The main repository
   now sees that the submodule's working directory is at a different commit than
   what is recorded. You need to commit this change in the main repository:

   ```bash
   git add path/to/submodule
   git commit -m "Update submodule path/to/submodule to latest commit"
   ```

5. **Push the main repository changes:**

   ```bash
   git push origin main # Or the appropriate branch
   ```

   This pushes the change in the main repository that updates the reference to
   the submodule's commit.

</details>
