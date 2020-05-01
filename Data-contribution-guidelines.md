<!-- LANG:EN, title="Data contribution guidelines"-->

In general, data edition conventions in Inventaire are mirroring conventions of the Wikidata Books project ([project page](https://www.wikidata.org/wiki/Wikidata:WikiProject_Books), [discussions](https://www.wikidata.org/wiki/Wikidata_talk:WikiProject_Books)). This proximity should allow to easily import data from Inventaire to Wikidata.

That said, many of those discussions aren't settled yet or followed by effects. That's for instance the case of discussions around the distinction between works and editions (more or less following the [FRBR](https://en.wikipedia.org/wiki/FRBR) model), and the need to have one entity for each of those and specific properties for those different levels.

Furthermore, contrary to Wikidata where data edition is weakly constrained, Inventaire data edition interface aim to make everyones contribution easy by constraining it as much as possible to avoid errors. For instance, the interface only allows to add humans as author of works, instead of allowing any kind of entity. Another example : you can't add an author to an edition (this can only be done at the work level), or an ISBN to a work (this can only be done at the edition level) (See the [entities map](https://inventaire.github.io/entities-map/))

**The following article gives a summary of the rules applied within Inventaire**. It's a work in progress, feel welcome to contribute or to [[Communication channels|request]] a rule to be explicited.

## Summary
- [Editions](#editions)
- [Works](#works)
- [Authors](#authors)
- [Publishers](#publishers)
- [Conflicts of interest](#conflicts-of-interest)
- [See also](#see-also)

## Editions
### Title and subtitle
Title (P1476) and subtitle (P1680) properties are available on editions. The use of a subtitle is especially recommended when [the title would be extremly long](https://inventaire.io/entity/inv:14c867eb4418af89860d7199c708a3e3/edit).

### Multi-work editions
Some editions are editions of several works. Example, ["Une saison en Enfer suivi de Les Illuminations"](https://inventaire.io/entity/isbn:9782253159049) is an edition gathering both the work [A Season in Hell](https://inventaire.io/entity/wd:Q301342) and the work [Illuminations](https://inventaire.io/entity/wd:Q2255881). To match this case, [both works where added in the "edition of" (P629) property](https://inventaire.io/entity/isbn:9782253159049/edit).

Sometimes it seems like the problem comes from the work level: when an edition is an edition of a whole serie (example: [Harry Potter: The Complete Collection](https://inventaire.io/entity/isbn:9781408856772)), it could make sense to make it just be an "edition of " the whole serie, instead of all of its part: that's not currently possible in Inventaire (it will be rejected as "wrong entity type").

## Works
### Title and subtitle
The status of  title (P1476) and subtitle (P1680) properties on works [not being very clear](https://www.wikidata.org/wiki/Property_talk:P1476#Original_title_(originally_asked_in_Wikidata:Project_chat)), those properties can't be set on works in Inventaire. Titles and subtitles are instead stored as labels, one per language. This might create case where different edition of a work had different titles within a same language: the work should have the label corresponding to the original or the most widespread title.

## Authors
### Author labels
* Author labels are made of the author name in the form **"FirstName LastName"**
* **The first name should not be abbreviated**
  *  Exception: when the author is known with this abbreviated name. Example: [J. K. Rowling](https://inventaire.io/entity/wd:Q34660)

## Publishers

## Conflicts of interest

Inventaire largely shares [Wikidata Conflict of Interest rules](https://www.wikidata.org/wiki/Wikidata:Requests_for_comment/Conflict_of_Interest), notably
> If you are an authority on an item (or a set of item), e.g. acting as their agent, or a company looking for the Wikidata items about their products (movies, cars, songs, etc.), you are allowed and indeed encouraged to keep the data about this item up-to-date and the coverage complete (e.g. box office, awards, cast, official Website, etc.).

Having publishers directly keep data about their productions in Wikidata and Inventaire up-to-date would be marvellous.

## See also
* [Entities map](https://inventaire.github.io/entities-map/)
* [[Data|Books data]]

<!-- LANG:FR, title="Conventions de contribution aux données"-->

De manière générale, les conventions d'édition des données dans Inventaire sont, sauf cas particuliers ci-dessous, calquées sur les conventions établie par le groupe de travail sur les livres de la communauté Wikidata ([page du projet](https://www.wikidata.org/wiki/Wikidata:WikiProject_Books), [discussions](https://www.wikidata.org/wiki/Wikidata_talk:WikiProject_Books)). Cette proximité doit permettre d'importer facilement des données d'Inventaire vers Wikidata.

Cela dit, de nombreux débats n'y sont pas encore tranchés ou suivi d'effets dans les données. C'est par exemple le cas des discussions autour de la distinction entre oeuvres et éditions (suivant de plus ou moins prêt le modèle [FRBR](https://fr.wikipedia.org/wiki/FRBR)), et la nécessité d'avoir une entité pour chacune d'elle et des propriétés spécifiques à ces différents niveau.

Par ailleurs, à la différence de Wikidata dont l'édition est faiblement contrainte, l'interface d'édition de donnée d'Inventaire vise à faciliter l'édition par tout un chacun, en contraignant l'édition autant que possible pour éviter les erreurs. Par exemple, l'interface ne permet d'ajouter que des humains comme auteur d'une oeuvre, et non n'importe quelle entité. Ou encore, il n'est pas possible d'ajouter un auteur à une édition (seulement possible au niveau d'une oeuvre) ou un ISBN à une oeuvre (seulement possible au niveau d'une édition)

**Les règles suivantes sont un résumé des règles qui s'appliquent sur Inventaire**. C'est encore très incomplet : vos contributions sont les bienvenues, n'hésitez pas à [[Communication channels|venir en discuter avec la communauté]].

## Sommaire 

- [Éditions](#editions)
- [Œuvre](#œuvre)
- [Auteurs](#auteurs)
- [Éditeurs](#éditeurs)
- [Conflits d'intérêt](#conflits%20d%27int%C3%A9r%C3%AAt)
- [Voir aussi](#voir-aussi)

## Éditions
## Œuvre
## Auteurs
## Éditeurs

## Conflits d'intérêt
Inventaire partage largement les [règles de Wikidata sur les conflits d'intérêt](https://www.wikidata.org/wiki/Wikidata:Requests_for_comment/Conflict_of_Interest), notamment pour ce qui est de l'édition de donnée concernant vos productions. Avoir les maisons d'éditions mettre à jour directement les données sur leurs productions dans Wikidata et Inventaire serait tout à fait merveilleux.

## Voir aussi
* [Carte des entités](https://inventaire.github.io/entities-map/)
* [[Data|Données des livres]]