---
sidebar_position: 1
title: Getting Started with Velu AI
description: Launch Velu AI, connect your knowledge sources, and guide it to ship documentation updates safely.
---

Velu AI is designed to keep your product documentation continuously up to date by ingesting signals across your toolchain, drafting changes, and delivering review-ready pull requests. This quickstart walks you through the first run experience so you can activate Velu AI as your autonomous documentation assistant.

## 1. Confirm prerequisites

Before you open the onboarding flow, make sure you have:

- **A GitHub account with write access to your documentation repository.** Velu AI uses its publishing layer to open reviewable pull requests against Markdown and MDX sources stored in GitHub. Ensure you can authenticate with either SSH or a personal access token that has `repo` scope.
- **Access to core context sources.** At minimum you will need Google Drive and Linear credentials so Velu can ingest PRDs, specs, and work items. Optional connectors (Slack, Jira, Confluence, Notion, etc.) can be added later to deepen Velu's context graph.
- **Administrator approval for data access.** Because Velu maintains governance logs and respects SOC2 controls, confirm you are allowed to grant repository and Drive access during onboarding.

## 2. Complete the signup onboarding

1. Navigate to the Velu AI signup page and create your workspace account.
2. When the onboarding wizard launches, review the overview screen outlining Velu's documentation automation goals (e.g., reducing stale content to < 5% and delivering updates within 24 hours of feature releases).
3. Select **Get Started** to begin connecting systems.

## 3. Connect the GitHub documentation repository

1. In the **Connect GitHub** step, choose **Authorize** to grant Velu AI access to the organization that owns your docs.
2. Pick the repository that stores your production documentation (for example a Docusaurus or Mintlify site).
3. Confirm the branch Velu should target for pull requests (commonly `main` or `docs`).
4. Save the connection. Velu will verify permissions and stage the publishing pipeline that powers diff-based updates and rollback controls.

## 4. Link context sources such as Google Drive and Linear

1. Proceed to **Connect Context Sources**.
2. Authorize Google Drive so Velu can index your PRDs, changelogs, and design docs. Velu's ingestion layer will automatically tag these documents as part of its structured knowledge graph.
3. Authorize Linear to pull product roadmap items, ticket updates, and release payloads. This helps Velu detect when documentation is drifting from in-flight engineering work.
4. (Optional) Add additional connectors like Slack, Confluence, or Zendesk to surface customer feedback and support themes in later updates.
5. Finish the onboarding flow. Velu will run an initial sync to map entities, features, and user flows across the connected sources.

## 5. Draft your first article with Velu

1. From the Velu workspace, open the **Ask Velu** interface (or the `/velu update docs` Slack command if your workspace uses Slack).
2. Prompt Velu to generate the onboarding article you need (for example, “Create an onboarding guide for the new analytics dashboard”).
3. Velu searches the connected context sources—including the Google Drive PRDs and Linear issues you just connected—to assemble relevant facts and draft the article.
4. Review the generated outline and content, providing inline feedback or follow-up prompts until it matches your documentation standard.

## 6. Review and publish via pull request

1. When satisfied with the draft, choose **Create Pull Request**.
2. Velu packages the update as a Git-style diff, applies your organization’s style rules, and opens a PR against the repository and branch you selected earlier.
3. Inspect the diff, add comments, and request any changes just as you would for a human-authored update. Velu’s governance layer tracks the discussion and confidence scores.
4. Merge the pull request to publish the documentation. Velu logs the change, updates the changelog queue, and marks the affected topics as current in its coverage dashboard.

## Next steps

- Configure approval workflows so high-risk updates require human sign-off before publishing.
- Add more connectors (Notion, Jira, Zendesk) to broaden Velu’s context graph and improve automation coverage.
- Monitor Velu’s metrics dashboard to ensure goals such as automation rate, staleness, and coverage are trending toward the targets defined in the PRD.

By completing these steps, Velu AI becomes the continuously learning documentation brain for your organization—ready to deliver accurate content the moment your product evolves.
