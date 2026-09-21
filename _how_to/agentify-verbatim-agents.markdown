---
title: Agentify Verbatim Agents
authors: Teresa J. Mayfield-Meyer, Angela Linn, Erica R. Krimmel
date_updated: 2026-08-03
redirect_from:
  - /how_to/How-to-Agentify-Verbatim-Agents.html
  - /how_to/How-to-Agentify-Verbatim-Agents/
  - /how_to/how-to-agentify-verbatim-agents.html
  - /how_to/how-to-agentify-verbatim-agents/
---

"Agentifying" refers to the process of converting information about a person or organization that is currently only recorded in a [verbatim agent](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctattribute_type#verbatim_agent) attribute into a full Arctos Agent record. Doing so may be appropriate if you learn more about the person or organization and need a place to store this information independent of the Catalog record. Follow these steps to create a new Agent record from a verbatim agent, and connect the new Agent to Catalog records in the appropriate roles (e.g. collector, creator, preparator, subject, etc.).

{% include tip.html content="See also this related [video tutorial](https://www.youtube.com/watch?v=np1jQzi0f9Q)" %}

## Create the Agent record

Before creating a new Agent record, [search Arctos carefully]({% link _how_to/search-agents.markdown %}) to make sure that the entity your verbatim agent represents does not **already** exist in Arctos, then follow the instructions in [How To Create an Agent]({% link _how_to/create-agents.markdown %}).

## Connect the new Agent to Catalog records

### Find Catalog records with the verbatim agent

From the [main Catalog record search](https://arctos.database.museum/search.cfm), search the `verbatim agent` _Record Attribute_ for the verbatim agent namestring.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Agents/image7.png)

Alternatively, from any Catalog record with an existing attribute containing the verbatim agent, click the _Search_ button next to the attribute.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Agents/image3.png)

### Add the Agent to Catalog records

Either of the options above will bring you to the Catalog record search results interface. Find _Manage > Collectors_ under the _Tools_ menu:

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Agents/image6.png)

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Agents/image8.png)

Enter the `Preferred Name` of the Agent in the _Name_ field, then select the Agent role and list order. Click the _Insert Agent_ button to connect the Agent record to the Catalog records listed in this interface.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Agents/image9.png)

To confirm you did this step correctly, performing a new Catalog record search using the _Agents (collector)_ field instead of via verbatim agent attribute. You should get the same results.

## What to do with the verbatim agent attribute

After agentifying, you may feel inclined to discard the verbatim agent attribute because they seem redundant, but in most cases they provide good information about verbatim documentation and should be left in place. If they are truly redundant (i.e. the Agent name is exactly the same and not at all ambiguous), these attributes can be removed using the [Un-Bulkload Attributes tool](https://arctos.database.museum/loaders/BulkUnLoadAttribute.cfm). 

{% include caution.html content="The Un-Bulkload Attributes tool will unload ALL verbatim agent attributes from the records indicated in the tool. If any records contain verbatim agents other than the one you want to remove, you may want to check with a DBA to have them removed for you." %}
