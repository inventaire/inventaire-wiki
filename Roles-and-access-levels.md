<!-- LANG:EN, title="Roles and access levels"-->
 
This page describes, in a non-exhaustive manner, who can do what on Inventaire. Different category of information can be displayed:
 
 **Entities**: information about resources (aka editions, authors, etc.)
 **Users**: information about humans (aka username, contributions, etc.)
 **Availability**: information about how to share (aka visibility, transactions, etc)
 
Different roles are attributed to anyone visiting inventaire.io :
 
**Public**: Any request from the wild web (users or not, bots or humans).
 **Authentified**: Users who registered and authentified on inventaire.
 **Data admin**: Users who can perform advanced tasks about resources data (entities).
 **Admin**: Users who have access to every tools available in the application.
 
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

### Who can do what about users

Unlike other CC0 wikis, inventaire carefully display contributions information (except for admins). This decision comes from the fact that some users might make the inventory of their books and edit data about those without having any knowledge to contribute to a CC0 based wiki. Therefore there is a privacy concern that contributions shall not be infered to deduce personal information about a user.

### Who can do what about availability

Visibility: private, public, network

[More to be written]