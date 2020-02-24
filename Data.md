<!-- LANG:EN, title="Data"-->

The Inventaire project has two pillars:
* The [book sharing web application](https://inventaire.io/welcome), inviting anyone to make the inventory of their books
* The **open data** project aiming at building a [CC0](https://creativecommons.org/publicdomain/zero/1.0/) [Wikidata](https://wikidata.org)-centered database on resources, to support the needs of the web app, while being enriched by its users, and more broadly speaking, to concretize our mission: **mapping resources with libre software and open knowledge**, starting with books.

This article aims to document this second aspect, by:
* making the **context of open data production in Inventaire** understandible by people who might be more interested in the structured data produced by the application than by its book sharing aspect
* helping **data re-use**, especially, but not only, by importing data produced in Inventaire back to Wikidata

See also [data.inventaire.io](https://data.inventaire.io), the home page to send to everyone who could be intested in the data aspect of Inventaire, but not necessarly in the web app itself.

## Summary
- [Data sources](#data-sources)
  - [Wikidata](#wikidata)
  - [Internal database](#internal-database)
  - [Web data seeds](#web-data-seeds)
- [Data structure](#data-structure)
  - [Differences between Wikidata and Inventaire terminologies](#differences-between-wikidata-and-inventaire-terminologies)
  - [Examples of relations between entities](#examples-of-relations-between-entities)
- [Data editor](#data-editor)
- [Data contribution](#data-contribution)
- [Raw data](#raw-data)
  - [API](#api)
  - [SPARQL endpoint](#sparql-endpoint)
  - [Dumps](#dumps)
  - [See also](#see-also)

## Data sources

Data about books, authors, series, subjects, etc, come from 3 sources:

### Wikidata
[![wd](https://www.wikidata.org/static/images/project-logos/wikidatawiki.png)](https://wikidata.org)

From the [Wikidata Introduction](https://www.wikidata.org/wiki/Wikidata:Introduction):
> Wikidata is a free, collaborative, multilingual, secondary database, collecting structured data to provide support for Wikipedia, Wikimedia Commons, the other wikis of the Wikimedia movement, and to anyone in the world.

The Wikidata community has a dedicated task force on books: [WikiProject Books](https://www.wikidata.org/wiki/Wikidata:WikiProject_Books)

### Internal database
As Wikidata doesn't aim to gather data on all books and their editions, but only those that match [certain notability criteria](https://www.wikidata.org/wiki/Wikidata:Notability), we can't only rely on it, thus the introduction of a **internal database**, made of users contributions, linked to Wikidata entities. See [[Data contribution guidelines]].

Those data will are published under a [CC0 license](https://en.wikipedia.org/wiki/CC0), so that the Wikidata community can import the entities that are relevant to Wikidata following their criteria.

### Web data seeds
**Basic Facts on books editions extracted from the wide web, proceessed, and enriched** to bootstrap the data set of an edition missing to the database. This is made in an attempt to ease and somewhat automatize what a user encountering missing data would have to do manually: go on the web, searching basic facts like a title, the author's name, a book cover. That's a temporary solution, waiting to be replaced by more reliable data sources, like raw libraries and publishers open data.

## Data structure

The term **entity** gathers all the concepts of **works** (books, comics, manga, etc.), **editions** of those works, their **authors** and **series**. Largely following [Wikidata data model](https://www.mediawiki.org/wiki/Wikibase/DataModel), those entities are linked together by **properties**.

### Differences between Wikidata and Inventaire terminologies
* In the [Wikidata terminology](https://www.wikidata.org/wiki/Wikidata:Glossary), *entities* gather both concepts of *items* (all the things with a Q-id) and *properties* (all things with a P-id)
* In [[Glossary|Inventaire terminology]], the equivalent of Wikidata items are called *entities* ([example](https://inventaire.io/entity/inv:456535701900dddbcdb246e9f9249bed)), the term *items* being used to refer to what users inventories are made of ([example](https://inventaire.io/items/bd5f8d1a1fd834c651fc947c7d24f6a4)), each item being an instance of an entity.

### Examples of relations between entities
* [*I, Robot*](https://inventaire.io/entity/isbn:9780007532278), the book edition uniquely identified by its [ISBN](https://en.wikipedia.org/wiki/ISBN): 978-0-00-753227-8 → is an **edition of** (property [P629](https://wikidata.org/entity/P629) in Wikidata) → the [work *I, Robot*](inventaire.io/entity/wd:Q393018), uniquely identified in Wikidata as [Q393018](https://www.wikidata.org/wiki/Q393018)
* the [work *I, Robot*](inventaire.io/entity/wd:Q393018) → has for **author** (property [P50](https://wikidata.org/entity/P50) in Wikidata) → [Isaac Asimov](https://inventaire.io/entity/wd:Q34981), uniquely identified in Wikidata as [Q34981](https://www.wikidata.org/wiki/Q34981)

This is how this graph of relations looks like:
* Series are made of several works
* An author can be the author of several works
* A work can have several editions
* Usually an edition is the edition of a unique work. In special cases, an edition can be the edition of several works (for instance, an edition that would gather the Harry Potter volumes 1 and 2): we call those composite or multi-work editions.

The user inventory is made of **items**, each item being an instance of an edition.

![entities map](https://raw.githubusercontent.com/inventaire/entities-map/master/screenshots/entities-map.png)

## Data editor
To edit Inventaire entities, you first need to [create an Inventaire account](http://inventaire.io/signup). In addition, to edit Wikidata entities from the Inventaire entity editor, you will be invited to connect your Wikidata account. But you can also simply click the "Edit on Wikidata" button.

To find an entity's editor page:
- from the entity's page ([example](https://inventaire.io/entity/wd:Q3366047)), click the pencil
- from the URL bar, add `/edit` at the end of the entity's page URL. Examples:
- https://inventaire.io/entity/wd:Q3366047 => https://inventaire.io/entity/wd:Q3366047/edit
- https://inventaire.io/items/af3b4551e35355f9ffbdcb06e3001403 => https://inventaire.io/items/af3b4551e35355f9ffbdcb06e3001403/edit

The editor is largely inspired by Wikidata own editor so that the Wikidata community feels at home ;) But at the same time, it is designed to make the contribution of anyone - aware of Wikidata or not - easy and welcome. Inputs values are thus more constrained than in Wikidata, a few examples:
* you won't be able to state that a book as a montaign for author
* following the [WikiProject Books](https://www.wikidata.org/wiki/Wikidata:WikiProject_Books) recommandations to separate works and their editions (the [FRBR](https://en.wikipedia.org/wiki/Functional_Requirements_for_Bibliographic_Records)-ish way), you won't be allowed to set an ISBN on a work
* additionnaly, you won't be allowed to set claims that belong to the work level on the edition, as we assume that editions inherit those from the works they are associated with, and that it would be unnecessary duplications

[![contributive data](https://trello-attachments.s3.amazonaws.com/56e00fd7fbc3e6a2cc85aa56/803x625/2261e082efceca9a8a7598726a818b16/contributive_data.png)](https://inventaire.io/entity/isbn:9782290349229/edit)

## Data contribution

For anyone willing to enrich Inventaire CC0 data from their own dumps, here is the properties inventaire can understand.

The [Inventaire client interface](https://github.com/inventaire/inventaire-client/) can read and interprete triples from Wikidata and Inventaire stores. In order to not be able to read every triples of Wikidata, Inventaire client reads only a limited set of **[whitelist properties](https://github.com/inventaire/inventaire/blob/master/server/lib/wikidata/whitelisted_properties.coffee)** that mimic [Wikidata](https://www.wikidata.org/wiki/Wikidata:List_of_properties) properties. The distribution of claims per properties is accessible through [this sparql query](https://query.inventaire.io/#%23Count%20the%20number%20of%20claims%20per%20property%0ASELECT%20%3Fproperty%20%28COUNT%28%3Fitem%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fitem%20%3Fproperty%20%3Fvalue%20.%0A%7D%0AGROUP%20BY%20%3Fproperty%0AORDER%20BY%20DESC%28%3Fcount%29)

The [Inventaire server](https://github.com/inventaire/inventaire) can read and write data only after typing every entity according to Inventaire own **[type model](https://github.com/inventaire/inventaire/blob/master/server/controllers/entities/lib/properties/properties_per_type.coffee)** which map types to properties.

Those two lists of properties ([client whitelist](https://github.com/inventaire/inventaire/blob/master/server/lib/wikidata/whitelisted_properties.coffee) and [server type model](https://github.com/inventaire/inventaire/blob/master/server/controllers/entities/lib/properties/properties_per_type.coffee)) represent what inventaire can read and write. If you have a dump of data matching those properties that you wish to integrate to Inventaire CC0 data, [contact the Inventaire team](mailto:hello@inventaire.io) so we can discuss it!

## Raw data
### API
*See [api.inventaire.io section on entities](https://api.inventaire.io/#/Entities)*
The API should look somewhat familar to [Wikidata API](https://www.wikidata.org/w/api.php) users, with a few notable differences:
- for convenience, the API returns both Wikidata and Inventaire entities
- the Inventaire entities data model doesn't have *qualifiers* at the moment, so labels and claims from both Wikidata and Inventaire entities are returned [simplified](https://github.com/maxlath/wikidata-sdk/blob/master/docs/simplify_entities_data.md)
- as Inventaire knows about both Wikidata and Inventaire entities, claims properties and entity values need to be prefixed:
```sparql
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX inv: <https://inventaire.io/entity/>
```

### SPARQL endpoint
A query service is available at https://query.inventaire.io/

### Dumps
All dumps can be found at https://dumps.inventaire.io
Available formats JSON, [NDJSON](https://en.wikipedia.org/wiki/JSON_Streaming#Line_delimited_JSON), TTL (turtle)

## See also
* [[Data contribution guidelines]]
* [CC0 is the best open data license](https://pietercolpaert.be/open%20data/2017/02/23/cc0.html)

<!-- LANG:FR, title="Données"-->

## Sommaire

- [Sources des données](#sources-des-donn%C3%A9es)
  - [Wikidata](#wikidata)
  - [Base de données interne](#base-de-donn%C3%A9e-interne)
  - [Amorces de données du web](#amorces-de-donn%C3%A9es-du-web)
- [Structure des données](#structure-des-donn%C3%A9e)
- [Editeur de données](#editeur-de-donn%C3%A9e)
- [Contribuer a la donnée](#contribuer-a-la-donn%C3%A9e)
- [Données brutes](#donn%C3%A9e-brutes)
- [Voir aussi](#voir-aussi)

## Sources des données

Les données sur les livres, auteurs, séries, sujets, etc, viennent de 3 sources :

### Wikidata
[![wd](https://www.wikidata.org/static/images/project-logos/wikidatawiki.png)](https://wikidata.org)

D'après l'[Introduction à Wikidata](https://www.wikidata.org/wiki/Wikidata:Introduction/fr):
> Wikidata est une base de données libre, collaborative, multilingue, et secondaire qui collecte des données structurées pour alimenter Wikipédia, Wikimedia Commons, les autres projets du mouvement Wikimédia et pour n'importe qui sur la planète.

La communauté Wikidata a un groupe de travail dédié aux livres : [WikiProject Books](https://www.wikidata.org/wiki/Wikidata:WikiProject_Books/fr)

### Base de données interne
Wikidata ne visant pas à avoir une fiche pour chaque livre et ses éditions, mais seulement ceux remplissant [certains critères de notoriété](https://www.wikidata.org/wiki/Wikidata:Notability/fr), nous ne pouvons nous reposer sur cette seule base de données, d'où l'introduction d'une **base de donnée interne à inventaire**, constituée par les contributions des utilisateurs, et liée à Wikidata. Voir les [[Data contribution guidelines|conventions de contribution aux données]].

Ces données seront ensuite publiée sous une [license CC0 license](https://fr.wikipedia.org/wiki/CC0) afin que la communauté Wikidata puisse importer les entités pertinante pour le projet Wikidata selon leurs propres critères d'admissibilité.

### Amorces de données du web
Des **faits de bases sur les éditions de livres extrait du web, traités et enrichis** pour amorcer la fiche d'une édition manquant à la base de donnée. Cela resulte d'une tentative de faciliter et quelque peu automatiser le travail qu'un utilisateur aurait à faire manuellement lorsqu'il fait face à des données manquantes pour une édition donnée. C'est une solution provisoire, en attendant de pouvoir la remplacer par des sources de données plus fiables, telles des données brutes et ouvertes des bibliothèques et éditeurs.

### Structure des données

Le terme d'entité (en anglais : `entity`) regroupe l'ensemble des concepts d'oeuvres (livres, BD, manga, etc.), les éditions de ces oeuvres, leurs auteurs et séries.

L'inventaire d'un utilisateur est lui constitué d'articles (en anglais : `item`), chaque article étant une instance d'une édition spécifique d'une oeuvre.

![entities map](https://raw.githubusercontent.com/inventaire/entities-map/master/screenshots/entities-map.png)

### Editeur de données
[![contributive data](https://trello-attachments.s3.amazonaws.com/56e00fd7fbc3e6a2cc85aa56/803x625/2261e082efceca9a8a7598726a818b16/contributive_data.png)](https://inventaire.io/entity/isbn:9782290349229/edit)

## Contribuer à la donnée

Pour celles et ceux qui souhaite enrichir les données CC0 d'inventaire et wikidata au dela de l'éditeur de données, voici un descriptif des propriétés utilisées par Inventaire.

Coté [interface client](https://github.com/inventaire/inventaire-client/), Inventaire peut lire de la données issues de Wikidata ET du stockage interne Inventaire. Pour ne pas demander l'intégralité des valeurs liées propriétés Wikidata, le client restreint les propriétées à celles inscrites sur **[cette liste blanche](https://github.com/inventaire/inventaire/blob/master/server/lib/wikidata/whitelisted_properties.coffee)**. Ces propriétés imitent celles employées par [Wikidata](https://www.wikidata.org/wiki/Wikidata:List_of_properties). On peut trouver l'intégralité des propriétés inscrites dans inventaire via cette [requête SPARQL](https://query.inventaire.io/#%23Count%20the%20number%20of%20claims%20per%20property%0ASELECT%20%3Fproperty%20%28COUNT%28%3Fitem%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fitem%20%3Fproperty%20%3Fvalue%20.%0A%7D%0AGROUP%20BY%20%3Fproperty%0AORDER%20BY%20DESC%28%3Fcount%29)

Coté [serveur](https://github.com/inventaire/inventaire), Inventaire peut lire et écrire des données sur sa base de données. Lors de la lecture ou de l'écriture d'une donnée un typage est effectué en fonction des propriétés, suivant **[ce modèle](https://github.com/inventaire/inventaire/blob/master/server/controllers/entities/lib/properties/properties_per_type.coffee)** .

Ces deux listes réprésentent ce qu'inventaire peut traiter aujourd'hui. Si vous détenez un dump de données correspondant à ces propriétés et que vous souhaiteriez intégrer à la base de données CC0 Inventaire, n'hésitez pas à [contacter l'équipe Inventaire](mailto:hello@inventaire.io) pour en discuter !

## Données brutes
### API
*Voir [api.inventaire.io section sur les entities](https://api.inventaire.io/#/Entities)*
L'API se veut proche de l'[API Wikidata](https://www.wikidata.org/w/api.php) avec quelques différences notables :
-pour un confort d'utilisation, l'API retourne à la fois des entités Inventaire et Wikidata
- les modèle de données des entités inventaire n'ont pas de *qualifiers* pour l'instant, donc les *labels* et les *claims* qui viennent à la fois de Wikidata et d'Inventaire sont retournées [simplifiées](https://github.com/maxlath/wikidata-sdk/blob/master/docs/simplify_entities_data.md)
- comme Inventaire reconnait à la fois les données issues Wikidata et d'Inventaire, les propriétés sur *claims* et les valeurs des entitiés doivent être prefixé:
```sparql
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX inv: <https://inventaire.io/entity/>
```

### Point d'entrée SPARQL
Un service de requête SPARQL est disponible sur https://query.inventaire.io/

### Dumps
All dumps can be found at https://dumps.inventaire.io
Available formats JSON, [NDJSON](https://en.wikipedia.org/wiki/JSON_Streaming#Line_delimited_JSON), TTL (turtle)

## Voir aussi
* [[Data contribution guidelines|Conventions de contribution aux données]]
* [CC0 is the best open data license](https://pietercolpaert.be/open%20data/2017/02/23/cc0.html)