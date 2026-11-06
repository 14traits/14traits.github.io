---
layout: project
title: "ARK"
caption: A pilot AI chatbot for Human Resource Assistants, in AWS GovCloud.
description: |
 - Agile software project delivering a pilot AI chatbot that answers policy and regulation questions for Human Resource Assistants.
 - Four AWS Lambda functions written in Go, handling the AWS Bedrock API, Okta authentication, and user sessions stored in DynamoDB.
 - Frontend single-page application built with React and TypeScript.
 - Deployed in AWS GovCloud at DoD Impact Level 4 (IL4).
 - Infrastructure and configuration written in Terraform and Ansible.

date: "13-10-2026"
image:
  path: /assets/img/projects/ark/hero.jpg
  srcset:
    1920w: /assets/img/projects/ark/hero.jpg
    960w: /assets/img/projects/ark/hero@0,5x.jpg
    480w: /assets/img/projects/ark/hero@0,25x.jpg
links:
  - title: USMEPCOM
    url: https://www.mepcom.army.mil
sitemap: false
---

ARK is a pilot chatbot that gives Human Resource Assistants quick answers to questions about policy and
regulations. I co-authored the pilot as part of my work
at USMEPCOM.

## How it's built

- The React and TypeScript SPA talks to four Go Lambda functions.
- The Lambdas call the AWS Bedrock API to generate answers and handle Okta authentication.
- User sessions are stored in DynamoDB.
- Everything is deployed to AWS GovCloud at DoD Impact Level 4, with infrastructure and configuration
  managed as code in Terraform and Ansible.
