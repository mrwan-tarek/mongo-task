# Jenkins SCM Polling vs Webhooks

## Poll SCM

**Overview:**
Poll SCM (Source Code Management) in Jenkins involves Jenkins periodically checking the SCM repository for changes.

**How it works:**
- Jenkins is configured to poll the SCM at specified intervals (e.g., every few minutes).
- Builds are triggered if changes are detected during the polling.

**Pros:**
- Simple to set up within Jenkins.
- Suitable for environments where direct webhook integration is not possible or allowed.

**Cons:**
- Potential delays in detecting changes due to polling intervals.
- Increased load on both Jenkins and the SCM system due to frequent polling.

**More Info:** [What is Poll SCM in Jenkins and how to configure Poll SCM?](https://www.geeksforgeeks.org/what-is-poll-scm-jenkins-and-how-to-configure-poll-scm/)

## Webhooks

**Overview:**
Webhooks in Jenkins allow for immediate triggering of builds upon SCM events.

**How it works:**
- When a change occurs in the SCM repository (e.g., commit, merge), the SCM system sends a webhook to Jenkins.
- Jenkins processes the webhook and triggers a build immediately.

**Pros:**
- Real-time triggering of builds, reducing latency in build initiation.
- More efficient resource usage as Jenkins only acts upon events, not polling.

**Cons:**
- Requires setup both in the SCM system (to send webhooks) and in Jenkins (to receive and process webhooks).
- Dependency on external systems (SCM providers) to correctly deliver webhooks.

**More Info:** For more details on webhooks, you can refer to external resources or documentation specific to your SCM provider.

## Recommendation

- **Use Poll SCM** for setups where immediate triggering via webhooks is not feasible or allowed.
- **Use Webhooks** for faster feedback and efficient CI/CD workflows, especially in environments where real-time updates are crucial.

