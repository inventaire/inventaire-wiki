<!-- LANG:EN, title="November 2017"-->

## Discussions
* ongoing discussion on the [setup of tools to **clean entities** in a more systematic fashion](https://github.com/inventaire/inventaire/issues/129)
* [on improving **scientific papers** support](https://twitter.com/andrawaag/status/936027866101420032), and more generally, **on the project direction as a discovery/recommendation tool**

## Documentation
- the [**Code Contributor Guidelines**](https://github.com/inventaire/inventaire/wiki/Code-Contributor-Guidelines) got updated
- **New User Tips**:
  - [Search Inventaire from your browser address bar](https://wiki.inventaire.io/wiki/Add-Inventaire-to-your-browser-search-engines)
- **New Developer Tips**:
  - [How to use the debugger](https://github.com/inventaire/inventaire/wiki/Use-the-debugger#server-side)

## Presentation
- the WikidataCon presentation *"Inventaire: Tale of a Wikidata-centered linked open contributive database on resources"* is online: [video](https://www.youtube.com/watch?v=nlxWy8ombEM&t=5m50s), [slides](https://hackmd.io/p/SJGdXy-RZ)

## Data
### New properties
Commits: server [e134590](http://github.com/inventaire/inventaire/commit/e134590), [05b48cc](http://github.com/inventaire/inventaire/commit/05b48cc) / client [73433bc](http://github.com/inventaire/inventaire-client/commit/73433bc), [d912093](http://github.com/inventaire/inventaire-client/commit/d912093)

**Authors**:
- Mastodon address ([wdt:P4033](https://www.wikidata.org/wiki/Property:P4033))

**Works**:
- based on ([wdt:P144](https://www.wikidata.org/wiki/Property:P144))
- inspired by ([wdt:P941](https://www.wikidata.org/wiki/Property:P941))

**Editions**:
- number of volumes ([wdt:P2635](https://www.wikidata.org/wiki/Property:P2635))

## Developments
### Welcome page
- the section [*some of the last books listed*](http://inventaire.io/welcome) is now generated from the [`/api/items?action=recent-public` endpoint](https://github.com/inventaire/inventaire/blob/bbc70f2/server/controllers/items/recent_public.coffee), which takes care to return items from different users and in the user language. (issues: [#102](https://github.com/inventaire/inventaire/issues/102) and [#127](https://github.com/inventaire/inventaire/issues/127))

### Groups
Following pandark issues ([#121](https://github.com/inventaire/inventaire/issues/121), [#122](https://github.com/inventaire/inventaire/issues/122)), groups got a major update:
- [**Group board**](https://inventaire.io/network/groups/settings):
  - a sub-menu was added to allow inviting to the group by email
  - sub-menus are now wrapped by default for more clarity
- [improved API documentation](https://api.inventaire.io/#/Groups)

## Deployment
 * inventaire.io joins wiki.inventaire.io in automating its SSL/TLS setup using [**LetsEncrypt**](https://letsencrypt.org). Commit: [2e43036@deploy](https://github.com/inventaire/inventaire-deploy/commit/2e43036)

## Other Noteworthy Stuff
*  **Barcode Scanner/Firefox**: Firefox for Android 57 seems to have fixed the issue with autofocus while using the scanner

<hr>

[[October 2017|← October 2017]] - [[News|All News]] - [[December 2017|December 2017 →]]