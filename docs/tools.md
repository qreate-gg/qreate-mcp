# Qreate MCP tool reference

Catalogue inspected on 13 October 2026 through the authenticated Qreate connection. This documents the exposed client tools, not private API routes or the server implementation.

## Read and discover

| Tool | Purpose |
| :--- | :--- |
| `qreate_list_servers` | List the Discord servers the connected account administers. Obtain server identifiers here before server-specific calls. |
| `qreate_get_capabilities` | Read current supported change categories, module catalogue, execution flow and refused actions. |
| `qreate_get_server` | Read a server summary, including enabled modules and plan information. |
| `qreate_get_server_context` | Read the server summary, channels, roles and module state together before planning. |
| `qreate_get_channels` | List channels, identifiers, types and categories. |
| `qreate_get_roles` | List roles, identifiers, positions and whether an integration manages them. |
| `qreate_get_modules` | List modules and whether each is enabled, disabled or unconfigured on the selected server. |
| `qreate_get_module_config` | Read the selected module's current settings. |
| `qreate_get_recipes` | List the available ready-made server templates. |
| `qreate_get_run` | Read a planning run, including its pending question and question revision. |
| `qreate_list_runs` | List recent planning runs and their states for the server. |

## Prepare without applying

| Tool | Purpose |
| :--- | :--- |
| `qreate_plan_setup` | Turn a request into a concrete plan, or ask for information needed to complete it. |
| `qreate_answer_plan_question` | Answer the question in an existing run, preserving its context. Use the returned question revision. |
| `qreate_preview_plan` | Read the stored plan's field-by-field changes for review. |
| `qreate_plan_recipe` | Preview the channels, roles and module setup for a chosen template. |
| `qreate_preview_message` | Prepare a standalone channel message, optionally with an embed and link buttons. |

Planning and drafting do not apply Discord changes or publish messages.

## Execute with explicit approval

| Tool | Purpose and boundary |
| :--- | :--- |
| `qreate_apply_plan` | Apply the stored plan the user reviewed and approved. Refuses stale plans. |
| `qreate_apply_recipe` | Apply a template after its setup has been previewed and approved. Matching existing channels and roles are reused. |
| `qreate_publish_message` | Publish the reviewed draft using its draft identifier and preview hash. Reusing a published draft does not post twice. |
| `qreate_undo_changes` | Reverse an applied batch by its returned batch identifier. This changes the live server and requires user approval. |

Undo operates on Qreate change batches. It is not a promise that any Discord action or published message can be reversed.

## Current module catalogue

The capability response lists 36 modules. A catalogue entry describes a Qreate module; it does not imply a dedicated MCP tool for every operation inside that module.

| Area | Modules |
| :--- | :--- |
| Onboarding and access | Welcome Messages, Auto Roles, Reaction Roles, Verification, Rules, Introductions |
| Support and operations | Ticket System, Forms & Applications, DM Log, Logging, Moderation, Platform Notifications |
| Engagement | Birthdays, Leveling System, Reputation, Giveaways, Suggestions, Starboard, Polls, Events, Achievements, Supporters, Invite competition, Member Count Trackers |
| Workflows and publishing | Automations, Reminders, Scheduled Messages, Custom Commands, Briefings |
| Games and voice | LFG System, Temp Channels, Shop, Challenges, Trade Calls |
| Feeds and links | Qonnect, Link Cards |

## Unsupported client actions

The live capability contract refuses deletion of channels, roles, messages and records; member bans, kicks and timeouts; and changes to Qreate's authority. Use the Qreate dashboard or Discord for operations outside the exposed MCP contract.

Use live tool discovery and `qreate_get_capabilities` as the authority when this reference and a future server version differ.
