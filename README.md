# Udacity-DevOps-Auto-Deploy-Superpowers

## Give your Application Auto-Deploy Superpowers

In this project, you will prove your mastery of the following learning objectives:

- Explain the fundamentals and benefits of CI/CD to achieve, build, and deploy automation for cloud-based software products.
- Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.
- Utilize a configuration management tool to accomplish deployment to cloud-based servers.
- Surface critical server errors for diagnosis using centralized structured logging.

## Final Exercise: Give Your Application Auto-Deploy Superpowers
<b>Explain the Fundamentals and Benefits of CI/CD to Achieve, Build, and Deploy Automation for Cloud-Based Software Products </b>

You are leading a team to develop the UdaPeople product, a revolutionary concept in Human Resources which promises to help small businesses care better for their most valuable resource: their people. Before implementing CI/CD for the UdaPeople product, you need authorization from the people who write the checks. Create a proposal in document or presentation form that "sells" the concept of CI/CD to non-technical decision-makers in the UdaPeople organization.

While writing this proposal document/presentation, step out of your technical role and step into the world of revenue and costs. You will need to translate the benefits of CI/CD from technical language to the business's values. To appeal to what makes business people tick, you'll need to focus on benefits that create revenue, protect revenue, control costs, or reduce costs.

The deliverable should be "near-production-quality", but you should try to time-box your work to about 30 minutes. In other words, it should be good enough to submit to a manager in a real job. It should not be a messy or last-minute submission. You may use public domain or open source templates and graphics if you'd like. But please make sure the content is your own. Your presentation should be no longer than 5 slides. Your manager prefers to view presentations that are short and sweet!

Your presentation should be in PDF format named "presentation.pdf" and should be included in your code repository root folder.

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
1. CloudFormation templates - For your convenience, we have provided necessary CloudFormation templates that you can use throughout the deployment phase of your project. You can find those templates in the /.circleci/files folder. It has these files:

cloudfront.yml - We will instruct you to use this file to manually create a stack.
backend.yml and frontend.yml - Your CircleCI job will run these files. We will hold you along the step-by-step instructions ahead.
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

### Rubric
Before you start coding your solution, it will be a good idea to have a quick look at the Rubric criteria against which your submisssion will be evaluated.

![Diagram of CI/CD Pipeline we will be building.](udapeople.png)

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
