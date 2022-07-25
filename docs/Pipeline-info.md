+ # Pipeline process using CircleCI. 

**There are many other pipeline-as-a-service companies that offer a similar set of services, but for the purpose of this project, CircleCI presents a great set of features and has the advantage of being popular in the industry.**

**Pipelines are normally written inside configuration files as a list of steps. In the case of CircleCI, this file will always be located inside a .circleci folder and will be named config.yml.**

**It contains the following sections:**

Steps :

1. Install

2. Build

3. Deploy

+ # orbs 
- orgs contain basic recipes and reproducible actions (install node, AWS etc...).

**Node** node: circleci/node@4.1.0

**EB** eb: circleci/aws-elastic-beanstalk@2.0.1

**AWS-CLI** aws-cli: circleci/aws-cli@1.3.1

+ # jobs

- jobs are groups of commands that we want to run. This is where we will run commands to install, build and/or deploy our application.

+ ## build

+ ### build steps

**install Node and checkout code**

- node/install
- checkout

+ #### Use root package.json to install dependencies in the frontend

**npm run frontend:install**


+ ### Install dependencies in the the backend API

**npm run api:install**


+ ### install and Build the frontend app

**npm run frontend:build**


+ ### install and Build the backend API

**npm run api:build**


**deploy step will run only after manual approval**
+ ## deploy

+ ### deploy steps

- node/install
- aws-cli/setup
- eb/setup
- checkout


#### deploy frontend app

**npm run frontend:deploy**


#### deploy backend app

**npm run api:deploy**

