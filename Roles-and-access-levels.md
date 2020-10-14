<!-- LANG:EN, title="Roles and access levels"-->

This page describes, in a non-exhaustive manner, who can do what on Inventaire. Different category of information can be displayed:

**Users**: information about humans (aka username, contributions, etc.) and their items (aka their inventory)
**Entities**: metadata about those belongings (aka [authors, works, editions, etc](https://inventaire.github.io/entities-map/))

Different roles are attributed to anyone visiting inventaire.io :

**Public**: Any request from the wild web (users or not, bots or humans).
**Authentified**: Users who registered and authentified on inventaire.
**Data admin**: Users who can perform advanced tasks about resources data (entities).
**Admin**: Users who have access to every tools available in the application.

### Who can do what about users

| Action \ Access Level      |Admin |Data admin|Authentified | Public |
| ----------- | ----------- |----------- | ----------- | ----------- |
| View username | x|x|x|x
| View presentation (aka bio) | x|x|x|x
| View items |(1)|(1)|(1)|(1)
| View shelves |(1)|(1)|(1)|(1)
| View contributions to entities (2) | x
| Request item |(3)|(3)|(3)
| View items and shelves count |(4)|(4)|(4)|(4)

**(1)**: depends on item/shelf visibily setting and users relations

**(2)**: Unlike other wikis such as Wikipedia or Wikidata, inventaire doesn't make contribution history public (accessible only by admins). This decision comes from the fact that some users might make the inventory of their books and edit data about those without having any knowledge that they are contributing to a wiki. There is therefore a privacy concern that people might share more private information than they realize about their interests.
**(3)**: it depends on the item's visibily setting  and on transaction mode (you can only request an item available for giving, lending, or selling)
**(4)**: the count displayed to a certain user will be the count of items or shelves that user is allowed to see

### Who can do what about entities

| Action \ Access Level      |Admin |Data admin|Authentified | Public |
| ----------- | ----------- |----------- | ----------- | ----------- |
| View entity | x|x|x|x
| [View recently changed entities](https://inventaire.io/entity/changes) | x|x|x|x
| Search | x|x|x|x
| Create, update or remove entity |x|x|x
| Revert edit entity |x|x|x
| Move entity to Wikidata |x|x|x
| Delete isolated entities |x|x|x
| [View duplicate entity](https://inventaire.io/entity/deduplicate?uris=wd:Q156268) |x|x
| Merge entities |x|x
| Revert entities merge |x|x
| View non-anonymized entity history |x
| View users contributions |x

Most of those access levels per action can be seen in the [entities controller](https://git.inventaire.io/inventaire/tree/master/server/controllers/entities/entities.js)

[More to be written]