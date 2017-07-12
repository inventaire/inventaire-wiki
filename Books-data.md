<!-- LANG:EN, title="Books data"-->

## Summary

- [Data sources](#data-sources)
  - [Wikidata](#wikidata)
  - [Internal database](#internal-database)
  - [Web data seeds](#web-data-seeds)
- [Data structure](#data-structure)
- [Data editor](#data-editor)
- [See also](#see-also)

## Data sources

Books data come from 3 sources:

### Wikidata
[![wd](https://www.wikidata.org/static/images/project-logos/wikidatawiki.png)](https://wikidata.org)

From the [Wikidata Introduction](https://www.wikidata.org/wiki/Wikidata:Introduction):
> Wikidata is a free, collaborative, multilingual, secondary database, collecting structured data to provide support for Wikipedia, Wikimedia Commons, the other wikis of the Wikimedia movement, and to anyone in the world.

The Wikidata community has a dedicated task force on books: [WikiProject Books](https://www.wikidata.org/wiki/Wikidata:WikiProject_Books)

### Internal database
As Wikidata doesn't aim to gather data on all books and their editions, but only those that match certain notoriety criteria, we can't only rely on it, thus the introduction of a **internal database**, made of users contributions, linked to Wikidata entities. See [[Data contribution guidelines]].

Those data will are published under a [CC0 license](https://en.wikipedia.org/wiki/CC0), so that the Wikidata community can import the entities that are relevant to Wikidata following their criteria.

### Web data seeds
**Basic Facts on books editions extracted from the wide web, proceessed, and enriched** to bootstrap the data set of an edition missing to the database. This is made in an attempt to ease and somewhat automatize what a user encountering missing data would have to do manually: go on the web, searching basic facts like a title, the author's name, a book cover. That's a temporary solution, waiting to be replaced by more reliable data sources, like raw libraries and publishers open data.

## Data structure

The term `entity` gathers all the concepts of works (books, comics, manga, etc.), editions of those works, their authors and series.

The user inventory is made of `items`, eich item being an instance of the specific edition of a work.

![entities map](https://raw.githubusercontent.com/inventaire/entities-map/master/screenshots/entities-map.png)

## Data editor
![contributive data](https://trello-attachments.s3.amazonaws.com/56e00fd7fbc3e6a2cc85aa56/803x625/2261e082efceca9a8a7598726a818b16/contributive_data.png)

## See also
* [[Data contribution guidelines]]
* [CC0 is the best open data license](https://pietercolpaert.be/open%20data/2017/02/23/cc0.html)

<!-- LANG:FR, title="Données des livres"-->

## Sommaire

- [Sources des données](#sources-des-donn%C3%A9es)
  - [Wikidata](#wikidata)
  - [Base de données interne](#base-de-donn%C3%A9e-interne)
  - [Structure des données](#structure-des-donn%C3%A9e)
  - [Editeur de données](#editeur-de-donn%C3%A9e)
  - [Amorces de données du web](#amorces-de-donn%C3%A9es-du-web)
- [Voir aussi](#voir-aussi)

## Sources des données

Les données des livres viennent de 3 sources :

### Wikidata
[![wd](https://www.wikidata.org/static/images/project-logos/wikidatawiki.png)](https://wikidata.org)

D'après l'[Introduction à Wikidata](https://www.wikidata.org/wiki/Wikidata:Introduction/fr):
> Wikidata est une base de données libre, collaborative, multilingue, et secondaire qui collecte des données structurées pour alimenter Wikipédia, Wikimedia Commons, les autres projets du mouvement Wikimédia et pour n'importe qui sur la planète.

La communauté Wikidata a un groupe de travail dédié aux livres : [WikiProject Books](https://www.wikidata.org/wiki/Wikidata:WikiProject_Books/fr)

### Base de données interne
Wikidata ne visant pas à avoir une fiche pour chaque livre et ses éditions, mais seulement ceux remplissant certains critères de notoriété, nous ne pouvons nous reposer sur cette seule base de données, d'où l'introduction d'une **base de donnée interne à inventaire**, constituée par les contributions des utilisateurs, et liée à Wikidata. Voir les [[Data contribution guidelines|conventions de contribution aux données]].

Ces données seront ensuite publiée sous une [license CC0 license](https://fr.wikipedia.org/wiki/CC0) afin que la communauté Wikidata puisse importer les entités pertinante pour le projet Wikidata selon leurs propres critères d'admissibilité.

### Amorces de données du web
Des **faits de bases sur les éditions de livres extrait du web, traités et enrichis** pour amorcer la fiche d'une édition manquant à la base de donnée. Cela resulte d'une tentative de faciliter et quelque peu automatiser le travail qu'un utilisateur aurait à faire manuellement lorsqu'il fait face à des données manquantes pour une édition donnée. C'est une solution provisoire, en attendant de pouvoir la remplacer par des sources de données plus fiables, telles des données brutes et ouvertes des bibliothèques et éditeurs.

### Structure des données

Le terme d'entité (en anglais : `entity`) regroupe l'ensemble des concepts d'oeuvres (livres, BD, manga, etc.), les éditions de ces oeuvres, leurs auteurs et séries.

L'inventaire d'un utilisateur est lui constitué d'articles (en anglais : `item`), chaque article étant une instance d'une édition spécifique d'une oeuvre.

![entities map](https://raw.githubusercontent.com/inventaire/entities-map/master/screenshots/entities-map.png)

### Editeur de données
![contributive data](https://trello-attachments.s3.amazonaws.com/56e00fd7fbc3e6a2cc85aa56/803x625/2261e082efceca9a8a7598726a818b16/contributive_data.png)

## Voir aussi
* [[Data contribution guidelines|Conventions de contribution aux données]]
* [CC0 is the best open data license](https://pietercolpaert.be/open%20data/2017/02/23/cc0.html)