Kyverno Policies Helm Chart

This repository contains a curated Helm chart of essential Kyverno policies. The policies are automatically downloaded and packaged into a Helm chart on a weekly basis by a GitHub Actions workflow.

🚀 How It Works

A GitHub Actions workflow is scheduled to run every Monday at 3 AM UTC. This workflow automates the entire process of maintaining the Helm chart:

    Downloads and Syncs Policies: It fetches the latest versions of a predefined list of Kyverno policies and saves them to the local policies/ directory.

    Checks for Updates: It compares the newly downloaded policies against the policies in the repository.

    Packages and Updates the Helm Chart: If any policy has been updated or if the Helm chart files do not exist, the workflow will:

        Create the necessary directory structure (helm-chart/, helm-chart/templates/).

        Copy the latest policies into the helm-chart/templates/ directory.

        Create or update core Helm files such as Chart.yaml, values.yaml, and _helpers.tpl.

        Bump the chart's patch version (e.g., from 1.0.0 to 1.0.1) to reflect the changes.

    Commits and Pushes: Finally, it commits all changes and pushes them to the repository, ensuring the Helm chart is always up-to-date with the upstream sources.

This automated process ensures that the policies in this chart are always current without any manual intervention.
