# actions_and_pages
Objective is to Follow and Implement - https://resources.github.com/learn/pathways/automation/essentials/automated-application-deployment-with-github-actions-and-pages/

Summary: GitHub Actions and Pages POC
Target Time: 7 Days

GitHub Actions - Workflow for Build Test and Deploy

Sample Application use: next.js ( Node JS based application ::Assuming )

Note: 
__Amplifon__ is an Organisation in Healthcare domain which has used GitHub Actions for _automating_ CI/CD to adopt Operational Agility by Refactoring, Centralising and Standardizing codebase, Distributed Collaboration, Data _Security_, Optimizing engineering operations and address _cost efficiency_

__TELUS__ is IT and Communication enabler organisation. They _unified_ various tools and technologies using GitHub Actions. 

# Building a workflow using GitHub Actions

Sub-Objective: To understand the use case from Amplifon

Created local repo [https://github.com/git-shwetank/actions-learning-pathway] from template- https://github.com/github/actions-learning-pathway

Note: GitHub Actions doesn't provide free __'Runners'__ Agents to use for private use. Hence the repository should be made public.

__Actions__ are identified by _name_ and trigger based _on_ repository actions like 'push' and have _jobs_ which execute when triggering occurs.

These __jobs__ utilize resources on a 'Runner' a.k.a. Agent which may be Physical Server System or Virtual Computing Unit. In our case we have used a GitHub hosted runner agent.

__Jobs__ comprise of _steps_. 

It seems that a Step can be an Action. Hence, it sounds like an Action is a re-usable unit.

There are 'Starter Workflow actions' as well seen on Actions landing page. Catering to specific type of needs.

When the Workflow Action is committed. It is visible under 'Actions' tab
<img width="1918" height="873" alt="image" src="https://github.com/user-attachments/assets/848aaca9-0f7d-4876-8b6a-38421b990ae6" />

Status is shown as-
<img width="1919" height="937" alt="image" src="https://github.com/user-attachments/assets/b6b06d52-698c-4753-ad5e-9e80018335f9" />

Details of execution is shown as follows:-

<img width="1914" height="788" alt="image" src="https://github.com/user-attachments/assets/08d9924a-a770-4743-aab4-13c6dcfbc0b2" />





