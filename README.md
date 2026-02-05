🛠️ Automated Server Health Monitoring using GitHub Actions
📌 Project Overview

This project demonstrates an automated server health monitoring pipeline built using GitHub Actions.
The workflow runs on every code push, provisions a temporary Linux server, checks system health metrics, generates a report, and raises alerts if defined thresholds are exceeded.

This project simulates how DevOps engineers monitor infrastructure and detect issues automatically using CI pipelines.

🎯 What This Project Does

On every push to the main branch, the pipeline:

Spins up a fresh Ubuntu Linux environment

Checks disk usage of the server

Applies threshold-based alerting

Generates a server health report

Uploads the report as a downloadable artifact

If the disk usage exceeds the defined limit, the pipeline fails intentionally, acting as an alert.

⚙️ Technologies & Tools Used

Git & GitHub – Version control and repository hosting

GitHub Actions – CI automation platform

YAML – Workflow configuration

Linux (Ubuntu Runner) – Execution environment

Bash Scripting – Monitoring and alert logic

🔄 How the Workflow Works
1️⃣ Trigger

The workflow is triggered automatically on every push to the repository.

on:
  push:

2️⃣ Environment Provisioning

GitHub Actions creates a temporary Ubuntu Linux virtual machine for each run.

runs-on: ubuntu-latest

3️⃣ Disk Usage Monitoring

The pipeline checks disk usage using standard Linux commands:

df /


The usage percentage is extracted and evaluated against a threshold.

4️⃣ Alerting Logic

If disk usage exceeds 80%, the pipeline fails using:

exit 1


A failed pipeline acts as an alert, similar to how monitoring systems notify teams in real environments.

5️⃣ Report Generation

A health report is generated automatically:

=== SERVER HEALTH REPORT ===
Disk usage: 37%
Checked at: Thu Feb 5 13:44:23 UTC 2026

6️⃣ Artifact Upload

The generated report is uploaded as a GitHub Actions artifact, allowing it to be downloaded and reviewed.

🚨 Alerting Behavior

✅ Disk usage ≤ 80% → Pipeline succeeds

❌ Disk usage > 80% → Pipeline fails (alert triggered)

This models real-world monitoring systems, where unhealthy conditions block deployments and require attention.

🧠 Key Concepts Learned

Continuous Integration (CI)

Infrastructure automation

Linux-based monitoring

Threshold-based alerting

CI pipeline failures as alerts

Artifact generation and usage

Debugging and fixing CI workflows

🌍 Real-World Relevance

This project reflects how DevOps teams:

Automate infrastructure checks

Detect issues early

Use CI pipelines for monitoring

Prevent faulty deployments

Maintain system reliability

The same principles apply to tools like Jenkins, GitLab CI/CD, AWS CloudWatch, and Azure Monitor.

🏁 Conclusion

This project provided hands-on experience with DevOps automation, monitoring, and alerting using GitHub Actions.
It serves as a strong foundational DevOps project and can be extended further with CPU, memory checks, notifications, and cloud integrations.
