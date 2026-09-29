# Toponymie — Meylargues / Saint-Sauveur-la-Vallée (Cœur de Causse, INSEE 46138)

**Glossaire des racines toponymiques occitanes/quercynoises** utiles au prospecteur, suivi du **relevé des lieux-dits réels de l'emprise d'étude**, classés par rang d'intérêt. Zone pilote : hameau de Meylargues, commune déléguée de Saint-Sauveur-la-Vallée, commune nouvelle Cœur de Causse (Lot, causse de Gramat, domaine linguistique occitan quercynois).

**Emprise d'étude** : lon 1.4963–1.5847, lat 44.5921–44.6549 (~49 km²). Centre : lon 1.5405, lat 44.6235.

> **Révision du 2026-09-27.** Ce document corrige une version antérieure qui contenait plusieurs erreurs factuelles graves : un monument historique inscrit (château de Labastide-Murat, XIXe siècle) présenté comme un site castral médiéval de rang 1, des sources inventées (« catégorie Château » du cadastre Etalab, qui n'existe pas), et une couverture cadastrale limitée à une seule commune (46138) sur les six qui intersectent l'emprise (52,5 % de la surface seulement). Chaque correction ci-dessous a été **revérifiée indépendamment** cette session à partir des sources primaires (WFS BD TOPO V3, cadastre Etalab, OSM, Wikidata, Wikipédia FR, geo.api.gouv.fr) — le détail des vérifications figure en §4.

---

## 0. Synthèse d'exécution

| Métrique | Résultat |
|---|---|
| **Lieux-dits relevés et géocodés** | **70 Points** dans `data/derived/toponymes.geojson` (+42 par rapport à la version précédente) |
| **Couverture cadastrale** | **6 communes** dépouillées (Cœur de Causse 52,5 %, Lamothe-Cassel 21,4 %, Les Pechs du Vers 12,7 %, Soulomès 5,8 %, Frayssinet 4,3 %, Ussel 3,3 % de l'emprise — pourcentages calculés par intersection géométrique en Lambert-93, somme = 100,0 %) |
| **Sources interrogées** | Cadastre Etalab (6 communes), WFS BD TOPO V3 (`toponymie`, `zone_d_habitation`, `lieu_dit_non_habite`, `detail_orographique`, `cimetiere`, `construction_ponctuelle`, `zone_d_activite_ou_d_interet`, `commune_associee_ou_deleguee`), OSM (nœuds/voies ponctuels + tags MH), Wikidata (statuts de protection, dates), Wikipédia FR (toponymie/histoire), geo.api.gouv.fr (contours communaux) |
| **Rang 0 (repères / exclusions)** | 12 entrées — 2 monuments historiques inscrits, 1 cimetière actif, 5 bourgs/chefs-lieux, 1 grotte (prudence), 3 zones bâties |
| **Rang 1 (signal fort)** | 8 entrées |
| **Rang 2 (moyen)** | 31 entrées |
| **Rang 3 (faible / prudence)** | 19 entrées — dont l'ensemble « Cinq Pierres » (zone à prudence mégalithe/borne, 3 polygones fusionnés) |
| **Exclusions actives** | Château de Labastide-Murat (MH inscrit PA00095306, tampon 500 m), église Saint-Vit de Puycalvel (MH inscrit PA00095121, tampon 300 m), cimetière/église de Murat (tampon 150 m), Grotte Bourrue (prudence sécurité), zone bâtie du Bourg de Labastide-Murat |
| **Zones sensibles (non-exclusion mais prudence)** | Tour de Soyris (cimetière paroissial disparu probable), ensemble Cinq Pierres (mégalithe potentiel) |
| **Hors emprise (signalé, non intégré au geojson)** | Église Saint-Jean-Baptiste de Goudou (MH inscrit PA00125599, 15/11/1993 — à 182 m au-delà du coin nord-est, son tampon de protection empièterait sur l'emprise si elle est élargie) ; lieu-dit Saint-Hilaire (46138, ~665 m au nord) |

---

## 1. Glossaire des racines toponymiques (occitan quercynois)

Racines à repérer sur IGN/cadastre/Cassini pour prioriser une zone avant même de sortir le détecteur. Domaine occitan quercynois, causse de Gramat.

| Racine | Sens | Signal archéologique | Exemple dans l'emprise |
|---|---|---|---|
| **-argues / -anicus, -anicas** | Suffixe gallo-romain de domaine (nom de personne + suffixe adjectival), parallèle à -ac. Évolution attestée -anicum > -argues (Vendargues : 924→1536 ; Lansargues : 1152) | Domaine antique — signal plausible mais anthroponyme rarement identifiable | *Meylargues* (rang 2, [HYPOTHÈSE] sur l'anthroponyme précis) |
| **-ac (< -acum)** | Suffixe gallo-romain de domaine (nom de personne + -acum), très fréquent en Quercy | Domaine antique probable — **piège Polge** fréquent (patronyme de propriétaire tardif) | *Rignac (Renius), Cuzac (Cusius), Foissac, Carniac, Brassac, Regagnac, Gauléjac, Ravazac, Madirac* |
| **Castel / Castèl** | Château, enceinte fortifiée | Site castral médiéval — **attention : un « Château » cartographié peut être un château d'époque moderne/contemporaine (cf. Château de Labastide-Murat, 1807-1815, MH), pas systématiquement médiéval.** Vérifier la datation avant de conclure. | *Château de Labastide-Murat (exclusion MH, XIXe s.)* ; le seul site castral médiéval documenté ici est le « réduit » à tour du fort de Soyris/Labastide, sous le bâti actuel du Bourg |
| **Mota / Motte** | Butte artificielle, motte castrale | Fortification médiévale (XIe-XIIIe s.) | *Lamothe-Cassel* (chef-lieu communal, toponyme motte castrale attesté par l'histoire communale — Wikipédia FR) ; emplacement précis de la motte non localisé |
| **Bastida / Bastide** | Ville neuve fortifiée (fondation XIIIe s.) | Habitat médiéval planifié | *Labastide-Murat* (fondée 1238 par Fortanier de Gourdon, nommée La Bastide-Fortunière jusqu'en 1852) — **PAS** un lieu-dit isolé nommé « La Bastide » (aucun lieu-dit cadastral de ce nom ; le point BD TOPO homonyme désigne un simple écart du bourg) |
| **Glèisa / Capèla / Église, Chapelle** | Église, chapelle | Édifice religieux disparu **OU** terre appartenant à une église existante — les deux lectures sont possibles selon le contexte | *Champ de l'Église* (x2 dans l'emprise, aux deux lectures possibles), *Pièce de Capelle* |
| **Sant- / Saint-** | Vocable hagionymique | Chapelle/paroisse disparue **si** hors bourg actuel ; simple bourg actif sinon | *Saint-Sauveur, Saint-Cernin (Saturninus), Saint-Georges (Lamothe-Cassel), Saint-Martin (Ussel), Saint-Vit (Puycalvel)* — tous des bourgs/églises actifs, repères |
| **Cros** | Creux, dépression | Topographique, souvent piège Polge | *Les Croses* (46138, hors sélection) |
| **Peyre / Pierre** | Pierre / pierre levée | **Mégalithe (dolmen, menhir) possible — zone à prudence si confirmé, PAS une cible.** Peut aussi être un bornage de limite paroissiale. | *Cinq Pierres* (ensemble fusionné, 3 communes — voir §3) |
| **Cayre / Cairon / Cayrou** | Pierre, tas de pierres | Amas d'épierrement OU vestige effondré (cazal) OU tumulus/pseudo-tumulus — à distinguer sur le terrain | *Fontaine des Cayres, Les Cayres, Le Cayrou, Le Cayrol, Chayroux* |
| **Mas** | Tenure agricole médiévale à moderne (Quercy : dès le XIVe s. selon Lartigaut, pas seulement XVIIe-XIXe) | Habitat rural, occupation parfois ancienne | *Mas Lagarde, Mas de Puycalvel, Mas Blanc, Mas de Confiance* (hors sélection rang 1-3) |
| **Borie** | En Quercy : **métairie, ferme, domaine agricole** (occitan bòria) — PAS « cabane en pierre sèche » (sens forgé au XIXe s. en Provence ; dans le Lot ces cabanes se nomment *caselles/gariottes*) | Habitat rural, métairie parfois désertée | *Les Bories, La Borie, Laborie Blanche, Pièce de Laborie* |
| **Clau / Claux** | Enclos, clôture | Parcelle close ancienne | *Le Clos* (Lamothe-Cassel, hors sélection) |
| **Camp** | Champ (latin *campus*) — pas « enclos » | Signal faible seul, terme très générique | *Camp Grand (x2, homonymes distincts), Camp de Lasfargues, Camp des Roumioux* |
| **Molin** | Moulin | Mobilier de circulation (monnaies, ferrures) aux abords | *Moulin de Caviole (hydraulique, [FAIT]), Moulin Neuf, Moulin du Hasard (à vent), Moulin de Merle* |
| **Teulièra** | Tuilerie (< tegulae latin) | Atelier antique ou moderne | *La Tuilerie (probablement moderne, cf. État-major), Les Teulières* |
| **Fon / Font** | Source, fontaine | Sanctuaire de source antique **possible** mais non démontré ici | *Fontaine des Cayres* (nom dérivé du lieu-dit voisin Les Cayres, pas d'un aménagement de pierre isolé) |
| **Farga / Faure** | Forge / forgeron | Signal métallurgique — scories, minerai | *Clos de Fargues, Camp de Lasfargues, Lafaurie, Ferrières* |
| **Fornet / Foulon** | Petit four / moulin à fouler le drap | Signal artisanal | *Le Fournet, Foulon* |
| **Igue** | Gouffre/aven vertical (relief karstique) | Pas une cible directe — risque physique | Racine absente en toponyme direct ; phénomène apparenté : *Cloup de Leygue* (doline) |
| **Cloup** | Doline (dépression karstique, variante de « clòt » — non sourcé pour l'étymologie précise, mais le sens de doline est attesté localement) | Apparenté à l'igue — prudence gouffre | *Cloup de Leygue* |
| **Lacoste** | La còsta = la côte, la pente — **PAS** « à côté du lac » | Terrain en pente, signal faible | — |
| **Jasse** | Bergerie, parc à moutons | Signal pastoral | *Les Jasses* |
| **Pech / Puech / Suc** | Colline, hauteur (le suc/suq est la variante locale affaiblie, ex. Cinq Pierres à la limite de plusieurs pechs) | Poste de guet possible si associé à un autre indice défensif | *Le Puech, Pech la Garde, Pech Lagarde (x2, homonymes), Pech Latour* |
| **Garda / Garde** | Guet, surveillance — **OU patronyme Lagarde** (piège Polge fréquent, plusieurs occurrences homonymes dans l'emprise) | Poste défensif possible OU simple nom de propriétaire | *Pech la Garde, Pech Lagarde, Mas Lagarde* |
| **Justícia / Justices** | Lieu d'exercice de la haute justice seigneuriale (souvent gibet — cf. Marmier 1881 sur les toponymes de fourches patibulaires) | Signal socio-historique | *Les Justices* (cohérent avec la haute justice de la baronnie de Labastide) |
| **Muratum** | Lieu fortifié, muré (latin) | Habitat ancien fortifié | *Murat* (hameau de Lamothe-Cassel, église + cimetière actifs) |

**Piège Polge applicable partout dans cette emprise** : les suffixes -ac, -argues et le déterminant « Lagarde/Latour/Leygue/Fargues/Foissac » recouvrent aussi bien des domaines antiques que des **patronymes de propriétaires ou de maires du XIXe-XXe siècle** (Foissac et Latour ont tous deux été maires de Labastide-Murat). Statut plafonné à [À VÉRIFIER] ou [HYPOTHÈSE] tant qu'une source secondaire (Bazalgues, *À la découverte des noms de lieux du Quercy*, 2002 ; Dauzat & Rostaing) ne confirme pas l'étymon pour ce lieu-dit précis.

---

## 2. Lieux-dits réels de l'emprise, classés par rang

Toutes les coordonnées ci-dessous ont été **recalculées cette session** (centroïde d'aire exact via shapely, pas une moyenne de sommets) à partir du cadastre Etalab (millésime 2026-06-01) et de la BD TOPO V3 (WFS `data.geopf.fr`, BBOX en ordre lat,lon avec CRS urn). Le rôle `EXCLUSION` signale un site protégé ou sensible à ne jamais traiter comme cible ; `SENSIBLE` signale une prudence sans protection réglementaire confirmée.

### Rang 0 — Repères et exclusions (12 entrées)

| Nom | Forme source | Lat | Lon | Statut | Commune | Interprétation |
|---|---|---|---|---|---|---|
| **Saint-Sauveur-la-Vallée (bourg actuel)** | Saint-Sauveur-la-Vallée | 44.60653 | 1.55298 | [FAIT] | Cœur de Causse (46138) | Ancien chef-lieu de commune (fusionné dans Cœur de Causse le 01/01/2016), église et bourg toujours en activité. Repère cartographique central de la zone, pas une cible archéologique — sol occupé et bâti moderne. |
| **Labastide-Murat (bourg, ancienne bastide La Bastide-Fortunière)** | Labastide-Murat / la Bastide-Fortunière | 44.64668 | 1.56778 | [FAIT] | Labastide-Murat (46138) | Chef-lieu de la commune déléguée Labastide-Murat (Cœur de Causse). Ancienne bastide fondée en 1238 par Fortanier de Gourdon sur la paroisse primitive de Soyris ; nommée La Bastide-Fortunière jusqu'au 15/04/1852, renommée en hommage à Joachim Murat (né ici en 1767). Repère, pas une cible : bâti actuel dense. |
| **Le Bourg — polygone cadastral (Labastide-Murat)** | Le Bourg | 44.64617 | 1.56866 | [FAIT] | Labastide-Murat (46138) | Le polygone cadastral « LE BOURG » recouvre le centre actuel de Labastide-Murat, pas un hameau distinct nommé « Soyris » : Soyris (paroisse disparue, voir plus bas) est à 886 m au SSE. Fusionné avec le repère du bourg ci-dessus — géométrie conservée pour référence de zone bâtie à exclure. **[EXCLUSION: bâti dense actuel (pas un MH, simple zone habitée)]** |
| **La Bastide (écart/quartier de la bastide)** | la Bastide | 44.65010 | 1.57242 | [FAIT] | Labastide-Murat (46138) | Aucun lieu-dit cadastral « La Bastide » n'existe dans les 6 communes de l'emprise : le nom vient de la BD TOPO seule et désigne un écart/quartier périphérique nord-est de la bastide de Labastide-Murat (lotissements la Barthe/le Hasard), pas un site distinct. Repère de tissu bâti périphérique, pas une cible. |
| **Château de Labastide-Murat — MONUMENT HISTORIQUE INSCRIT** | le Château | 44.64168 | 1.56216 | [FAIT] | Labastide-Murat (46138) | Château néoclassique construit 1807–1815 pour Joachim Murat (architecture classique/Empire, 3e quart XIXe s. selon la fiche de protection), PAS un site castral médiéval. Inscrit MH : façades et toitures le 16/09/1991, parc le 24/03/1992 (parcelles A 599 et 600). L'ancien point du relevé (1.55997/44.64136) tombait à 180 m du bâtiment, dans le parc inscrit (parcelle A600) — corrigé ici sur le bâtiment (parcelle A599). Exclu du scoring comme cible : propriété privée protégée. Un site castral antérieur éventuel resterait une hypothèse non sourcée. **[EXCLUSION: MH inscrit PA00095306 (façades/toitures 16/09/1991, parc 24/03/1992)]** |
| **Église Saint-Vit de Puycalvel — MONUMENT HISTORIQUE INSCRIT** | Église Saint-Vit de Puycalvel | 44.60346 | 1.52402 | [FAIT] | Lamothe-Cassel (46151) | Église romane du XIIe siècle, agrandie/transformée au XVe, inscrite monument historique le 28/06/1927. Cimetière communal contigu. Exclue du scoring comme cible — MH + emprise funéraire. **[EXCLUSION: MH inscrit PA00095121 (28/06/1927)]** |
| **Murat — église de l'Assomption et cimetière** | Murat | 44.62232 | 1.50969 | [FAIT] | Lamothe-Cassel (46151) | Hameau de Lamothe-Cassel avec église et cimetière actifs. Toponyme muratum (latin) = lieu fortifié/muré. Repère bâti + zone funéraire — exclu du scoring. **[EXCLUSION: cimetière communal actif]** |
| **Saint-Cernin (bourg actuel)** | Saint-Cernin | 44.59273 | 1.58165 | [FAIT] | Les Pechs du Vers (46252) | Chef-lieu de la commune déléguée Saint-Cernin (Les Pechs du Vers, fusion 01/01/2016). Le point-étiquette IGN du hameau tombe à ~110 m sous la limite sud de l'emprise, mais l'église Saint-Saturnin, le cimetière, la mairie et 79 % du polygone cadastral LE BOURG (46252) sont bien dans l'emprise. Hagiotoponyme (Saturninus, évêque de Toulouse) mais bourg actif — repère, pas un site à fouiller aux archives. |
| **Second édifice de culte de Saint-Cernin** | édifice avec clocher, Saint-Cernin | 44.59449 | 1.58301 | [À VÉRIFIER] | Les Pechs du Vers (46252) | Second bâtiment à vocation cultuelle recensé par l'IGN près du bourg de Saint-Cernin, nature exacte non précisée par la BD TOPO (chapelle ?). |
| **Lamothe-Cassel — bourg, église Saint-Georges** | Lamothe-Cassel | 44.61253 | 1.50597 | [FAIT] | Lamothe-Cassel (46151) | Chef-lieu de la commune déléguée Lamothe-Cassel. Toponyme issu de mota/moteta (motte castrale, « la Mothe-Cassel », érigée près d'un chemin de pèlerinage — cf. Wikipédia). Bourg actif, repère cartographique. |
| **Ussel (bourg, église Saint-Martin)** | Ussel | 44.59407 | 1.49943 | [FAIT] | Ussel (46323) | Chef-lieu de la commune d'Ussel (non fusionnée). Bourg et église actifs — repère, pas une cible. |
| **Grotte Bourrue** | Grotte Bourrue | 44.60957 | 1.51156 | [À VÉRIFIER] | Lamothe-Cassel (46151) | Cavité karstique. Prudence : ce n'est pas une cible de prospection (statut archéologique et risques physiques inconnus). Signalée pour information/sécurité uniquement. **[EXCLUSION: cavité — prudence sécurité, pas une cible]** |

### Rang 1 — Signal fort (8 entrées)

| Nom | Forme source | Lat | Lon | Statut | Commune | Interprétation |
|---|---|---|---|---|---|---|
| **Puycalvel (hameau)** | Puycalvel | 44.60291 | 1.52307 | [À VÉRIFIER] | Lamothe-Cassel (46151) | Habitat groupé autour de l'église Saint-Vit (XIIe s.). Noyau ancien probable — mobilier d'occupation continue possible en périphérie de l'église (hors périmètre MH/cimetière). |
| **Motte castrale de la Mothe-Cassel — emplacement non localisé** | la Mothe-Cassel (motte castrale) | 44.61264 | 1.50624 | [À VÉRIFIER] | Lamothe-Cassel (46151) | Butte artificielle médiévale attestée par la toponymie et l'histoire communale, mais emplacement précis non localisé par les sources consultées. À rechercher au LiDAR autour du bourg et des anciens chemins. |
| **Soyris (paroisse disparue, castrum)** | Soyris | 44.63903 | 1.57182 | [À VÉRIFIER] | Labastide-Murat (46138) | Paroisse primitive Saint-Étienne de Soyris, sur laquelle la bastide de Labastide-Murat fut fondée en 1238 ; église aujourd'hui disparue. Castrum et repaire de Soyris mentionnés en 1290 ; un château de Soyris encore habité en 1772. Zone à fort potentiel d'occupation continue (paroissiale puis seigneuriale). |
| **Tour de Soyris** | Tour de Soyris | 44.63901 | 1.57163 | [À VÉRIFIER] | Labastide-Murat (46138) | Tour répertoriée par l'IGN mais avec un statut « Collecté » (non validé). Rattachée au lieu-dit cadastral SOYRIS. Sensible : une église et un cimetière paroissial disparus sont probables à proximité immédiate (paroisse Saint-Étienne de Soyris) — prudence sur toute sépulture éventuelle avant prospection. **[SENSIBLE: cimetière paroissial disparu possible à proximité]** |
| **Nougayrol (Soulomès)** | Nougayrol | 44.62197 | 1.56586 | [À VÉRIFIER] | Soulomès (46310) | Candidat pour la « terre et château de Nougayrols » mentionnée en 1465-1761. Second candidat homonyme (Nougeyral) à Lamothe-Cassel, voir ci-dessous — les deux restent à trancher. |
| **Nougeyral (Lamothe-Cassel)** | Nougeyral | 44.61976 | 1.50057 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Second candidat homonyme pour la « terre et château de Nougayrols » (1465-1761) — polygone partagé avec Cloup de Leygue (rang 3, ci-dessous). |
| **La Garnède** | la Garnède | 44.61878 | 1.56830 | [À VÉRIFIER] | Soulomès (46310) | Seigneurie des Soyris mentionnée en 1550-1567. À croiser avec archives seigneuriales. |
| **Pièce de Capelle** | Pièce de Capelle | 44.59722 | 1.57126 | [HYPOTHÈSE] | Les Pechs du Vers (46252) | Capela = chapelle. Pourrait aussi renvoyer aux seigneurs de Lacapelle (attestés à Puycalvel, 1457-1648, selon monographie Albe) — un patronyme, pas nécessairement un édifice. |

### Rang 2 — Moyen (31 entrées)

| Nom | Forme source | Lat | Lon | Statut | Commune | Interprétation |
|---|---|---|---|---|---|---|
| **Meylargues** | Meylargues (lieu-dit habité) | 44.62303 | 1.54042 | [HYPOTHÈSE] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Hameau qui donne son nom au projet. Le suffixe -argues correspond, dans le sud-est occitan, au type gallo-romain -ANICUM/-ANICAS (nom de personne + suffixe de domaine), évolution attestée par des formes datées ailleurs (Vendargues : Venerianicus 924 → Vendrargues 1536 ; Lansargues : Lanzanegues 1152). Le type est donc plausible ([FAIT] pour le mécanisme général), mais l'anthroponyme sous-jacent à Meylargues reste inconnu — aucune forme ancienne locale antérieure à Cassini n'a été retrouvée, et Dauzat & Rostaing ne traitent que les noms de communes (pas les hameaux). Le poids de la seigneurie de 1690 relève de l'histoire, pas de la toponymie. Point corrigé sur le hameau BD TOPO (le point cadastral moyen tombait à 243 m à l'OSO, dans un champ). |
| **La Courtie (ruines)** | La Courtie | 44.62493 | 1.58216 | [FAIT] | Soulomès (46310) | Ruine cartographiée par l'IGN. Datation et nature précises non connues. Groupe avec Pech Latour (631 m) et les Teulières (631 m). |
| **Champ de l'Église (Saint-Sauveur-la-Vallée)** | Champ de l'Eglise | 44.61701 | 1.53672 | [HYPOTHÈSE] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Toponyme « champ de l'église » : peut signaler une église disparue OU une terre appartenant à une église existante (fabrique, cure) — le même nom existe à Lamothe-Cassel (ci-dessous), à 140 m d'une église toujours active. Aucune chapelle disparue signalée ici par les sources consultées. Aucune église actuelle à moins de 1,8 km (Saint-Vit de Puycalvel : 1812 m ; point de culte non identifié vers 1.5534/44.6059 : 1811 m). À traiter comme surface (72 ha), pas comme point unique. |
| **Champ de l'Église (Lamothe-Cassel)** | Champ de l'Eglise | 44.62262 | 1.51054 | [À VÉRIFIER] | Lamothe-Cassel (46151) | Homonyme du précédent, à 26-76 m de l'église de l'Assomption de Murat (active) et de son cimetière — illustre que ce toponyme ne signale pas toujours une église disparue. |
| **La Tuilerie** | La Tuilerie | 44.65275 | 1.57595 | [À VÉRIFIER] | Labastide-Murat (46138) | L'État-major (XIXe s.) porte déjà « la Tuilerie » en périphérie nord-est du bourg — probablement une tuilerie moderne/contemporaine, rien n'indique une villa gallo-romaine sous-jacente. |
| **Les Teulières (Soulomès)** | les Teulières / la Teulière | 44.61949 | 1.58445 | [HYPOTHÈSE] | Soulomès (46310) | Forme occitane de « tuilerie » (teulièra), homologue à La Tuilerie ci-dessus. |
| **Les Bories** | les Bories | 44.62191 | 1.49639 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Borie = métairie/ferme en Quercy (occitan bòria), pas « cabane en pierre sèche » (sens forgé au XIXe s. en Provence ; dans le Lot ces cabanes se nomment caselles/gariottes — Wikipédia FR « Borie », revérifié). Lieu-dit « non habité » : métairie désertée possible, à vérifier sur Cassini/État-major/cadastre napoléonien. |
| **Fontaine des Cayres** | Fontaine des Cayres | 44.64056 | 1.51447 | [HYPOTHÈSE] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | « Cayres » renvoie au lieu-dit voisin Les Cayres/Cayrès (313-71 m), pas à un aménagement de pierres isolé. Fontaine du hameau des Cayres, plausible point d'eau ancien ; tout usage cultuel de source reste une hypothèse non étayée. |
| **Moulin de Caviole (moulin hydraulique ancien)** | Moulin Caviole / le Moulin de Caviole | 44.61008 | 1.54579 | [FAIT] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Moulin hydraulique ancien, bien étayé par Cassini et l'État-major. Mobilier de circulation (monnaies, ferrures) aux abords reste une hypothèse, pas un fait établi. |
| **Le Moulin Neuf** | le Moulin Neuf | 44.60038 | 1.55577 | [HYPOTHÈSE] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Moulin voisin du précédent, omis du relevé initial. Mobilier de circulation attendu aux abords — hypothèse. |
| **Le Moulin du Hasard (moulin à vent)** | le Moulin du Hasard | 44.65053 | 1.57936 | [FAIT] | Labastide-Murat (46138) | Moulin à vent recensé par l'IGN en sortie nord-est du bourg de Labastide-Murat. |
| **Moulin de Merle** | Moulin de Merle | 44.65265 | 1.50429 | [À VÉRIFIER] | Frayssinet (46113) | Moulin en limite ouest de l'emprise (commune de Frayssinet). |
| **Rignac** | Rignac | 44.59481 | 1.57241 | [À VÉRIFIER] | Les Pechs du Vers (46252) | Type étymologique -acum confirmé pour la commune homonyme du Lot (Renius + -ac) — l'application à ce lieu-dit reste [À VÉRIFIER]. Piège Polge possible (patronyme tardif). |
| **Cuzac** | Cuzac | 44.63330 | 1.54888 | [À VÉRIFIER] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Même type étymologique que Rignac (Cusius + -ac), confirmé pour la commune homonyme du Lot. |
| **Foissac** | Foissac | 44.62309 | 1.56996 | [À VÉRIFIER] | Soulomès (46310) | Suffixe -ac probable. Foissac est aussi un patronyme local (maire de Labastide-Murat 2001-2014) — piège Polge à garder en tête. |
| **Carniac** | Carniac | 44.64711 | 1.57961 | [HYPOTHÈSE] | Labastide-Murat (46138) | Suffixe -acum. La racine Carn- admet deux hypothèses documentées (Wikipédia « Carnac-Rouffiac ») : (1) anthroponyme gaulois *Carnus (majoritaire) ; (2) pré-celtique *karn « amas de pierres » (minoritaire, Dauzat). Aucune source ne mentionne un sens de « charnier »/dépôt pastoral. |
| **Brassac** | Brassac | 44.63677 | 1.57568 | [À VÉRIFIER] | Labastide-Murat (46138) | Suffixe -ac. Même réserve (piège Polge) que Rignac/Cuzac. |
| **Regagnac** | Regagnac | 44.64528 | 1.54824 | [À VÉRIFIER] | Cœur de Causse (46138) | Suffixe -ac. Même réserve que ci-dessus. |
| **Gauléjac** | Gauléjac / Gaullegeac | 44.62064 | 1.52191 | [À VÉRIFIER] | Lamothe-Cassel (46151) | Suffixe -ac. Aussi nom des vicomtes de Puycalvel (1457-1648, monographie Albe) — piège Polge patronymique probable. |
| **Ravazac** | Ravazac | 44.62719 | 1.51839 | [À VÉRIFIER] | Lamothe-Cassel (46151) | Suffixe -ac. Même réserve. |
| **Madirac** | Madirac | 44.59637 | 1.51662 | [À VÉRIFIER] | Lamothe-Cassel (46151) | Suffixe -ac. Même réserve. |
| **Ferrières** | Ferrières | 44.60459 | 1.50751 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Ferrièra = lieu du fer. Signal métallurgique potentiel (scories, minerai). |
| **Clos de Fargues** | Clos de Fargues | 44.64222 | 1.57712 | [HYPOTHÈSE] | Labastide-Murat (46138) | Farga = forge. Signal métallurgique ou patronyme (Fargues). |
| **Camp de Lasfargues** | Camp de Lasfargues | 44.60061 | 1.52012 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Même racine farga (forge) ou patronyme Fargues. |
| **Lafaurie** | Lafaurie | 44.59666 | 1.55925 | [HYPOTHÈSE] | Les Pechs du Vers (46252) | Faure = forgeron. Signal métallurgique ou patronymique. |
| **Le Fournet** | le Fournet | 44.61656 | 1.52575 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Fornet = petit four (à pain, à chaux ou artisanal). Signal artisanal générique. |
| **Pech Lagarde (Lamothe-Cassel)** | Pech Lagarde | 44.62665 | 1.52390 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Sommet nommé + hameau + lieu-dit — homonyme du Pech la Garde de Labastide-Murat (rang 3, ci-dessous), à 3563 m. « Garde » = guet OU patronyme Lagarde. |
| **Mas Lagarde** | le Mas Lagarde | 44.60807 | 1.53347 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Mas (métairie médiévale/moderne en Quercy — Lartigaut) + patronyme ou toponyme Lagarde probable. |
| **Pech Latour** | Pech Latour | 44.62868 | 1.57619 | [HYPOTHÈSE] | Soulomès (46310) | Latour est aussi un patronyme local (maire de Labastide-Murat 1876-1882) — piège Polge. À 631 m de La Courtie et des Teulières. |
| **Camp des Roumioux** | Camp des Roumioux | 44.60150 | 1.52666 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Roumioux = pèlerins (occitan romieu). Camp = champ. Signal historique lié aux chemins de pèlerinage vers Rocamadour, sans mobilier attendu spécifique. |
| **Les Justices** | Les Justices | 44.60360 | 1.53782 | [À VÉRIFIER] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Toponyme judiciaire — désigne fréquemment l'emplacement d'un ancien gibet seigneurial. Cohérent avec la haute justice attestée de la baronnie de Labastide (monographie Albe). Homologues : Lasjustices (Ussel) et Les Fourques (limite nord de l'emprise), tous deux hors emprise stricte. |

### Rang 3 — Faible / prudence (19 entrées)

| Nom | Forme source | Lat | Lon | Statut | Commune | Interprétation |
|---|---|---|---|---|---|---|
| **Le Puech** | Le Puech | 44.62019 | 1.53189 | [FAIT] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Colline nommée, toponyme générique de relief — signal faible seul. |
| **Cloup de Leygue** | Cloup de Leygue | 44.62031 | 1.49964 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Doline karstique (cloup = clòt). Leygue est aussi un patronyme attesté localement (Guillaume de Leygue, 1537, monographie Albe) — piège Polge possible sur le déterminant. Lieu-dit non habité, à Lamothe-Cassel (pas 46138). |
| **Cinq Pierres (ensemble, 3 communes)** | les Cinq Pierres | 44.63050 | 1.51966 | [HYPOTHÈSE] | Labastide-Murat / Saint-Sauveur-la-Vallée / Lamothe-Cassel (46138 + 46151) | ZONE À PRUDENCE. Ce n'est pas un doublon local mais un seul ensemble toponymique en 3 polygones cadastraux contigus, à la jonction de plusieurs anciennes communes/paroisses, longé par un grand chemin (Cassini, État-major). Aucun mégalithe recensé dans OSM ni dans les bases consultées à cette exécution, mais l'absence de source négative n'exclut rien : mégalithe (dolmen/menhir) OU bornage de limite paroissiale restent deux hypothèses concurrentes. NE PAS TRAITER COMME UNE CIBLE avant vérification (Atlas des patrimoines, SRA Occitanie, terrain). **[SENSIBLE: mégalithe potentiel — prospection interdite si confirmé]** |
| **Croix de chemin sans nom (bourg de Labastide-Murat)** | wayside_cross, sans name (OSM) | 44.64930 | 1.56746 | [FAIT] | Labastide-Murat (46138) | Le nom « Croix Blanche » attribué à ce point est inventé : le nœud OSM ne porte aucun nom. Situé dans le bourg de Labastide-Murat, à 3227 m (pas ~2 km) du lieu-dit cadastral La Croix Blanche. Simple repère de circulation ancienne, pas une cible. |
| **Croix Blanche (hameau)** | la Croix Blanche | 44.65021 | 1.52238 | [À VÉRIFIER] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Point recentré sur le hameau IGN validé (le centroïde cadastral du doc initial tombait à 356 m). Une croix de chemin est cartographiée à 55 m — le lien nom/objet reste une hypothèse. |
| **Le Camp Grand (hameau, Ussel)** | le camp grand | 44.60001 | 1.50235 | [FAIT] | Ussel (46323) | Camp = champ (latin campus), pas « champ clos ancien ». Hameau distinct du lieu-dit cadastral homonyme ci-dessous (2329 m d'écart). |
| **Camp Grand (lieu-dit, Lamothe-Cassel)** | Camp Grand | 44.60311 | 1.53136 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Toponyme générique (camp = champ). Signal faible seul. |
| **Roc de Bragues** | Roc de Bragues | 44.63028 | 1.57334 | [HYPOTHÈSE] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Affleurement rocheux nommé, repère géologique/paysager plutôt qu'anthropique. |
| **Montcuq (lieu-dit)** | Montcuq | 44.60782 | 1.54154 | [FAIT] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Étymologie établie pour la commune homonyme du Lot (mont + *kuk) — nom de relief générique, sans lien de proximité avec la commune de Montcuq-en-Quercy-Blanc (~43 km au sud-ouest). |
| **Le Cayrou (tumulus ou épierrement ?)** | le Cayrou | 44.61205 | 1.50879 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Cayrou = tas de pierres. Peut désigner un simple amas d'épierrement agricole OU se confondre avec un tumulus/pseudo-tumulus — à vérifier avant toute conclusion (pas une cible tant que la nature n'est pas établie). |
| **La Borie** | La Borie | 44.65388 | 1.56161 | [À VÉRIFIER] | Labastide-Murat (46138) | Borie = métairie (voir Les Bories ci-dessus). Hameau actuellement habité — toponyme banal dans l'emprise (Laborie, Laborie Blanche, Pièce de Laborie, Lasbouriettes). |
| **Pech la Garde (Labastide-Murat)** | Pech la Garde | 44.65101 | 1.55705 | [HYPOTHÈSE] | Labastide-Murat (46138) | Schéma colline + patronyme fréquent dans l'emprise (Pech Lagarde à Lamothe-Cassel, à 3563 m ; Pech Latour ; le Mas Lagarde) — piège Polge classique. Poste de guet possible OU simple patronyme Lagarde. |
| **Les Cayres / Cayrès** | Les Cayres / Cayrès | 44.63532 | 1.51751 | [FAIT] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Lieu-dit dont dérive le nom de la Fontaine des Cayres (rang 1, ci-dessus). |
| **Chayroux / Chayroux-Bas** | Chayroux | 44.64376 | 1.55986 | [HYPOTHÈSE] | Saint-Sauveur-la-Vallée / Cœur de Causse (46138) | Variante de cayrou/cairon (lieu pierreux). Position : [FAIT]. Sens précis : hypothèse. |
| **Le Cayrol** | Le Cayrol | 44.59668 | 1.49910 | [HYPOTHÈSE] | Ussel (46323) | Même racine que Cayrou/Chayroux (lieu pierreux). |
| **Laborie Blanche** | Laborie Blanche | 44.60198 | 1.56710 | [HYPOTHÈSE] | Les Pechs du Vers (46252) | Borie = métairie. Toponyme banal de l'emprise. |
| **Pièce de Laborie** | Pièce de Laborie | 44.59717 | 1.50609 | [HYPOTHÈSE] | Ussel (46323) | Même racine borie (métairie). |
| **Les Jasses** | les Jasses | 44.59977 | 1.53144 | [HYPOTHÈSE] | Lamothe-Cassel (46151) | Jasse = bergerie/parc à moutons en occitan. Signal pastoral générique. |
| **Foulon** | Foulon | 44.65471 | 1.54589 | [HYPOTHÈSE] | Cœur de Causse (46138) | Foulon = moulin à fouler (drap). Signal artisanal générique. Le lieu-dit déborde au nord de l'emprise d'étude. |

---

## 3. Zones à prudence et exclusions

### 3.1 Monuments historiques inscrits — exclusion stricte

| Site | Référence MH | Dates d'inscription | Tampon proposé | Source de vérification |
|---|---|---|---|---|
| **Château de Labastide-Murat** | PA00095306 | Façades/toitures : 16/09/1991 · Parc : 24/03/1992 | 500 m | OSM way/298756904 (ref:mhs, mhs:inscription_date) + Wikidata Q15944355 (P1435, P580) — deux sources indépendantes concordantes |
| **Église Saint-Vit de Puycalvel** | PA00095121 | 28/06/1927 | 300 m | OSM way/298267132 (ref:mhs, mhs:inscription_date) + Wikidata Q22939568 |
| **Église Saint-Jean-Baptiste de Goudou** *(hors emprise, buffer mordant)* | PA00125599 | 15/11/1993 | 500 m — **note pour agrandissement futur de l'emprise, non intégré au geojson actuel** (centre à 182 m au-delà du coin NE) | Wikidata Q22969044 (P1435, qualificateur P580) |

Ces trois inscriptions ont été vérifiées indépendamment via **deux sources structurées concordantes** (tags OSM `heritage`/`ref:mhs`/`mhs:inscription_date` + déclarations Wikidata P1435/P580), sans jamais s'appuyer sur la seule page Mérimée (interface JavaScript non lisible par requête simple — voir §4).

### 3.2 Zones sensibles (prudence, pas de protection réglementaire confirmée)

- **Tour de Soyris** — statut BD TOPO « Collecté » (non validé par l'IGN). La paroisse Saint-Étienne de Soyris a disparu ; une église et un cimetière paroissial sont probables à proximité immédiate. Prudence sur toute découverte de sépulture.
- **Ensemble « Cinq Pierres »** (3 polygones cadastraux fusionnés, ~64 ha, à la jonction Labastide-Murat/Saint-Sauveur/Lamothe-Cassel/Beaumat) — mégalithe (dolmen/menhir) **ou** bornage de limite paroissiale. Aucun mégalithe recensé dans OSM à cette exécution (miroir Overpass `overpass.kumi.systems` injoignable ce jour — délai réseau > 90 s sans réponse ; **le résultat négatif n'est donc pas confirmé, seulement non-infirmé**). **Ne jamais traiter comme une cible** avant vérification : Atlas des patrimoines (atlas.patrimoines.culture.fr), service régional de l'archéologie (SRA Occitanie), ou reconnaissance terrain.
- **Grotte Bourrue** — cavité karstique, seule grotte nommée de l'emprise. Pas une cible : statut archéologique inconnu, risque physique (chute, effondrement).

### 3.3 Règle d'application (scoring)

Conformément à la règle « sites connus = jamais de cible » (doctrine du projet) :
1. Exclure du calcul de score tout point `rank: 0` avec `role: "exclusion"`, avec le tampon (`buffer_m`) indiqué.
2. Signaler visuellement (sans exclure) tout point avec `role: "sensible"`.
3. L'ensemble Cinq Pierres reste au geojson en un point unique (étiquette IGN, 1.51966/44.63050) faute de schéma multipolygone dans ce fichier — la prudence doit être appliquée manuellement par l'app tant qu'un statut définitif n'est pas connu.

---

## 4. Sources interrogées — détail technique et vérifications effectuées cette session

| Source | Requête | Résultat vérifié cette session |
|---|---|---|
| **Cadastre Etalab** | `cadastre-{46138,46151,46252,46310,46113,46323}-lieux_dits.json.gz` (millésime 2026-06-01) | 302+86+155+31+127+33 = **734 polygones** sur les 6 communes (auparavant : 302 sur 46138 seul) |
| **Cadastre Etalab** | `cadastre-46138-parcelles.json.gz` | Point-in-polygon exact : l'ancien point « Le Château » (1.55997/44.64136) tombe dans la parcelle **A 600** (15,9 ha, le parc inscrit) ; le bâtiment BD TOPO/OSM (1.56216/44.64168) tombe dans la parcelle **A 599** — confirme exactement la fiche de protection MH (« CADA A 599, 600 ») |
| **BD TOPO V3 WFS** | 8 couches (`toponymie`, `zone_d_habitation`, `lieu_dit_non_habite`, `detail_orographique`, `cimetiere`, `construction_ponctuelle`, `zone_d_activite_ou_d_interet`, `commune_associee_ou_deleguee`), BBOX `44.5921,1.4963,44.6549,1.5847,urn:ogc:def:crs:EPSG::4326` | 256+123+44+21+7+34+47+6 = **538 objets**. Vocabulaire vérifié : `zone_d_habitation` contient réellement 2 « Château » (dont Tour de Soyris ET le Château lui-même — le second avait été oublié), 1 « Ruines » (La Courtie) ; `lieu_dit_non_habite` contient 41 « Lieu-dit non habité » + 3 « Bois » — **aucune catégorie OSM (isolated_dwelling, wayside_cross, memorial) n'existe dans ce champ** : erreur de vocabulaire de la version précédente confirmée |
| **OSM API** | `api.openstreetmap.org/api/0.6/{node,way}/{id}.json`, User-Agent navigateur | 7 objets vérifiés individuellement (château, croix, 5 églises) — tags bruts cités dans les sources de chaque entrée §2 |
| **Wikidata** | `Special:EntityData/{Q-id}.json` | 8 entités vérifiées (château, 3 églises, cimetière, mégalithes du Lot) — confirme indépendamment les dates MH lues sur OSM (concordance à 100 %) |
| **Wikipédia FR** | API `action=query&prop=extracts`, 12 pages | Confirme l'étymologie/histoire de Labastide-Murat, Lamothe-Cassel, Montcuq, Rignac, Cuzac, Carnac-Rouffiac, Vendargues/Lansargues (type -anicum/-argues) et Borie (métairie en Quercy vs cabane en Provence) |
| **geo.api.gouv.fr** | `communes?codeDepartement=46&format=geojson&geometry=contour` | Intersection géométrique (Lambert-93, shapely/pyproj) des 6 communes avec l'emprise : **52,5 % / 21,4 % / 12,7 % / 5,8 % / 4,3 % / 3,3 % = 100,0 %** exactement |
| **Overpass OSM** | `overpass.kumi.systems/api/interpreter` (miroir habituel) | **Injoignable cette session** (délai > 90 s, 0 octet reçu, TLS OK mais pas de réponse HTTP) — `overpass-api.de` direct confirmé **406 Not Acceptable** comme documenté. Recherche de mégalithes dans OSM **non confirmée** cette session (voir §3.2) |
| **Mérimée (pop.culture.gouv.fr)** | Page notice HTML | **Non exploitable directement** : application JavaScript monopage sans données dans le HTML statique (`<title>Château - POP</title>` seul contenu utile). Contourné via OSM `ref:mhs`/`mhs:inscription_date` + Wikidata P1435/P580, deux sources indépendantes concordantes |

**Gotchas confirmés cette session (à propager si récurrents)** :
- Le miroir Overpass `overpass.kumi.systems` peut être injoignable (timeout sans erreur HTTP) même quand la poignée de main TLS réussit — prévoir un budget de retry et ne jamais présenter un « 0 résultat » Overpass comme une preuve d'absence sans le confirmer par un second essai à un autre moment.
- Les pages `pop.culture.gouv.fr/notice/merimee/*` sont des SPA JavaScript : aucune donnée n'est présente dans le HTML brut. Utiliser OSM (`ref:mhs`, `mhs:inscription_date`, `heritage`) et Wikidata (P1435, P580) comme sources structurées de remplacement.
- Le centroïde d'un polygone cadastral calculé par simple moyenne des sommets (méthode de la version précédente) peut s'écarter de 50 à 150 m du centroïde d'aire réel pour des polygones allongés ou concaves — utiliser le centroïde d'aire (shapely `.centroid`) systématiquement.
- BBOX WFS toujours en ordre **lat,lon** avec `urn:ogc:def:crs:EPSG::4326` pour EPSG:4326 (reconfirmé).

---

## 5. Travail restant

| Tâche | Raison | Priorité |
|---|---|---|
| Confirmer/infirmer mégalithe(s) à l'ensemble Cinq Pierres | Zone à prudence non tranchée — Overpass injoignable cette session, à retenter | **HAUTE** |
| Localiser précisément la motte castrale de la Mothe-Cassel au LiDAR | Attestée par l'histoire communale mais emplacement inconnu | **HAUTE** |
| Trancher Nougayrol (Soulomès) vs Nougeyral (Lamothe-Cassel) pour la « terre et château de Nougayrols » (1465-1761) | Deux candidats homonymes dans l'emprise | **MOYENNE** |
| Consulter les compoix/terriers des AD46 pour l'anthroponyme sous-jacent à Meylargues | Dauzat & Rostaing ne traitent que les communes, pas les hameaux | **MOYENNE** |
| Vérifier au sol/Atlas des patrimoines la nature de la Tour de Soyris (tour féodale vs clocher) et l'emplacement du cimetière paroissial disparu | Statut BD TOPO « Collecté » = non validé | **MOYENNE** |
| Reconfirmer l'absence de mégalithe OSM autour de Cinq Pierres (miroir Overpass) | Résultat non obtenu cette session (timeout réseau) | **MOYENNE** |
| Vérifier Rignac/Cuzac/Foissac/Carniac/Brassac/Regagnac/Gauléjac/Ravazac/Madirac contre les compoix (piège Polge patronymique) | Distinguer domaine antique réel de patronyme tardif | **BASSE** |

---

## 6. Fichiers générés

- **`data/derived/toponymes.geojson`** : FeatureCollection (70 Points, WGS84 lon/lat, CRS EPSG:4326). Propriétés de base : `name`, `sourceForm`, `source`, `rank`, `interpretation`, `status` (schéma inchangé) ; propriétés ajoutées pour les exclusions/zones sensibles : `commune`, `role` (`exclusion`|`sensible`), `protection`, `buffer_m`.
- **Ce fichier** : glossaire des racines + relevé classé, référence textuelle.

**Filtrage à appliquer lors du chargement du geojson dans l'app** :
- Exclure `rank: 0` du scoring de cible (repère seulement).
- **Exclure activement** (buffer négatif) tout point `role: "exclusion"`, rayon `buffer_m`.
- **Signaler visuellement sans exclure** tout point `role: "sensible"` (Tour de Soyris, ensemble Cinq Pierres).
- Traiter l'ensemble Cinq Pierres comme un périmètre à vérifier avant tout affichage en cible, jamais comme un signal positif de rang 3 standard.
