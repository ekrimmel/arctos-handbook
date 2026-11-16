---
title: Create and Manage Your Arctos Team
authors: Teresa J. Mayfield-Meyer, Shannen Robson, Michelle Koo, Erica Krimmel
date_updated: 2026-11-16
redirect_from:
  - /how_to/How-to-Create-your-Arctos-Team-Users-and-Operators.html
  - /how_to/How-to-Create-your-Arctos-Team-Users-and-Operators/
  - /how_to/how-to-create-your-arctos-team-users-and-operators.html
  - /how_to/how-to-create-your-arctos-team-users-and-operators/
---

This guide describes how to manage Arctos access for your team of staff, students, and/or volunteers who assist with data entry or other collection data management tasks.

Anyone can have an Arctos **user account**, which is needed to view and download data in Arctos. Users log into Arctos via a local account that they create on [https://arctos.database.museum](https://arctos.database.museum), or via an existing GitHub or Google account that Arctos uses to authenticate them. **Operators** are special users who are granted permissions to edit data and/or access data normally hidden from the public. Because some types of data (e.g. taxonomy, media, agents, places) are shared among collections, Operators who have access to these types of data must fully understand that Arctos is a shared system, and must always consider the implications of working in a shared system. When you are logged in as an Operator, you only have access to shared data and data from the collections you have permissions for. This means that it makes sense for Operators to also have a separate Arctos user account to view data across all Arctos collections.

## Tasks for new users

If you are new to Arctos, or newly in a role where you will have access to edit data in Arctos, you need to become an Arctos Operator. To do so, follow these instructions:

1. **Create a TACC user account**. [Check if you already have one here](https://accounts.tacc.utexas.edu/login); if not, then create a new account at [https://accounts.tacc.utexas.edu/register](https://accounts.tacc.utexas.edu/register). Note that your affiliation and email address should be those associated with an Arctos institutional member.
1. **Log into Arctos using the "Log in with TACC" button** and credentials for your newly created account. This creates a new Arctos account with your TACC credentials.
1. **Add your preferred email to your Arctos profile**. Arctos sends notifications to Operators via email, and it does not need to use the same email as the one associated with your TACC account. Go to your Arctos account profile (click _Profile_ in the top right menu) and add your preferred email address, even if it is the same as what you used with TACC.
1. **Create a GitHub account** if you expect to do more than basic data entry and don’t already have one. See [How To Create A GitHub Account]({% link _how_to/use-github-for-arctos.markdown %}).
1. **Tell your Arctos manager your TACC and GitHub usernames**. Your Arctos manager is the person authorized to grant Operator permissions for the collection you work with. Depending on the circumstance, this may be your supervisor, a colleague, or an Arctos staff member. If you are unsure whether you need a GitHub account, start by telling your Arctos manager your TACC username; your GitHub account can always be linked later.

### TACC tips

Following TACC's security policies keeps Arctos database operations safe! See TACC [account documentation](https://docs.tacc.utexas.edu/basics/accounts/) for troubleshooting common problems. In particular, see TACC's [limitations on email addresses](https://docs.tacc.utexas.edu/basics/accounts/#newaccounts). Before requesting additional help, ensure that you can [log in to your TACC account](https://accounts.tacc.utexas.edu/login?redirect_url=profile), and that multi-factor authentication is enabled in your account.

Other helpful links include:
 -[Reset Password](https://accounts.tacc.utexas.edu/forgot_password)
 -[Find your username](https://accounts.tacc.utexas.edu/forgot_username)
 -[TACC login support](https://accounts.tacc.utexas.edu/login_support)

## Tasks for Arctos managers

In this context, Arctos managers are people authorized to grant Operator permissions for one or more Arctos collections, e.g. a Collection Manager or Curator at an Arctos member institution. These people have the `manage_collection` role assigned to their Operator account, and should be listed as one of the contacts on the Arctos collection. It is important to have someone from the member institution actively managing access to Arctos collection(s), because Arctos staff can't always tell who should or should not be given permissions. The following sections describe common tasks for Arctos managers.

### Create a new Arctos Operator

If you have someone new to Arctos, or newly in a role where they need access to edit data in Arctos, you need to make them an Arctos Operator. First, have the new person follow the instructions above in [Tasks for new users](#tasks-for-new-users), then:

1. **Ensure the new Operator has an Arctos Agent record**. [Search to find an existing Agent record](https://arctos.database.museum/agent.cfm), or follow the instructions on [How to Create Agents]({% link _how_to/create-agents.markdown %}) if no record exists yet. Make sure that the Agent record has a valid email address attribute and, if relevant, GitHub identifier attribute.
1. **Link the Agent to the Operator account**. Go to [Tools Directory > Agents & Users > Operator: Manage](https://arctos.database.museum/AdminUsers.cfm) and enter the TACC username given to you by the user, then click "edit" next to the search result where the authentication is listed as "TACC OAuth." On the next interface, click "add Agent" to search for and attach the correct Arctos Agent record.
1. **Invite Operator**. Under the section of the interface labeled "Database User Status," click the button to "Invite Operator"; note that this button will not appear if a valid email address is not present in the user's Arctos profile (see step 3 in [Tasks for new users](#tasks-for-new-users)). Doing so will send the user an email notification.

### Assign Operator permissions

Once you have created an Operator, they need permissions. There are two categories of permissions: (1) permission to work with data for specific collections, and (2) permission to work with specific types of data. For example, an Operator with permissions for `UAM:Mamm` and `data_entry` can only enter basic catalog record data for the UAM:Mamm collection. To assign permissions:

1. In the green box at the bottom of the _Manage Operator_ interface, click "enable user management" and a table will appear. Permissions for roles are listed on the left and for collections on the right.
1. Choose the collection you want to grant this Operator access to and click the "Grant Access" button. The collection you selected and a "revoke" button will appear below. To grant access to another collection, repeat the process.
1. Choose the roles you want this Operator to have by selecting from the dropdown list and clicking "Grant Role." If you want to grant more than one role, repeat the process. All Operators should be assigned the `coldfusion_user` role. Any Operator can assign permissions that they have to any other Operator, which means that it is important to understand the power you are granting! [Read the role definitions before assigning roles](https://arctos.database.museum/Admin/user_roles.cfm).
1. Before the Operator can make full use of Arctos as you have assigned, they will need to log out of Arctos and log in again. Remind them that when logged in as an Operator, they will only see the collections to which they have access. To view data for more than those collections, they will need to search while logged in under a user account (local, GitHub, or Google).

#### Recommended reading for various permissions

Operators need to understand the implications of the permissions they are granted, and to that end, we recommending reading Handbook pages related to the various roles. During the data migration process, Arctos staff typically use GitHub issues to assign readings to incoming users and document that they understand the implications of the permissions being granted. If you have access to the [data-migration repository on GitHub](https://github.com/ArctosDB/data-migration/issues) and find it helpful, you are welcome to use the same issue templates to assign readings to your own team members. Otherwise, the list of recommended readings is here:

Role | Recommended reading
--- | ---
`data_entry`, `manage_specimens`, `manage_records` | (1) [Sharing Data and Resources]({% link _documentation/sharing-data-and-resources.markdown %}), (2) [Understanding Cataloged Items]({% link _documentation/catalog.markdown %}#understanding-cataloged-items)
`manage_transactions` | (1) documentation for [Transactions]({% link _documentation/transactions.markdown %}), (2) documentation for [Accessions]({% link _documentation/accession.markdown %}), (3) [How to Create an Accession]({% link _how_to/create-an-accession.markdown %}), (4) documentation for [Permits]({% link _documentation/permits.markdown %}), (5) [How to Create and Edit Permits]({% link _how_to/create-a-permit.markdown %}), (6) documentation for [Loans]({% link _documentation/loans.markdown %}), (7) [How to Create a New Loan]({% link _how_to/create-a-new-loan.markdown %})
`manage_publications` | (1) documentation for [Publications]({% link _documentation/publications.markdown %}), (2) [How to Create a Publication]({% link _how_to/create-a-publication.markdown %})
`manage_agents` | (1) documentation for [Agents]({% link _documentation/agent.markdown %}), (2) [Creating Meaningful Agents]({% link _best_practices/agents.markdown %}), (3) [How to Create Agents]({% link _how_to/create-agents.markdown %})
`manage_taxonomy` | (1) documentation for [Taxonomy]({% link _documentation/taxonomy.markdown %}), (2) [How to Edit Taxon Records]({% link _how_to/edit-taxa.markdown %}), (3) [How to Manage Taxonomic Classifications]({% link _how_to/manage-taxonomic-classifications.markdown %}), (4) [How to Create Linnaean Taxa]({% link _how_to/create-taxa.markdown %})
`manage_locality` | (1) documentation for [Higher Geography]({% link _documentation/higher-geography.markdown %}), (2) documentation for [Locality]({% link _documentation/locality.markdown %}), (3) [How to Understand the Arctos Locality Model]({% link _how_to/understand-the-arctos-locality-model.markdown %}), (4) [How to Create a Locality]({% link _how_to/create-a-locality.markdown %}), (5) [How to Create a New Collecting Event for a Locality]({% link _how_to/create-a-new-collecting-event-for-a-locality.markdown %})
`view_container`, `update_container`, `manage_container` | (1) documentation for [Container]({% link _documentation/container.markdown %}), (2) [How to Start Object Tracking]({% link _how_to/start-object-tracking.markdown %}), (3) [How to Create and Edit Containers]({% link _how_to/create-and-edit-containers.markdown %})
`manage_media` | (1) documentation for [Media]({% link _documentation/media.markdown %}), (2) [How to Create Media]({% link _how_to/create-media-images.markdown %})

### Periodically review access

It is a good idea to periodically review who has access to do what for the collections you manage in Arctos. To review, go to [Tools Directory > Internal Settings > Manage Collection](https://arctos.database.museum/Admin/Collection.cfm) and:

1. Select your collection's GUID prefix in the dropdown menu, then click the "Go" button.
1. Scroll down to the bottom of the _Manage Collection_ interface to the "Collection Operator Summary" section.
1. Review each of the entries in the list of Operators.
1. Click on any username to manage that user's operator status and add/remove permissions.

#### Locking and unlocking Operator accounts

When a member of your Arctos team leaves, **DO NOT** delete or alter the account or the user's Agent login name. Doing so will destroy their edit history and may have other unintended consequences. Instead, click on "Lock Account" in the [_Manage Operator_](https://arctos.database.museum/AdminUsers.cfm) interface. Doing this avoids the possibility of accidental or intentional data editing, while preserving the user's ability to be re-activated as an Arctos Operator in the future (e.g. if they later work at another collection that uses Arctos). Users whose accounts have been locked will not be able to log into Arctos. You can unlock an account by clicking on "unlock account" under the section of the interface labeled "Database User Status." Operators whose accounts are unlocked will regain their previous permissions. Note that Operator accounts automatically lock after 6 months of inactivity, so you may need to regularly unlock accounts for faculty or other occasional users of your collections on Arctos.

{% include caution.html content="Do not unlock an account unless you are fully aware of the circumstances under which it was locked and are (or are in communication with) the 'supervisor' of all collections to which the user has access. Assume all unlock requests are phishing attacks until proven otherwise." %}