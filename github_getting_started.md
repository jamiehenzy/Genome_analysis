## Setting up your bioinformatics portfolio on Github

This guide will walk you through creating a GitHub account, setting up your portfolio repository, and connecting the university cluster to your GitHub account so you can push your work there directly from the command line.

Don't worry if none of these terms are familiar yet. Each term will be explained as we go.

## What Is GitHub, and Why Are We Using It?

GitHub is a website that stores code and documents in an organized, version-controlled way. Think of it as Google Drive, but specifically designed for code and documentation, with the added feature that it keeps a complete history of every change you make.

By the end of this course, your GitHub repository will be a **portfolio** — a professional record of the bioinformatics skills you have developed. This is something you can share with future employers or graduate programs to demonstrate real, hands-on experience.

## Part 1: Create a GitHub Account

1. Go to [https://github.com](https://github.com)
2. Click **Sign up**
3. Enter your email address, create a password, and choose a username

> **Choosing a username:** Pick something professional — ideally your name or a close variation of it. This username will appear on your portfolio and may be seen by future employers. Avoid usernames with random numbers or nicknames.

4. Follow the prompts to verify your email address and complete setup
5. When asked about your plan, choose the **Free** option — it includes everything you need

---

## Part 2: Create Your Portfolio Repository and Add the .gitignore File

A **repository** (often called a "repo") is a folder on GitHub that stores all the files for a project. You will create one repository that will serve as your course portfolio.

1. Once logged in, click the **+** icon in the top right corner of the page
2. Select **New repository**
3. Fill in the following:
   - **Repository name:** `bioinformatics-portfolio` (use hyphens, not spaces)
   - **Description:** `Bioinformatics coursework portfolio — [Your Name]`
   - **Visibility:** Set to **Public** (this allows others, including future employers, to see your work)
   - Check the box that says **Add a README file**
4. Click **Create repository**

You should now see your new repository with a single file called `README.md`. This file is the front page of your portfolio, which we will edit later.

### Add the .gitignore File

A `.gitignore` file tells Git which files it should never push to GitHub. In our case, these include large data files like raw sequencing reads and genome assemblies that have no place in a code repository. Your instructor has provided this file for you.

Add it to your repository now, before you do anything else:

1. Go to your instructor's GitHub page and open the `.gitignore` file they have provided. Copy its entire contents.
2. In your own repository, click **Add file → Create new file**
3. Name the file `.gitignore` . Note: the dot at the beginning is essential, so don't leave it out!
4. Paste the contents you copied into the editor.
5. Click **Commit new file**

Your repository should now contain two files: `README.md` and `.gitignore`.

> **Note:** Files beginning with a dot are hidden on Linux systems. When you later clone your repository onto the cluster and type `ls`, you won't see `.gitignore` in the listing but rest assured, it is there. To see hidden files, use `ls -a` instead.

---

## Part 3: Connect the Cluster to Your GitHub Account

To push files from the university cluster to GitHub, you need to set up an **SSH key**. This is a secure way for the cluster to prove its identity to GitHub without needing a password every time.

Think of it like a lock and key: you will generate a matched pair of keys on the cluster, give GitHub the "lock" (the public key), and the cluster keeps the "key" (the private key). When you push files, GitHub checks that they match.

### Step 1: Log into the cluster

Log into the university cluster as you normally would.

### Step 2: Generate an SSH key pair

At the command prompt, type the following command and press Enter:

```bash
ssh-keygen -t ed25519 -C "your_github_email@example.com"
```

Replace `your_github_email@example.com` with the email address you used to sign up for GitHub.

You will see several prompts:
- **"Enter a file in which to save the key"** — just press Enter to accept the default location
- **"Enter passphrase"** — you can press Enter twice to skip setting a passphrase (fine for a course setting)

You should see a message confirming the key was created, along with a small piece of ASCII art. That means it worked.

### Step 3: Display your public key

Now you need to copy your public key to give to GitHub. Type:

```bash
cat ~/.ssh/id_ed25519.pub
```

This will print a long string of characters starting with `ssh-ed25519`. **Select and copy the entire line**, from `ssh-ed25519` all the way to the end (including your email address).

### Step 4: Add the public key to GitHub

1. Go to [https://github.com](https://github.com) and log in
2. Click your profile picture in the top right corner, then click **Settings**
3. In the left sidebar, click **SSH and GPG keys**
4. Click the green **New SSH key** button
5. In the **Title** field, type something descriptive like `University Cluster`
6. In the **Key** field, paste the public key you copied in the previous step
7. Click **Add SSH key**

### Step 5: Test the connection

Back on the cluster, type:

```bash
ssh -T git@github.com
```

You may see a message asking if you want to continue connecting. Type `yes` and press Enter. If everything worked, you should see a message like:

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

If you see your GitHub username in that message, you are successfully connected.

---

## Part 4: Clone Your Repository onto the Cluster

**Cloning** means downloading a copy of your GitHub repository onto the cluster so you can add files to it and push them back up.

### Step 1: Get the SSH address of your repository

1. Go to your portfolio repository on GitHub
2. Click the green **Code** button
3. Make sure **SSH** is selected (not HTTPS)
4. Copy the address — it will look like: `git@github.com:yourusername/bioinformatics-portfolio.git`

### Step 2: Clone the repository on the cluster

On the cluster, navigate to your home directory or wherever you keep your course files:

```bash
cd ~
```

Then clone the repository:

```bash
git clone git@github.com:yourusername/bioinformatics-portfolio.git
```

Replace `yourusername` with your actual GitHub username.

You should now see a new directory called `bioinformatics-portfolio`. Navigate into it:

```bash
cd bioinformatics-portfolio
```

If you type `ls`, you should see the `README.md` file that GitHub created automatically.

---

## Part 5: Configure Git on the Cluster

Before you can push files, you need to tell Git who you are. You only need to do this once. Type the following two commands, replacing the information in quotes with your own:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_github_email@example.com"
```

---

## Part 6: Your First Push — Editing the README

Let's practice the full workflow by editing your README file and pushing it to GitHub.

### The basic Git workflow

Every time you want to save your work to GitHub, you will follow three steps:

| Step | Command | What it does |
|------|---------|--------------|
| 1. Stage | `git add` | Tells Git which files you want to save |
| 2. Commit | `git commit` | Saves a snapshot of those files with a description |
| 3. Push | `git push` | Sends the snapshot to GitHub |

### Edit the README

Open the README file with a text editor. The simplest editor available on most clusters is `nano`:

```bash
nano README.md
```

You will see the contents of the file. Replace or add to it so it looks something like this:

```
# Bioinformatics Portfolio

**Name:** Your Name  
**Course:** BIOL XXXX — Introduction to Bioinformatics  
**Semester:** Spring 2026  

## About This Portfolio

This repository documents the bioinformatics skills I developed during my 
introductory bioinformatics course, including:

- Unix command line navigation and cluster computing
- Quality control and trimming of sequencing data
- Read alignment and mapping
- Differential gene expression analysis
- Phylogenetic analysis

## Repository Organization

Each folder corresponds to a unit of the course and contains scripts, 
summary results, and documentation of the methods used.
```

When you are done editing, press **Ctrl+X** to exit nano, then **Y** to confirm saving, then **Enter** to keep the filename.

### Stage, commit, and push

Now run the three steps:

```bash
git add README.md
git commit -m "Add initial portfolio README"
git push
```

After the push completes, go to your repository on GitHub and refresh the page. You should see your updated README displayed on the front page of your repository.

**Congratulations — you just pushed your first file to GitHub.**

---

## Part 7: The Ongoing Workflow

From this point forward, whenever you complete work you want to add to your portfolio, the process is always the same three steps. For example, after completing the QC unit:

```bash
# Navigate to your portfolio directory
cd ~/bioinformatics-portfolio

# Copy or move your script into the right folder
cp ~/qc_unit/run_fastqc.sh 02_qc_trimming/

# Stage all new or changed files
git add .

# Commit with a descriptive message
git commit -m "Add FastQC script and QC summary for unit 2"

# Push to GitHub
git push
```

> **A note on commit messages:** Write your commit messages as short, specific descriptions of what you did — not just "update" or "changes." Good commit messages make your work history readable and look professional. Think of them as a lab notebook entry.

---

## Important Rules: What NOT to Push to GitHub

GitHub has a file size limit (100 MB per file) and is not designed for large data files. **Never push the following file types to GitHub:**

- Raw sequencing reads (`.fastq`, `.fastq.gz`)
- Genome assemblies (`.fasta`, `.fa`)
- Alignment files (`.bam`, `.sam`)
- Large index files

Your repository includes a `.gitignore` file (provided by your instructor) that automatically prevents these file types from being accidentally pushed. If you are ever unsure whether a file is appropriate to push, ask before trying.

What **should** go on GitHub:
- Shell scripts (`.sh`)
- R scripts (`.R`) and R Markdown files (`.Rmd`)
- Small results tables (`.csv`, `.txt`) with summary statistics
- Figures and plots (`.png`, `.pdf`)
- README and documentation files (`.md`)

---

## Quick Reference Card

| Task | Command |
|------|---------|
| Navigate into your portfolio directory | `cd ~/bioinformatics-portfolio` |
| Check the status of your files | `git status` |
| Stage a specific file | `git add filename` |
| Stage all changed files | `git add .` |
| Commit staged files | `git commit -m "your message here"` |
| Push to GitHub | `git push` |
| Pull updates from GitHub | `git pull` |
| See your commit history | `git log --oneline` |

---

## Getting Help

If something goes wrong, here are the most common issues and fixes:

**"Permission denied (publickey)"** — Your SSH key is not set up correctly. Go back to Part 3 and repeat the steps carefully, making sure you copied the full public key.

**"fatal: not a git repository"** — You are not inside your cloned portfolio directory. Use `cd ~/bioinformatics-portfolio` to navigate there first.

**"error: failed to push some refs"** — Someone (or you, from another location) made changes to GitHub that you don't have locally yet. Run `git pull` first, then try `git push` again.

If you encounter an error not listed here, copy the exact error message and bring it to office hours or post it on the course discussion board.
