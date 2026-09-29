# Sources de données — Meylargues (Saint-Sauveur-la-Vallée / Cœur de Causse, Lot 46)

Inventaire opérationnel des sources exploitables pour la prospection et l'analyse du secteur. Destiné aux lots pipeline de données et zones signalées (voir [`../PLAN.md`](../PLAN.md) pour l'équivalent des lots T3.1/T3.4 sur ce repo). Statuts : **[FAIT]** = sourcé/testé utilisable · **[À VÉRIFIER]** = plausible non confirmé · **[HYPOTHÈSE]** = inférence sans source.

**Date d'inventaire** : 2026-09-27. **Corrigé le** : 2026-09-27 (relecture croisée + revérification WFS/HTTP).
**Zone** : hameau de Meylargues, commune déléguée Saint-Sauveur-la-Vallée, commune nouvelle Cœur de Causse (Lot 46, 46240). Centre lon 1.5405 / lat 44.6235. Emprise d'étude (lidarBbox) : lon 1.4963–1.5847 / lat 44.5921–44.6549 (~7×7 km, 48,9 km²). Environnement large (bbox) : lon 1.4405–1.6405 / lat 44.5235–44.7235.
**Réseau** : `curl -4` obligatoire (IPv6 échoue sur ce Mac) ; User-Agent navigateur requis pour Gallica (403 sinon) et recommandé pour POP-Mérimée. **Toujours mettre les URL de requête WFS/WMTS entre guillemets** dans le shell — le `&` non protégé tronque l'URL au premier paramètre. Nominatim : 1 req/s. Overpass : `overpass-api.de` renvoie 406 depuis cette machine → utiliser le miroir `https://overpass.kumi.systems/api/interpreter`. WFS `data.geopf.fr` en EPSG:4326 : **BBOX en ordre lat,lon** avec CRS urn (ex. `BBOX=44.5921,1.4963,44.6549,1.5847,urn:ogc:def:crs:EPSG::4326`) et **toujours ajouter `SRSNAME=urn:ogc:def:crs:EPSG::4326`**, sinon les couches `patrinat_*` reviennent en EPSG:3857 et les calculs de surface/distance sont faux sans erreur visible — l'ordre lon,lat renvoie 0 résultat **sans erreur**.

---

## Tableau récapitulatif

| Source | Contenu utile | Format/Protocole | Statut | Accessibilité | Attribution |
|--------|---|---|---|---|---|
| **Cartes anciennes (flux national IGN — repris du spike Gers)** |
| Cassini (BnF, 1756–1815) | Bâti, moulins, chapelles, chemins | WMTS `BNF-IGNF_GEOGRAPHICALGRIDSYSTEMS.CASSINI` | [FAIT — vérifié GetTile z14 sur l'emprise] | data.geopf.fr, z6–14 (préfixe `BNF-IGNF_` requis, plafonne à z14) | Etalab 2.0 / IGN |
| État-major (1820–1866) | Habitats, voies, parcellaire | WMTS `GEOGRAPHICALGRIDSYSTEMS.ETATMAJOR40` | [FAIT — vérifié GetTile z15 sur l'emprise] | data.geopf.fr, z6–15 | Etalab 2.0 / IGN |
| **Orthophotos modernes (flux national IGN)** |
| Ortho RVB courante | Marqueurs de sol, accès, bâti | WMTS `ORTHOIMAGERY.ORTHOPHOTOS` | [FAIT — vérifié GetTile z17 sur l'emprise] | data.geopf.fr, z0–19 | Etalab 2.0 / IGN |
| Ortho très haute résolution (THR) | 10–20 cm GSD, détails fins | WMTS `THR.ORTHOIMAGERY.ORTHOPHOTOS` | **[INDISPONIBLE SUR LA ZONE]** — 404 « No data found » testé aux zooms 14/16/18/19 sur 5 points de l'emprise | data.geopf.fr, PM_6_21 (couverture partielle nationale, pas ici) | Etalab 2.0 / IGN |
| Ortho infrarouge (IRC) | Traces phytographiques, humidité | WMTS `ORTHOIMAGERY.ORTHOPHOTOS.IRC` | [FAIT — vérifié GetTile z17 sur l'emprise] | data.geopf.fr, z6–19 | Etalab 2.0 / IGN |
| IRC-Express multi-millésime | Comparaison année à année, crop marks | WMTS `ORTHOIMAGERY.ORTHOPHOTOS.IRC-EXPRESS.{2024,2025,2026}` | **[SEUL 2025 DISPONIBLE]** — 2024, 2023 et 2026 renvoient 404 aux zooms 14–16 sur l'emprise (2024 : 200 seulement au z12, couverture voisine) ; 2025 répond 200 aux z16–17 sur les 5 points testés | data.geopf.fr, PM_0_19 | Etalab 2.0 / IGN |
| Ortho 1950–1965 | Avant remembrement, chemins creux, parcellaire ancien | WMTS `ORTHOIMAGERY.ORTHOPHOTOS.1950-1965` (PM, `image/png`, style `BDORTHOHISTORIQUE` ou `normal`) | [FAIT — vérifié GetTile z16–17 sur l'emprise, en plus du test Gers 2026-08-08] | data.geopf.fr | Etalab 2.0 / IGN |
| **Relief et terrain** |
| LiDAR HD (MNT 0,5 m + nuage de points) | Micro-topographie, anomalies de terrain (mottes, enclos, ruines arasées de Nougayrol/Puycalvel) | GeoTIFF (MNT, via WMS-R) + COPC.LAZ (nuage de points), dalles 1 km×1 km | **[FAIT]** — non bloquant, voir détail §4 | data.geopf.fr (WFS métadonnées + WMS-R/téléchargement direct) | Etalab 2.0 / IGN |
| **Parcellaire et usage des terres** |
| Cadastre Express (parcelles actuelles) | Délimitations de parcelles, repérage terrain | WMTS `CADASTRALPARCELS.PARCELLAIRE_EXPRESS` | [FAIT — vérifié GetTile z17 sur l'emprise] | data.geopf.fr | Etalab 2.0 / IGN |
| RPG (Registre parcellaire graphique) | Cultures déclarées, labour vs prairie | WFS | [FAIT — voir détail ci-dessous] | data.geopf.fr, couches `IGNF_RPG_PARCELLES-AGRICOLES-CATEGORISEES_2024:...` et `RPG.LATEST:parcelles_graphiques` | MAAF / IGN, Etalab 2.0 |
| **Archives historiques du Lot** |
| Cadastre napoléonien (AD46) | États de sections, plans (1808–1842), toponymie ancienne — cherché sous **Soulomès**, pas Saint-Sauveur-la-Vallée | Visionneuse zoomable en ligne | [FAIT — cotes identifiées, voir détail §1] | [archives.lot.fr/recherche-en-ligne/archives-numerisees/cadastre](https://archives.lot.fr/recherche-en-ligne/archives-numerisees/cadastre) (nouvelle URL) | Domaine public |
| Fonds seigneuriaux et iconographiques (AD46) | Chartrier de Vaillac (20 J), fonds Mailhol (34 Fi 2), J 2847, archives communales | Moteur BACH | [FAIT — voir détail §8] | [bach.lot.fr/archives/search](https://bach.lot.fr/archives/search) — **anti-robot, navigateur uniquement** | Domaine public / AD46 |
| Monographies Albe (Quercy.net) | Histoire paroissiale et seigneuriale commune par commune (Saint-Sauveur, Labastide-Murat, Saint-Cernin, Saint-Martin-de-Vers) | Pages HTML | [FAIT] — transcription retravaillée, sans cote d'archive (voir détail §2) | [archives.quercy.net/qmedieval/histoire/monog_albe/](http://www.archives.quercy.net/qmedieval/histoire/monog_albe/saintsauveur.html) | Public |
| **Patrimoine et archéologie** |
| Atlas des patrimoines (Patriarche) | Entités archéologiques, ZPPA, monuments historiques | Interface web ; pas de WMS/WFS public confirmé | [À VÉRIFIER] | [atlas.patrimoines.culture.fr/atlas/trunk/](http://atlas.patrimoines.culture.fr/atlas/trunk/) — **URL http, pas https** (l'ancienne URL https échoue en TLS, « wrong version number ») | Public / Ministère de la Culture |
| POP-Mérimée | Fiches détaillées des monuments historiques (Puycalvel, Labastide, Goudou, Vaillac, Soulomès) | Base web consultable par notice | [FAIT — 5 notices vérifiées HTTP 200] | [pop.culture.gouv.fr](https://pop.culture.gouv.fr/) | Public |
| Servitudes AC1 (abords MH) / PM1 (PPRI) | Périmètres réels de protection des MH, zones inondables | WFS `wfs_sup:assiette_sup_s` | [FAIT] | data.geopf.fr | Public / DGALN |
| CAG 46 — Carte archéologique de la Gaule, *Le Lot* | Inventaire des sites archéologiques par commune, âge du Fer → haut Moyen Âge | Ouvrage imprimé (AIBL), **2<sup>e</sup> édition, 2011** (A. Filippini et al., 264 p. ; 1<sup>re</sup> éd. 1990) | [À VÉRIFIER — non consulté en détail] | [aibl.fr/collections/carte-archeologique-de-la-gaule-46-le-lot](https://aibl.fr/collections/carte-archeologique-de-la-gaule-46-le-lot/) | AIBL |
| Société des études du Lot | Bulletin trimestriel, signalements de découvertes locales | Bulletin numérisé, 118 années disponibles | [FAIT — accessible sur Gallica] | [gallica.bnf.fr/ark:/12148/cb343873149/date](https://gallica.bnf.fr/ark:/12148/cb343873149/date) ; date de début exacte **[À VÉRIFIER]** (fondation de la société en 1872, 1<sup>er</sup> bulletin probablement 1873, pas 1875) | Public / Gallica |
| Inventaire des mégalithes — PNR Causses du Quercy | Localisation des dolmens/tumulus/menhirs du causse de Gramat | PDF de vulgarisation | [FAIT pour le PDF ; aucun mégalithe recensé (Wikipedia/Clottes) dans les 6 communes de l'emprise] | [parc-causses-du-quercy.fr — PDF mégalithes](https://www.parc-causses-du-quercy.fr/wp-content/uploads/2023/06/decouvrir_megalithes2014.pdf) | PNR Causses du Quercy |
| ADLFI (Archéologie de la France - Informations) | Notices d'opérations archéologiques par secteur | Revue en ligne (OpenEdition) | **[À VÉRIFIER]** — la notice « Causse de Gramat » (adlfi/10912) est protégée par un mur anti-robot Anubis, non contournée ; la notice probablement pertinente est adlfi/10772 (« Causse de Gramat et causse de Martel », Girault 1988-1991) | [journals.openedition.org/adlfi/10772](https://journals.openedition.org/adlfi/10772) — navigateur uniquement | Public / Ministère de la Culture |
| **Réglementation et zonages environnementaux** |
| Natura 2000 — ZSC FR7300910 « Vallées de la Rauze et du Vers » | Périmètre (~33 % de l'emprise), DOCOB, espèces/habitats protégés, 11 communes dont Cœur de Causse | WFS `patrinat_sic:sic` + PDF DOCOB | [FAIT — périmètre vérifié par WFS, DOCOB HTTP 200] | [DOCOB FR7300910](https://www.occitanie.developpement-durable.gouv.fr/IMG/pdf/docob_fr_7300910.pdf) ; [inpn.mnhn.fr/site/natura2000/FR7300910](https://inpn.mnhn.fr/site/natura2000/FR7300910) | Public / DREAL Occitanie, PNR (animation) |
| Natura 2000 — ZSC FR7300909 « Zone centrale du Causse de Gramat » | **Hors emprise** (≥2,25 km à l'est) — à ne plus utiliser pour ce secteur | WFS `patrinat_sic:sic` | [FAIT — hors emprise, vérifié WFS] | [inpn.mnhn.fr/site/natura2000/FR7300909](https://inpn.mnhn.fr/site/natura2000/FR7300909) | Public |
| ZNIEFF I 730010297 « Vallée du Vers » + 730010296 | Inventaire naturel non opposable, 36,6 % + 1 % du bbox large | WFS `patrinat_znieff1:znieff1` | [FAIT] | data.geopf.fr | Public |
| PNR Causses du Quercy / Géoparc mondial UNESCO | Charte du parc, patrimoine géologique et culturel — couvre 75,3 % du lidarBbox, pas l'intégralité | WFS `patrinat_pnr:pnr` / `patrinat_geoparc:geoparc` + site web | [FAIT — périmètre vérifié par WFS] | [parc-causses-du-quercy.fr](https://www.parc-causses-du-quercy.fr/) | Public |
| Code du patrimoine — détection de métaux | Cadre légal L542-1/R542-1/R544-3, déclaration L531-14, propriété L541-4 | Texte de loi + démarche en ligne | [FAIT] | [culture.gouv.fr — démarche autorisation](https://www.culture.gouv.fr/catalogue-des-demarches-et-subventions/autorisation/utilisation-de-materiel-permettant-la-detection-d-objets-metalliques-a-l-effet-de-recherches-de-monuments-et-d-objets-pouvant-interesser-la-prehist) ; Légifrance | Public / Légifrance |
| **Géologie et sols** |
| BRGM InfoTerre | Géologie karstique du causse (calcaires, dolines, réseau souterrain) | Cartes géologiques 1/50000 | [HYPOTHÈSE — non interrogé pour cette zone] | [infoterre.brgm.fr](https://infoterre.brgm.fr/) | Open data / BRGM |
| **Météorologie historique** |
| Open-Meteo | Précipitations (ERA5, depuis 1940), humidité du sol (ERA5-Land, depuis 1950) | API REST JSON | [FAIT — national, URL d'exemple corrigée] | [open-meteo.com](https://open-meteo.com/en/docs/historical-weather-api) (gratuit, 10k appels/j) | ERA5-Land/Copernicus |
| **Sources humaines** |
| Mairie déléguée de Saint-Sauveur-la-Vallée / Cœur de Causse | Micro-toponymie vivante, mémoire locale, accès terrain | Visite, entretien | [HYPOTHÈSE] | Mairie de Cœur de Causse | — |
| Exploitant(s) agricole(s) du causse | Connaissance empirique du terrain (cailloux, tuile, labours anciens) | Visite terrain | [HYPOTHÈSE] | À identifier sur place | — |

---

## Détail des sources spécifiques au Lot

### 1. Cadastre napoléonien — Archives départementales du Lot (AD46)

**Contenu** : le cadastre dit « napoléonien » du Lot a été levé entre **1808 et 1842** (et non 1807–1842). Les **4 119 plans** du département sont numérisés et consultables en ligne ([lot.fr — le cadastre napoléonien en ligne](https://lot.fr/node/1242), [departements.fr](https://departements.fr/le-cadastre-napoleonien-du-lot-accessible-sur-internet/)). Les feuilles sont au **1/2000, 1/2500 ou 1/5000** (pas uniformément 1/2500), le tableau d'assemblage au 1/10000–1/20000. Des **plans consulaires 1803–1807** existent aussi ; leur mise en ligne est annoncée pour le 2<sup>e</sup> semestre 2026.

**Règle de recherche** : « la recherche doit être effectuée sur la commune existante au moment de la réalisation du cadastre ». **Meylargues et Saint-Sauveur sont donc dans le cadastre de SOULOMÈS (1840)**, pas dans un cadastre propre à « Saint-Sauveur-la-Vallée » (voir [HISTOIRE.md](HISTOIRE.md) §1 et §8, divergence 1793/1845/1865 sur la création de la commune).

**Cotes identifiées** (base « Cadastre napoléonien » AD46, consultée au navigateur le 2026-09-27) :
- **Soulomès (1840)**, cote **3 P 2731** : Section A de Soulomès (3 f.), B de Nougayrol (4 f.), C de Saint-Sauveur (4 f.), **D de Meylargues (2 f., 15/07 et 05/11/1840)**. État de sections 1842 : **3 P 2309**. Matrices 1842–1932 : **3 P 2304 à 2308**.
- **Labastide-Murat (1840)**, cote **3 P 2619** : A la Ville, B Goudou, C Bramarigue, D la Devèze, E Trouals, F Soyris, G La Vaysse, H Crouzaval. État de sections 1842 : **3 P 1090**. Matrices : **3 P 1084–1087**.
- **Lamothe-Cassel (1826–1827)**, cote **3 P 2926** : A Murat, B Lamothe, C Puicalvel. État de sections 1829 : **3 P 1170**. Matrice : **3 P 1165**.
- **Saint-Cernin (1828)**, cote **3 P 2695** : A Negrié, B du Cayre, C Saint-Sernin (+ « Développement du village »), D Lespinasse…

**Accès** : nouvelle URL **[archives.lot.fr/recherche-en-ligne/archives-numerisees/cadastre/cadastre-napoleonien](https://archives.lot.fr/recherche-en-ligne/archives-numerisees/cadastre/cadastre-napoleonien)** — les anciennes URL `/r/32/…` et `/a/236/…` sont périmées. **Une réutilisation publique des images suppose de vérifier la licence de réutilisation des AD46** avant tout usage dans l'app.

**Importance critique** : plans non géoréférencés → calage manuel nécessaire (amers : église, croisements de chemins, limites parcellaires pérennes). **Priorité haute** pour la section D « de Meylargues » (domaine seigneurial mentionné par Albe, voir [HISTOIRE.md](HISTOIRE.md) §4.2).

**Attribution** : Domaine public / © Archives départementales du Lot

---

### 2. Monographies Albe (Quercy.net)

**Contenu** : monographies paroissiales et seigneuriales rédigées par l'abbé **Edmond Albe** (1861–1926), conservées en manuscrit aux **Archives diocésaines de Cahors**, et **transcrites par l'association Quercy.net** — le style télégraphique a été réécrit et les références d'archives d'origine ont été supprimées ; ce n'est donc **pas une édition fidèle**. Le « Dictionnaire des paroisses du diocèse de Cahors », qu'Albe préparait avec A. Viré, est **resté inachevé** à sa mort en 1926 ([présentation Quercy.net](http://www.archives.quercy.net/qmedieval/histoire/monog_albe/albe_presentation.html)).

**Monographies en ligne couvrant l'emprise** : Saint-Sauveur-la-Vallée, Labastide-Murat, Saint-Cernin, Saint-Martin-de-Vers. **Pas de monographie en ligne** (HTTP 404 testé le 2026-09-27) pour Soulomès, Lamothe-Cassel/Puycalvel, Ussel, Vaillac, Frayssinet, Montfaucon — pour ces communes, consulter les Archives diocésaines de Cahors ou les AD46 directement.

**Accès** : [archives.quercy.net/qmedieval/histoire/monog_albe/saintsauveur.html](http://www.archives.quercy.net/qmedieval/histoire/monog_albe/saintsauveur.html), [.../labastide_murat.html](http://www.archives.quercy.net/qmedieval/histoire/monog_albe/labastide_murat.html), [.../saint_cernin.html](http://www.archives.quercy.net/qmedieval/histoire/monog_albe/saint_cernin.html), [.../saintmartindevers.html](http://www.archives.quercy.net/qmedieval/histoire/monog_albe/saintmartindevers.html)

**Statut** : [FAIT] — pages consultées le 2026-09-27, chaque [FAIT] tiré d'Albe doit être cité comme « transcription Quercy.net », la cote d'archive originale restant à retrouver.

**Gotcha réseau** : le site sert en HTTP simple (pas de TLS moderne) — `WebFetch` standard échoue (`TLSV1_ALERT_INTERNAL_ERROR`) ; **utiliser `curl -4` avec un User-Agent de navigateur** :
```bash
curl -4 -s -A "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0 Safari/537.36" \
  "http://www.archives.quercy.net/qmedieval/histoire/monog_albe/saintsauveur.html"
```
Encodage **ISO-8859-1** (pas UTF-8).

**Attribution** : Public / Quercy.net

---

### 3. Atlas des patrimoines et POP-Mérimée (DRAC Occitanie)

**Contenu** : entités archéologiques, ZPPA, monuments historiques classés/inscrits, opérations de fouille.

**Accès** : Atlas des patrimoines à l'**URL http** (pas https) : [atlas.patrimoines.culture.fr/atlas/trunk/](http://atlas.patrimoines.culture.fr/atlas/trunk/) — l'ancienne URL https renvoie une erreur TLS (« wrong version number »), testée le 2026-09-27. POP-Mérimée : [pop.culture.gouv.fr](https://pop.culture.gouv.fr/) — 5 fiches vérifiées HTTP 200 pour cette zone : [PA00095306](https://pop.culture.gouv.fr/notice/merimee/PA00095306) (château de Labastide-Murat), [PA00095121](https://pop.culture.gouv.fr/notice/merimee/PA00095121) (église de Puycalvel), [PA00125599](https://pop.culture.gouv.fr/notice/merimee/PA00125599) (église de Goudou), [PA00095277](https://pop.culture.gouv.fr/notice/merimee/PA00095277) (château de Vaillac), [PA00095266](https://pop.culture.gouv.fr/notice/merimee/PA00095266) (église et presbytère de Soulomès).

**Statut** : [FAIT] pour POP-Mérimée ; **[À VÉRIFIER]** pour un flux WMS/WFS Patriarche exploitable en direct — aucun endpoint OGC public trouvé (comme pour le Gers). **Les servitudes AC1 (abords MH) et PM1 (PPRI) sont en revanche disponibles en WFS** sur `wfs_sup:assiette_sup_s` de data.geopf.fr — utilisé pour délimiter précisément les abords de Puycalvel, Labastide et Goudou (voir [HISTOIRE.md](HISTOIRE.md) §0). **La couche ZPPA du service national n'existe que pour le Centre-Val de Loire** (`zppa_cvl_…`) — les ZPPA du Lot restent à obtenir via l'Atlas des patrimoines ou la DRAC.

**Attribution** : Public / © Ministère de la Culture

---

### 4. LiDAR HD — couverture du Lot confirmée

**Contenu** : **MNT GeoTIFF à 0,5 m** (via WMS-R) — utile pour repérer mottes, enclos, ruines arasées (Nougayrol, Puycalvel) — et **nuage de points COPC.LAZ** (dalles 1 km×1 km), deux produits distincts du programme LiDAR HD.

**Statut** : **[FAIT]** — **64 dalles** de 1×1 km intersectent le lidarBbox, chacune avec une `url_mnt` exploitable, réparties sur deux missions : **21LHD2IN** (13/09–01/10/2021, 48 dalles) et **22LHD3JN** (27/04–10/05/2022, 16 dalles), éditées en 2025. **Ce n'est plus un bloquant.** Le pipeline du repo a déjà produit hillshade, SVF, LRM et openness dans `data/derived/` (constaté par listing, fichiers non touchés par ce lot).

**Vérification effectuée** (2026-09-27) :
```bash
curl -4 -s "https://data.geopf.fr/wfs/ows?SERVICE=WFS&VERSION=2.0.0&REQUEST=GetFeature&TYPENAMES=IGNF_LIDAR-HD_METADONNEE:metadata&BBOX=44.5921,1.4963,44.6549,1.5847,urn:ogc:def:crs:EPSG::4326&SRSNAME=urn:ogc:def:crs:EPSG::4326&OUTPUTFORMAT=application/json&COUNT=200"
```
→ HTTP 200, 64 entités. La carte de suivi `macarte.ign.fr` (précédemment citée comme voie de vérification `[MACHINE LOCALE]`) est **remplacée par cette couche WFS**, accessible sans contrainte réseau particulière.

**Plan B si une dalle manque** : repli sur RGE ALTI 1 m (résolution dégradée).

**Attribution** : Etalab 2.0 / © IGN – Programme LiDAR HD

---

### 5. Natura 2000, ZNIEFF, PNR/Géoparc — périmètres vérifiés par WFS

**Contenu** : le site pertinent pour l'emprise est la **ZSC FR7300910 « Vallées de la Rauze et du Vers et vallons tributaires »** (4 807 ha, ~33 % du lidarBbox), **pas** la ZSC FR7300909 « Zone centrale du Causse de Gramat » (6 413 ha), qui est **hors emprise** (≥2,25 km à l'est). Contexte non opposable : ZNIEFF I 730010297 « Vallée du Vers » (36,6 % du bbox large) et ZNIEFF I 730010296 (~1 %).

**Accès** :
- WFS Natura 2000 : `TYPENAMES=patrinat_sic:sic`, BBOX de l'emprise, `SRSNAME=urn:ogc:def:crs:EPSG::4326`.
- DOCOB FR7300910 : [occitanie.developpement-durable.gouv.fr/IMG/pdf/docob_fr_7300910.pdf](https://www.occitanie.developpement-durable.gouv.fr/IMG/pdf/docob_fr_7300910.pdf) (HTTP 200 vérifié).
- Fiche du site (PNR, animateur) : [reseaunatura2000lot.n2000.fr](https://reseaunatura2000lot.n2000.fr/reseau-lotois/vallees-de-la-rauze-et-du-vers-et-vallons-tributaires).
- WFS ZNIEFF : `TYPENAMES=patrinat_znieff1:znieff1` / `patrinat_znieff2:znieff2`.
- WFS PNR/Géoparc : `TYPENAMES=patrinat_pnr:pnr` / `patrinat_geoparc:geoparc` — confirme **75,3 % de couverture du lidarBbox**, pas l'intégralité (voir [HISTOIRE.md](HISTOIRE.md) §0).

**Statut** : [FAIT] pour les deux périmètres (vérifiés WFS le 2026-09-27) et pour le DOCOB (HTTP 200).

**Implication réglementaire** : voir §0 de [HISTOIRE.md](HISTOIRE.md).

**Attribution** : Public / DREAL Occitanie, opérateur PNR Causses du Quercy

---

### 6. PNR Causses du Quercy — Géoparc mondial UNESCO

**Contenu** : patrimoine géologique et culturel du causse (environ 600 dolmens recensés dans le Lot, pas 365), patrimoine bâti rural (caselles, gariottes, lavognes, murets de pierre sèche).

**Accès** : [parc-causses-du-quercy.fr](https://www.parc-causses-du-quercy.fr/) ; PDF *Découvrir... Les mégalithes des Causses du Quercy* : [lien direct](https://www.parc-causses-du-quercy.fr/wp-content/uploads/2023/06/decouvrir_megalithes2014.pdf) ; PDF phosphatières : [lien](https://www.parc-causses-du-quercy.fr/wp-content/uploads/2023/06/3-les-phosphatieres.pdf).

**Statut** : [FAIT] pour le label et le contenu général — **couvre 75,3 % du lidarBbox, pas l'intégralité** (le quart SO, Lamothe-Cassel + Ussel, en est exclu). **[À VÉRIFIER]** si une règle interne du parc s'ajoute au droit commun pour la détection ou l'approche des mégalithes — à confirmer auprès du PNR ; charte en révision pour la période 2027–2042.

**Attribution** : Public / PNR Causses du Quercy

---

### 7. RPG (Registre parcellaire graphique)

**Contenu** : parcelles agricoles catégorisées, avec un attribut permettant de distinguer labour et prairie — utile pour cibler les sols déjà retournés.

**Statut** : **[FAIT]** — l'ancien lien `api.gouv.fr/api/rpg` redirige désormais vers le catalogue générique data.gouv.fr, mais le RPG est disponible en WFS sur data.geopf.fr : couches `IGNF_RPG_PARCELLES-AGRICOLES-CATEGORISEES_2024:parcelles_agricole_categorisees_2024` et `RPG.LATEST:parcelles_graphiques`. Test `GetFeature` avec BBOX 44.615,1.53,44.63,1.55 → 20 entités renvoyées.

**Attribution** : MAAF / Open data, IGN Etalab 2.0

---

### 8. Fonds seigneuriaux et iconographiques — Archives départementales du Lot (AD46)

**Contenu** (au-delà du seul cadastre) : **Chartrier de Vaillac (20 J)**, sous-série « Territoire de Labastide-Murat, Goudou, Soyris, Soulomès » (ex. 20 J 21 : donation de Foulque de Soyris sur la paroisse de Soyris, 1294, et ventes de 1310 ; 20 J 7 : arrentement de 1334 ; 20 J 43 : testament de 1362). **J 2847** (Maylargues, XVI<sup>e</sup> s.). Saint-Sauveur-la-Vallée, archives communales déposées **EDT 291** (1740–1907 ; BMS 1740–1789). Dossiers communaux **2 O 310** (Saint-Sauveur) et **2 O 329** (Soulomès). Fonds Mailhol **34 Fi 2**, photos 1935–1960 (Nougayrol 2/897-901 ; Soyris 2/855, 2/864 ; Saint-Sauveur 2/884-886 ; Soulomès 2/894-902). **5 J** (collection Gransault-Lacoste et Laroussilhe, 1315–1916). « Table générale des archives antérieures à 1790 » (Fourastié et Prat, 1938/1950).

**[À VÉRIFIER]** Aucun compoix de Saint-Sauveur, Soulomès ou Labastide trouvé dans BACH ; Albe cite un « cadastre de Goudou » de 1788, non retrouvé.

**Accès et piège** : moteur BACH — [bach.lot.fr/archives/search](https://bach.lot.fr/archives/search/default/Goudou?view=list) (chercher « Goudou », « Soyris », « Nougayrol », « Maylargues », « Saint-Sauveur-la-Vallée »). **`archives.lot.fr` et `francearchives.gouv.fr` opposent un mur anti-robot JavaScript** — `curl` renvoie `403 Attack detected` — **consultation au navigateur uniquement**.

**Attribution** : Domaine public / © Archives départementales du Lot

---

## Résumé — bloquants avant pipeline de données

| Catégorie | Verdict | Bloquant ? |
|-----------|---------|---|
| **Cartes WMTS IGN** (Cassini, État-major, Ortho, IRC, 1950-65) | [FAIT — vérifié GetTile sur l'emprise Meylargues] | Non |
| **THR et IRC-Express 2023/2024/2026** | **Indisponibles sur la zone** (404 testés) | Non pour le pipeline (couches optionnelles) — **ne pas les afficher comme disponibles dans l'UI** |
| **LiDAR HD** | **[FAIT]** — 64 dalles, missions 2021/2022, non bloquant | Non |
| **Atlas des patrimoines (WMS/WFS)** | [À VÉRIFIER] — pas d'endpoint OGC public confirmé ; ZPPA nationale limitée au Centre-Val de Loire | Oui (moyen) — plan B export manuel = voie par défaut |
| **Cadastre napoléonien (AD46)** | [FAIT] — cotes identifiées, sous la commune de **Soulomès** | Non — calage manuel long mais pas bloquant |
| **Fonds seigneuriaux AD46 (BACH)** | [FAIT] pour l'accès, anti-robot sur `curl` | Non — navigateur uniquement |
| **CAG 46 (Le Lot, 2<sup>e</sup> éd. 2011)** | [À VÉRIFIER] — ouvrage non consulté en détail | Non — enrichissement |
| **Natura 2000 (FR7300910), ZNIEFF, PNR/Géoparc (75,3 %)** | [FAIT] — périmètres vérifiés WFS | Non pour le pipeline technique, **oui pour la conformité réglementaire avant sortie terrain** |
| **RPG** | [FAIT] — WFS testé | Non |
| **BRGM, Open-Meteo** | [HYPOTHÈSE]/[FAIT national] | Non — enrichissement scoring |

---

## Procédures d'accès (synthèse)

### IGN / data.geopf.fr (WMTS/WFS — identifiants identiques au spike Gers)

```bash
curl -4 "https://data.geopf.fr/wmts?SERVICE=WMTS&VERSION=1.0.0&REQUEST=GetCapabilities"
curl -4 "https://data.geopf.fr/wmts?SERVICE=WMTS&REQUEST=GetTile&VERSION=1.0.0&LAYER=BNF-IGNF_GEOGRAPHICALGRIDSYSTEMS.CASSINI&STYLE=normal&TILEMATRIXSET=PM&TILEMATRIX=14&TILEROW=<row>&TILECOL=<col>&FORMAT=image/png"
curl -4 "https://data.geopf.fr/wfs/ows?SERVICE=WFS&VERSION=2.0.0&REQUEST=GetFeature&TYPENAMES=patrinat_sic:sic&BBOX=44.5921,1.4963,44.6549,1.5847,urn:ogc:def:crs:EPSG::4326&SRSNAME=urn:ogc:def:crs:EPSG::4326&OUTPUTFORMAT=application/json"
```
**Toujours entre guillemets** — un `&` non protégé tronque l'URL au premier paramètre dans le shell. **Accès** : public, sans authentification. **Gotcha** : proxy Docker/conteneur bloque `data.geopf.fr` → tâches `[MACHINE LOCALE]` en environnement conteneurisé (non rencontré depuis ce Mac).

### Archives départementales du Lot (AD46)

```
https://archives.lot.fr/recherche-en-ligne/archives-numerisees/cadastre/cadastre-napoleonien → cadastre napoléonien (par commune : Soulomès, Labastide-Murat, Lamothe-Cassel, Saint-Cernin)
https://bach.lot.fr/archives/search → fonds seigneuriaux et iconographiques (BACH)
Anti-robot JavaScript sur archives.lot.fr et francearchives.gouv.fr → navigateur uniquement, curl → 403
```

### Quercy.net / monographies Albe

```bash
curl -4 -s -A "Mozilla/5.0 ..." "http://www.archives.quercy.net/qmedieval/histoire/monog_albe/<commune>.html"
```
Encodage ISO-8859-1. `WebFetch` standard échoue (TLS) — utiliser `curl`.

### Atlas des patrimoines / POP

```
http://atlas.patrimoines.culture.fr/atlas/trunk/ (interface web, http pas https, pas de WMS/WFS confirmé)
https://pop.culture.gouv.fr/ (recherche par notice Mérimée)
```

### Gallica (Combarieu 1881, Clottes 1977, Bulletin de la Société des études du Lot)

```bash
curl -4 -s -A "Mozilla/5.0 ..." "https://gallica.bnf.fr/ark:/12148/bpt6k939800h"
```
User-Agent navigateur requis (403 sinon).

### Overpass (chemins de pèlerinage, relations OSM)

```bash
curl -4 -s "https://overpass.kumi.systems/api/interpreter" --data-urlencode 'data=[out:json];rel(3371974,3372015,6439814);out geom;'
```
`overpass-api.de` renvoie 406 depuis cette machine → utiliser le miroir.

### Open-Meteo

```
https://archive-api.open-meteo.com/v1/archive?latitude=44.6235&longitude=1.5405&start_date=1950-01-01&end_date=2026-09-27&daily=precipitation_sum&hourly=soil_moisture_0_to_7cm
```
Corrigé : `precipitation` seul est invalide (le paramètre correct est `precipitation_sum` en `daily`), `soil_moisture_0_to_10cm` n'existe pas dans l'API d'archive (le pas correct est `soil_moisture_0_to_7cm`). URL testée, HTTP 200. Accès : gratuit, REST, 10k appels/jour.

---

## Notes pour l'orchestrateur

- **Flux IGN nationaux** : Cassini, État-major, Ortho, IRC et 1950-65 sont **confirmés sur la nouvelle bbox** (GetTile testé). **THR et IRC-Express 2023/2024/2026 sont indisponibles ici** — seul IRC-Express 2025 répond ; à ne pas proposer comme couches actives par défaut dans l'UI pour cette zone.
- **LiDAR HD n'est plus un bloquant** : 64 dalles couvrent l'emprise (missions 2021/2022), MNT et nuage de points tous deux accessibles en WFS/WMS-R/téléchargement direct.
- **Un bloquant de portée moyenne subsiste** : Atlas des patrimoines / ZPPA (pas d'endpoint OGC public pour l'Occitanie) — export manuel par défaut.
- **Réglementaire, pas seulement pipeline** : le site Natura 2000 pertinent est **FR7300910**, pas FR7300909 ; le PNR/Géoparc couvre 75,3 % de l'emprise, pas l'intégralité — à vérifier avant toute sortie terrain (voir §0 de [HISTOIRE.md](HISTOIRE.md)). Le Géoparc/PNR en tant que label n'est **pas** un bloquant réglementaire en soi (retiré du tableau des bloquants).
- **AD46** : deux portails distincts — le cadastre napoléonien (visionneuse) et le moteur BACH (chartrier de Vaillac, fonds Mailhol, J 2847) — tous deux bloqués pour `curl` par un mur anti-robot, consultation au navigateur uniquement.
- **Pas de clé/secret requis** — tout est public.

---

**Rédigé le** : 2026-09-27 | **Corrigé le** : 2026-09-27 | **Zone** : Meylargues / Saint-Sauveur-la-Vallée / Cœur de Causse (Lot 46)
