# Toponymie — Grove / Tullaghanbrogue (Co. Kilkenny, Irlande)

**Date de rédaction : 2026-09-28.** Zone : rayon d'environ 5 km autour de 52.600940 N, -7.328378 W (ITM 645497 E / 650176 N) — le moated site **KK023-031004-**, townland **Grove**, paroisse civile **Tullaghanbrogue**, barony **Shillelogher**, Co. Kilkenny.

**Cadrage — dossier de connaissance patrimoniale.** Ce document relève et interprète des noms de lieux pour comprendre l'histoire du peuplement. Il ne contient et ne doit pas contenir de recommandation de prospection, de réglage de détecteur ni d'estimation de mobilier : détecter sans consentement ministériel sur ce type de site est une infraction pénale en Irlande (National Monuments (Amendment) Act 1987, s.2). Le « rang » défini en §4 mesure la force d'un indice **historique**, pas un potentiel de prospection.

**Marqueurs** (contraignants, cf. `docs/PLAN.md` §0 et le brief commun) : **[FAIT]** sourcé et vérifié cette session ; **[À VÉRIFIER]** plausible, non confirmé cette session ; **[HYPOTHÈSE]** déduction sans source. Aucune déduction n'est présentée comme un fait.

**Méthode** : calquée sur le lexique gascon du `docs/PLAN.md` §2.5 (Armous-et-Cau), adaptée à l'irlandais. Sources principales : [logainm.ie](https://www.logainm.ie/en/) (Placenames Database of Ireland, glossaire et fiches de townlands), [townlands.ie](https://www.townlands.ie/), et **Carrigan, W. 1905, *The History and Antiquities of the Diocese of Ossory*, vol. 3** — lu **intégralement** cette session via [archive.org/details/historyantiquiti0003revw](https://archive.org/details/historyantiquiti0003revw) (texte OCR téléchargé et dépouillé par mots-clés), ce qui confirme et prolonge nettement la citation du brief commun (« Carrigan 1905, vol. 3, p. 385-389 »). O'Kelly, O. 1969, *The place-names of County Kilkenny*, cité par le SMR mais **non accessible en ligne cette session** [À VÉRIFIER — salle de lecture ou bibliothèque universitaire irlandaise].

---

## 0. Synthèse d'exécution

| Métrique | Résultat |
|---|---|
| **Toponymes relevés et géolocalisés** | **50** entrées dans `data/toponymes.geojson` |
| **Townlands travaillés en profondeur (Tier 1)** | 18 (Tullaghanbrogue, Grove, Kyleandangan, Aghenderry, Booly, Ballybur + Ballybur Lower + Ballybur Upper, Church Hill, Castleinch or Inchyolaghan, Desart Court/Demesne, Ballymack (Desart), Grangecuffe, Raheenduff, Grange, Kilballykeefe, Burnchurch, Ballykeefe) |
| **Autres townlands du rayon (Tier 2)** | 27 — lecture rapide (nom anglais + type de monument SMR), étymologie précise **non vérifiée sur logainm.ie** cette session sauf mention contraire |
| **Microtoponymes (non-townland)** | 5 — tous lus directement dans Carrigan 1905 ou déjà sourcés par le brief commun |
| **Rang 1 (nom = monument, confirmé par le SMR)** | 22 entrées |
| **Rang 2 (indice non confirmé par le SMR)** | 8 entrées |
| **Rang 3 (descriptif ou anthroponyme)** | 20 entrées |
| **Statut** | 15 [FAIT], 21 [À VÉRIFIER], 14 [HYPOTHÈSE] |
| **Hors rayon, exclu** | **Danesfort** (townland, ~7,4 km du point — calcul ci-dessous) : mentionné en §5 pour son intérêt méthodologique uniquement, aucun point geojson |
| **Non exploité** | O'Kelly 1969 (salle de lecture) ; OS Name Books individuels (logainm.ie ne les affiche pas en ligne pour ce secteur cette session) |

---

## 1. Lexique irlandais — équivalent du lexique gascon (PLAN §2.5)

Source principale : **[logainm.ie/en/glossary](https://www.logainm.ie/en/glossary)** (glossaire officiel de la Placenames Database of Ireland), complété par des citations directes de **P.W. Joyce**, *The Origin and History of Irish Names of Places* (via [libraryireland.com](https://www.libraryireland.com/IrishPlaceNames/)) et de Carrigan 1905 pour les cas concrets.

| Terme irlandais | Sens | Ce que le nom signale historiquement |
|---|---|---|
| `ráth` | ring-fort (levée de terre circulaire) | Habitat fortifié protohistorique/haut médiéval — l'équivalent structurel de la *mothe* gasconne mais bien plus fréquent en Irlande |
| `lios`, `lis` | ring-fort, enclos | Idem *ráth* ; souvent utilisé de façon interchangeable dans la toponymie (cf. Desart Court/Lios Loinín, §2) |
| `dún` | fort (souvent plus grand/plus prestigieux qu'un ráth) | Fort royal ou seigneurial ; à Kilkenny le composé `daingean` (forteresse, apparenté) joue un rôle voisin (Kyleandangan, §2) |
| `cathair`, `caher` | fort de pierre circulaire | Équivalent de *caiseal* ; rare dans ce secteur (argile, pas de pierre sèche dominante) |
| `caiseal`, `cashel` | fort de pierre circulaire sans mortier | Idem — non rencontré dans le rayon étudié |
| `móta`, `mota` | motte (tertre artificiel, souvent anglo-normand) | Motte castrale — confirmée ici par KK023-032---- (Castle - motte), à ~25 m du moated site de Grove |
| `caisleán` | château | Fortification de pierre médiévale ou post-médiévale — l'anglais « castle » sert souvent de calque direct (Castleinch, Castleblunden, Ballykeefecastle) |
| `cill`, `kil-` | église | **Église, souvent disparue** — le marqueur ecclésiastique le plus productif du secteur (Kilballykeefe, Kilmog) |
| `teampall` | église | Idem *cill* ; composé dans *Cnoc an Teampaill* (Church Hill) |
| `díseart`, `desert` | ermitage | Site d'ermite/de retraite monastique — **piège** à Desart Court, voir §5 |
| `tobar` | puits | Puits sacré, souvent christianisé — Thubberniclaush (Kilballykeefe), le puits de Grange |
| `gráinseach`, `grange` | grange, ferme monastique | Dépendance agricole d'une abbaye — Grangecuffe, Grange |
| `baile`, `bally-` | townland, ville, tenure | Générique le plus fréquent — **souvent suivi d'un patronyme** (voir §5) |
| `áth` | gué | Point de franchissement ancien — plusieurs gués nommés dans les bornages de 1607 (« le Maddeduffe », « Aghenore », « Agheline ») |
| `bóthar` | route | Voie ancienne — « Boher-na-monnach » (chemin des moines, Annamult, Carrigan p.578) |
| `droichead` | pont | Point de franchissement aménagé — non rencontré nommément dans le rayon |
| `muileann` | moulin | Site économique — confirmé par le moulin à roue horizontale KK019-038 (Castleinch) |
| `cnoc` | colline | Site de hauteur — souvent combiné à un mot ecclésiastique ou funéraire (Cnoc an Teampaill) |
| `tulach`, `tulachán` | tertre, colline, monticule | **Motte, tumulus ou point haut occupé** — élément du nom paroissial Tulchán Bróg (Tullaghanbrogue), confirmé par la motte KK023-032 ; aussi Tullamaine |
| `carn` | cairn, amas de pierres | Monument funéraire ou repère — non rencontré nommément dans le rayon |
| `leacht` | tombeau, monument commémoratif | Marqueur funéraire ou de dévotion — non rencontré nommément, mais catégorie SMR proche (« chest tomb », « graveslab ») abondante à Grove et Burnchurch |
| `cloch` | pierre, construction de pierre | Édifice ou mégalithe selon le contexte — non rencontré nommément |
| `coill`, `kyle-` | bois | Élément descriptif, mais **porteur de signal quand combiné** à un mot fortifié (Kyleandangan = « bois de la forteresse ») |
| `doire`, `derry` | bois de chênes | Descriptif pur — Aghenderry (« champ du bois de chênes »), nom qui ne signale rien malgré un ringfort attesté (§5) |
| `achadh`, `agha-` | champ | Descriptif pur, très fréquent, faible valeur diagnostique isolément |
| `inis`, `inse` | île, pré riverain | Descriptif topographique — Inse Uí Uallacháin (Castleinch), où c'est le nom ANGLAIS (« Castle ») qui porte le signal, pas l'irlandais |
| `buaile`, `booly` | enclos à bétail, pacage d'estive | Site de transhumance saisonnière — type de site reconnu en archéologie du paysage irlandais (Booly, confirmé par un enclos SMR) |
| `sean` | vieux | Qualificatif — Oldtown (« baile sean ») |
| `ros` | hauteur boisée, bois, promontoire | Descriptif topographique — non rencontré nommément dans le rayon (cf. Rossdamma, paroisse de Grange, non individuellement vérifié) |
| `cluain` | pré, pâturage | Descriptif topographique — candidat concurrent pour le second élément de « Desart » (Lios **Cluainín**, lecture de Carrigan — voir §2 et §5) |
| `garrán` | bosquet, taillis | **Purement descriptif** — c'est le nom actuel de Grove (An Garrán), qui remplace depuis 1666 seulement l'ancien nom porteur de signal (Tullaghanbroge) : voir §5 |
| `daingean` | forteresse, place forte | Apparenté à *dún* — Kyleandangan (« le bois de la forteresse »), confirmé par un enclos SMR |

**Point de méthode Joyce**, confirmé par recherche cette session : Joyce note que les incursions scandinaves (« Danes ») **n'ont laissé pratiquement aucune trace dans la toponymie irlandaise**, qui reste très majoritairement celtique — un point directement utile pour l'avertissement sur « Danesfort », §5.

---

## 2. Townlands du rayon (~5 km)

### 2.1 La paroisse civile de Tullaghanbrogue

**[À VÉRIFIER — synthèse de recherche web, non lue sur une fiche logainm unique]** La paroisse civile de **Tullaghanbrogue** (irl. *Tulchán Bróg*) s'étend sur les baronies de **Shillelogher et Crannagh**, 14,1 km², et compte **18 townlands** selon townlands.ie. Les townlands identifiés cette session : **Desart Court** (la plus grande, 498 ac. 2 r. 3 p.), **Grove** (328 ac. 2 r. 26 p.), **Aghinraheen** (321 ac. 2 r. 27 p., irl. *Achadh an Ráithín* — « champ du petit ráth », signal non confirmé par le SMR dans le rayon étudié), **Ballykeefecastle**, **Ballykeefe**, **Ballybur**, **Kyleandangan**, **Aghenderry**, **Coolapoge** (irl. *Cúil Lapóg*, attesté « Cowleloppoge »/« Cowluppoge » dans les inquisitions de 1607/1626-7 citées par Carrigan). **9 autres townlands de la paroisse n'ont pas été individuellement recherchés cette session** — liste complète : [townlands.ie/kilkenny/tullaghanbrogue1/](https://www.townlands.ie/kilkenny/tullaghanbrogue1/).

Point capital, lu directement dans Carrigan (1905, p.385) : **« The parish church of Tullaghanbroge, now generally called Grove, is still a substantial, but very broken, ruin »** — dès 1905, le nom *Grove* avait déjà supplanté l'ancien nom paroissial dans l'usage courant, bien que l'un et l'autre désignent le **même lieu**.

### 2.2 Townlands travaillés en profondeur (Tier 1)

| Townland (EN) | Irlandais (logainm) | Formes historiques attestées | Étymologie / sens | Rang | Statut |
|---|---|---|---|---|---|
| **Tullaghanbrogue** (paroisse/manoir) | *Tulchán Bróg* | Thulachbroc, Tulachbroc, Tolachanbroc, Tulagbroc (reg. abbaye St Thomas, Dublin, XIII<sup>e</sup> s.) ; Tilhanbrog, Tylabrog, Tyllahtnebrog, Tillaghbrok, Tulohanbrog (Red Book of Ossory) ; Tullaghanbroge (inq. 1607, 1626-7) ; Tullihanbrog (épitaphe 1597) ; Tullohaune (Down Survey, 1655-6) ; Tullaghane (renommé « Cuffe's grove », 1666) | *tulchán* = petit tertre (diminutif de *tulach*) ; second élément *bróg* non résolu [À VÉRIFIER] | **1** | Forme *Tulchán Bróg* [FAIT] : c'est le nom de la paroisse civile sur la fiche logainm de Grove ([26411](https://www.logainm.ie/en/26411), relue par l'orchestrateur le 2026-09-28). ID propre de la paroisse : [À VÉRIFIER] |
| **Grove** | *An Garrán* ([26411](https://www.logainm.ie/en/26411)) | = Tullaghanbrogue ci-dessus (même lieu, renommé 1666) | *garrán* = bosquet (purement descriptif — voir §5) | **1**\* | [FAIT] |
| **Kyleandangan** | *Coill an Daingin* ([26413](https://www.logainm.ie/en/26413)) | — | *coill* (bois) + *daingean* (forteresse) : « le bois de la forteresse » | **1** | [FAIT] |
| **Aghenderry** | *Achadh an Doire* ([26403](https://www.logainm.ie/en/26403)) | — | *achadh* (champ) + *doire* (bois de chênes) — purement descriptif | **3** | [FAIT] |
| **Booly** | *An Bhuaile* ([26121](https://www.logainm.ie/en/26121)) | — | *buaile* = enclos à bétail saisonnier (transhumance) | **1** | [FAIT] |
| **Ballybur** (×3 : plain, Lower, Upper) | *Baile an Bhurraigh* (Íochtarach/Uachtarach) ([26405](https://www.logainm.ie/en/26405)) | Ballibur (Comerford, « lord of Ballibur », tombeau 1637) | *baile* + élément « Bhurraigh » non traduit par logainm (probable patronyme) | **3** | [À VÉRIFIER] |
| **Church Hill** | *Cnoc an Teampaill* ([26880](https://www.logainm.ie/en/26880)) | — | *cnoc* (colline) + *teampall* (église) | **1** | [FAIT] |
| **Castleinch or Inchyolaghan** | *Inse Uí Uallacháin* ([1273](https://www.logainm.ie/en/1273)) | Inchevolahane (renommé « Castle Inch », 1666) ; Inchywoolahan/Inchyholohan | irl. = *inis* + patronyme Ó Uallacháin ; EN « Castle » ajouté en 1666, signale directement le château | **1** | [FAIT] |
| **Desart Court / Desart Demesne** | *Lios Loinín* (logainm) / *Lios Cluainín* (Carrigan) | Lyslonyn, Lislonyn, Leslonyn, Lislone (inq. 1607-1636) ; Lissnonyne (1641) ; Lislonen (forfeiture 1653 ; renommé « Cuffe's Desert », 1666) ; Dizart/Desart (dès 1691) ; Lischlooineen/Lislooineen (prononciation relevée par Carrigan) | *lios* (ringfort) + second élément disputé : Loinín (nom propre) ou *cluainín* (petit pré) — non tranché | **1** | [À VÉRIFIER] |
| **Ballymack (Desart)** | *Baile Mhic Dháith* ([26118](https://www.logainm.ie/en/26118)) | — | *baile* + Mac Dáith : Carrigan traduit lui-même « the Town of David's Son » | **3** | [FAIT] |
| **Grangecuffe** | *Gráinseach Chuffe* ([26882](https://www.logainm.ie/en/26882)) | Cuffe's Grange / Cuff's Grange (formes locales) | *gráinseach* = ferme monastique ; Carrigan y situe les vestiges concrets de la grange | **2**\*\* | [À VÉRIFIER] |
| **Raheenduff** | *An Ráithín Dubh* ([26884](https://www.logainm.ie/en/26884)) | — | *ráithín* (petit ráth) + *dubh* (noir) | **1** | [FAIT] |
| **Grange** (Shillelogher By.) | *An Ghráinseach* (générique) | — | *gráinseach* = ferme monastique, générique | **1** | [À VÉRIFIER] ID logainm |
| **Kilballykeefe** | *Cill Bhaile Uí Chaoimh* ([26385](https://www.logainm.ie/en/26385)) | Balykene (« Chapel of Balykene », conf. c.1230) | *cill* (église) + baile Uí Chaoimh | **1** | [FAIT] |
| **Burnchurch** | *An Teampall Loiscthe* | — | *teampall loiscthe* = « l'église brûlée » — l'anglais est une traduction exacte, pas un hasard | **1** | [À VÉRIFIER] ID logainm |
| **Ballykeefe** | *Baile Uí Chaoimh* ([26345](https://www.logainm.ie/en/26345)) | — | *baile* + Ó Caoimh : Carrigan traduit « the Town of O'Keeffe » | **3** | [FAIT] |

\* Rang 1 obtenu **via la forme historique** (Tullaghanbroge/*tulachán*) : le nom actuel (*An Garrán*, « bosquet ») est en lui-même purement descriptif et ne signalerait rien seul — voir méthode §4 et avertissement §5.
\*\* Non confirmé par un point SMR dans l'extraction 5 km utilisée cette session ; Carrigan atteste pourtant des vestiges *de visu* en 1905 (§5, §6).

### 2.3 Autres townlands du rayon (Tier 2 — lecture rapide, non vérifiée individuellement sur logainm.ie)

Relevé à partir des 134 enregistrements de `smr_5km.geojson` (champ `TOWNLAND`) : nom anglais, lecture des éléments reconnaissables, type de monument SMR confirmant ou non. **Étymologie précise non vérifiée sur logainm.ie cette session** pour ces 27 townlands, sauf mentions Carrigan explicites.

| Townland | Lecture rapide du nom | Monument(s) SMR dans le townland | Rang |
|---|---|---|---|
| Ballycallan | *baile* + patronyme probable [HYPOTHÈSE] | Église, croix, 5 graveslabs, enclos, pierre inscrite | 2 |
| Ballykeefe Bog / Ballykeefe Hill / Ballykeefecastle | *baile* Uí Chaoimh + qualificatif anglais ; **Ballykeefecastle** signale directement un château | Enclos ; enclos ; **Castle + Bawn** | 3 / 2 / **1** |
| Bodalmore | élément non identifié [HYPOTHÈSE] | Enclos | 3 |
| Castleblunden | « castle » + patronyme Blunden | **Castle + Bawn**, enclos, sépulture | **1** |
| Coalsfarm | anglais descriptif [HYPOTHÈSE] | Enclos | 3 |
| Curragh (Crannagh By.) | *currach* = marécage — descriptif | Enclos, croix | 3 |
| Damma Upper | élément non identifié [HYPOTHÈSE] | Maison XVII<sup>e</sup> s. (non médiéval) | 3 |
| Farmley | anglais [HYPOTHÈSE] | Tower house, bawn — non annoncés par le nom | 3 |
| Gorteenteen | *goirtín* (petit champ) + élément non résolu | Ringfort-rath | 2 |
| Goslingstown | patronyme Gosling + « town » | Tower house, maison XVI<sup>e</sup>/XVII<sup>e</sup> s. | 3 |
| Graigueooly | *gráig* (hameau) + élément non résolu | Ringfort-rath, sépulture, fulacht fia | 2 |
| Greatwood | anglais descriptif — nom « silencieux » | Église + enclos ecclésiastique | 3 |
| Grevine West | élément non identifié [HYPOTHÈSE] | Enclos | 3 |
| Knocklegan | *cnoc* + élément non résolu | Pierre dressée | 2 |
| Knockreagh | *cnoc* + *riabhach* (grisâtre) — descriptif | Fulacht fia | 3 |
| Michaelschurch | « church » (St Michael) : signal direct | Église, 2 monuments muraux, cimetière | **1** |
| Newlands | anglais moderne, descriptif | Enclos | 3 |
| Newtown (Baker) | *baile nua* — nom générique fréquent | 2 enclos | 3 |
| Oldtown (Shillelogher By.) | *baile sean* — nom générique | 2 systèmes de champs anciens, 2 enclos | 2 |
| Ovenstown | anglais [HYPOTHÈSE] | Enclos | 3 |
| Parkmore | *páirc mór* — descriptif (demesne) | Enclos | 3 |
| Raheenapisha | *ráithín* + élément non résolu [HYPOTHÈSE] | **Moated site, 2 enclos, four à sécher le grain** | **1** |
| Rathaleek | *ráth* + élément non résolu [HYPOTHÈSE] | Enclos | **1** |
| Tullamaine (Ashbrook) | *tulach* + élément additionnel ; cité « Kiltullaghmaine » par Carrigan (bornage 1607/1626-7) | Enclos, église, cimetière, habitat groupé, puits sacré | **1** |
| Kilmog or Racecourse | *cill* + élément non résolu [HYPOTHÈSE] ; cité « Kilmeggeth otherwise Kilmogg » par Carrigan dès le XIII<sup>e</sup> s. | Église, cimetière, bullaun stone, arbre sacré, midden | **1** |

---

## 3. Microtoponymes (non-townland)

| Nom | Irlandais | Sens / contexte | Source |
|---|---|---|---|
| **Roilig a Tulacháin** | *Roilig an Tulcháin* | « le cimetière du tulchán » — cimetière de Tullaghanbrogue/Grove | OS Letters 1839 (O'Flanagan 1930), cité par le SMR (WEB_NOTES) et le brief commun |
| **The Glebe** | — | Champ à l'est d'un puits probablement sacré et de fondations dites d'un « ancien monastère », à Grove | **[FAIT, lu directement]** Carrigan 1905, vol.3 p.386 : *« many traces of foundations, which are said to mark the site of an ancient monastery... known as 'the glebe' »* |
| **Cill Féichín / Tamplefeighane** | *Cill Féichín* | Église détruite dédiée à saint Féichín, « Church field » du demesne de Desart Court | **[FAIT, lu directement]** Carrigan 1905, vol.3 p.389 |
| **Thubberniclaush** | *Tobar Naomh Nioclás* | Puits de saint Nicolas, patron de l'église de Kilballykeefe | **[FAIT, lu directement]** Carrigan 1905, vol.3 p.436 |
| **Pawrknagullam** | *Páirc na gColúr* | « le champ des pigeons », site des vestiges de la grange monastique à Cuffe's Grange | **[FAIT, lu directement]** Carrigan 1905, vol.3 p.391-392 |

Autres microtoponymes lus dans les bornages de 1607/1626-7 (Carrigan p.387-388) sans localisation précise possible cette session : « le Maddeduffe » (gué), « Tobernedoihy » (*Tobar na n-Ochtar*, puits de la jonction des domaines), « Monynenemanleman », « Boherkeagh », « Gorteviskey ». **[À VÉRIFIER — non géolocalisés]**.

---

## 4. Méthode de classement par rang (1-3)

Le rang mesure la **force de l'indice historique porté par le nom**, pas un potentiel de prospection (cadrage §0). Trois niveaux, appliqués au **meilleur signal disponible sur l'ensemble des formes attestées** d'un même lieu (pas seulement la forme actuelle) :

- **Rang 1** : le nom (actuel OU historique) désigne directement un type de monument (ráth, lios, dún, caiseal, móta, caisleán, cill, teampall, díseart, tobar, gráinseach, tulach, muileann, daingean, buaile...), **et** un monument SMR de type cohérent est recensé dans le même townland.
- **Rang 2** : le nom porte un indice de ce type, mais **non confirmé** par un point SMR dans l'extraction 5 km utilisée cette session (ex. Grangecuffe — Carrigan atteste des vestiges, le SMR open data n'en recense aucun point dans ce townland précis).
- **Rang 3** : nom descriptif (relief, végétation, hydrographie) ou anthroponyme (*Bally* + patronyme) — sans lien démontré avec un monument, **même si un monument s'y trouve** (cas explicitement conservé en rang 3, pas requalifié, pour garder le rang lisible comme « ce que dit le nom » et non « ce que porte le terrain » — la colonne « monument(s) SMR » du §2.3 sert précisément à afficher l'écart).

**Choix méthodologique explicite, différent d'une lecture au premier degré du nom actuel seul** : à Grove, le nom en usage depuis 1666 (*An Garrán*, « bosquet ») est en lui-même rang 3 (purement descriptif). Mais comme il s'agit du **même lieu** que la paroisse médiévale *Tullaghanbroge* (attestée dès le XIII<sup>e</sup> s., contenant *tulachán*, confirmée par une motte et un moated site), l'entrée est classée **rang 1 via sa forme historique**, avec un avertissement explicite en interprétation (§5). Ce choix privilégie l'utilité pour comprendre le peuplement, comme le demande le cadrage de la mission, au prix d'un écart avec une lecture strictement synchronique du nom.

---

## 5. Avertissement méthodologique — pièges de la toponymie irlandaise

Équivalent du « piège Polge » du `docs/PLAN.md` §2.5 (Gascogne), adapté aux pièges spécifiquement irlandais rencontrés cette session — **tous illustrés par un cas concret du rayon étudié, pas par principe général**.

**1. L'anglicisation peut effacer le signal — ou le créer.** Le même acte administratif (la concession du 26 octobre 1666 à Joseph Cuffe, lue intégralement dans Carrigan 1905 p.388-389) renomme trois townlands **dans deux directions opposées** : *Tullaghane* (contenant *tulachán*, rang 1) devient **« Cuffe's grove »** — un nom qui n'évoque plus rien d'archéologique ; *Lislonen* (contenant *lios*, rang 1) devient **« Cuffe's Desert »** — qui ressemble à *díseart* (ermitage) mais n'en dérive pas ; *Inchevolahane* devient **« Castle Inch »** — qui, à l'inverse, **ajoute** un signal explicite (« castle ») absent du nom irlandais d'origine. **Conclusion opérationnelle** : le nom actuel seul ne suffit jamais à conclure — chercher systématiquement les formes antérieures à 1650-1700.

**2. *Bally* + patronyme est le piège le plus fréquent**, structurellement identique au piège Polge gascon (« nom de domaine = nom de propriétaire »). Deux cas confirmés **par Carrigan lui-même** dans le rayon : **Ballymack** = *Baile Mhic Dháith*, que Carrigan traduit littéralement « the Town of David's Son » (1905, p.384) ; **Ballykeefe** = *Baile Uí Chaoimh*, « the Town of O'Keeffe » (p.435). Aucun des deux ne signale un type de monument — malgré des monuments bien réels à Ballymack (fulacht fia, enclos).

**3. « Grange » n'est pas toujours là où on l'attend.** Le townland uni « Grange » et le townland « Grangecuffe » sont deux lieux distincts. Or Carrigan (1905, p.391-392) situe précisément les **vestiges matériels** de la grange monastique (fondations, « monastery yard », cimetière) à **Cuffe's Grange**, pas au townland « Grange » lui-même — qui porte pourtant le nom générique. Un nom en *gráinseach* n'est donc pas automatiquement le point exact du site.

**4. Les noms en « Danes » sont presque toujours un contresens historique.** Recherche confirmée cette session : Joyce note que les incursions scandinaves n'ont laissé pratiquement aucune trace dans la toponymie irlandaise. **Danesfort** (irl. *Dún Feart*, « fort du tumulus funéraire ») en est un exemple documenté : Carrigan (1905, p.371) montre que le nom vient d'un *dún* générique déjà attesté en 1307 (« manor of Dunfert »), sur lequel James, 3<sup>e</sup> comte d'Ormond, a bâti un château **vers 1391-1405** — rien à voir avec des Vikings. **Danesfort est hors du rayon de 5 km étudié ici** (townland à 52,5731 N / -7,22804 W, soit environ **7,4 km** du point de départ — calcul : Δlat×111 ≈ 3,1 km, Δlon×111×cos(52,6°) ≈ 6,8 km, distance ≈ √(3,1² + 6,8²) ≈ 7,4 km) ; il n'a donc pas d'entrée dans le geojson, mais mérite cette note pour qui étendrait le rayon.

**5. Un nom purement descriptif ne garantit pas l'absence de monument** — le miroir exact du piège n°1. **Aghenderry** (*Achadh an Doire*, « champ du bois de chênes ») ne contient aucun mot de monument, et pourtant un ringfort-rath y est recensé (KK023-033----). **Ballymack (Desart)** est un anthroponyme pur, et pourtant un fulacht fia et deux enclos y sont recensés. La toponymie est un **indice complémentaire**, jamais un filtre d'exclusion.

**6. La segmentation d'un nom peut rester disputée entre sources sérieuses.** Pour Desart Court, logainm.ie donne *Lios Loinín* (« le ringfort de Loinín », nom propre) tandis que Carrigan (1905, p.389) transcrit la prononciation locale *Lischlooineen* et la lit *Lios Cluainín* (« le ringfort du petit pré »). Les deux lectures conservent *lios* (rang 1 dans les deux cas) mais divergent sur le second élément — **non tranché dans ce dossier**, signalé [À VÉRIFIER] dans le geojson.

**7. Les doublons de noms entre baronies piègent le classement, pas l'interprétation.** Le Co. Kilkenny compte plusieurs townlands homonymes distingués uniquement par leur barony (« Grove (Shillelogher By.) », « Raheenduff (Shillelogher By.) »...). Une recherche qui ignore ce suffixe risque de fusionner deux lieux distincts — vérifié cette session en confondant un instant un « Church Hill » du Roscommon avec celui de Grange, Co. Kilkenny (corrigé après vérification croisée townlands.ie/logainm.ie).

---

## 6. Croisement toponymes ↔ monuments SMR

Townlands du Tier 1 dont le nom (actuel ou historique) désigne un type de monument, avec confirmation ou non par un point SMR dans le townland :

| Townland | Élément du nom | Monument attendu | Confirmé par le SMR ? |
|---|---|---|---|
| Grove / Tullaghanbrogue | *tulachán* (via forme historique) | motte, tertre | **Oui** — KK023-032---- Castle-motte, KK023-031004- Moated site |
| Kyleandangan | *daingean* | fortification | **Oui** — KK023-034---- Enclosure |
| Booly | *buaile* | enclos pastoral | **Oui** — KK023-064---- Enclosure |
| Church Hill | *teampall* | église | **Oui** — KK023-036001- Church + 7 autres monuments |
| Castleinch (nom EN) | « castle » | château | **Oui** — KK023-002---- Castle - unclassified |
| Desart Court/Demesne | *lios* | ringfort | **Oui** — KK022-020---- Enclosure - large enclosure (+ description *de visu* Carrigan 1905) |
| Desart Court/Demesne (Cill Féichín) | *cill* | église | **Oui** — KK022-021001- Church |
| Raheenduff | *ráithín* | petit ringfort | **Oui** — KK023-035---- Enclosure - large enclosure |
| Grange | *gráinseach* | grange monastique | **Oui** (partiel) — KK023-132---- Enclosure, mais Carrigan situe le site réel à Grangecuffe |
| Grangecuffe | *gráinseach* | grange monastique | **Non dans l'extraction SMR** — attesté par Carrigan (fondations, « monastery yard ») hors SMR |
| Kilballykeefe | *cill* | église | **Oui** — KK022-015001- Church + Moated site |
| Burnchurch | *teampall loiscthe* | église | **Oui** — KK023-053001- Church + 16 autres monuments |
| Tullamaine (Ashbrook) | *tulach* | tertre/motte | **Oui** (contexte) — enclos, église, cimetière |
| Kilmog or Racecourse | *cill* | église | **Oui** — KK023-009003- Church |
| Aghenderry | *(aucun mot de monument)* | — | **Sans objet** — ringfort présent (KK023-033) malgré un nom muet (voir §5.5) |
| Ballymack (Desart) | *(anthroponyme)* | — | **Sans objet** — fulacht fia + enclos présents malgré un nom muet |
| Ballybur (×3) | *(probable anthroponyme)* | — | **Aucun monument SMR recensé** dans le rayon étudié pour ces townlands |

---

## 7. Points restés [À VÉRIFIER] ou non traités

- ID logainm.ie exact pour : la paroisse Tullaghanbrogue, le townland « Grange » (page townlands.ie en 404 cette session), le townland « Burnchurch ».
- Segmentation définitive du second élément de « Desart »/*Lios Loinín*/*Lios Cluainín* (§5.6).
- Second élément de « Tulchán **Bróg** » (Tullaghanbrogue) : non résolu.
- O'Kelly, O. 1969, *The place-names of County Kilkenny* : **non accessible en ligne cette session** — seule source citée par le SMR qui n'a pas pu être consultée directement (à l'inverse de Carrigan 1905, lu intégralement).
- OS Name Books individuels du secteur (au-delà des OS Letters 1839 déjà citées par le brief) : logainm.ie affiche l'existence d'archives de la Placenames Branch pour plusieurs fiches (mention « some of the documentation from the archives... is available ») mais le contenu détaillé n'a pas été extrait cette session.
- 9 des 18 townlands de la paroisse de Tullaghanbrogue, et l'intégralité des townlands hors du sous-ensemble « a un monument SMR ≤ 5 km », n'ont pas été individuellement recherchés (rayon dépouillé via `smr_5km.geojson`, pas via un inventaire cadastral exhaustif comme pour Armous-et-Cau — aucun équivalent du cadastre napoléonien n'existe pour l'Irlande).
- Étymologie précise de 14 des 27 townlands du Tier 2 (marqués [HYPOTHÈSE] dans le geojson ; les 13 autres sont marqués [À VÉRIFIER], lecture plus assurée mais non confirmée sur logainm.ie) : lecture des éléments anglais/irlandais reconnaissables, non vérifiée fiche par fiche.

---

## 8. Fichier généré

**`data/toponymes.geojson`** — FeatureCollection, WGS84, 50 points (18 townlands Tier 1 + 27 townlands Tier 2 + 5 microtoponymes), 11 propriétés par entité (`name_en`, `name_ga`, `logainm_id`, `logainm_url`, `historical_forms`, `meaning_fr`, `rank`, `smr_confirmed`, `loc_source`, `status`, `source`). Validé par `python3 -c "import json; json.load(open(...))"` — voir `metadata.attribution` au niveau de la FeatureCollection pour la mention de source (OSM/ODbL, logainm.ie, SMR).
