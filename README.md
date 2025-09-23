Kyverno Policies Helm Chart

This repository contains a curated Helm chart of essential Kyverno policies. The policies are automatically downloaded and packaged into a Helm chart on a weekly basis by a GitHub Actions workflow.

🚀 How it Works

A GitHub Actions workflow is scheduled to run every Monday at 3 AM UTC. This workflow performs the following tasks:

    Downloads Policies: It fetches the latest versions of a predefined list of Kyverno policies directly from the official nirmata/kyverno-policies and kyverno/policies GitHub repositories.

    Checks for Updates: It compares the newly downloaded policies against the policies in the repository.

    Updates Helm Chart: If any policy has been updated, the workflow:

        Replaces the old policy files with the new ones.

        Bumps the patch version of the Helm chart (e.g., from 1.0.0 to 1.0.1) to reflect the changes.

        Commits and pushes the updates to the repository, creating a new version of the Helm chart.

This automated process ensures that the policies in this chart are always up-to-date with the upstream sources.
