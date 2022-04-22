# Udacity-DevOps-Auto-Deploy-Superpowers

In this project, you will prove your mastery of the following learning objectives:

- Explain the fundamentals and benefits of CI/CD to achieve, build, and deploy automation for cloud-based software products.
- Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.
- Utilize a configuration management tool to accomplish deployment to cloud-based servers.
- Surface critical server errors for diagnosis using centralized structured logging.

## Final Exercise: Give Your Application Auto-Deploy Superpowers
<b>Explain the Fundamentals and Benefits of CI/CD to Achieve, Build, and Deploy Automation for Cloud-Based Software Products </b>

You are leading a team to develop the UdaPeople product which promises to help small businesses care better for their most valuable resource: their people. Before implementing CI/CD for the UdaPeople product, you need authorization from the people who write the checks. Create a proposal in presentation form that "sells" the concept of CI/CD to non-technical decision-makers in the UdaPeople organization.

While writing this proposal document/presentation, step out of your technical role and step into the world of revenue and costs. You will need to translate the benefits of CI/CD from technical language to the business's values. To appeal to what makes business people tick, you'll need to focus on benefits that create revenue, protect revenue, control costs, or reduce costs.

The deliverable should be "near-production-quality", but you should try to time-box your work to about 30 minutes. In other words, it should be good enough to submit to a manager in a real job. It should not be a messy or last-minute submission. You may use public domain or open source templates and graphics if you'd like. But please make sure the content is your own. Your presentation should be no longer than 5 slides. Your manager prefers to view presentations that are short and sweet!

Presentation should be in PDF format named "presentation.pdf" and should be included in your code repository root folder.

## directory structure relevant for the project:
``` bash
├── .circleci # You will develop the files in this directory. 
│   ├── ansible
│   └── files
├── backend  # Do not run npm commands here (on your local machine). 
│   ├── src
│   └── test
├── frontend # Do not run npm commands here (on your local machine). 
│   ├── src
│   └── types
└── util     # Files relevant for the running the app locally (Optional).
```

## Contents of the .circleci directory
1. CloudFormation templates - We have provided necessary CloudFormation templates that you can use throughout the deployment phase of your project. You can find those templates in the /.circleci/files folder. It has these files:

- cloudfront.yml - We will instruct you to use this file to manually create a stack.
- backend.yml and frontend.yml - Your CircleCI job will run these files. We will hold you along the step-by-step instructions ahead.

Note that no changes are required in three files mentioned above, except updating the EC2 key pair name and suitable AMI name in the backend.yml file later.

2. Ansible Playbooks and Roles - The /.circleci/ansible directory contains the playbook files and roles that you will develop, per instructions on the next page.

3. CircleCI config.yml file - We left a scaffolded/incomplete /.circleci/config.yml file to help you get started with CirlcCI's configuration. This file has intentionally failing/incomplete jobs. To call attention to unfinished jobs, we left some "non-zero error codes" (e.g. exit 1) for you to remove when you have finished implementing the jobs.

```
The starter config.yml file will not work out-of-the-box. It is provided to help you understand the final structure of the CircleCI configuration.
```

## The backend and the frontend
```
Tip: It is a good practice to read through the frontend and backend README.
```
Do not run NPM commands either in the backend or the frontend folders on your local machine. Instead, you will run the suitable NPM commands as part of the CircleCI jobs.

Also, note that we have provided an easy-to-fix compile error in the backend. In addition, there is one failing test in both the frontend and backend. Details are present in the next section. This means, the starter code will not work out of the box on your local machine either.

## Screenshots and URLs
Throughout this project, you will be asked to take screenshots or provide URLs to aid in the evaluation process once you're done with the project (see details in the Rubric below).

It's worth mentioning here since it's much harder to harvest some screen shots once you've passed certain milestones. It's best if you take screenshots along the way and store them in a folder on your computer until you're ready to turn the project in. Also, it's good to keep a document or notepad with the list of urls that are requested.

## Rubric
Before you start coding your solution, have a quick look at the Rubric criteria against which your submisssion will be evaluated.

### PROJECT SPECIFICATION

Section 1: Selling CI/CD to your Team/Organization

Explain the fundamentals and benefits of CI/CD to achieve, build, and deploy automation for cloud-based software products. 
=> The CI/CD benefits proposal contains essential benefits of CI/CD, and describes the business context that will benefit from the automation tools. Explanation should include benefits that translate to revenue and cost for the business.

Section 2: Deploying Working, Trustworthy Software

Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.

=> A public git repository with your project code. [URL01]

=> Evidence of code-based CI/CD configuration in the form of yaml files in your git repository.

=> Console output of various pre-deploy job failure scenarios:

=> Build Jobs that failed because of compile errors. [SCREENSHOT01]

=> Failed unit tests. [SCREENSHOT02]

=> Failure because of vulnerable packages. [SCREENSHOT03]

=> An alert from one of your failed builds. [SCREENSHOT04]

Evidence in your code that:

=> Compile errors have been fixed.

=> Unit tests have been fixed.

=> All critical security vulnerabilities caught by the “Analyze” job have been fixed.

Utilize a configuration management tool to accomplish deployment to cloud-based servers.

=> Console output of appropriate failure for infrastructure creation job (using CloudFormation). [SCREENSHOT05]

=> Console output of a smoke test job that is failing appropriately. [SCREENSHOT06]

=> Console output of a successful rollback after a failed smoke test. [SCREENSHOT07]

=> Console output of successful promotion of new version to production in CloudFront. [SCREENSHOT08]

=> Console output of successful cleanup job that removes old S3 bucket and EC2 instance. [SCREENSHOT09]

=> Evidence that deploy jobs only happen on master branch. [SCREENSHOT10]

=> Evidence of deployed and functioning front-end application in an S3 bucket [URL02] and in CloudFront. [URL03]

=> Evidence of healthy back-end application. [URL04]

Section 3: Turn Errors into Sirens

Surface critical server errors for diagnosis using centralized logging.

=> Evidence of Prometheus Server. [URL05]

=> Evidence that Prometheus is monitoring memory, cpu and disk usage of EC2 instances. [SCREENSHOT11]

=> Evidence that Prometheus and AlertManager send alerts when certain conditions exist in the EC2 instance. [SCREENSHOT12]

Suggestions to Make Your Project Stand Out!

=> Add custom alert messages with more specific CI/CD pipeline failure reasons. The more specific the message, the faster the UdaPeople dev team can fix the issue.

=> Use Circle CI locally to test your pipeline before pushing to git.

=> Integrate other types of analysis or notification jobs.

=> Write your own smoke tests to build more confidence before promoting the new build to production.


### Instructions

* [Selling CI/CD](instructions/0-selling-cicd.md)
* [Getting Started](instructions/1-getting-started.md)
* [Deploying Working, Trustworthy Software](instructions/2-deploying-trustworthy-code.md)
* [Configuration Management](instructions/3-configuration-management.md)
* [Turn Errors into Sirens](instructions/4-turn-errors-into-sirens.md)

### Project Submission

For your submission, please submit the following:

- A text file named `urls.txt` including:
  1. Public Url to GitHub repository (not private) [URL01]
  1. Public URL for your S3 Bucket (aka, your green candidate front-end) [URL02]
  ```
  Note: The services should be up and running while the reviewer evaluates your project. If you use Udacity provided AWS account, the EC2 instance will shut down (not terminate) automatically after the session ends at every 4 hours. Therefore, you can consider rerunning the CircleCI pipeline just before the submission for provisioning the new AWS resources and provide the working URL02.
  ```
  1. Public URL for your CloudFront distribution (aka, your blue production front-end) [URL03]
  1. Public URLs to deployed application back-end in EC2 [URL04]
  1. Public URL to your Prometheus Server [URL05]
- Your screenshots in JPG or PNG format, named using the screenshot number listed in the instructions. These screenshots should be included in your code repository in the root folder.
  1. Job failed because of compile errors. [SCREENSHOT01]
  1. Job failed because of unit tests. [SCREENSHOT02]
  1. Job that failed because of vulnerable packages. [SCREENSHOT03]
  1. An alert from one of your failed builds. [SCREENSHOT04]
  1. Appropriate job failure for infrastructure creation. [SCREENSHOT05]
  1. Appropriate job failure for the smoke test job. [SCREENSHOT06]
  1. Successful rollback after a failed smoke test. [SCREENSHOT07]  
  1. Successful promotion job. [SCREENSHOT08]
  1. Successful cleanup job. [SCREENSHOT09]
  1. Only deploy on pushed to `master` branch. [SCREENSHOT10]
  1. Provide a screenshot of a graph of your EC2 instance including available memory, available disk space, and CPU usage. [SCREENSHOT11]
  1. Provide a screenshot of an alert that was sent by Prometheus. [SCREENSHOT12]
  1. Provide a screenshot showing the evidence of deployed and functioning front-end application in CloudFront (aka, your production front-end). [URL03_SCREENSHOT]
  1. Provide a screenshot showing the evidence of a healthy backend application. The backend endpoint status should show a healthy response. [URL04_SCREENSHOT]
  1. Provide a screenshot of your Prometheus server showing UP state [URL05_SCREENSHOT]

- Your presentation should be in PDF format named "presentation.pdf" and should be included in your code repository root folder. 

Before you submit your project, please check your work against the project rubric. If you haven’t satisfied each criterion in the rubric, then revise your work so that you have met all the requirements. 

### Built With

- [Circle CI](www.circleci.com) - Cloud-based CI/CD service
- [Amazon AWS](https://aws.amazon.com/) - Cloud services
- [AWS CLI](https://aws.amazon.com/cli/) - Command-line tool for AWS
- [CloudFormation](https://aws.amazon.com/cloudformation/) - Infrastrcuture as code
- [Ansible](https://www.ansible.com/) - Configuration management tool
- [Prometheus](https://prometheus.io/) - Monitoring tool

### License

[License](LICENSE.md)
