# Sources de données — Grove / Tullaghanbrogue (Co. Kilkenny, Irlande)

Inventaire opérationnel des sources exploitables pour l'étude patrimoniale du site.

**Ce dossier ne contient aucune recommandation de prospection.** Utiliser un détecteur de métaux pour rechercher des objets archéologiques sans consentement ministériel est une infraction pénale en Irlande (National Monuments (Amendment) Act 1987, s.2), et ce lieu est un complexe de monuments enregistrés.
Cadre légal détaillé → `CADRE_LEGAL.md` (écrit par un autre agent, non repris ici).

**Date d'inventaire** : 2026-09-28
**Zone** : townland de **Grove** (« An Garrán »), paroisse civile de **Tullaghanbrogue**, barony de **Shillelogher**, comté de **Kilkenny**.
**Coordonnées** : 52.600940°N / -7.328378°W (ITM 645497 E / 650176 N).
**Monument de référence** : SMR **KK023-031004-** (« Moated site »), Municipal District Callan–Thomastown.

**Clé de lecture** :
- **[FAIT]** = sourcé et testé cette session, utilisable tel quel.
- **[À VÉRIFIER]** = plausible, non confirmé cette session.
- **[HYPOTHÈSE]** = déduction sans source, à ne pas traiter comme un fait.

**Méthode** : chaque source a été testée par requête réelle depuis ce conteneur (code HTTP `curl`), sauf mention contraire explicite. La mention « code HTTP non revérifié cette session » signale un fait ou une URL identifiés par recherche documentaire, non repassés au test direct. Aucune URL n'est inventée.

---

## Tableau récapitulatif

| Source | Contenu utile | Format/Protocole | Statut | Accessibilité (test conteneur, 2026-09-28) | Licence/Attribution |
|---|---|---|---|---|---|
| **Archéologie** |
| SMR Open Data (National Monuments Service) | Fiche complète KK023-031004- et 133 autres sites ≤ 5 km | ArcGIS FeatureServer, REST/JSON | [FAIT] | `services-eu1.arcgis.com` → HTTP 200, requête réelle `where=SMRS='KK023-031004-'` testée | CC BY 4.0 / National Monuments Service, Government of Ireland |
| SMR Zones (zones de notification) | Polygones R139005 (~4,6 ha), R139014 (~1,4 ha), etc. | ArcGIS FeatureServer `SMRZoneOpenData` | [FAIT] | HTTP 200 | CC BY 4.0 / NMS |
| Historic Environment Viewer | Visualisation web SMR + RMP + zones | Webapp ArcGIS Online | [FAIT] | `maps.archaeology.ie` → 301 → `heritagedata.maps.arcgis.com` HTTP 200 | NMS |
| RMP_extents | Repérage feuille RMP papier + lien image | ArcGIS FeatureServer | [FAIT] | HTTP 200 ; la requête **spatiale** au point renvoie la planche `023-` (champ `county` = « Co. Kilkenny », pas « KILKENNY ») avec le lien vers la carte scannée, page 24 | NMS |
| **RMP de Kilkenny (1996) — manuel + cartes scannés** | **Liste légale** des monuments protégés (s.12 loi 1994) : Grove = KK023-030, KK023-031, KK023-032 (page « 023- 3 » du manuel) | PDF (manuel OCRisé 169 p. ; cartes 48 p.) | [FAIT] | Manuel <https://www.archaeology.ie/app/uploads/2025/03/Archaeology-RMP-Kilkenny-Manual-1996-0022.pdf> et carte <https://www.archaeology.ie/app/uploads/2025/03/Archaeology-RMP-Kilkenny-Map-1996-0023.pdf> : HTTP 200, téléchargés et lus par l'orchestrateur le 2026-09-28 ; exemplaires papier aussi au Planning Department du comté (CDP) | NMS / Government of Ireland |
| NIAH — buildingsofireland.ie + service | Bâti protégé post-1700 à proximité | Site + ArcGIS FeatureServer `NIAHBuildingsOpenData` | [FAIT] | `buildingsofireland.ie` HTTP 200 ; service HTTP 200, requête fenêtre ~7×6 km → 12 entités | NIAH / Dept. Housing, LG & Heritage |
| excavations.ie | Base de rapports de fouilles (1970-présent) | Site web, recherche mot-clé | [FAIT] | HTTP 200 ; recherche « Tullaghanbrogue » → 0 résultat (testé) | Wordwell Ltd. |
| National Museum of Ireland — fichiers topographiques | Objets/trouvailles enregistrés par townland | Consultation sur demande (Irish Antiquities Division) | [À VÉRIFIER procédure] | `museum.ie` HTTP 302→200 | Public |
| heritagemaps.ie | Portail cartographique Heritage Council (projets par comté) | Webapp | [FAIT] | HTTP 200 | Heritage Council |
| Kilkenny County Development Plan (volet archéologie) | Politique RMP, renvoi à archaeology.ie | HTML/PDF | [FAIT ancienne version / À VÉRIFIER version en vigueur] | `kilkennycoco.ie/cdp/.../vol1sec9.htm` HTTP 200 ; plan 2021-2027 sur `consult.kilkenny.ie` → connexion refusée [MACHINE LOCALE] | Kilkenny County Council |
| **Cartes anciennes** |
| Down Survey 1655-6 | Carte de baronnie Shillelogher, « Tullohaune »=Grove, terriers 1641/1670 | Site interactif (prévu) | [À VÉRIFIER — migration de domaine] | `downsurvey.tcd.ie` bloqué SSL [MACHINE LOCALE] ; `downsurvey.tchpc.tcd.ie` → 301 → `www.downsurvey.ie` HTTP 200 mais contenu réduit (page « Home » seule), anciens chemins en 404 | Public / TCD |
| OS 6-inch (1839) / 25-inch (~1900) — GeoHive/Tailte | Cadastre + bâti pré-remembrement | Visionneuse web historique | [À VÉRIFIER] | `webapps.geohive.ie` [MACHINE LOCALE, CONNECT échoué] ; `www.geohive.ie` HTTP 200 (portail) ; `osi.maps.arcgis.com` webapp HTTP 200 | Tailte Éireann, licence exacte non relue |
| National Library of Scotland — maps.nls.uk | OS Ireland 6-inch géoréférencé, 1829-1969 | Viewer + tuiles | [À VÉRIFIER — protection anti-bot] | `/os/6inch-ireland/` HTTP 405 ; `/copyright.html` → CAPTCHA AWS WAF | CC BY 3.0 pour l'usage du viewer (restrictions commerciales sur certaines couches) — via recherche, page d'origine non lue |
| Grand Jury maps du comté de Kilkenny | Cartographie de comté XVIIIe s. | Archives papier | [HYPOTHÈSE] | Non localisé en ligne cette session | — |
| Taylor & Skinner, *Maps of the Roads of Ireland* (1778) | Routes et gentry seats en 1777-78 | Atlas numérisé | [FAIT existence] | `archive.org/details/TaylorSkinnerMapsOfTheRoadsOfIrelandSurveyed1777` | Domaine public |
| **Imagerie** |
| Orthophotos Tailte Éireann | Ortho couleur courante | WMS/WMTS (à confirmer) | [À VÉRIFIER] | Portail `tailte.ie/services/geohive/` HTTP 200 ; endpoint tuile non testé directement | Tailte Éireann |
| Esri World Imagery / Bing / Google | Fond satellite générique | Tuiles commerciales | [HYPOTHÈSE licence] | Usage courant ; conditions par fournisseur non relues cette session | Propriétaire — pas de réutilisation libre |
| Photos aériennes historiques OSi (1995/2000/2005) | Cliché avant infrastructures récentes | Archives OSi/Tailte | [HYPOTHÈSE] | Aucun service en ligne localisé cette session | Tailte Éireann |
| CUCAP (Cambridge University Collection of Aerial Photography) | Obliques, survols Irlande 1951-1973 | Catalogue en ligne | [FAIT existence / À VÉRIFIER couverture Grove] | `cambridgeairphotos.com` HTTP 200 (catalogue non interrogé pour Grove précisément) | Cambridge University, droits d'usage à vérifier par cliché |
| **Relief et LiDAR** |
| Index de couverture LiDAR GSI/OPW/TII | Qui a volé quoi, où, quand, sous quelle licence | ArcGIS MapServer REST (5 couches testées) | [FAIT — 0 couverture au point exact] | `gsi.geodata.gov.ie/server/rest/services/Lidar/...` HTTP 200 (le endpoint REST répond alors que le portail racine renvoie 403) | CC BY 4.0 / GSI & OPW |
| data.gov.ie — Open Topographic Lidar Data | Fiche nationale, organismes contributeurs, 2015-2021 | CKAN API JSON | [FAIT] | `data.gov.ie/api/3/action/package_show` HTTP 200 | CC BY 4.0 |
| Copernicus GLO-30 / EU-DEM | MNT de repli si LiDAR absent | GeoTIFF téléchargeable | [HYPOTHÈSE] | Non testé cette session | Copernicus / EEA, libre |
| **Toponymie** |
| logainm.ie | Formes gaéliques (« An Garrán » = Grove), dossiers archivistiques | Site + recherche protégée (ALTCHA) | [FAIT] fiches (26411 = Grove relue) / [À VÉRIFIER] recherche automatisée | Accueil HTTP 200 ; avec `curl`, recherche et fiches → défi anti-bot ALTCHA ; avec WebFetch ou un navigateur, les fiches se lisent (voir §5.1) | Placenames Branch (DCHG) / Fiontar, DCU |
| townlands.ie | Limites de townland (OSM), « Grove » = 328 ac. 2 roods 26 perches | Site + données OSM | [FAIT] | Accueil + page licence HTTP 200 ; pages de townland individuelles → 403 dans ce conteneur | **ODbL** (Open Data Commons Open Database License) — lu sur `/page/copyright/` |
| OS Name Books de Kilkenny | Formes de noms de lieux relevées ~1830 | Numérisation partielle | [HYPOTHÈSE] | Non localisé précisément cette session | — |
| **Archives et imprimés** |
| O'Flanagan 1930 — OS Letters, Kilkenny 1839 | Description de « Tullaghanbrogue » par les topographes de l'OS | Typescript numérisé | [FAIT existence / MACHINE LOCALE lecture] | `askaboutireland.ie` HTTP 403 dans ce conteneur ; original salle de lecture RIA | Public |
| Griffith's Valuation (1847-1864) | Occupants du townland de Grove au milieu XIXe s. | Livres numérisés + cartes | [FAIT existence / MACHINE LOCALE accès] | `askaboutireland.ie` HTTP 403 ; `irishgenealogy.ie` HTTP 403 (les deux bloqués ici) | Public / Valuation Office |
| Valuation Office — Cancelled Books | Suivi des occupants 1850s-1980s | PDF couleur par comté, non indexés | [FAIT existence] | `historyireland.com/valuation-office-cancelled-books/` HTTP 200 ; conservation Tailte Éireann | Public |
| Census 1901 / 1911 | Recensement nominatif du townland de Grove | Base de recherche NAI | [À VÉRIFIER — MACHINE LOCALE] | `census.nationalarchives.ie` bloqué | Public / National Archives of Ireland |
| Registry of Deeds | Transactions foncières enregistrées depuis 1708 | Index + mémoriaux, salle de lecture Dublin | [HYPOTHÈSE procédure] | Non testé cette session | Public / Tailte Éireann |
| Calendar of Ormond Deeds | Actes de la seigneurie d'Ormond (dont Kilkenny) | Volume numérisé, éd. Curtis/IMC | [FAIT] | `archive.org/details/calendaroformond03ormo` (vol. 3) | Domaine public |
| Irish Fiants (Tudor) | Concessions royales XVIe s. | Reports of the Deputy Keeper (repro.) | [À VÉRIFIER] | Non localisé sur archive.org avec les requêtes testées cette session | — |
| *Inquisitionum...repertorium* (Hardiman, 1826) | Inquisitions post-mortem (manoir de Tullaghanbrogue, 1607/1626-7) | 2 volumes numérisés | [FAIT existence / À VÉRIFIER vol. I = Lagenia] | `archive.org/details/india.history.resource.77918` (Vol. I) et `.77919` (Vol. II) | Domaine public |
| Civil Survey 1654-6 | Description des terres, paroisse par paroisse | Volumes IMC (Simington) | [À VÉRIFIER — comté de Kilkenny probablement absent] | Seul un volume Waterford avec appendice partiel « Kilkenny city and liberties » identifié | Public |
| Virtual Record Treasury of Ireland | Reconstitution des archives détruites en 1922 | Portail de recherche numérique | [FAIT accessible / À VÉRIFIER contenu] | `virtualtreasury.ie` HTTP 200 | Public |
| Estate papers Desart/Cuffe | Titres du « manor of Tullaghanbroge » après 1666 | Fonds NLI + landedestates.ie | [FAIT sites accessibles / À VÉRIFIER fonds précis] | `landedestates.ie` HTTP 200 ; `nli.ie` HTTP 200 ; recherche ciblée non aboutie cette session | Public |
| Carrigan 1905, *Diocese of Ossory*, vol. 3 | Référence SMR principale (p. 385-9) | Livre numérisé | [FAIT] | `archive.org/details/historyantiquiti0003revw` (vol. 3 confirmé) | Domaine public |
| Orpen 1909, JRSAI 39, « Motes and Norman castles in Ossory » | Motte attribuée au manoir de Tullaghanbrogue, St Leger | Article de revue | [FAIT existence JSTOR / À VÉRIFIER lien exact] | `jstor.org/journal/transkilkarchsoc` HTTP 200 (revue mère existante ; lien stable de l'article JRSAI non récupéré) | JSTOR / RSAI |
| O'Kelly 1969, *Place-names of Co. Kilkenny* | Étymologie des toponymes du comté | Ouvrage imprimé | [HYPOTHÈSE] | Non testé, cité par le SMR | — |
| Old Kilkenny Review | Articles annuels (Kilkenny Archaeological Society, depuis 1948) | Revue + index en ligne | [FAIT] | `kilkennyarchaeologicalsociety.ie/okr-index/` HTTP 200 | Kilkenny Archaeological Society |
| **Folklore** |
| Schools' Collection (dúchas.ie) | Récits collectés 1937-39 dans les écoles de la paroisse | Manuscrits numérisés | [FAIT accessible / À VÉRIFIER école précise] | HTTP 200 (→ `/en`) ; navigation par comté/LogainmID confirmée, école de Tullaghanbrogue non localisée | National Folklore Collection UCD, licence non relue [À VÉRIFIER] |
| Main Manuscript Collection | Collecte adulte pré-1937, peu numérisée | Manuscrits (UCD) | [HYPOTHÈSE] | Non testé | UCD |
| **Contexte naturel** |
| GSI — géologie (substrat, dépôts quaternaires) | Carte 1:100 000 | WMS (`gis.epa.ie/geoserver`) | [FAIT service / À VÉRIFIER unité exacte sous Grove] | `GetCapabilities` HTTP 200 | CC BY 4.0 (GSI) |
| Teagasc/EPA — Irish Soil Information System | Séries de sol (213 séries), drainage | WMS `EPA:SOIL_SISNationalSoils` | [FAIT] | HTTP 200 | CC BY 4.0 |
| EPA — hydrographie (WFD) | Cours d'eau le plus proche : **Ennisnag Stream** | WFS `EPA:WFD_RiverWaterBodiesActive` | [FAIT] | HTTP 200 ; requête bbox réelle → entité « ENNISNAG STREAM_010 » (EU_CD IE_SE_15E020700) | Public / EPA |
| **Sources humaines** (contacts institutionnels publics) |
| National Monuments Service | Autorité de tutelle SMR/RMP, consentement ministériel | `archaeology.ie` | [FAIT] | Accessible (confirmé ce jour) | Institution publique |
| Heritage Officer, Kilkenny County Council | Interlocuteur patrimoine du comté | `kilkennycoco.ie` | [FAIT] | → `/eng/` HTTP 200 | Institution publique |
| Kilkenny Archaeological Society (Rothe House) | Mémoire locale, bibliothèque, Old Kilkenny Review | `rothehouse.com` / `kilkennyarchaeologicalsociety.ie` | [FAIT] | HTTP 200 (les deux) | Institution associative |
| Sociétés d'histoire locale (Callan, Kilmanagh, Danesfort...) | Mémoire de proximité | À identifier | [HYPOTHÈSE] | Non identifiées nommément cette session | — |
| Paroisse de Tullaghanbrogue/Callan | Registres, mémoire orale | Contact paroissial | [HYPOTHÈSE] | Non identifié cette session | — |
| National Museum of Ireland | Objets et fichiers topographiques | `museum.ie` | [FAIT] | HTTP 302→200 | Institution publique |

---

## Détail des sources

### 1. Archéologie

#### 1.1 SMR Open Data — la source la plus riche pour ce lieu précis

**Service** : `https://services-eu1.arcgis.com/HyjXgkV6KGMSF3jt/ArcGIS/rest/services/SMROpenData/FeatureServer/0`

**Test réel effectué cette session** :
```
GET .../query?where=SMRS='KK023-031004-'&outFields=SMRS,MONUMENT_CLASS,TOWNLAND,COUNTY&f=json
→ HTTP 200, réponse JSON complète (coordonnées ITM 645497/650176, WEB_NOTES, REFERENCES_)
```

**Description lue directement dans le service** (`serviceDescription`) :
> « *This Archaeological Survey of Ireland dataset is published from the database of the National Monuments Service Sites and Monuments Record (SMR). Open Data Bulk Data Downloads (version date: 01/12/2025)* »

La date de version 01/12/2025 correspond à celle citée dans le brief.

**Licence** : Creative Commons Attribution 4.0 International, attribution « National Monuments Service, Government of Ireland » — lue sur `archaeology.ie/open-data` (HTTP 301, accessible).

**Statut** : [FAIT]

#### 1.2 SMR Zones — ce qu'une zone représente juridiquement

Service jumeau : `SMRZoneOpenData` FeatureServer. Son `serviceDescription`, lu cette session, clarifie un point souvent mal interprété :
> « *SMRZones represent an area around each monument... This area does not define the extent of the monument, nor does it define a buffer area beyond which ground disturbance should not take place... It is not a constraint area for screening.* »

Traduction : la zone SMR n'est ni le périmètre du monument ni une zone de contrainte d'examen — seulement l'aire dans laquelle le monument est réputé se trouver.

Les fichiers déjà présents dans le scratchpad (`smr_5km.geojson`, `smr_3km.geojson`, `smrzones_5km.geojson`) sont des extraits ponctuels de ces mêmes services. Pratiques pour cette session, mais la source pérenne à citer reste le service ArcGIS en direct, pas l'extrait local.

**Statut** : [FAIT]

#### 1.3 RMP_extents et le RMP de Kilkenny 1996 (manuel + cartes légaux)

Champs lus dans le schéma du service `RMP_extents` : `image_url`, `county`, `SHEET_NO`, `pdf_page_no`.

- Une requête attributaire `county='KILKENNY'` renvoie 0 résultat : le champ stocke en réalité la valeur « Co. Kilkenny ».
- Une requête **spatiale** au point exact (lon/lat WGS84) fonctionne : elle renvoie la planche `023-`, `pdf_page_no` 24, et un `image_url` vers la carte RMP scannée de 1996.

Le **manuel RMP de Kilkenny (1996)** — la liste légale des monuments protégés au sens de l'art. 12 de la loi de 1994 — est publié en PDF OCRisé sur archaeology.ie, avec la carte correspondante :
- Manuel : <https://www.archaeology.ie/app/uploads/2025/03/Archaeology-RMP-Kilkenny-Manual-1996-0022.pdf>
- Carte : <https://www.archaeology.ie/app/uploads/2025/03/Archaeology-RMP-Kilkenny-Map-1996-0023.pdf>
- Les deux répondent HTTP 200 ; téléchargés et lus par l'orchestrateur le 2026-09-28.

La page « 023- 3 » du manuel liste, pour **GROVE** :
- `KK023-030---` — « Ecclesiastical remains » (avec les sous-entrées -03001 à -03005)
- `KK023-03101-` — « Earthwork(s) »
- `KK023-032---` — « Moated site »

C'est la preuve documentaire que le complexe est bien inscrit au RMP légal — pas seulement au SMR, qui est la base de connaissance. Le RMP est la liste qui déclenche l'obligation légale de notification (voir `CADRE_LEGAL.md`, §1). Exemplaires papier consultables aussi au Planning Department du comté (feuilles « Sheet 1-16, 17-33, 34-47 », cf. §1.6 ci-dessous).

**Statut** : [FAIT]

#### 1.4 NIAH

Requête testée sur une fenêtre d'environ 7×6 km centrée sur Grove (`returnCountOnly=true`) → **12 entités**.
Le service fonctionne, mais aucune requête n'a isolé le townland de Grove lui-même — à affiner avec une géométrie plus précise si besoin.

**Statut** : [FAIT]

#### 1.5 excavations.ie — correction par rapport au brief

**excavations.ie est accessible** (HTTP 200, contenu réel récupéré). Le brief le listait comme bloqué ; un test direct cette session montre le contraire, y compris sur le moteur de recherche interne :
```
GET https://excavations.ie/?s=Tullaghanbrogue → HTTP 200
"Sorry, but nothing matched your search terms" → 0 rapport de fouille sous ce nom
```

Pied de page lu : « *Copyright © 2026, Wordwell Ltd., Excavations.ie* ».

**Statut** : [FAIT] (accès), [FAIT] (0 résultat pour ce townland)

#### 1.6 Kilkenny County Development Plan

La version consultée (`kilkennycoco.ie/cdp/cdpvol1/vol1/vol1sec9.htm`, HTTP 200) est probablement antérieure au plan 2021-2027 actuellement en révision sur `consult.kilkenny.ie` (chapitre 9.3.1, « Archaeological Heritage »).

Cette dernière URL a échoué (connexion réinitialisée) depuis ce conteneur → [MACHINE LOCALE].

Le texte lu recommande de vérifier systématiquement les mises à jour sur `archaeology.ie`.

**Statut** : [FAIT version ancienne / À VÉRIFIER version en vigueur]

---

### 2. Cartes anciennes

#### 2.1 Down Survey — migration de domaine constatée

- `downsurvey.tcd.ie` échoue en TLS depuis ce conteneur (certificat ne correspondant pas au nom d'hôte demandé) → **[MACHINE LOCALE]**.
- `downsurvey.tchpc.tcd.ie` redirige (HTTP 301) vers un troisième domaine, `www.downsurvey.ie` (HTTP 200).
- Ce dernier ne présente qu'une page WordPress minimale (« Home », aucun autre lien détecté) ; les anciens chemins connus (`down-survey-maps.php`) renvoient 404.

**Conclusion honnête** : le projet Down Survey existe et est largement documenté par des tiers (TCD, Wikipedia), mais son visualisateur interactif — carte de la baronnie de Shillelogher, où figure « Tullohaune »=Grove, terriers de propriétaires 1641/1670 — n'a **pas** pu être confirmé fonctionnel depuis ce conteneur ce jour. Le site est peut-être en cours de migration ; à retester en navigateur.

**Statut** : [À VÉRIFIER]

#### 2.2 OS 6-inch / 25-inch — GeoHive, Tailte, ArcGIS Online

- `webapps.geohive.ie/mapviewer/` (le viewer historique cité par la documentation Tailte) échoue avec `CONNECT tunnel failed, 502` → [MACHINE LOCALE], conforme au brief.
- `www.geohive.ie` (« GeoHive Hub ») répond HTTP 200 mais son contenu n'a pas été exploré en profondeur.
- `osi.maps.arcgis.com/apps/webappviewer/index.html?id=bc56a1cf08844a2aa2609aa92e89497e` répond HTTP 200 et n'est pas concerné par le blocage de `webapps.geohive.ie` — piste à privilégier en navigateur.

Aucun endpoint XYZ/WMS ouvert n'a été identifié et testé directement cette session pour les fonds historiques Tailte.

**Statut** : [À VÉRIFIER]

#### 2.3 National Library of Scotland

La collection existe bien pour l'Irlande : « *Ordnance Survey Maps Six-Inch Ireland, 1829-1969* » (`maps.nls.uk/os/6inch-ireland/`).

Accès direct entravé depuis ce conteneur :
- `/os/6inch-ireland/` → HTTP 405
- `/copyright.html` → CAPTCHA AWS WAF (« *Human Verification* », JavaScript requis)

→ à traiter comme **[MACHINE LOCALE]**.

Licence (via recherche documentaire, page d'origine non lue) : Creative Commons Attribution 3.0 Unported pour l'usage du viewer, avec restrictions commerciales possibles sur les feuilles encore sous droits (au-delà de 1955 environ) — à confirmer en navigateur.

**Statut** : [À VÉRIFIER]

#### 2.4 Taylor & Skinner 1778

Confirmé numérisé sur archive.org : identifiant `TaylorSkinnerMapsOfTheRoadsOfIrelandSurveyed1777`.

Utile pour repérer la route Kilkenny–Callan et les gentry seats mentionnés à l'époque ; d'éventuelles mentions autour de Tullaghanbrogue/Grove restent à vérifier page par page.

**Statut** : [FAIT existence]

#### 2.5 Grand Jury maps de Kilkenny

Non localisées en ligne cette session — probablement des documents d'archives papier uniquement (NLI, Kilkenny Local Studies).

**Statut** : [HYPOTHÈSE]

---

### 3. Imagerie

Le portail `tailte.ie/services/geohive/` et la page produit `tailte.ie/map-shop/professional-map-products/historic-maps-and-data/` répondent tous deux HTTP 200, mais aucun endpoint de tuiles orthophoto n'a été testé directement (pas d'identifiant de couche confirmé, à la différence des flux IGN français déjà documentés pour Armous).

Les fonds Esri World Imagery / Bing / Google restent des fonds satellite génériques à conditions d'usage propriétaires (aucune page de licence relue cette session) — utilisables comme fond de carte, jamais comme donnée réutilisable librement.

Les photographies aériennes historiques OSi (1995/2000/2005) évoquées dans le brief n'ont pas de service en ligne identifié cette session.

**CUCAP** confirme avoir « *several thousand images taken over Ireland (1951-73)* ». Son catalogue de recherche, `cambridgeairphotos.com`, répond HTTP 200. Aucune requête n'a été passée dans le catalogue lui-même pour vérifier la présence d'un cliché oblique sur Grove/Tullaghanbrogue précisément → **[À VÉRIFIER]**, mais la piste est réelle et gratuite à interroger (recherche par townland/comté).

---

### 4. Relief et LiDAR

C'est le point le plus travaillé de cette session, avec des requêtes spatiales réelles.

**Constat de méthode important, non documenté dans le brief** : le portail `gsi.geodata.gov.ie` (racine ArcGIS Enterprise) renvoie HTTP 403, **mais ses services REST individuels répondent normalement**. Le chemin `https://gsi.geodata.gov.ie/server/rest/services/Lidar/<NOM>/MapServer` fonctionne pour au moins 5 couches d'index de couverture :

- `IE_GSI_LiDAR_Coverage_GSI_Phase2_IE26_ITM` (GSI, 2018)
- `IE_GSI_LiDAR_Coverage_OPW_IE26_ITM` (OPW national)
- `IE_GSI_LiDAR_Coverage_TII_IE26_ITM` (Transport Infrastructure Ireland, corridors routiers)
- `IE_GSI_LiDAR_Coverage_OPW_NASC_IE26_ITM` (OPW National Aerial Survey Contract, 2011, 2 m)
- `IE_GSI_LiDAR_Coverage_GSI_DCHG_DP_IE26_ITM` (GSI / Dept. Culture-Heritage / Discovery Programme)

Chaque polygone porte les champs `DATA_URL`, `DATA_NAME`, `LICENCE`, `RESOLUTION`, `DATECAPTUR`, `OWNER`, `SURVEYOR`, `RMS_ERROR`. Attribution lue textuellement dans le champ `LICENCE` :
> « *Contains Irish Public Sector Data (Geological Survey Ireland & the Office of Public Works) licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) licence.* »

**Test au point exact du monument** (ITM 645497, 650176) dans les 5 couches → `"features":[]` à chaque fois. **Aucune couverture confirmée.**

**Test en boîte de 10 km** sur la couche OPW-NASC (2011, 2 m) : des tuiles de 2×2 km bien réelles existent tout autour —
- `OPW_2149`/`OPW_2150` à l'E 646-648 / N 652-656
- `OPW_3414`/`OPW_3417`/`OPW_3418` à l'E 640-644 / N 644-648

mais **aucune tuile ne couvre la case E 644-648 × N 648-652, qui contient précisément le site**. Un manque de couverture localisé apparaît donc dans cette génération de données (2011-2018).

Le jeu national fédérateur `open-topographic-lidar-data` sur `data.gov.ie` (CKAN `package_show`, HTTP 200) confirme que ces mêmes contributeurs — GSI, DCHG, Discovery Programme, Heritage Council, TII, NYU, OPW, Westmeath CoCo — couvrent la période 2015-2021 sous licence CC BY 4.0.

**[FAIT] Contre-vérification de l'orchestrateur (2026-09-28)** : le dossier REST `Lidar` de GSI publie 9 services d'index. Chacun a été interrogé au point exact (ITM 645497/650176, `inSR=2157`, sur le bon numéro de couche) : OPW_NASC/3, OPW/3, GSI_Phase2/12, TII/0, GSI_DCHG_DP/0, OPW_Cork/2, NYU_Dublin/4, WH_CoCo/0 et Photogrammetry_GSI/3. **Les 9 renvoient 0 entité.** Aucune couverture LiDAR ou photogrammétrique ouverte n'est donc indexée sur Grove. **[À VÉRIFIER]** Reste possible un programme postérieur à ces index (après 2021) ou un levé non versé à GSI.

À défaut, Copernicus GLO-30 / EU-DEM (résolution ~25-30 m) donnerait un contexte de pente très général, mais ne permettrait aucune détection de micro-relief (fossé, motte, levée) — non testé cette session.

**Statut global** : [FAIT] pour la méthode et l'absence de couverture dans les 5 couches testées ; [À VÉRIFIER] pour l'exhaustivité (couches non testées).

---

### 5. Toponymie

#### 5.1 logainm.ie

`logainm.ie` répond HTTP 200 sur sa page d'accueil. La fiche du jeu de données correspondant sur `data.gov.ie` confirme que le site donne accès à « *archival records and placenames research conducted by the State* ».

En revanche, sa recherche interne (formulaire `action="/ga/s"`, paramètre `txt`) redirige systématiquement vers `/ga/altcha/verify?returnUrl=...` — un défi anti-robot ALTCHA (preuve de travail résolue en JavaScript) — qui empêche toute extraction automatisée du numéro d'entrée pour « Tullaghanbrogue » ou « Grove » depuis ce conteneur.

**Procédure recommandée** :
1. Recherche manuelle en navigateur sur logainm.ie (le défi se résout normalement pour un navigateur réel).
2. Une fois l'identifiant numérique obtenu, la fiche se lit à `logainm.ie/en/<ID>`.
3. Croisement possible avec le Schools' Collection via `duchas.ie/en/cbes/stories?LogainmID=<ID>`.

**Mise à jour de l'orchestrateur (2026-09-28)** : les fiches passent le défi quand on les lit avec l'outil WebFetch (un navigateur réel aussi), mais pas avec `curl`. Fiche relue : **[26411](https://www.logainm.ie/en/26411) = « An Garrán / Grove »**, townland, barony *Síol Fhaolchair / Shillelogher*, paroisse civile ***Tulchán Bróg / Tullaghanbrogue***, sens « the grove ». Les autres identifiants relevés par le lot Toponymie sont dans `TOPONYMIE.md` et `data/toponymes.geojson`.

**Statut** : [FAIT] pour la lecture des fiches (26411 relue) ; [À VÉRIFIER] pour la recherche automatisée par nom (bloquée par ALTCHA avec `curl`)

#### 5.2 townlands.ie

Confirmé par recherche documentaire : Grove (barony Shillelogher, paroisse Tullaghanbrogue) fait 328 acres, 2 roods et 26 perches, nom irlandais « An Garrán ».

Page de licence lue directement (HTTP 200) :
> « *Since this is derived from OpenStreetMap data, it's under the same licence as that. Namely the Open Data Commons Open Database License (ODbL). Consult the OpenStreetMap Copyright guide for more information.* »

Dernière mise à jour affichée sur le site : 24 avril 2022.

Les pages de townland individuelles renvoient HTTP 403 dans ce conteneur (chemin exact non confirmé pour Grove).

**Statut** : [FAIT]

#### 5.3 OS Name Books de Kilkenny

Non localisés précisément cette session.

**Statut** : [HYPOTHÈSE]

---

### 6. Archives et imprimés

#### 6.1 Le bloc askaboutireland / irishgenealogy — bloqué mais central

Les blocages `askaboutireland.ie` (HTTP 403, confirmé à nouveau cette session) et `irishgenealogy.ie` (HTTP 403, nouveau constat) touchent un nombre important de sources de premier plan :
- **Griffith's Valuation** (occupants du townland de Grove, milieu XIXe s.)
- Les **OS Letters** d'O'Flanagan 1930 (section Kilkenny 1839, qui décrit Tullaghanbrogue)
- Une partie du **Carrigan** numérisé

Toutes restent **[MACHINE LOCALE]** pour un accès direct. L'original des OS Letters se consulte aussi en salle de lecture de la Royal Irish Academy.

#### 6.2 Valuation Office — Cancelled Books

Conservés désormais par Tailte Éireann (transfert 2023 depuis Abbey Street vers le Distillery Building), numérisés par comté en PDF non indexés — consultables sur demande.

Procédure décrite sur `historyireland.com/valuation-office-cancelled-books/` (HTTP 200, lu cette session).

**Statut** : [FAIT existence]

#### 6.3 Recensements et Registry of Deeds

- **Census 1901/1911** : `census.nationalarchives.ie` reste bloqué (conforme au brief). Aucune alternative gratuite équivalente identifiée cette session → **[MACHINE LOCALE]**.
- **Registry of Deeds** : non testé cette session → [HYPOTHÈSE] pour la procédure exacte.

#### 6.4 Trois textes de référence confirmés sur archive.org

Trois textes directement cités par le SMR ont été localisés avec leur identifiant exact :

**Carrigan 1905**, *The History and Antiquities of the Diocese of Ossory*, vol. 3
→ `archive.org/details/historyantiquiti0003revw` (champ `volume: "3"` confirmé dans les métadonnées)
→ contient les pages 385-9 citées par le SMR pour l'église et le manoir de Tullaghanbrogue.
**Statut** : [FAIT]

***Inquisitionum in Officio Rotulorum Cancellariae Hiberniae asservatarum Repertorium*** (Hardiman, 1826)
→ Vol. I : `archive.org/details/india.history.resource.77918` · Vol. II : `.77919`
→ les inquisitions de 1607 et 1626-7 citées dans le brief (Edmund Sentleger, « of Tullaghanbroge ») proviennent de ce répertoire.
→ la correspondance usuelle Vol. I = Lagenia (Leinster) n'a **pas** été confirmée dans les métadonnées lues cette session.
**Statut** : [FAIT existence des deux volumes / À VÉRIFIER Vol. I = Lagenia]

**Calendar of Ormond Deeds** (éd. Curtis, Irish Manuscripts Commission)
→ seul le volume 3 a été retrouvé sur archive.org (`calendaroformond03ormo`) ; les autres volumes publiés (1932-1943) n'ont pas été localisés avec les requêtes testées.
**Statut** : [FAIT vol. 3 / À VÉRIFIER autres volumes]

#### 6.5 Sources non confirmées cette session

- **Irish Fiants** : non retrouvés sur archive.org avec les formulations testées (« irish fiants », « fiants ») → [À VÉRIFIER]. Probablement disponibles sous le titre des *Reports of the Deputy Keeper of the Public Records in Ireland* (7e-22e rapports, XIXe s.), non recherchés sous ce titre cette session.
- **Civil Survey** : ne semble **pas** avoir de volume dédié au comté de Kilkenny. Seul un volume Waterford (vol. VI) avec un appendice partiel « Kilkenny city and liberties » a été identifié → à traiter comme absent pour le comté entier sauf contre-preuve.

#### 6.6 Estate papers, JSTOR, Old Kilkenny Review

- `virtualtreasury.ie` (HTTP 200) et les fonds NLI/landedestates.ie (HTTP 200 chacun) sont accessibles pour rechercher les papiers de l'estate Desart/Cuffe (le « manor of Tullaghanbroge » devenu « Cuffe's grove » en 1666). Aucune recherche ciblée n'a abouti avec les chemins testés cette session ; la navigation par formulaire de recherche reste à faire en interface.
- **Orpen 1909** (JRSAI 39) : la revue existe sur JSTOR (`jstor.org/journal/transkilkarchsoc`, HTTP 200) ; le lien stable exact de l'article de 1909 n'a pas été récupéré.
- **Old Kilkenny Review** : index en ligne confirmé accessible (`kilkennyarchaeologicalsociety.ie/okr-index/`, HTTP 200).
- **O'Kelly 1969** : non testé, cité par le SMR uniquement → [HYPOTHÈSE].

---

### 7. Folklore

`duchas.ie` répond HTTP 200 (redirection vers `/en`).

Structure de navigation du **Schools' Collection**, confirmée par recherche documentaire :
- par comté (`/en/cbes/volumes?CountyID=...`)
- par école (`/en/cbes/schools`)
- par croisement direct avec un identifiant logainm (`/en/cbes/stories?LogainmID=...`)

Aucun identifiant précis d'école pour la paroisse de Tullaghanbrogue n'a été trouvé cette session — le site est une application JavaScript, peu exploitable par simple `curl` → **[À VÉRIFIER en navigateur]**.

Les conditions de réutilisation exactes (habituellement une licence Creative Commons non-commerciale pour ce type de collection) n'ont pas été relues sur le site lui-même cette session → **[À VÉRIFIER]**, à confirmer avant toute citation longue.

La Main Manuscript Collection (collecte adulte pré-1937) est peu numérisée et n'a pas été testée → [HYPOTHÈSE].

---

### 8. Contexte naturel

Le géoserveur `gis.epa.ie/geoserver/EPA/` héberge à la fois la géologie GSI, les sols Teagasc/EPA et l'hydrographie — tous testés et fonctionnels (WMS/WFS, HTTP 200), sous licence Creative Commons Attribution 4.0.

- **Sols** : couche `EPA:SOIL_SISNationalSoils` (213 séries de sol identifiées au niveau national, selon la documentation Teagasc). **[FAIT]**
- **Géologie** : substrat 1:100 000 accessible, mais l'unité exacte sous Grove n'a pas été extraite (`GetCapabilities` confirmé seulement) → **[À VÉRIFIER]**.

**Découverte la plus utile de cette section** : une requête WFS réelle sur `EPA:WFD_RiverWaterBodiesActive` (bbox centrée sur le site) identifie un cours d'eau nommé :

> **Ennisnag Stream** — `NAME: "ENNISNAG STREAM_010"`, `EU_CD: "IE_SE_15E020700"`, longueur 32 km, bassin « 184 Nore », unité de gestion « IE_SE_Kings », `LocalAuthority: "KILKENNY COUNTY COUNCIL"`.

C'est le cours d'eau nommé le plus proche identifié par l'EPA dans le voisinage immédiat des coordonnées du site.

**[À VÉRIFIER]** : la correspondance exacte entre ce tronçon nommé et le « meandering stream » mentionné par le SMR comme longeant le monument au N avant d'être redressé (visible sur la 1ère édition OS 6-inch de 1839) n'a **pas** été vérifiée géométriquement. C'est une piste solide, pas une identification confirmée.

**Statut** : [FAIT] pour le test WFS et le nom du cours d'eau ; [À VÉRIFIER] pour son identification au ruisseau du SMR.

---

### 9. Sources humaines

Uniquement des institutions publiques ou associatives, coordonnées publiques :

- **National Monuments Service** — via `archaeology.ie`, autorité compétente pour tout consentement au titre du National Monuments Act.
- **Heritage Officer**, Kilkenny County Council — `kilkennycoco.ie/eng/`, HTTP 200.
- **Kilkenny Archaeological Society / Rothe House** — `rothehouse.com` et `kilkennyarchaeologicalsociety.ie`, HTTP 200 chacun.
- **National Museum of Ireland** — `museum.ie`, HTTP 302→200, division Irish Antiquities pour les fichiers topographiques.

Non identifiés nommément cette session, à demander à l'utilisateur ou à rechercher via le Heritage Officer :
- Sociétés d'histoire locale de Callan, Kilmanagh ou Danesfort → [HYPOTHÈSE]
- Contact paroissial pour Tullaghanbrogue/Callan → [HYPOTHÈSE]

---

### 10. Compatibilité avec l'app treasure-detector

L'app `treasure-detector` actuelle est construite entièrement sur des flux WMTS IGN (France uniquement, `data.geopf.fr`) — aucune de ces couches ne fonctionne en Irlande.

**À titre de connaissance uniquement** — rappel : détecter en Irlande est une infraction pénale, voir `CADRE_LEGAL.md` — les équivalents irlandais identifiés cette session par couche :

| Couche France (IGN) | Équivalent Irlande | Disponibilité en flux | Licence |
|---|---|---|---|
| Cassini (1756-1815) | Down Survey (1655-6) | [À VÉRIFIER] — visualisateur non confirmé fonctionnel ce jour (§2.1) | Publique / TCD |
| État-major (1820-66) | OS 6-inch, 1ère éd. (1829-34/1839) | [À VÉRIFIER] — GeoHive/Tailte bloqué ici, NLS protégé par CAPTCHA (§2.2-2.3) | Tailte Éireann / CC BY 3.0 (NLS) |
| Ortho courante/IRC | Orthophotos Tailte Éireann | [À VÉRIFIER] — portail confirmé, endpoint de tuile non testé (§3) | Tailte Éireann |
| LiDAR HD (0,5 m) | GSI/OPW Open Topographic LiDAR | [FAIT service, couverture lacunaire à Grove] (§4) | CC BY 4.0 |
| Cadastre Express | Land Registry / Tailte Éireann (`landdirect.ie`) | [FAIT accessible, HTTP 200] — structure des données non explorée | Tailte Éireann |
| Atlas des patrimoines (Patriarche) | SMR / National Monuments Service | [FAIT — service ArcGIS testé et fonctionnel, RMP légal inclus] (§1.1-1.3) | CC BY 4.0 |

**Constat** : le seul bloc réellement « prêt à brancher » côté Irlande, avec la même robustesse que les flux IGN documentés pour Armous, est l'écosystème ArcGIS du National Monuments Service (SMR, zones, RMP_extents, NIAH) — REST/JSON, sans authentification, licence claire.

Tout le reste (cartes historiques, LiDAR, orthophotos) demande soit un accès navigateur (protections anti-bot ou blocages proxy constatés sur GeoHive, NLS, Down Survey, askaboutireland), soit une confirmation de couverture avant tout usage.

En l'état, et indépendamment de l'interdiction légale de détecter, l'app telle que conçue pour Armous-et-Cau **ne pourrait pas être redéployée sur l'Irlande sans réécrire entièrement sa couche de cartes anciennes et LiDAR**.
