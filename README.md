# Turbin3 Q3 Solana Builder Proof of Learn

Welcome to my proof-of-learning repository for the Turbin3 Solana Builders cohort!

This repository serves as a collection of my work and progress throughout the program. It's designed to showcase the concepts learned and projects built during the program.

## Structure

This repository utilizes git submodules to organize the code and projects from each week of the bootcamp. Each submodule points to a specific repository containing the code for that week's module. If you are unfamiliar with git submodules head into [Working with Git Submodules](#working-with-git-submodules) section on the bottom for a quick guide on how to clone and update the submodules.

## Modules

The repository is split into the following modules:

* [`week0-typescript`](./week0-typescript): Prerequisite works for interacting with the Solana blockchain using TypeScript.
* [`week0-rust`](./week0-rust): Prerequisite works for building Solana programs using Rust.
* [`week1-spl`](./week1-spl): Working with the Solana Program Library (SPL), focusing on token programs.
* [`week1-nft`](./week1-nft): Exploring Non-Fungible Tokens (NFTs) on Solana.
* [`week2-vault`](./week2-vault): Building a secure vault program using the Anchor framework.

Feel free to explore the individual module directories to see the code and projects for each week!

---

## Working with Git Submodules

<details>
<summary>Git Submodules Guide</summary>

This repository uses git submodules to manage the code for each week of the bootcamp. If you're new to git submodules, here's a quick guide on how to work with them:

### Cloning the Repository (First Time)

When you clone this repository for the first time, the submodules are not automatically initialized or updated. You need to do this separately:

1. **Clone the main repository:**

    ```bash
    git clone git@github.com:solana-turbin3/Q3_25_Builder_IndraLukmana.git
    ```

2. **Initialize and update submodules:**
    Navigate into the cloned directory:

    ```bash
    cd <repository_directory>
    ```

    Then, run the following command to initialize and update all submodules:

    ```bash
    git submodule update --init --recursive
    ```

    * `--init`: Initializes the submodule, registering the submodule's path and URL in the main repository's `.git/config`.
    * `--recursive`: Updates nested submodules as well, ensuring you get the correct versions of all dependencies.

### Updating the Local Repository and Submodules

To pull the latest changes from the main repository and update all submodules to the versions specified by the main repository:

1. **Pull changes in the main repository:**

    ```bash
    git pull origin main
    ```

2. **Update submodules:**
    After pulling the main repository changes, update the submodules to match the commit specified in the main repository:

    ```bash
    git submodule update --recursive
    ```

    This command fetches the latest commits for each submodule and updates them to the commit recorded in the main repository.

### Handling Submodule Updates

If you make changes *within* a submodule (e.g., inside one of the weekly code directories) and push those changes to the submodule's remote repository, you need to update the main repository to point to the new commit of that submodule:

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

4. **Commit the submodule update in the main repository:**
    The main repository now sees that the submodule's working directory is at a different commit than what is recorded. You need to commit this change in the main repository:

    ```bash
    git add path/to/submodule
    git commit -m "Update submodule path/to/submodule to latest commit"
    ```

5. **Push the main repository changes:**

    ```bash
    git push origin main # Or the appropriate branch
    ```

    This pushes the change in the main repository that updates the reference to the submodule's commit.

</details>
