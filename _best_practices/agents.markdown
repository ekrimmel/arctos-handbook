---
title: Creating Meaningful Agents
authors: Teresa J. Mayfield-Meyer, Dusty L. McDonald, Erica R. Krimmel
date_updated: 2026-07-31
redirect_from:
 - /best_practices/Agents.html
 - /best_practices/Agents/
 - /best_practices/agents.html
 - /best_practices/agents/
---

Agents are people, organizations, groups, code, or any human entity that performs actions. This includes collectors, authors of publications, users of objects, issuers of identifiers and, if you enter or edit data, you are an Agent. A single Agent can have many roles and many names. No matter how many roles or names an Agent has, there should be only one Agent record in Arctos to represent them. Agent records are never deleted and the `agent_id` is permanent and stable, so you can reliably link to an Arctos Agent record via the URL, e.g. [https://arctos.database.museum/agent/21314876](https://arctos.database.museum/agent/21314876).

{% include caution.html content="Agents are shared by all Arctos members. Always use caution when creating or editing a shared resource and make sure that others who might be affected by a change are notified." %}

## Before creating a new Agent

### Consider whether you actually need an Agent

Agents should exist only when they carry independent information. The [verbatim agent](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctattribute_type#verbatim_agent) attribute is functionally similar to Agents, and should be used for linking low-information names to catalog records. Using `verbatim agent` may be an appropriate choice if the agent is relatively unknown, unlikely to become known, and has no or little other activity. For example, "fisherman" should always be a verbatim agent, but "G. Hope" may also be appropriate to enter as a verbatim agent if you are unlikely to discover any additional disambiguating information.

**---DESCRIBE WHERE VERBATIM AGENT DIFFERS, DwC export, no activity, reports---**

### Use the existing Agent for "unknown"
Arctos has an [Agent record for "unknown"](https://arctos.database.museum/agent/0) when the person or organization doing the collecting, identifying, borrowing, etc. is unknown or unclear. Do not create new Agents such as "Collector unknown" or "Determiner unknown." Consider using the [unknown](https://arctos.database.museum/agent/0) Agent along with the [verbatim agent](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctattribute_type#verbatim_agent) attribute rather than creating cryptic agents such as "A. B. C." or "S. Smith."

### Avoid duplicating Agents

No matter how many roles or alternate names a person or organization has, they should be represented by a single Agent record. Multiple Agent records that refer to the same entity make discovery difficult. Before new Agent records are created, [search Arctos carefully]({% link _how_to/search-agents.markdown %}) to check that the "new" Agent does not already exist. Some examples of things to look for include:

 - someone who may have married and is now known by both a birth name and a married name

 - non-English names that may exist in the database under alternative transliterations. For example, Felix Chernyavski’s name is published in English as Tchernyavski and Chernyavsky. In these cases, use the `aka` Agent attribute for name variants rather than creating additional Agents.

For legacy data, determining whether or not you would be creating a duplicate agent can be challenging. Are Robert Smith, R. Smith, and Bob Smith three agents or one? Sometimes, the activities already recorded for an Agent makes the answer clear; e.g., there were probably not two Eleazer Fitzgarrolds collecting grasshoppers in northern Madagascar in the 1930s. To see Agent activity, click on the _Show all Activity_ link from any Agent record. If you cannot determine whether or not your namestring is new or a duplicate Agent, use the existing Agent in Arctos. Having multiple Agents collecting under the name "R. Smith" doesn’t affect any conceivable use of the data, and if one of the R. Smiths distinguishes themselves somehow, a new Agent can be created then.

When you create a new or edit an existing Agent record, provide as much information as possible to help avoid duplicate Agents in the future. If you find duplicate Agent records, don't orphan them! Flag them by creating a `bad duplicate of` relationship to the preferred Agent record so that the duplicate Agent will be hidden. Any other types of records attached to the bad duplicate should be updated to the preferred Agent.

## Preferred name

`Preferred Name` is the namestring displayed for an Agent by default. It is also used in various Arctos data entry interfaces as a shortcut to point the database at an Agent record, e.g. when entering information about the collector or the determiner of an identification. `Preferred Name` does not need to be unique within Arctos.

The following guidelines apply to preferred names:
- Use the most complete name possible. For people, format as "First Middle Last" as a matter of convention for Western names. Exceptions to this convention should be made according to cultural preferences or at the request of the individual represented by the Agent record.
- Follow Wikipedia for the `Preferred Name` of non-person Agents. See for example https://en.wikipedia.org/wiki/United_States_Fish_and_Wildlife_Service, which should be entered in Arctos as "United States Fish and Wildlife Service."
- Follow abbreviations in `Preferred Name` with a period and space, e.g. "J. J. Smith" never "JJ Smith" or "J J Smith." If nonstandard data are important search terms, include them as `aka` attributes. 
- Do not use extraneous spaces, nonprinting characters, or (for person Agents) commas in `Preferred Name`.
- Consider only including prefix, suffix, title, etc. in `aka` attributes so that the `Preferred Name` does not change over time. For example, if "John Smith" has a son and becomes "John Smith Senior," and then "John Smith Junior" has a son and becomes "John Smith II," or if "Captain John Smith" gets promoted to "Major John Smith." If you must create a `Preferred Name` with a prefix or suffix, ensure the bare name exists as an `aka`.
- Don't include parenthetical information in `Preferred Name`. If the parenthetical is descriptive, use an Agent attribute instead, e.g. "Ken Green (Ohio)" should be "Ken Green" with a `correspondence address` attribute of "Ohio." The value of `Preferred Name` formerly had to be unique within Arctos but that is no longer true.
- Avoid abbreviations. For example, "Co." has multiple meanings whereas "Company" is unambiguous, and "John J. Smith" is more ambiguous than "John Johnson Smith." If you do abbreviate, include an unabbreviated equivalent, e.g. via an `aka` attribute. There are a few exceptions for common abbreviations:
    - "St." is acceptable as part of a `Preferred Name` when that is the convention for spelling the name, e.g. "Althea St. Martin." Note, do not use "St." to abbreviate a name with "Saint."
    - "Mrs." is acceptable at the beginning of a `Preferred Name` when no further information is available, e.g. "Mrs. Hendershaw."
    - "Dr." is acceptable at the beginning of a `Preferred Name` when no further information is available, e.g. "Dr. Hendershaw."
    - "Jr." is acceptable at the end of a `Preferred Name`, although in general suffixes belong in `aka` names. Do not use a comma, e.g. "Larry Amox Jr." not "Larry Amox, Jr."
    -	"Sr." is acceptable at the end of a `Preferred Name`, although in general suffixes belong in `aka` names. Do not use a comma, e.g. "Larry Amox Sr." not "Larry Amox, Sr."
- Don't include anything other than Agent information in Agent records, e.g. uncertainty in the way an agent was recorded on a catalog record. A collector recorded as "John Smith?" could use either the Agent "unknown" or "John Smith" and document the uncertainty of "?" in an appropriate remarks field on the catalog record or via the `verbatim agent` catalog record attribute.

### Different Agent, same name

Agents who have the same `Preferred Name` need to carry sufficient information to be distinguishable from each other. That is, do not create a second "John Doe" unless there is sufficient evidence to separate them from the existing Agent. Ideally, agents who share a preferred name should have a `not the same as` relationship with each other. See, for example, [Caitlin Curry](https://arctos.database.museum/agent/21356015) and [Caitlin Curry](https://arctos.database.museum/agent/21308564).

Because `Preferred Name` does not need to be unique within Arctos, applications that use strings to identify Agents (such as the catalog record bulkloader) cannot use `Preferred Name` as a value if there is more than one Agent record with that value. Instead, the `agent_id` (e.g. "https://arctos.database.museum/agent/21308564") must be used. This value can be found on any Agent page using the _Copy Stable Identifier_ button.

## Agent attributes

Detailed information about Agents is captured in the attribute structure used throughout Arctos. See the full list of [Agent attribute types in that code table](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctagent_attribute_type). Although users can "delete" attributes in the user interface, they are not actually deleted from the database, only deprecated in order to maintain a history of change. Each attribute has metadata associated with it: `begin date` and `end date` for cases when the attribute is time-bound, `related agent` for relationships, `determined` date and `determiner` to capture who asserted this attribute when, as well as `method` and `remark`. Attribute metadata is only required in certain circumstances (e.g. `related agent` for relationship-type attributes) but it is frequently helpful to include.

Attributes exist to capture data explicitly and more specific attribute types are generally preferred over the `remarks` attribute. For example, a `remark` of "also goes by Bob Jones" doesn't help other Arctos users find the Agent record in the way that an `aka` of "Bob Jones" does. The exception is for information that should not be visible to the public; this can go into `curatorial remarks` and stay safely hidden.

### Additional names

Name components are always useful to include, e.g. multiple `first name` attributes where a person's first name has variations such as "Robert" and "Bob." Note that an Arctos bot will create `first name`, `middle middle`, and `last name` attributes based on the `Preferred Name`. **---WHAT ALL DOES THIS BOT DO?---** Similarly, the `aka` attribute is very handy for recording name variants, e.g. "Bob Jones" is the `Preferred Name` is "Robert Jones." Use `aka` attributes to include common ASCII-128 (A-Z, no accents or foreign characters) variants, alternative transliterations, and text interpretations of symbols. For example:
- "Николай Е. Докучаев" is an acceptable `Preferred Name`, but should have an `aka` attribute of "Nikolai E. Dokuchaev"
- "Raúl Gutiérrez" should include an `aka` attribute of "Raul Gutierrez."
- "Ida Schoenfeld" should include an `aka` attribute of "Ida Schönfeld" 
- "Smith & Wesson" should include an `aka` attribute of "Smith and Wesson"

### Identifiers

Identifier-type attributes connect Arctos Agents to the broader information ecosystem. Whenever possible, add `Wikidata` (for dead people or organizations) and `ORCID` (for living people) attributes to make the Agent record easy to disambiguate from potential duplicates. Any Agent that is an Arctos operator should also have a `GitHub` attribute to facilitate communication there.

### Contacts and links

Address-type attributes provide the ability to add disambiguating information explicitly, rather than as remarks. Contact information recorded in `correspondence`, `shipping`, `phone`, `email`, etc. attributes provides geographical context to the Agent and also facilitates Arctos transactions such as loans. Even vague information is appropriate to include here, e.g. a `home` address attribute of "Ohio." Address attributes are not publicly visible, except for `url`, though they _are_ visible to any [Arctos operator]({% link _documentation/users.markdown %}).

The `url` attribute provides a flexible place to link external resources, such as biographical information, professional profiles, and organizational or personal websites.

### Events

Important dates related to an Agent can be captured via event-type attributes, e.g. `alive`, `born`, `died`. When recording dates, it is best practice to document the source of the date using attribute metadata. For example, if you find an obituary for an Agent, record the date as `died` along with your own name and date as the attribute `determiner` and `determined` date, and provide a URL to the obituary in the attribute `method`. If the obituary has useful details about the Agent, it may be appropriate to additionally record it in a `url` attribute. Note that the `born` attribute is not publicly visible, though it _is_ visible to any [Arctos operator]({% link _documentation/users.markdown %}).

### Status

Whenever possible, add an appropriate `status` attribute to indicate the data quality or completeness of a given Agent record. Learn more from the [code table definition](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctagent_attribute_type#status). An Agent may only have one `status` attribute, and an Arctos bot flags any Agents without a `status` as "unverified."

## Relationships

Relationships between Agents are a fundamental feature in Arctos. Like date of birth and date of death, relationships can be critical to understanding duplication and similarities in names, e.g. knowing that "John Smith Jr. is `child of` John Smith" helps clarify the situation even in the face of suddenly-ambiguous names, promotions, marriages, and other name changes or alternatives. Most relationships are familial (e.g. `spouse of`, `parent of`), professional (e.g. `student of`, `employee of`) or, for organization Agents, structural (`division of`, `established by`). Relationships can be between Agents of different types, for instance "John Doe" might be a `student of` both "James Jameson" (his advisor) and "University of Alabama" (his alma mater).

Dates are often very useful metadata to associate with relationships. For example, "John Doe" was a `student of` "University of Alabama" with a `begin date` and `end date` provides additional context. Dates can be as imprecise as the year, which is helpful for legacy Agent information.

The relationship `not the same as` is useful in understanding that suspiciously similar names are not duplicates, but do in fact refer to separate agents. For example, [Caitlin Curry](https://arctos.database.museum/agent/21356015) and [Caitlin Curry](https://arctos.database.museum/agent/21308564). The relationship `bad duplicate of` hides the bad duplicate Agent record and is how Arctos addresses duplicates without deleting Agent records.

## Editing existing Agents

Because Agents are shared by all Arctos members, always be conscientious when editing Agent records. If you notice that the `status` is "verified" (represented by a gold star icon) be extra cautious about editing existing information or deleting any data. Rather than deleting, best practice is to add a second version of the attribute and/or deprecate anything outdated using the `end date` attribute metadata. To see metadata about who edited what parts of an Agent record and when, click on the _Show metadata_ button from any Agent page.

For Agents of any status, never change the fundamental nature of the existing Agent. For example, if there is a "John Doe" collecting birds in Wyoming in 1990, and you have a "John Doe" who collected grasshoppers in Madagascar in 1872, it should be assumed that these are two separate Agents, and it would be appropriate to create a new Agent with the same `Preferred Name` (or use the [verbatim agent](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctattribute_type#verbatim_agent) attribute). Occasionally you will come across overloaded Agents, that is, Agent records which in fact represent multiple entities. If there is enough information to disambiguate the entities, you may want to split a new Agent off; be sure to create a `not the same as` relationship to prevent subsequent confusion, and inform any Arctos members whose collections may need to update which Agent their data is referencing.