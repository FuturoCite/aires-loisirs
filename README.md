# standard-aires-loisirs
Ce schéma permet de modéliser les différents attributs des aires de loisirs. On entend par aires de loisirs : Aire de jeux, Aire de pique-nique, Aire de sports, Barbecue, Fitness urbain, Kiosque à musique, Mini-golf, Observatoire nature, Parcours santé, Patinoire, Piscine, Piste de sport, Port de plaisance, Sentier pieds nus, Skatepark, Table de jeux, Table de ping-pong, Zone de baignade, Autre. 
Un jeu de données basé sur ce standard devra contenir un seul type d'aires de loisirs.

## Contexte

Il existe un besoin d'harmonisation de la publication en open data de données essentielles produites par les administrations publiques wallonnes. En octobre 2022, plus de 660 jeux de données sont publiés sur le portail [Open Data Wallonie Bruxelles (ODWB)](https://www.odwb.be/explore/?sort=modified), qui sont très hétérogènes. 

Constatant la production de jeux de données disparates à l'échelle de la fédération Wallonie-Bruxelles, FuturoCité a réuni, dans le cadre d'un groupe de travail sollicité depuis mai 2021, une vingtaine de collectivités. La concertation de celles-ci a permis 1) d'identifier collectivement des jeux de données jugés prioritaires et 2) de s'accorder sur des spécifications des modèles de données. 
La standardisation de ces données prioritaires est en effet essentielle pour s'assurer de leur publication homogène et de faciliter leur exploitation (notamment leur agrégation) par les réutilisateurs. Elle facilitent l'exploitation des données publiées par les réutilisateurs (agrégation, consolidation et traitements automatiques).

## Construction du schéma de données 

Les membres du groupe de travail ont défini un schéma de données qui décrit le format des fichiers, les différents champs, les valeurs possibles… Ils se sont appuyés sur un état des lieux du patrimoine de données des collectivités wallonnes et sur une étude des modèles utilisés par des collectivités déjà productrices de ces données (notamment Liège et Namur), en prenant en compte les retours faits par les réutilisateurs de données. 

## Description du schéma

Un [gabarit au format tableur](https://github.com/FuturoCite/standard-aires-loisirs/blob/main/Schema_aires_loisirs_gabarit.xlsx) est également prévu pour faciliter la publication d'un jeu de données conforme au format du schéma.

Un exemple valide au format CSV est consultable [ici](https://github.com/FuturoCite/standard-aires/blob/main/exemple-valide.csv). 

Le tableau ci-dessous donne un aperçu des champs du schéma.

<table>
<tr><td><strong>Nom</td><td><strong>Remplissage obligatoire/optionnel</td><td><strong>Description</td></tr>
<tr><td>Identifiant (id)</td><td>Obligatoire</td><td>Ce champ contient un identifiant unique local. Le producteur de données le génère en associant  le code INS de la commune dans laquelle se situe l'aire de loisirs à un nombre. Ce champ permet d'éviter localement les doublons. Le code INS de la commune est accessible ici : https://statbel.fgov.be/fr/open-data/code-refnis</td></tr>
<tr><td>Nom (name)</td><td>Obligatoire</td><td>Ce champ contient le nom de l'aire de loisirs</td></tr>
<tr><td>Description (description)</td><td>Obligatoire</td><td>Ce champ contient la description de l'aire de loisirs</td></tr>
<tr><td>Type (type)</td><td>Obligatoire</td><td>Ce champ indique le type des aires de loisirs présents dans ce jeu. Les valeurs possibles sont : Aire de jeux, Aire de pique-nique, Aire de sports, Barbecue, Fitness urbain, Kiosque à musique, Mini-golf, Observatoire nature, Parcours santé, Patinoire, Piscine, Piste de sport, Port de plaisance, Sentier pieds nus, Skatepark, Table de jeux, Table de ping-pong, Zone de baignade, Zone de baignade, Autre</td></tr>
<tr><td>Photos (pictures)</td><td>Optionnel</td><td>Ce champ contient une liste d'urls, séparés par des virgules, qui renvoient vers des photos de l'aire de loisirs</td></tr>
<tr><td>Nom de la commune (municipality)</td><td>Obligatoire</td><td>Ce champ contient le nom de la commune dans laquelle se situe l'aire de loisirs. Le nom de la commune provient de la base de données BeST Address : https://opendata.bosa.be/index.fr.html  ou de la liste des codes INS : https://statbel.fgov.be/fr/open-data/code-refnis </td></tr>
<tr><td>Code INS (ins_code)</td><td>Obligatoire</td><td>Ce champ contient le code INS de la commune où se situe l'aire de loisirs. Il est accessible ici :  https://statbel.fgov.be/fr/open-data/code-refnis </td></tr>
<tr><td>Partie de commune (zone_address)</td><td>Optionnel</td><td>Ce champ contient le nom de la partie de commune où se situe l'aire de loisirs, conforme à l'appelation dans StatBel : https://statbel.fgov.be/fr/propos-de-statbel/methodologie/classifications/geographie</td></tr>
<tr><td>Code INS de la partie de commune (ins_zone_address)</td><td>Optionnel</td><td>Ce champ contient le code INS de la partie de commune où se situe l'aire de loisirs. La découpe géographique de StatBel Level 5 (NIS6) liste ces codes : https://statbel.fgov.be/fr/propos-de-statbel/methodologie/classifications/geographie</td></tr>
<tr><td>Nom de rue (street_name)</td><td>Obligatoire</td><td>Ce champ renseigne le nom de la voirie où se situe l'aire de loisirs (ou de la voirie la plus proche si elle n'est pas en voirie).</td></tr>
<tr><td>Code rue BeSTAddress (street_number)</td><td>Obligatoire</td><td>Ce champ contient le code de la voirie où se situe l'aire de loisirs dans la base de données BeSTAdress (ou de la voirie la plus proche si elle n'est pas en voirie) : https://opendata.bosa.be/index.fr.html</td></tr>
<tr><td>Code rue national (street_number_rrn)</td><td>Optionnel</td><td>Code de la voirie où se situe l'aire de loisirs dans le registre national (ou de la voirie la plus proche si elle n'est pas en voirie)</td></tr>
<tr><td>Numéro de police le plus proche (house_number)</td><td>Optionnel</td><td>Ce champ est recommandé. Il contient le numéro de police (numéro de maison) le plus proche de l'aire de loisirs</td></tr>
<tr><td>Distance au point d'adresse (distance)</td><td>Optionnel</td><td>Ce champ indique la distance, en mètres, entre l'aire de loisirs et le point d'adresse le plus proche introduit via les autres champs (code_rue_bestadress, num_police, …). En cas de décimale, le séparateur est le point. </td></tr>
<tr><td>Précisions sur l'emplacement (location_details)</td><td>Optionnel</td><td>Ce champ précise l'emplacement de l'aire de loisirs</td></tr>
<tr><td>Coordonnées (coordinates)</td><td>Obligatoire</td><td>Ce champ indique les coordonnées de l'aire de loisirs. Il est au format GeoJSON (se référer au fichier csv d'exemple et/ou à la documentation pour un exemple de valeur bien formatée). S'il est impossible d'exporter la donnée depuis un logiciel métier, les coordonnées d'un lieu peuvent être générées ici : https://www.coordonnees-gps.fr/carte/pays/BE</td></tr>
<tr><td>Geométrie (geometry)</td><td>Optionnel</td><td>Ce champ indique la zone géopgrahique de l'aire de loisirs grâce à une liste de coordonnées. Cette liste est générée à partir d'un fichier GPX.</td></tr>
<tr><td>Contact (contact)</td><td>Optionnel</td><td>Ce champ contient les informations de contact. Nous recommandons d'indiquer uniquement le site web de l'aire de loisirs afin de faciliter la maintenance et mise à jour des données</td></tr>
<tr><td>Age minimum (minimum_age)</td><td>Optionnel</td><td>Ce champ est recommandé. Ce champ précise l'age minimum recommandé</td></tr>
<tr><td>Age maximum (maximum_age)</td><td>Optionnel</td><td>Ce champ est recommandé. Ce champ précise l'age maximum recommandé. Si l'aire de loisirs est adaptée aux adultes mettre 99.</td></tr>
<tr><td>Accessibilité PMR (disabled_access)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs est accessible aux personnes à mobilité réduite. Si l'emplacement est accessible utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Module PMR (pmr_module)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs est équipée de modules accessibles aux personnes à mobilité réduite. Si des modules accessibles aux personnes à mobilité réduite existent utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Nombre de modules (number_of_mods)</td><td>Optionnel</td><td>Ce champ précise le nombre de modules présents sur l'aire de loisirs. Définition de la notion de module selon le type du jeu : pour le type Aire de jeux, un module est une structure ; pour le type Aire de pique-nique, un module est une table de pique-nique ; pour le type Aire de sports, un module est un terrain ; pour le type Barbecue, un module est un barbecue ; pour le type Fitness urbain, un module est un équipement ; pour le type Kiosque à musique, un module est un kiosque ; pour le type Mini-golf, un module est un trou ; pour le type Observatoire nature, un module est un observatoire ; pour le type Parcours santé, un module est une station d'exercices ; pour le type Patinoire, un module est une patinoire ; pour le type Piscine, un module est un bassin ; pour le type Piste de sport, un module est une piste ; pour le type Port de plaisance, un module est un quai d'amarrage ; pour le type Sentier pieds nus, un module est un tronçon avec un revêtement particulier ; pour le type Skatepark, un module est une rampe ; pour le type Table de jeux, un module est une table ; pour le type Table de ping-pong, un module est une table ; pour le type Zone de baignade, un module est un bassin ou un espace de baignade délimité.</td></tr>
<tr><td>Sécurisation (securing)</td><td>Optionnel</td><td>Ce champ décrit les dispositifs mis en place pour la sécurité</td></tr>
<tr><td>Type de surface (surface_type)</td><td>Obligatoire</td><td>Ce champ décrit la surface de l'aire de jeux. Les valeurs possibles sont :  Bois,  Dalles amortissantes EN1177,  Gravier,  Herbe,  Sable,  Terre, Surface dure, Mixte, Autre</td></tr>
<tr><td>Site fermé (closed_site)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs se situe sur un site fermé par des barrières. Si le site est fermé utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Banc (bench)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs est équipée de bancs. Si le site dispose de bancs utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Table (table)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs est équipée de tables Si le site dispose de tables utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Ombre (shadow)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs offrent des zones d'ombre. Si le site dispose de zones d'ombre utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Restauration (catering)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs propose de la restauration avec vue sur l'aire de loisirs. Si le site dispose de restauration avec vue utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Point d'eau potable (drinking_water_point)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs est équipée de points d'eau potable. Si le site dispose de points d'eau potable utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Poubelle (trash_can)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs est équipée de poubelles. Si le site dispose de poubelles utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Conditions d'accès (access_conditions)</td><td>Optionnel</td><td>Ce champ décrit les conditions d'entrées à l'aire de loisirs</td></tr>
<tr><td>Horaires (schedule)</td><td>Optionnel</td><td>Le champ indique les horaires auxquels l'aire de loisirs est accessible. Il respecte le format proposé par OpenStreetMap (https://wiki.openstreetmap.org/wiki/FR:Key:opening_hours). L'outil YoHours (https://projets.pavie.info/yohours/) permet de générer des horaires au bon format. Le format OSM permet d'indiquer des exceptions pendant certaines périodes (vacances, jours fériés…). Pour les générer au bon format en utilisant YoHours, il suffit de les renseigner en cliquant sur le bouton 'plus' vert, situé en haut à gauche.</td></tr>
<tr><td>Tarif (prices)</td><td>Optionnel</td><td>Ce champ décrit le tarif d'accès à l'aire de loisirs. Si une page web décrit le tarif, il est préférable de référencer cette page plutôt que de décrire les tarifs.</td></tr>
<tr><td>Gestionnaire (provider)</td><td>Optionnel</td><td>Ce champ est recommandé. Ce champ renseigne le gestionnaire de l'aire récréative</td></tr>
<tr><td>Couvert (covered)</td><td>Optionnel</td><td>Ce champ précise si l'aire de loisirs est couverte. Si le site est couvert utiliser la valeur 'true'. Si non, la valeur 'false'. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Superficie (area)</td><td>Optionnel</td><td>Ce champ renseigne la superficie de l'aire de loisirs en m²</td></tr>
<tr><td>Année de certification (cartification_year)</td><td>Optionnel</td><td>Ce champ fournit l'année d'obtention du certificat dans le format AAAA. Si non applicable/non connu : ne pas renseigner ce champ.</td></tr>
<tr><td>Année de réalisation (completion_year)</td><td>Optionnel</td><td>Ce champ précise l'année d'installation de l'aire de loisirs dans le format AAAA</td></tr>
<tr><td>Date de création de la donnée (created_date)</td><td>Optionnel</td><td>Ce champ indique la date de création de la donnée dans le jeu. Il respecte le format ISO 8601 : année-mois-jour (YYYY-MM-DD)</td></tr>
<tr><td>Date de dernière modification de la donnée (last_modified_date)</td><td>Optionnel</td><td>Ce champ indique la date de la dernière modification de la donnée dans le jeu. Il respecte le format ISO 8601 : année-mois-jour (YYYY-MM-DD).</td></tr>
</table>

## Format de fichier 

Le format de fichier retenu pour la publication des données est le CSV (Comma Separated Values, valeurs séparées par des virgules).

Les fichiers doivent, sauf exception et autant que possible, respecter les règles de formatage suivantes :

* l’encodage des caractères est UTF-8,
* le séparateur des colonnes est la virgule,
* le séparateur des nombres décimaux est le point,
* le séparateur de valeurs multiples dans un champ est le point-virgule,
* si un champ contient une virgule, il doit être entouré de guillemets doubles,
* chaque ligne doit avoir le même nombre de champs,
* le type MIME ou Content-Type est text/csv.

### Recommandations pour le nommage des fichiers 

Les fichiers doivent, sauf exception et autant que possible, respecter les règles de nommage suivantes :

* YYYY-MM-DD : Date de création du fichier
* idProducteur : code INS unique de la commune pour identifier le producteur
* circuits-touristiques : nom du fichier, en minuscules non accentuées
* territoire : Nom du territoire concerné, non accentué (exemple : Liege)
* extension : Si les règles de formatage sont respectées, l'extension est .csv

Exemple : 2022-10-25_62063_aires-loisirs_Namur.csv

### Recommandations pour la mise en conformité 

Ces conseils reprennent ceux du [Socle commun des données locales publié par OpenDataFrance](https://scdl.opendatafrance.net/docs/recommandations-relatives-aux-jeux-de-donnees.html)

Les fichiers doivent comporter :

* Toutes les colonnes, y compris celles dont les cellules ne sont pas renseignées, dans le bon ordre, et avec des en-têtes correctement nommées sur la première ligne (nom correspondant strictement au schéma)
* Autant de lignes que nécessaire comprenant des cellules dont les valeurs peuvent être obligatoires (elles doivent être impérativement renseignées) ou optionnelles (elles sont seulement recommandées ou soumises à condition de disponibilité / pertinence)
