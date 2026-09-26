---
layout: project
title: "Flavor Day"
caption: Every Culver's Flavor of the Day, on one map.
description: |
 - Frontend single-page application built with React 19, Vite, and TypeScript.
 - Map rendered with MapLibre GL JS over self-hosted Protomaps vector tiles on Cloudflare R2.
 - No custom backend server: the SPA reads straight from Supabase Postgres via PostgREST, secured with row-level security.
 - Daily ingestion via a Supabase Edge Function on a `pg_cron` schedule, sweeping Culver's locator API with an adaptive grid.
 - Self-hosted Caddy locator proxy behind a Cloudflare Tunnel, so data pulls egress from a residential IP.
 - DevOps CI/CD pipeline in GitLab with Infisical-injected secrets, deploying to Cloudflare Pages and Supabase.

date: "19-06-2026"
image:
  path: /assets/img/projects/flavorday/map.jpg
  srcset:
    1920w: /assets/img/projects/flavorday/map.jpg
    960w: /assets/img/projects/flavorday/map@0,5x.jpg
    480w: /assets/img/projects/flavorday/map@0,25x.jpg
links:
  - title: Link
    url: https://www.flavorday.app
sitemap: false
---

Flavor Day finds the Culver's Flavor of the Day near you, without extra clicks. Every location is
dropped on the map as a marker showing that day's custard, so you can see at a glance where to go.

![Flavor Day zoomed in on a store popup with directions](/assets/img/projects/flavorday/popup.jpg)

## Why the rewrite

The original Flavor Day (2022) was a Ruby on Rails API and a Vue.js SPA, shipped as Docker containers to a
DigitalOcean droplet. Then Culver's retired the locator endpoint the Rails app depended on, and the daily
data pulls broke.

Rather than patch it, I rebuilt it as a TypeScript monorepo with almost no ops to run:

- The rake tasks became a Supabase Edge Function on a `pg_cron` schedule. It waits on a canary store until
  Culver's rolls the day's flavor, then subdivides its search grid wherever the API hits its 100-result
  cap, and upserts flavors, locations, and today's pairings.
- The Rails API went away. The React app queries a `today_flavors` view directly with `supabase-js`.
- Culver's serves degraded responses to datacenter IPs and drops the flavor from dense metros like
  Milwaukee and Madison. Ingestion therefore routes through a small Caddy proxy on my home lab, fronted
  by a Cloudflare Tunnel.

![The whole Flavor Day map, coast to coast](/assets/img/projects/flavorday/coverage.jpg)

![Flavor Day on a phone](/assets/img/projects/flavorday/mobile.jpg){:width="430"}
