<!-- LANG:EN, title="Glossary"-->

### Claim
Equivalent to [Wikidata Claim](https://www.wikidata.org/wiki/Wikidata:Glossary#Claim)

### Data seed
See [[Data#web-data-seeds]]

### Edition

### Entity
<span style="color: red;font-weight:bold;">⚠</span>Equivalent to [Wikidata Item](https://www.wikidata.org/wiki/Wikidata:Glossary#Item)

### Item
A book in a user inventory
<span style="color: red;font-weight:bold;">⚠</span> Not to be confused with a Wikidata Item (see [[Glossary#Entity|Entity]])

### Label
Equivalent to [Wikidata Label](https://www.wikidata.org/wiki/Wikidata:Glossary#Label)

### Placeholder
An entity that was created semi-automatically for structural needs.

For instance, as all editions should have an associated work, [importing](https://inventaire.io/add/import) generalist "book" data (typically a title, an author name, and an ISBN) gives the following workflow for each entry:
* either the work and author can be identified within existing Wikidata and Inventaire entities, and only the edition entity is created
* or, in the case the work and author can't be identitifed, several entities are created:
  * an edition (using the ISBN and the title)
  * an associated **placeholder** work (using the edition title as label)
  * one or more **placeholder** authors (that will be referenced from the work)
 
While the edition is likely to not have any duplicate given it has an ISBN, the work and author entities that were automatically created might be duplicates of existing entities: this is OK, we have [[Tools#Entities|tools to deduplicate]] those entities.

### Property
Equivalent to [Wikidata Property](https://www.wikidata.org/wiki/Wikidata:Glossary#Property)