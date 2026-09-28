---
title: Migrating Data into Arctos
authors: Teresa J. Mayfield-Meyer, Erica R. Krimmel
date_updated: 2026-07-31
status: draft
redirect_from:
  - /how_to/data_migration.html
  - /how_to/data_migration/
---

How data are migrated to Arctos depends on the state of the existing collection data as well as the size and scope of the collection. Arctos staff can provide a basic assessment for prospective collections on how simple or complex their data migration may be. That said, all data migrations require dedicated time from both Arctos and the staff at incoming collections. For more complex migrations, institutions should consider how to account for work related to data migration regardless of whether that work is performed by Arctos staff or by staff within the institution.

Data migration is centered on Catalog Records, since these are the primary form of record-keeping for collection objects in Arctos. There are two main ways to create Catalog Records in Arctos: via the Data Entry interface or via Bulkloading.

**Data Entry interface:** For collections coming into Arctos with little to no data in a digital format, the Data Entry interface can be used to create one catalog record at a time. This interface is based on a customizable form, and uses existing data authorities and code tables to populate values for geography, taxonomy, agents, attribute types, and part names. The advantage of entering data using this form is that it requires minimal knowledge about how data are structured in Arctos. The disadvantage is that data entry is slower because the records are entered one at a time. However, the process can be sped up by customizing the form. Note also that certain data must already exist in Arctos to populate single record data entry. This includes [selection of code table terms in Manage Collection]({% link _best_practices/data-migration.markdown %}#collection-level-metadata), [setting up Operators to work in your collection]({% link _best_practices/data-migration.markdown %}#user-management), and creation of necessary [Agents]({% link _best_practices/data-migration.markdown %}#migrate-agent-data), [Accessions]({% link _best_practices/data-migration.markdown %}#migrate-accession-data), [Taxonomy]({% link _best_practices/data-migration.markdown %}#XXX), and [Higher Geography]({% link _best_practices/data-migration.markdown %}#XXX).

_See also [How To Enter Data for a Single Record](/how_to/enter-data-for-a-single-record)._

**Bulkloading data:** For collections coming into Arctos with existing data in a digital format, e.g. from another database or in spreadsheets, bulkloading data into Arctos will likely be more efficient. To do so, there are a suite of Arctos tools (“bulkloaders”) that share a common structure and can use CSV-formatted data to batch create most types of records (e.g. catalog records, agents, localities, events, taxonomy, etc.). The bulkloader for Catalog Records can also create data related to parts, localities, and events. Formatting CSV files for bulkloading involves using the correct column headings, as well as the correct values for data controlled by authorities and code tables. The advantage of bulkloading data is that a large number of records can be created at once. The disadvantage is that there is more of a learning curve, and that bulkloading requires knowledge about how Arctos data are structured.

_See also documentation for the [Bulkloader](/documentation/bulkloader), [Bulkloader Field Documentation](https://docs.google.com/spreadsheets/d/1VbNC3k17WAHMum_qD5UYoXxUUWwXXh5gZSM5vfGvRzU/edit?usp=sharing) and [How to Bulkload Catalog Records](/how_to/bulkload-catalog-records)._

## Overview

In general, the data migration process has a standard sequence of events (see diagram below) as well as an iterative nature. Within that process, each incoming collection will have unique needs. Arctos works with incoming collections to document such needs via a Data Migration Plan. 

**---INSERT A DIAGRAM?---**

### People involved

Data migration is a collaboration between Arctos and the incoming collection(s). Even the simplest migration involves onboarding new Arctos users and setting up collection metadata and preferences. The following roles typically participate in migration:
- The **Arctos Director** finalizes the initial onboarding of a new collection and kicks off the data migration process.
- The **Data Migration Specialist** is an Arctos staff member who works closely with the incoming collection(s) to identify pain points and future road blocks for the migration project.
- A **Collections Manager, Curator**, or similar position at the new member institution is ultimately responsible for the success of their data migration. This person should be familiar with any existing legacy data, have access and authority to make data decisions on behalf of the incoming collection(s), and have time available to devote to the migration process.
- The **Arctos Programmer** is an Arctos staff member who is responsible for database development and other technical tasks, and who may be consulted during migration if the incoming data have unique needs.
- Members of the **[Arctos Working Group](https://arctosdb.org/contacts/)**, especially Officers, may participate as mentors for the incoming collection. Arctos staff can make recommendations about mentorship.

### Project management

Arctos uses Google Drive and GitHub as project management tools. It is important that staff from incoming collection(s) have accounts they can use for both Google and GitHub. Google Drive is a shared workspace for documents, both archiving documents exchanged between the incoming collection(s) and Arctos staff, and collaborating on active working documents like data formatted for bulkloaders. GitHub issues facilitate task management, and GitHub projects provide a helpful visualization of work to do. Beyond the scope of data migration, GitHub is also an important tool for asking questions and receiving help from Arctos staff and community both during data migration and as an ongoing Arctos user.

For each incoming data migration project, the following resources will be set up:
1. A folder for the member institution in the Data Migration directory of the Arctos Working Group Google Drive. This folder should be named with the institution code (e.g. “UCM”) and shared with the relevant collection contact(s).
1. A Data Migration Plan as a Google Document in the Arctos Working Group Google Drive folder created above. The plan will be completed by the Data Migration Specialist in collaboration with staff from the incoming collection(s). A [template](https://docs.google.com/document/d/1mbHQj6jBrfvh72UC_QJgV091hG3MXnRmU0REezE63EA/edit?usp=drive_link) exists to use as a starting place.
1. A GitHub project in the [Arctos Github Organization](https://github.com/orgs/ArctosDB/projects) for the member institution, using the [Onboarding and Data Migration project template](https://github.com/orgs/ArctosDB/projects/225).

Arctos has a [private GitHub repository designated for data migration issues](https://github.com/ArctosDB/data-migration). Access to this repo is restricted to Arctos members. This means files or information exchanged here are not publicly available, so collections can be less concerned about accidentally sharing sensitive or in-progress data. GitHub issues in this repository help with task management during data migration, and issue templates are available to streamline the process. GitHub issues and projects are optionally available as project management tools to any Arctos member, and essential for incoming collection(s) using Arctos staff (e.g. Data Migration Specialist) or community mentors to support their data migration.

_See also [How to Get Started in Github for Arctos](/how_to/use-github-for-Arctos) and [How to Create and Manage Github Issues for Arctos](/how_to/use-issues-in-Arctos)._

{% include task.html content="If you are a new Arctos user, you will typically be assigned a GitHub issue to [Set up your GitHub for Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/admin-set-up-github.md)" %}

## Prepare for migration

The [Arctos Handbook](https://handbook.arctosdb.org/) and the [Learn Arctos](https://arctosdb.org/learn/) page of the website are the best places to begin learning how to use Arctos. In addition to reading and exploring independently, ask questions! Data Migration Specialists, other Arctos staff, and members of the community are all here to support new users.

_See also documentation on [Sharing Data and Resources](/documentation/sharing-data-and-resources) and [Understanding Cataloged Items](/documentation/catalog#understanding-cataloged-items)._

{% include task.html content="If you are a new Arctos user, you will typically be assigned a GitHub issue to [Learn about shared data in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/prepare-shared-data.md)" %}

### Collection-level metadata

Administrative metadata about collections is presented on the [Arctos Collections](https://arctos.database.museum/home.cfm) page in the detail view for each entry. Some metadata is required, and this is included in the initial request to create a new collection. Staff from a collection can edit both required and additional metadata via the [Manage Collection](https://arctos.database.museum/Admin/Collection.cfm) tool. At bare minimum, new collections should add a logo, ensure that all their contacts are correct, and pick authority (Code Table) values to make available to their records.

_See also [How to Manage Collection Metadata](/how_to/manage-collection-metadata) and [How to Apply Licensing and Terms](/how_to/apply-licensing-and-terms)._

{% include task.html content="You will be assigned one or more GitHub issues to [Review and complete collection metadata record(s)](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/prepare-collection-metadata.md), depending on how many collections you are setting up" %}

### User management

Arctos users who need access to edit data in your collection are called “operators.” Operators can be assigned permission for working (1) in specific collections, and (2) with specific types of data.

_See also [How To Create and Manage Your Arctos Team: Users and Operators](/how_to/create-your-arctos-team-users-and-operators)._

{% include task.html content="At least one person at every Arctos institution should understand how to invite new users to become operators, grant permissions to operators, and manage operator access to their collections. Anyone who should be given this permission will be assigned a GitHub issue to [Learn about user management in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/prepare-user-management.md)." %}

### Data crosswalk

## Migrate Transactions

Transactions in Arctos include accessions, loans, borrows and permits. All Arctos records require an associated accession. If your institution does not currently use accessions, at least one "legacy accession" will need to be created to facilitate entry of catalog records into Arctos. Legacy accession data can be entered individually or created in bulk, depending on how many legacy records exist.

_See also: documentation for [Transactions](/documentation/transactions) and [Accessions](/documentation/accession), [How to Create an Accession](/how_to/create-an-accession), and [How to Bulkload Accessions](/how_to/bulkload-accessions)._

Permits and loans can also be migrated into Arctos, depending on the preference of the incoming collection. Permits may be associated with accessions, and if so, they should be added first so that they can more easily be associated with the accession records being migrated. If existing loans are to be migrated, it is generally best to wait until catalog records are already in Arctos. Legacy loans can be added most efficiently using the bulkload process.

_See also: documentation for [Permits](/documentation/permits) and [Loans](/documentation/loans), [How to Create and Edit Permits](/how_to/create-a-permit), [How to Create a New Loan](/how_to/create-a-new-loan), and [How to Bulkload Loans](/how_to/bulkload-legacy-loans)._

{% include task.html content="At least one person at every Arctos institution should have permission to manage Transactions. Anyone who should be given this permission will be assigned a GitHub issue to [Learn about Transactions in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/transactions-learn-permission.md)." %}

## Reconcile and prepare data

### Agents

Agents in Arctos are people, organizations, groups, code, or any human entity that performs actions.  They are recorded in every area of collections management, thus need to be the first data entered into Arctos. Migrating agents can be very time intensive, but the payoff is having detailed concepts for people and organizations that provide appropriate credit for their actions and a basis for trust. Agents may be added individually or in bulk, but either way a diligent effort should be made to ensure that duplicate agents are minimized and any new Agents include enough information to disambiguate them from anyone with a similar name. Agents are a shared resource in Arctos; familiarize yourself and follow our [best practices for Creating Meaningful Agents]({% link _best_practices/agents.markdown %}).

{% include task.html content="At least one person at every Arctos institution should have permission to manage Agents. Anyone who should be given this permission will be assigned a GitHub issue to [Learn about Agents in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/agents-learn-permission.md)." %}

#### Find and tidy Agents in legacy data

Data migration generally will require the addition of many Agents, which is better accomplished in bulk. Create a list of all people and organizations included in the data to be migrated–pull from fields for collectors, preparators, determiners, donors, publication authors, etc. Aggregating all Agent names into a single list will allow you to disambiguate, merge, and tidy your Agent names once versus duplicating these steps for multiple fields.

Once you have a single list of names, review it for duplicates (e.g. alternate spellings of the same name, or versions of "unknown"). Try to make each name as complete as possible. Don't lose the original spellings/abbreviations as you will need to ensure they are either part of an Agent or are modified in your data to match an Agent name before you load your data.

Include any disambiguating information available, such as birth and death dates, addresses (including Wikidata, ORCiD, and Library of Congress), and relationships to other agents.

Arctos has the following tools to help you prepare your data:
- [Agent: Deconcatenator](https://arctos.database.museum/DataServices/agent_splitter.cfm) will attempt to separate multi-agent strings (e.g. "Jim Smith and John Doe") into individual Agents; it is almost always necessary to spend time manually reviewing and correcting the results before proceeding.
- [Agent: Format Namestring](https://arctos.database.museum/DataServices/split_agent_namestring.cfm) will attempt to transform the format of individual Agent names into Arctos' preferred (and sometimes required) format.
- [Agent: Name Splitter](https://arctos.database.museum/loaders/agentNameSplitter.cfm) will help build the file required for bulkloading.

Use the Agent PreBulkload tool to help make decisions about which names in your list need to be added to Arctos Agents, which may require addition of information to an existing agent, and which might be better represented as a verbatim agent.

"Repatriation" - pushing cleaned versions of Agents back to the original (usually catalog record) data - will be necessary at multiple points in this process. The Pre-Bulkloader has tools to facilitate some of these, but others will be manual. Those using this process are expected to have the tools and knowledge to accomplish this, or to work closely with someone who does. A great deal of problems are caused by losing the ability to repatriate - the file being actively updated should always contain data which can be used to link the changed data back to the original.

To modify a few existing agent agents, simply use the Arctos forms. For example, if you have "Some Random Agent" and "Some R. Agent" has been suggested, you could simply locate the "Some R. Agent" record in Arctos and modify it as necessary. Arctos loads records against all available data, so a new catalog record containing "Some Random Agent" will load to "Some R. Agent" as long as "Some R. Agent" contains alternate name (aka) "Some Random Agent" AND there are no other uses of "Some Random Agent" in any other agent profile.

### Identifications

Taxonomic names in Arctos are a shared resource controlled by a [code table](https://arctos.database.museum/taxonomy.cfm). Data migration generally will require the addition of many taxon names which is better accomplished in bulk. Create a list of all scientific names used to identify your specimens. This list should be in a single column of an Excel spreadsheet with the column header **scientific_name** and saved as a CSV. Review the list for alternate spellings and versions of "unidentifiable". Try to make each name as complete as possible and to ensure that there are no duplicates. Don't lose the original spellings/abbreviations as you will need to ensure they are modified in your data to match a Taxon name before data migration.

Isolate the names that FAIL in the results from the [Taxon Name Checker](https://arctos.database.museum/loaders/taxon_name_check.cfm) and use the [GlobalNames Verifier](https://verifier.globalnames.org/) to help determine if they are names you should add to Arctos or if they are names that need to be corrected in your data. For names that need to be added, use the [Taxon Name: Bulkload Tool](https://arctos.database.museum/loaders/BulkloadTaxonomy.cfm) to add them. This allows you to use the names, but does not provide related classifications to continue with that see the Classifications step.

{% include tip.html content="See also [How to Edit Taxon Records](/how_to/edit-taxa), [How to Create Linnaean Taxa](/how_to/create-taxa), and the documentation for [Taxonomy](/documentation/taxonomy)" %}

{% include task.html content="At least one person at every Arctos institution should have permission to manage Taxonomy. Anyone who should be given this permission will be assigned a GitHub issue to [Learn about Taxonomy in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/taxonomy-learn-permission.md)." %}

#### Classifications

For any names that were added in the previous data migration step, there will not be a related classification in any of the local Arctos taxonomy sources. You can also check after records have been loaded using [Tools Directory > Data Quality > Taxonomy: Find Gaps](https://arctos.database.museum/Reports/flat_taxonomy_gap.cfm) to see if you have any identifications without a related classification.

For a small number of new names, these can be created manually. To create a large number of classifications, use the [Classification: Bulkload Tool](http://arctos.database.museum/tools/BulkloadClassification.cfm).

{% include tip.html content="See also [How to Manage Taxonomic Classifications](/how_to/manage-taxonomic-classifications)" %}

### Places and events

#### Higher Geography

Higher geography is a combination of terms delineating geopolitical and physical units on the surface of the Earth and is controlled by a [code table](https://arctos.database.museum/place.cfm?sch=geog). To ensure that your data will load properly, it is important to make sure that higher geography is extracted from locality as HIGHER_GEOG in your migration data and that it matches values in the code table. If you need new terms added, contact your mentor or post issues to GitHub.

https://arctos.database.museum/DataServices/geog_lookup.cfm

{% include tip.html content="See also the documentation for [Higher Geography](/documentation/higher-geography)" %}

#### Localities

Localities are a shared resource in Arctos. Always be cautious if a locality applies to specimens outside of your collection and make sure that any edits to a shared locality are discussed with sharing collections.

Every object record is required to be assigned a locality (place of collection). Localities include coordinates used for mapping.
Localities may be treated in several different ways.  
1. If you have many specimens from a single specific locality, you may want to manually create that locality and use the locality id in your bulkload file.
1. You can also bulkload your data with the localities you have entered, but beware, localities that are exactly alike should load as a single locality shared by many specimens, but just one little difference (a capital letter or period, for example) will create two localities when you think there is only one.  These can be merged later, if you find them.

In some cases, it may be beneficial to migrate locality data before catalog records. For example, if a collection uses standard or named localities or wishes to encumber locality information. If this seems like a better path for the data, you may wish to explore the [Bulkload Locality Tool](https://arctos.database.museum/tools/bulkloadLocality.cfm).

Even if localities are not created in advance, it may pay to review the localities that are associated with incoming data in order to standardize them. This could mean re-ordering information so that two currently different localities are now the same:

Austin, 10th and Main
10th and Main, Austin

OR

City of Austin
Austin

In addition, much of the information in a single “field” in the data to be migrated may actually perform better if parsed into [locality attributes](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctlocality_attribute_type) and/or individual locality fields:

- township, section, range and aliquot
- chronostratigraphic terms
- lithostratigraphic terms
- elevation
- depth

Finally, cleaning up specific locality is encouraged:

- standardize [city name], "city of" vs. "within"
- remove abbreviations, or standardize them: Rd, St, Ave, Blvd, Wy, Hwy, Rte, mi, km, ft, m, yds
- use decimals for distances (e.g. 1.5 mi vs 1 1/2 mi)
- add context (e.g. N/S/E/W of ___ vs N)
- Remove non-printing or extraneous characters (e.g. �)

{% include tip.html content="See also [How to Understand the Arctos Locality Model](/how_to/understand-the-arctos-locality-model), [How to Create a Locality](/how_to/create-a-locality), and the documentation for [Locality](/documentation/locality)" %}

{% include task.html content="At least one person at every Arctos institution should have permission to manage Localities. Anyone who should be given this permission will be assigned a GitHub issue to [Learn about Localities in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/locality-learn-permission.md)." %}

### Parts

Part names, record attributes, part attributes and locality attributes along with other data recorded in Arctos are controlled by code tables. Any of these types of data that are represented in the data to be migrated need to be mapped to terms in the appropriate Arctos code table. If you need new terms added, contact your mentor or post issues to GitHub.

Part (object descriptions) names must match to the available parts vocabulary in Arctos. Each collection type has a unique set of available part names. If you need to add a part name, you will need to request it and provide a definition for the part.

Attributes must match to the available attributes in Arctos. Each collection type has a unique set of available attributes. If you need to add an attribute, you will need to request it and possibly provide a controlled vocabulary for the attribute value (for example, sex is the attribute, with possible values of male, female, etc.).

### Catalog record attributes

### Object tracking
Object tracking is a powerful tool that allows Arctos collections to track the physical location of parts. Planning for object tracking before migration  is encouraged, however, object tracking can be established at any time. 

{% include tip.html content="See also [How to Start Object Tracking](/how_to/start-object-tracking), [How to Create and Edit Containers](/how_to/create-and-edit-containers), and the documentation for [Container](/documentation/container)" %}

{% include task.html content="At least one person at every Arctos institution should have permission to manage Containers. Anyone who should be given this permission will be assigned a GitHub issue to [Learn about Localities in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/locality-learn-permission.md)." %}

## Migrate catalog records
Once your data has been tidied and matched to Arctos Code Tables and other resources, you can build a bulkload file.

https://arctos.database.museum/Bulkloader/bulkloaderBuilder.cfm

{% include tip.html content="See also [How to Bulkload Catalog Records](/how_to/bulkload-catalog-records)" %}

## Migrate Media

{% include tip.html content="See also [How to Create Media](/how_to/create-media-images), and the documentation for [Media](/documentation/media)" %}

{% include task.html content="At least one person at every Arctos institution should have permission to manage Media. Anyone who should be given this permission will be assigned a GitHub issue to [Learn about Media in Arctos](https://github.com/ArctosDB/data-migration/blob/master/.github/ISSUE_TEMPLATE/locality-learn-permission.md)." %}


## Publish to data aggregators
Once your records are in Arctos, you may wish to publish them to the Global Biodiversity Information Facility (GBIF) or the Global Genome Biodiversity Network (GGBN).

