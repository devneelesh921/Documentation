# Branch access policies

## Author

|Author | Created on | Version    | Last updated by     | Comment         |
|-------|------------|------------|---------------------|-----------------|
|Akshit kapil | 11-06-2024      | 1          |Akshit kapil | Initial Commit  |
***
## Table of Contents

- [Introduction](#introduction)
- [Branch Protection Rules](#branch-protection-rules)
  - [Few reasons why Branch Protection Rules are Important](#few-reasons-why-branch-protection-rules-are-important)
  - [Protection rules available](#protection-rules-available)
- [Creating Branch Protection Rules](#creating-branch-protection-rules)
- [Access permissions](#access-permissions)
  - [Types of Github Account](#types-of-github-account)
- [Roles in an organisation](#roles-in-an-organisation)
  - [Roles available for an organization repository](#roles-available-for-an-organization-repository)
- [Creating a repository role](#creating-a-repository-role)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Reference Links](#reference-links)

***
## Introduction

Branch access policies in Git, used on platforms like GitHub, GitLab, or Bitbucket, are rules that control how and when changes can be made to branches in a repository. These policies help ensure that important branches, like the main or production branches, are protected from unauthorized changes. They can require code reviews, enforce certain checks, and prevent direct edits to sensitive branches, promoting better code quality and team collaboration.
***

## Branch Protection Rules
Git branch protection rules are a powerful configuration option that enables repository administrators to enforce security policies. 
This helps protect the git branches from unexpected code commits or deletion by any unauthorized person(s) / user group(s).

### Few reasons why Branch Protection Rules are Important

| Reasons  | 
|----------|
| TO avoid unnecessary code commits to the branch |
| TO enforce code reviews before merging the code to the branch |
| TO maintain a healthy codebase without affecting collaboration |
| TO maintain a commit history [by disallowing force pushes (git push origin <your_branch_name> --force)]  |

### Protection rules available
| Rules  | Description |
|----------|----------|
| **Require a pull request before merging** | When enabled, all commits must be made to a non-protected branch and submitted via a pull request before they can be merged into a branch that matches this rule. |
| **Require branches to be up to date before merging** | Each commit will have a status defined for it. Namely, error, failure, pending, success. Enable this option, if you want the status checks to be in success state before merging the commits into the protected branches.  |
| **Require conversation resolution before merging** | When enabled, all conversations on code must be resolved before a pull request can be merged into a branch that matches this rule. |
| **Require signed commits** |  Enable this option, if you want verified signatures on the commits pushed to this branch. |
| **Require linear history** | Prevent merge commits from being pushed to matching branches. Prevents collaborators from pushing merge commits to the branch. |
| **Lock branch** | Branch become read-only. Users cannot push to the branch. Locked branches can also not be deleted. |
***

## Creating Branch Protection Rules
- Navigate to your repository homepage at Github. Then click on the Settings Option
  
![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/0e57df1f-316c-4784-b990-4627432c9985)

- In the "Code and automation" section of the sidebar, click  Branches

![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/e52fb713-34e4-4606-bd10-dc21270be088)

- Next to "Branch protection rules", click Add rule
   
![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/524c226f-9ee6-4a4b-9b65-e0f639a2685c)
  
- Under "Branch name pattern", type the branch name or pattern you want to protect

![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/4f3439a7-ca15-43d1-91c3-10b4fa6bcee3)

- Select the protection rules for your branch and then click on create
***

## Access permissions
To perform actions on GitHub, such as creating pull requests or changing billing settings, a person must have sufficient access, controlled by permissions. Permissions define the ability to perform specific actions (e.g., deleting an issue). A role is a set of permissions assigned to individuals or teams.

With roles, you can control who has access to your accounts and resources on GitHub and the level of access each person has. Roles work differently for different types of accounts. For more information about accounts, see "[Types of GitHub accounts](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/about-custom-repository-roles)."
### Types of Github Account
There are three types of accounts on GitHub.

| Type | Description   |
|-----|--------------------------|
| [Personal accounts](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-user-account-settings/permission-levels-for-a-personal-account-repository) | A repository owned by a personal account has two permission levels: the repository owner and collaborators |
| [Organization accounts](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization) | Organization owners can assign roles to individuals and teams giving them different sets of permissions in the organization. |
| [Enterprise accounts](https://docs.github.com/en/enterprise-cloud@latest/admin/managing-your-enterprise-account/about-enterprise-accounts) | GitHub Enterprise Cloud and GitHub Enterprise Server offer enterprise accounts for centralized management of policy, billing, and promoting innersourcing across multiple organizations. |
***

## Roles in an organisation
Organization owners can assign roles to individuals and teams giving them different sets of permissions in the organization. You can give organization members, outside collaborators, and teams of people different levels of access to repositories owned by an organization by assigning them to roles. Choose the role that best fits each person or team's function in your project without giving people more access to the project than they need.

### Roles available for an organization repository
| Type of role| Description |
|-----|--------------------------|
| Read | Recommended for non-code contributors who want to view or discuss your project |
| Write | Recommended for contributors who actively push to your project |
| Maintain | Recommended for project managers who need to manage the repository without access to sensitive or destructive actions. | 
| Triage | Recommended for contributors who need to manage issues, discussions, and pull requests but don't have write access. |
| Admin | Recommended for people who need full access to the project, including sensitive and destructive actions like managing security or deleting a repository |
| Custom roles | Only organizations that use GitHub Enterprise Cloud can create custom repository roles. |
***

## Creating a repository role
- In the upper-right corner of GitHub, select your profile photo, then click  Your organizations.

![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/822279f0-e61d-46d9-a284-5a08bc798ff0)

- Under "Organizations", next to the name of your organization, click Settings.

![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/65d83bd5-9da0-4de0-ac4e-b76f2f68574e)

- In the "Access" section of the sidebar, click  Repository roles.

![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/743f7c35-5bd8-4049-aefc-0e6f1e94cf87)

- Scroll to the "Custom roles" section, then click Create a Role. Fill out all the details and then click on create role.

![image](https://github.com/mygurkulam-p9/documentation/assets/160398005/23005f83-2243-4494-bc5b-c3fed721674b)

***
## Conclusion
Access policies and branch protection rules are like security guards for your code. They make sure only the right people can make changes, which keeps your code safe and working well. They also help everyone work together smoothly and follow the rules, like making sure changes get reviewed before they're added. So, they're important because they keep your code secure, organized, and running smoothly.
***

## Contact Information

| Name| Email Address :mailbox:   |
|-----|--------------------------|
| Akshit kapil |akshit.kapil.snaatak@mygurukulam.co | 
***
## Reference Links

| Links | Description      |
|-----  |--------------------------|
| https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches | About protected branches |
| https://spectralops.io/blog/how-to-set-up-git-branch-protection-rules/ | How to set up Git branch protection rules |
| https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization | Roles in an organisations |

