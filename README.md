# Ovation Green

This documentation aims to provide step-by-step guidance on setting up the Ovation Green SCADA source repository ([scada-pc](https://github.com/ovationgreen/scada-pc)) on your local machine.

## Purpose

The purpose of this document is to provide guidance for setting up a new local repository and migrating from an old self-hosted repository to GitHub. Please note that the configuration of additional tools, such as IDEs, compilers, continuous integration systems, and others, is beyond the scope of this documentation. However, if needed, information on configuring these tools may be added at a later stage.

## Preconditions

* To proceed, please ensure that you are logged into GitHub using an Emerson email address. If you are using a different GitHub account or do not have one yet, kindly create an account using your Emerson email address. Once done, please reach out to the repository owner at [Orest.Pankevych@Emmerson.com](mailto:Orest.Pankevych@Emmerson.com) to obtain the necessary permissions.

## Software

Please ensure that the additional software listed below is installed before proceeding with the next steps. After installation, it is necessary to restart all terminals (such as cmd, git-bash, Windows Terminal, etc.) and file managers (such as Total Commander, Far manager, etc.).

* [Git](https://git-scm.com/downloads)
* [GitHub CLI](https://cli.github.com)
* [GitHub Desktop](https://desktop.github.com)

## Folder structure

It is recommended to maintain the legacy folder hierarchy when setting up a new repository to ensure compatibility with previously configured environments. Please clone the new repository inside the `F:\CVSSandbox\Project\P00518` folder.

## Authentification

To perform an interactive setup and enable Git to work with the GitHub repository, please run the following command:

```
gh auth login
```

While executing the command, you will be prompted with a series of questions. Please provide your answers to the questions as indicated below:
1. What account do you want to log into? `Github.com`
2. What is your preferred protocol for Git operations? `HTTPS`
3. Authenticate Git with your GitHub credentials? `Yes`
4. How would you like to authenticate GitHub CLI? `Login with a web browser`.

Press `Enter` to continue, and in the web browser that opens, authorize your Git client by following the instructions. You can now proceed with cloning the GitHub repository.

## Cloning

When setting up the repository for the first time, run the following command in the terminal

```
gh repo clone ovationgreen/scada-pc
```
