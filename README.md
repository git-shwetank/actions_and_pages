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

Followed the steps in the tutorial reference- But faced an environment issue on Runner. When executing - 'npm test' a job step command.
npm test looks for package.json of Node project and has a declaration to execute [next lint] command which uses next.js eslint packages to verify vulnerabiltiy in code packages, hence need to configure it to complete sucessfully. 

This was replicated on local set up and was fixed by changing command to explicitly sending configuration response as command argument. The command was modified to - [next lint --strict]

Please see before and after change from local 

(Notes: nodejs version and npm version were not matching on runner compared to local first, And even when asserted to match failure remains the same on runner but local command worked to match expectation of not throwing error or blocking the execution. However, when fix is deployed on runner it was seen to have worked but only causes job step to fail without further step propogation.)

The behaviour should be treated as expected behaviour. However, I found that if a job is expected to pass and error should be a False Positive. The job step can use _continue-on-error_ and _continue-on-failure_ options set to 'true' like our scenario the test step is running a Static Code Analysis instead of functional conformance and which is likely to fail but doesn't affect the functioning of the application. 
<img width="662" height="460" alt="image" src="https://github.com/user-attachments/assets/ee93bfd3-ff59-45fc-8ee1-fec24eb01b63" />

