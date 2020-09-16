<!-- LANG:EN, title="Roles and access levels"-->
 
Different roles are attributed to anyone visiting inventaire.io :
 
**Public**: Any request from the wild web (users or not, bots or humans).
 **Authentified**: Users who registered and authentified on inventaire.
 **Data admin**: Users who can perform advanced tasks about bibliographical data (entities).
 **Admin**: Users responsible for the future's well being of the platform.
 
### Who can do what about entities
 
| Action \ Access Level      |Admin |Data admin|Authentified | Public |
| ----------- | ----------- |----------- | ----------- | ----------- |
| View entity | x|x|x|x
| [View recently changed entities](https://inventaire.io/entity/changes) | x|x|x|x
| Search | x|x|x|x
| Create, update or remove entity |x|x|x
| Revert edit entity |x|x|x
| Move entity to Wikidata |x|x|x
| Delete entity |x|x|x
| [View duplicate entity](https://inventaire.io/entity/deduplicate?uris=wd:Q156268) |x|x
| Merge entities |x|x
| Revert merge entities |x|x
| View non-anonymized entity history |x
| View users contributions |x

Most of those access levels per action can be seen in the [entities controller](https://git.inventaire.io/inventaire/tree/master/server/controllers/entities/entities.js)

###  Why contributions are not displayed to everyone
Some users might make the inventory of their books and edit data about those without having any knowledge to contribute to a CC0 based wiki. Therefore there is a privacy concern that contribution to bibliographical data cannot be  infered to deduce personal information. This is why, unlike other CC0 wikis, inventaire carefully display contributions information (except for admins).