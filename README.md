Poll SCM:
How it works: Jenkins regularly checks the SCM (Source Control Management) for changes. You can configure the polling interval, for example, every 5 minutes.
Pros:
Simple to set up, no need to configure webhooks.
Works with any SCM that Jenkins supports.
Cons:
Inefficient: Jenkins will keep polling the SCM even if no changes have occurred, which can lead to unnecessary load on both Jenkins and the SCM.
Delay: There could be a delay between when a change is made and when Jenkins detects it, depending on the polling interval.

GitHub hook trigger for GITScm polling:
How it works: GitHub sends a webhook to Jenkins whenever there is a push event to the repository. Jenkins then triggers the job based on this webhook.
Pros:
Efficient: Jenkins only runs the job when there are actual changes, reducing unnecessary load.
Immediate: Jenkins triggers the job almost instantly after changes are pushed, leading to faster builds and deployments.
Cons:
Requires additional setup: You need to configure webhooks in the GitHub repository settings.
Network dependency: Requires Jenkins to be accessible from GitHub, meaning you need to handle firewall and network configuration.
![image](https://github.com/user-attachments/assets/f067876e-b59c-4a83-b8cb-6ea85b58c4a5)

When to use which:
Poll SCM is good for simpler setups or when webhooks are not an option (e.g., internal SCMs without webhook support).
GitHub hook trigger is better for most cases, especially if you want faster and more efficient builds.
