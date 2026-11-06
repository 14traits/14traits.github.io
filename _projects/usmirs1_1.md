---
layout: project
title: "USMIRS 1.1"
caption: Applicant Processing System for the Dept of Defense.
description: |
 - Agile software project enabling the mission of USMEPCOM: a system of interconnected services for processing US military applicants.
 - Built with Ruby, Ruby on Rails, React, TypeScript, and Postgres.
 - Deployed in AWS GovCloud at DoD Impact Level 4 (IL4).
 - Infrastructure and configuration written in Terraform and Ansible.
 - Automated delivery to lower environments with GitLab Runners to AWS CodeBuild and CodePipeline.
date: "15-02-2020"
image:
  path: /assets/img/projects/usmirs/hero.jpg
  srcset:
    1920w: /assets/img/projects/usmirs/hero.jpg
    960w: /assets/img/projects/usmirs/hero@0,5x.jpg
    480w: /assets/img/projects/usmirs/hero@0,25x.jpg
links:
  - title: Link
    url: https://www.mepcom.army.mil
sitemap: false
---

USMIRS 1.1 is a system of interconnected services that enables the mission of USMEPCOM. It lives in
AWS GovCloud, and most of my contributions were in the DevSecOps world: building the CI/CD process and
editing the Infrastructure as Code (IaC).

## The Biometrics deployment

During the final stages of USMIRS 1.1, I led a team of Civil Service engineers to deploy a Biometrics
Solution that our contract team could not deliver. It became USMEPCOM's first, and so far only,
government-led and government-developed cloud deployment to AWS.

- I was the only engineer on the team who could read and write Terraform, so I solely refactored the IaC
  and developed the missing parts so it could target an entirely different server OS platform.
