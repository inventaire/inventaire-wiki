<!-- LANG:EN, title="Tools"-->
 
Those tools are largely experimental and often require to be able to perform actions that currently require admin rights. See [issue#91](https://github.com/inventaire/inventaire/issues/91)

**Legend**:
* <span class="square yellow"></span> : **experimental** - usually means that the interface is very rough, not self-explanatory
* <span class="square blue"></span> : **requires admin rights**
* <span class="square purple"></span> : **some actions require admin rights**
* <span class="square lime"></span> : **doesn't requires admin rights**
 
## Entities
### Editor 
* location: `/entity/[uri]/edit` ([example](https://inventaire.io/entity/isbn:9791020906427/edit))
* description: anyone can edit the properties of an entity. All pencil buttons on entities pages lead you to the entity editor  (ex: [on the top right of this page](https://inventaire.io/entity/isbn:9791020906427)) .
* categories: <span class="square lime"></span>

### Graph cleanup
* location: `/entity/[uri]/edit` ([example](https://inventaire.io/entity/isbn:9791020906427/edit))
* categories: <span class="square purple"></span>  <span class="square yellow"></span>


### Merge
* location: on entities editor pages
* categories: <span class="square blue"></span>

### Deduplication
Tools specialized for finding duplicated entities and inviting the user to confirm it should be merged.

#### Deduplication Tasks
* location: [`/tasks`](https://inventaire.io/tasks)
* categories: <span class="square blue"></span> <span class="square yellow"></span> 

#### Find most common names among Inventaire human entities
* location: [`/entity/deduplicate`](https://inventaire.io/entity/deduplicate)
* categories: <span class="square blue"></span> <span class="square yellow"></span> 
* warning: that's some scary stuff

#### Merge suggestions
* location: `/entity/[uri]`
* categories: <span class="square blue"></span> <span class="square yellow"></span>