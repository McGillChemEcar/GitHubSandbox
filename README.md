# McGill Chem-E Car GitHub Tutorial

Welcome to McGill Chem-E Car! This is the repository to provide a brief introduction to GitHub, and how to use this tool to manage our code development. 

## Introduction

There is an online book giving the background information of Git, and the advantages of using it. If you are interested in learning more deeply about Git, this book can be found by this [link](https://git-scm.com/book/en/v2).

GitHub will slowly take over the position of Google Drive to store Arduino codes for Chem-E Car. Although the website of GitHub has become fairly easy to use without having any coding experience, knowing some shortcut will improve the efficiency in playing around the code.

Table of Contents:
* [Getting Started](#getting-started)
    + [Prerequisites](#prerequisites)
    + [Git Installation](#git-installation)
    

## Getting Started

This section will provide the information in order to set up Git on your own IT equipment, including the environment requirements, and resources to be downloaded.

### Prerequisites

A computer that runs Windows, Mac OS, or Linux as the operating system with internet. You should also sign up for GitHub at https://github.com. It is reocmmended to use an official e-mail account, e.g. McGill e-mail as your account e-mail address. 

### Git Installation

Different operating systems will have different setup steps. Use the following links to install the git that's suitable for your device:

* [Windows](https://git-scm.com/download/win)
* [Mac OS](https://git-scm.com/download/mac)
* [Linux](https://git-scm.com/downloads)

## SSH and GitHub

Once git is installed on your machine, we will need to set up SSH on our personal computer. For windows users, start a Bash window as soon as the installation finishes. For Mac OS users, open a terminal and follow the steps to set up your SSH. For a more detailed description, please visit this [site](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent). 

* [Check existing SSH](#check-existing-ssh)
* [Generate New SSH](#generate-new-ssh)

### Check Existing SSH

In a Bash or Terminal, type the following command to search for existing SSH:
```
ls -al ~/.ssh
```

If you already have an SSH set up, there should be some files listed with file names like:
+ id_dsa.pub
+ id_ecdsa.pub
+ id_ed25519.pub
+ id_rsa.pub

If you do not see any of the files above, or receive an error that _/.~ssh_ does not exist, don't worry! We'll generate one in the next section. 

### Generate New SSH

In the bash or the terminal, type the command below to set up SSH to your own computer. 
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Then you should be prompted to "Enter a file in which to save the key", press Enter to accept the default location. Afterwards, type a passphrase at the prompt. Note that it is possible that the terminal does not show **anything** when you are typing a passphrase. If you think you made a mistake, hold Backspace for a while to delete it completely then enter the passphrase again. 

### Adding the SSH key to the ssh-agent
After generating the key, type the following command to add your SSH key to the agent", and you should see an output similar to what's after the ">" on the second line. 
```
eval $(ssh-agent -s)
> Agent pid 59566
```

### Adding New SSH Key to GitHub Account
We are almost there! Now we just need to add the new SSH key to our GitHub account. Type the following command to copy your new SSH key to the clipboard:
```
clip < ~/.ssh/id_rsa.pub
```

Now go to the GitHub webpage, and navigate yourself to the following page:

![Image of profile](https://help.github.com/assets/images/help/settings/userbar-account-settings.png)

In the user setting sidebar, click **SSH and GPG keys**.

![SSHandGPGKeys](https://help.github.com/assets/images/help/settings/settings-sidebar-ssh-keys.png)

Click New SSH Key or Add SSH key. 

![newSSH](https://help.github.com/assets/images/help/settings/ssh-add-ssh-key.png)

And you should see the following dialog box: 

![newSSHDialog](https://help.github.com/assets/images/help/settings/ssh-key-paste.png)

In the title field, put some descriptive title such as "Thomas's DELL XPS" and paste your new SSH key into the Key field, and click Add SSH key, then we're all set!

## First Use of Git
Now let's try to use git for the first time. There is a playground repository so we can explore the features of GitHub. In your terminal, in a desired directory, type the command:
```
git clone https://github.com/McGillChemEcar/GitHubSandbox
```

If you see that your terminal has downloaded something, then your git is fully set up and ready to go! 

Now open or create a text file and type some rediculous stuff inside. Save the file and type the commands:
```
git add .
git commit -m "some message here"
git push
```

Then you should see your modifications being pushed up to the cloud. 
