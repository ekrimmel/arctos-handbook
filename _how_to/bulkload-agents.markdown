---
title: Prepare Agents for Bulkloading
authors: Dusty L. McDonald, Teresa Mayfield-Meyer, Erica Krimmel
date_updated: 2026-08-04
redirect_from:
  - /how_to/How-to-Bulkload-Agents.html
  - /how_to/How-to-Bulkload-Agents/
  - /how_to/how-to-bulkload-agents.html
  - /how_to/how-to-bulkload-agents/
  - /how_to/How-to-deal-with-Agent-Bulkloader-results.html
  - /how_to/How-to-deal-with-Agent-Bulkloader-results/
  - /how_to/how-to-deal-with-agent-bulkloader-results.html
  - /how_to/how-to-deal-with-agent-bulkloader-results/
---

Before creating agents, any new agent name should be checked against existing agents in Arctos. For single agents, this can be done through an Agent Search. If you need to check a list of names, then the Agent Pre-Bulkload Tool will help you do this in bulk. This tool will only review agents; it will not add or modify existing agents.


### Use the pre-bulkloader

After careful review and any necessary correction of the above, it should be simple to create a file which will bulkload into Arctos. This should be loaded into the [Agent: Pre-Bulkload](https://arctos.database.museum/loaders/pre_bulkload_agents.cfm) tool.


The file should look something like this:

<img width="883" alt="Screen Shot 2021-10-15 at 10 21 56 AM" src="https://user-images.githubusercontent.com/5720791/137527996-47497dd2-bd89-4e1d-aee4-b7c74e0face4.png">

note the replacement of preferred name with the suggestion (don't forget to repatriate!) and the addition of agent_type.

Upload, read the directions, set to "autoload", download the CSV when status has changed.

<img width="1433" alt="Screen Shot 2021-10-15 at 10 23 59 AM" src="https://user-images.githubusercontent.com/5720791/137528261-74a8fb3f-25a3-48ca-8f6e-26cb5eb7dbcc.png">

Note that Arctos has detected "Angie" is probably a variant of "Angela" and suggested an existing Agent. This should be ** carefully** checked, and when correct:

1. Update the original data to use the preferred name from the existing Arctos agent, and 
2. Delete the agent from the upload file; it already exists, there's not need to do anything additional

Any "fatal" errors **must be** addressed at this time.

This process will often need repeated, and will often result in more mergers within the file. Don't lose your repatriation path!

## How to Interpret the Results

Once the Agent Prebulkloader has processed your agent list you will have a lot of information in the Status Column. Interpreting the statuses can be difficult. Below are some helpful hints for working with the various statuses.

**no problems detected**: This message can arise because both new and existing data are unambiguous, or because the input is nothing like any existing data in Arctos (e.g., because it's horribly mis-spelled!). The latter are deserving of further scrutiny.

**Check for abbreviations and acronyms. Do not create unnecessary variations of `unknown.`**: This is usually attached to low-information names and may usually be ignored, but check that eg., person agents are in fact persons and not groups or organizations.

**FATAL ERROR: duplicate of**: The exact string match of the agent already exists. If the agent seems like the same entity, the row can generally just be deleted - there's nothing to add, the specimens will successfully load against the existing data. If the duplicate seems like a new agent, email us (or use the contact link on any Arctos page) - these must be dealt with on a case-by-case basis.

**FATAL ERROR: {anything except duplicate of...}**: The problem should be clear from the status; fix and re-run.

**possible duplicate ....** - ideally check all of the suggestions in Arctos, make sure you're not creating duplicates, and flag any duplicates you do find. Realistically, check the things that look particularly suspicious. For example, if the new data contain "N. Wood" and a half-dozen "N. {some initial} Wood" agents exist, there will likely not be enough information to come to a defensible conclusion, and simply creating "N. Wood" may be a realistic choice. The situation may become more apparent when specimens are re-attached, at which time creating relationships ("bad duplicate of" or "not the same as") would be appropriate. A "Nathaniel Wood" being suggested as a duplicate of "Nathaniel {some initial} Wood" is much more likely to be a resolvable situation and deserves more scrutiny.

If duplicates exist within the file - for example, if "Some Random Agent" and "Some R. Agent" are on two rows and should be the same agent - simply add "Some R. Agent" as an "aka" name (using any available OTHER_NAME_n/OTHER_NAME_TYPE_n pair) of "Some Random Agent" and delete the "Some R. Agent" row (or vice-versa). This will create an agent with a preferred name of "Some Random Agent" and an AKA name of "Some R. Agent." 

Batch modifications are possible; consult with a DBA.

### Request Agent Bulkload

Agents are treated as authority data and the Agent Bulkloader requires the [manage_codetables](https://arctos.database.museum/Admin/user_roles.cfm#manage_codetables) role. Use results from the Agent Prebulkload tool to [request an Agent Bulkload](https://github.com/ArctosDB/arctos/issues/new?assignees=&labels=Function-Agents%2C+Priority-High+%28Needed+for+work%29&projects=&template=agent-bulkload-request.md&title=Agent+Bulkload+Request). The Agent Bulkload Tool accepts the same columns as the pre-bulkloader, and works like all component loaders. 

The data should be discussed with the users before proceeding. Most all data will have some "errors" from the pre-bulkloader; ensure that this are caused by missing data, and not withheld data. Ensure the user understands and has provided what's expected at this point.

Carefully review before proceeding.