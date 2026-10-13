# Qreate MCP usage examples

Replace the descriptive channel and role names in these prompts with your own. The assistant should resolve real identifiers from Qreate rather than inventing them.

## Understand the server

> List my servers. For the one I choose, read its channels, roles and module states, then summarize the current setup.

The assistant lists accessible servers, confirms the selected server and reads its context. This does not change Discord.

## Build onboarding around existing roles

> Read my server and plan a welcome message in the welcome channel. Reuse my existing Member role where appropriate. Show me the complete changes before applying anything.

The assistant reads context, prepares a setup plan and shows its preview. Missing details are answered in the same planning run. Only an explicit approval authorizes application.

## Prepare support

> Plan a ticket setup for this community. Check the current ticket configuration and staff roles first. Ask me what you need to know and show the final plan.

This is a request to the planner, not a promise of a particular panel configuration. The plan and the current capability contract determine the supported result.

## Set up an automation

> Plan an automation that posts “The community event is starting” in my event channel when my chosen trigger occurs. Ask me to specify the trigger and show the proposed rule.

Automation setup uses the planning flow. Creating the rule is different from publishing a standalone message now.

## Start from a template

> List the available Qreate server templates. Help me choose one and preview the channels, roles and module settings it would create.

Discover actual templates before choosing a recipe. Apply the selected template only after the user approves its preview.

## Draft an announcement

> Draft “Welcome to our new community!” for my announcements channel, with a link button to https://qreate.gg. Show the entire draft before sending.

Use `qreate_preview_message`, display the draft, then call `qreate_publish_message` only after approval. The Announcements module must be enabled. Mentions that should notify users belong in message content, not inside an embed.

## Continue work and reverse a batch

> Show my recent Qreate planning runs and resume the one waiting for my answer.

> Show the result of the setup you applied. I want to review reversing that change batch.

Read the specific run before answering its pending question. For reversal, use the batch identifier returned by the applied setup and obtain explicit approval. Do not infer that an announcement can be deleted through MCP.
