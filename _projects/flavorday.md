---
layout: project
title: "Flavor Day"
caption: Geographical representation of all of Culver's Flavor of the Day in one map.
description: >
 - ETL ingestion of data from Culver’s API
 -  Daily update of data via rack tasks using the whenever gem 
 - Backend RESTful API using MVC architecture built with Ruby on Rails.
 - Frontend single-page application built with npm, webpack, Vue.js, Bootstrap, and MapBox GLJS.    
 - DevOps CI:CD Pipeline, GitHub actions build the front and backend Docker containers, then pushes them to DockerHub. Digital Ocean Droplet pulls the latest container from DockerHub using WatchTower to deploy them to the production server. 

date: "25-09-2022"
image:
  path: /assets/img/projects/hydejack-site.jpg
  srcset:
    1920w: /assets/img/projects/hydejack-site.jpg
    960w: /assets/img/projects/hydejack-site@0,5x.jpg
    480w: /assets/img/projects/hydejack-site@0,25x.jpg
links:
  - title: Link
    url: https://www.flavorday.app
sitemap: false
---
