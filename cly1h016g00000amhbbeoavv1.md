---
title: "Steps to Use SSH for Secure GitHub Connections on Ubuntu Terminal"
datePublished: Sun Jun 30 2024 11:31:06 GMT+0000 (Coordinated Universal Time)
cuid: cly1h016g00000amhbbeoavv1
slug: steps-to-use-ssh-for-secure-github-connections-on-ubuntu-terminal
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719746544795/fd416b26-3aae-4b0c-9885-5dd156d49cc1.png
tags: ubuntu, github, git, ssh

---

GitHub, a leading platform for version control and collaboration on software projects, offers secure access to repositories through SSH (Secure Shell) connections. This guide will walk you through setting up and using SSH to securely connect your Ubuntu system to GitHub, ensuring safe and efficient management of your repositories.

## Step 1: Check for Existing SSH Keys

Before generating new SSH keys, it's important to check if you already have SSH keys set up on your Ubuntu system:

```bash
ls -al ~/.ssh
```

Look for files named `id_rsa` (private key) and `id_`[`rsa.pub`](http://rsa.pub) (public key). If these files exist, you can skip to Step 3. Otherwise, proceed to Step 2 to generate new SSH keys.

## Step 2: Generate New SSH Keys

If you don't have SSH keys, generate them using the `ssh-keygen` command. Open a terminal and enter:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Replace `"`[`your_email@example.com`](mailto:your_email@example.com)`"` with the email address associated with your GitHub account. You can also leave it blank.

Follow the prompts to save the keys in the default location (`~/.ssh/id_rsa`), or specify a different location if needed.

## Step 3: Add Your SSH Key to the SSH Agent

To ensure your SSH key is used for authentication, add it to the SSH agent:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

## Step 4: Add Your SSH Key to Your GitHub Account

Next, you need to add your SSH public key to your GitHub account:

1. Copy your SSH public key to the clipboard:
    
    ```bash
    sudo apt install xclip  # Install xclip if you don't have it
    xclip -sel clip < ~/.ssh/id_rsa.pub
    ```
    
2. Go to [GitHub.com](http://GitHub.com) and navigate to **Settings &gt; SSH and GPG keys &gt; New SSH key**.
    
3. Paste your SSH key into the "Key" field and give it a descriptive title.
    
4. Click **Add SSH key**.
    

See;

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719746943121/bbd55d70-a12c-43bd-9af8-652a87d018e3.png align="center")

## Step 5: Test Your SSH Connection

To verify that your SSH connection to GitHub is working correctly, run the following command in your terminal:

```bash
ssh -T git@github.com
```

You may see a message asking you to confirm the authenticity of the host. Type `yes` to continue. If everything is set up correctly, you should see a message confirming that you've successfully authenticated.

## Step 6: Using SSH with GitHub

Now that your SSH connection is established, you can use it to interact with GitHub repositories securely. For example, when cloning a repository, use the SSH URL:

```bash
git clone git@github.com:username/repository.git
```

Replace `username` with your GitHub username and `repository` with the name of the repository you want to clone.

## Conclusion

Setting up SSH for GitHub on your Ubuntu system enhances security and simplifies authentication when interacting with repositories. By following these steps, you've configured a secure and efficient way to manage your GitHub projects using SSH. Enjoy seamless collaboration and version control with confidence in your connection's security.