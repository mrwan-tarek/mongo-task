# Jenkins Poll SCM vs Webhook

![Jenkins Poll SCM vs Webhook](images/jenkins-poll-scm-vs-webhook.png)

This repository provides an overview of the differences between Poll SCM and Webhooks in Jenkins.

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

![Poll SCM Configuration](images/poll-scm-config.png)

### Webhook Configuration

![Webhook Configuration](images/webhook-config.png)

---

## Conclusion

Understanding the differences between Poll SCM and Webhooks helps in choosing the appropriate method based on project requirements and infrastructure capabilities.

---

This repository serves as a guide to help you leverage Poll SCM and Webhooks effectively in your Jenkins automation workflows. Contributions and feedback are welcome!

