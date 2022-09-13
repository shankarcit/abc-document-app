# DevOps Engineer Assignment Brief

We understand that your time is valuable and want to thank you for working on this exercise.

A major aspect of the role is to design and implement the next generation of infrastructure and
CI/CD for data science at Paidy.
In this exercise you will be working to make the documentation for our internal Python package,
PaidySuperAI, publicly available so that it's easy for our data scientists to review it while
building the next generation ML models.

Please note, that anything you build as part of this assignment is entirely owned by you in
perpetuity.

We might store/archive your solution and use it internally for discussion and evaluation.

## The Assignment

For the source Python files in the subfolder `src/`, on any change within the source files,
the build pipeline (can be CircleCI, GitHub Actions, BitBucket pipelines, etc.) shall:

1. Generate browsable documentation for PaidySuperAI (preferably using pydoc or Sphinx)
2. Containerize the documentation and upload it to AWS ECR
3. Deploy it on AWS and make it publicly accessible / browsable

Please see the requirements below for additional restrictions.

## Requirements

Please keep the following things in mind:

* Approach the exercise as if you are working in a real production environment.
* Document and explain any assumptions and decisions you make, and any shortcuts you take (for
  example, due to time constraints) in the process.
* Use AWS, Terraform, and Python where applicable.
* The documentation must be containerized.
* Since PaidySuperAI is an internal package we want to limit access to the documentation, blocking
  all IPs outside the range `60.125.0.0/16` and `152.165.0.0/16`.
* Share the code, and documents you create or are going to present as part of this project with your
  interviewers. Version control solutions like GitHub, Gitlab, BitBucket, etc… are all
  acceptable). Please restrict public access to your submission.

****************************************************************************************************************************

# Solution:

App Name: abc-document-app

## Description:
The is the auto documentation app built using Sphinx.

I had a challenge with sphinx build. It builds a html with dead links and docstrings are not pulled in. I spent almost 5 hours to trouble shoot. 
I need to work with python developers. Since I have htmls generated, I proceeded with building application with broken links.

## Architecture:
https://github.com/shankarcit/abc-document-app/blob/develop/Images/architecture.jpg

Programming Language: Python
Build tool: Circle CI
Platform: Azure Kubernetes cluster
Version Control: Github
Cloud: AWS
Container Registry: ECR
IAC tool: Terraform with S3, Dynamo DB backend

All AWS resources are built only by Terraform

Creating a PR to develop branch will deploy to Dev cluster
Creating a PR to sqa branch will deploy to sqa cluster

