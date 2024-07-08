# Jenkins Poll SCM vs Webhook

![Jenkins Poll SCM vs Webhook](https://dz2cdn1.dzone.com/storage/temp/5679141-screen-shot-2017-06-21-at-43750-pm.png)


## Table of Contents
1. [Introduction](#introduction)
2. [Poll SCM](#poll-scm)
3. [Webhooks](#webhooks)
4. [Comparison](#comparison)
5. [Visual Representation](#visual-representation)
6. [Conclusion](#conclusion)

---

## Introduction

Jenkins offers multiple methods for triggering builds, each with its own advantages and use cases. Two primary methods are Poll SCM and Webhooks.

### Poll SCM

Poll SCM involves Jenkins periodically checking the version control system (VCS) for changes based on a configured schedule. It's suitable when direct webhook integration is not feasible or desired.

### Webhooks

Webhooks allow the VCS to notify Jenkins immediately when a change occurs, triggering a build promptly. This reduces latency and enhances automation efficiency.

---

## Comparison

### Key Differences

- **Poll SCM:**
  - Jenkins polls the VCS at regular intervals.
  - Requires configuring a cron expression.
  - Suitable for environments without webhook support.

- **Webhooks:**
  - VCS notifies Jenkins of changes in real-time.
  - Eliminates polling delay.
  - Preferred for faster build triggering and efficiency.

---

## Visual Representation

### Poll SCM Configuration

![Poll SCM Configuration](https://i.sstatic.net/8HvxY.png)

### Webhook Configuration

![Webhook Configuration](https://argo-cd.readthedocs.io/en/stable/assets/webhook-config.png)

---
