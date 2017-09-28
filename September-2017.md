<!-- LANG:EN, title="September 2017"-->

## Data

### Whitelisting website and social network properties
Authors can now be linked to their website and social networks accounts, and works can be linked to a website.
**commits**: [674fd9f@server](https://github.com/inventaire/inventaire/commit/674fd9f), [d662fb0@server](https://github.com/inventaire/inventaire/commit/d662fb0), [1d02add@client](https://github.com/inventaire/inventaire-client/commit/1d02add)

## Developments

### Accept Wikimedia project sitelinks as alias URIs
It was already possible to find authors by their twitter name:
* [https://inventaire.io/entity/twitter:NaomiAKlein](https://inventaire.io/entity/twitter:NaomiAKlein)

It is now also possible to find all sorts of entities using the title of one of their page on a Wikimedia project:
* [https://inventaire.io/entity/enwiki:Naomi_Klein](https://inventaire.io/entity/enwiki:Naomi_Klein)
* [https://inventaire.io/entity/eswikiquote:J. K. Rowling](https://inventaire.io/entity/eswikiquote:J. K. Rowling)

**commit**: [32c4070@server](https://github.com/inventaire/inventaire/commit/32c4070)

### Added even more alias URIs: VIAF, BNF, Open Library, Facebook
* https://inventaire.io/entity/viaf:247820026
* https://inventaire.io/entity/bnf:145422980
* https://inventaire.io/entity/ol:OL36858W
* https://inventaire.io/entity/openlibrary:OL36858W
* https://inventaire.io/entity/fb:thomaspikettyofficiel
* https://inventaire.io/entity/facebook:DalaiLama

**commit**: [aa10e1e@server](https://github.com/inventaire/inventaire/commit/aa10e1e)

### Increasing entity claims constraints
  The webapp was already only suggestion humans as possible authors, series as series, etc, but the server was still accepting claim values without checking the type. That's what was fixed by [4ab8cdb](https://github.com/inventaire/inventaire/commit/4ab8cdb)
 
<hr>

[[August 2017|← August 2017]] - [[News|All News]] - [[October 2017|October 2017 →]]