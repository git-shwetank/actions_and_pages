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

# Building an application with GitHub Actions workflow

Configure Action for Build -
<img width="1310" height="798" alt="image" src="https://github.com/user-attachments/assets/905ab7b8-76c6-493e-bce9-cb69b700d2de" />

Result:
<img width="939" height="428" alt="image" src="https://github.com/user-attachments/assets/f6024f26-c028-49ed-a99a-74674b2ac6a5" />

<img width="1652" height="757" alt="image" src="https://github.com/user-attachments/assets/7ddad902-b8ab-446a-a407-40c2811a4732" />
<img width="1848" height="827" alt="image" src="https://github.com/user-attachments/assets/6c0c5f7c-eafa-4262-bcd7-3cfcc3b3a503" />

# Testing applications with GitHub Actions

Followed the steps in the tutorial reference- But faced an environment issue on Runner. When executing - 'npm test' a job step command.
npm test looks for package.json of Node project and has a declaration to execute [next lint] command which uses next.js eslint packages to verify vulnerabiltiy in code packages, hence need to configure it to complete sucessfully. 

This was replicated on local set up and was fixed by changing command to explicitly sending configuration response as command argument. The command was modified to - [next lint --strict]

Please see before and after change from local 

(Notes: nodejs version and npm version were not matching on runner compared to local first, And even when asserted to match failure remains the same on runner but local command worked to match expectation of not throwing error or blocking the execution. However, when fix is deployed on runner it was seen to have worked but only causes job <a name="someName">step to fail without further step propogation</a>.)

The behaviour should be treated as expected behaviour. However, I found that if a job is expected to pass and error should be a False Positive. The job step can use _continue-on-error_ and _continue-on-failure_ options set to 'true' like our scenario the test step is running a Static Code Analysis instead of functional conformance and which is likely to fail but doesn't affect the functioning of the application. 
<img width="662" height="460" alt="image" src="https://github.com/user-attachments/assets/ee93bfd3-ff59-45fc-8ee1-fec24eb01b63" />
<img width="1821" height="759" alt="image" src="https://github.com/user-attachments/assets/cb607587-4a08-4228-8064-ca0d3ba4affc" />
<img width="1912" height="833" alt="image" src="https://github.com/user-attachments/assets/fd9f2bf4-68c4-4444-a69e-83dffa086813" />

# Configure your deployment environment in GitHub

- How to create a new deployment  environment

GitHub Settings -> Environment
GitHub Settings -> Pages -> Select Source as GitHub Actions

- Best practices for configuring deployment environments
Enviornment Variables and Secrets

# Automating and deploying workflows with GitHub Actions
deploying our Next.js application to GitHub Pages with GitHub Actions!

- How to set permissions for specific use-cases

- How to choose a deployment environment in a workflow

- How to deploy a Next.js static site to GitHub Pages with GitHub Actions

upload artifact actions workflow is deprecated and needs to upgrade to v4
<img width="1900" height="833" alt="image" src="https://github.com/user-attachments/assets/49550993-59e6-48d0-b357-e8ce19a69606" />

Important Note: using the latest version of GitHub Actions Workflow (predefined) is essential to avoid any errors when step executes
<img width="1901" height="831" alt="image" src="https://github.com/user-attachments/assets/a7bd0733-d64b-4efb-b87e-d6761ed2d4b3" />
