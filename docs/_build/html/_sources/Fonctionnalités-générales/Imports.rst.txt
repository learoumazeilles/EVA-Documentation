.. include:: ../substitutions.rst
Imports
=======

Si vous avez une large base de données à ajouter, il est utile de recourir aux imports qui permettent d'insérer plusieurs entrées d'un coup grâce à un format tableur. 

Procédure générale
~~~~~~~~~~~~~~~~~~

La précédure pour les imports est similaire dans la majorité des cas (exeption des imports budgets, territoires et mots clés et référentiels) et suit la logique suivante :

1. Créer un fichier tableur avec l’outil de tableur privilégié (Excel, Numbers, Google Sheet, Calc…) et remplir les données avec les en-têtes de colonnes correspondantes
2. Sauvegarder au format csv
3. Importer dans EVA

Quelles colonnes pour chaque import ?
#####################################

-> -> **Des exemples de fichiers Excel et csv** sont disponibles `ICI <https://fpnrf-my.sharepoint.com/:f:/g/personal/lroumazeilles_parcs-naturels-regionaux_fr/ElO1DP6dPJ1Mm2rn9hXL_MIBlJX3-IA-uYKlfkxfk9xGwA?e=QuNBOP>`_ <-- <--


* L’ordre des colonnes n’a pas d’importance, certaines cases peuvent être vides si elles ne sont pas dans les colonnes de champs obligatoires.
* Dans certaines colonnes, on peut indiquer un texte librement, pour d’autres seulement certains mots sont acceptés (indiqué en **gras** dans les tableaux ci-dessous) ou seulement des chiffres, les majuscules/minuscules sont importantes.
* Les mots clés et référentiels peuvent s’ajouter dans des colonnes supplémentaires s’ils ont été paramétrés précédemment.

Import utilisateurs
###################

Colonnes obligatoires : Prénom, Nom, Nom d’utilisateur, Rôle, Mot de passe, Adresse email

Autres colonnes possibles : Civilité, Couleur 

\+ les mots clés

+---------+---------+----------------+------------------+----------+----------------+------------+------------+
|Nom*     | Prénom* | Nom            | Rôle             | Mot de   | Civilités      | Adresse    | Couleur    |
|         |         |                |                  |          |                |            |            |
|         |         | d'utilisateur* |                  | passe    |                | email*     |            |
+=========+=========+================+==================+==========+================+============+============+
| *Texte* | *Texte* | *Texte*        | Nom du rôle      | *Texte*  | **M.** ou      | *Texte*    | Code hex   |
|         |         |                |                  |          |                |            |            |
|         |         |                | prédéfini dans   |          | **Non binaire**| *format*   | example :  |
|         |         |                |                  |          |                |            |            |
| *libre* | *libre* | *libre*        | le module admin  | *libre*  | ou **Mme.**    | *email*    | #fcba03    |
+---------+---------+----------------+------------------+----------+----------------+------------+------------+

.. Note::
	La couleur est utile pour l'affichage de l'agenda par exemple.

Import indicateurs
##################

Colonnes obligatoires : Nom, Type, Opérateur de synthèse annuelle

Autres colonnes possibles : Archivé (oui/non ou 1/0), Description, Définition, Méthode, Interprétation, Unité de mesure 

\+ les mots clés

.. warning::
	Ne pas indiquer la colonne « Valeurs » (provoque un bug).

+---------+----------+-------------+---------+-------------+-----------+
|Nom*     | Type*    | Opérateur   | Archivé | Description | Unité     |
|         |          |             |         |             |           |
|         |          | de synthèse |         |             | de        |
|         |          |             |         |             |           |
|         |          | annuelle*   |         |             | mesure    |
+=========+==========+=============+=========+=============+===========+
| *Texte* |**Libre** | **Somme**   | **Oui** | *Texte*     | *Texte*   |
|         |          |             |         |             |           |
|         |          | **Moyenne** | **Non** |             |           |
|         |          |             |         |             |           |
|         |          | **Médiane** | (défaut |             |           |
|         |          |             |         |             |           |
|         |          | **Maximum** | non)    |             |           |
|         |          |             |         |             |           |
| *libre* |**Liste** | **Minimum** |         | *libre*     | *libre*   |
+---------+----------+-------------+---------+-------------+-----------+

Import mesures d'indicateurs
############################

Colonnes obligatoires : Indicateur (ID ou nom exact), Type (Réalisé ou Cible), Valeur, Date fin/réalisée

Autres colonnes possibles : Fiche (titre ou code ou ID), date début, commentaires, source, territoires

Pour indiquer plusieurs territoires, les séparer par '--', ex : Commune1 -- Commune2


+------------+-----------+-------------+---------+------------+------------+--------------+
|Indicateur* | Type*     | Valeur*     | Fiche   | Date fin/  | Date       | Commentaires |
|            |           |             |         |            |            |              |
|            |           |             |         | Réalisée*  | début      |              |
+============+===========+=============+=========+============+============+==============+
| ID         |**Réalisé**| *Texte*     | ID ou   | Date       | Date       | *Texte*      | 
|            |           |             |         |            |            |              |
| ou         |           |             | Code ou | au format  | au format  |              |
|            |           |             |         |            |            |              |
| nom        |**Cible**  | *numérique* | Titre   | JJ/MM/AAAA | JJ/MM/AAAA | *libre*      |
+------------+-----------+-------------+---------+------------+------------+--------------+

.. note::
	Pour le lien à la fiche dans le document d'import dans la colonne, il faut indiquer fiche SOIT l'ID de la fiche, SOIT son code, SOIT son titre mais ne pas mélanger les références dans le même import. Ensuite, lors de l'import il faut spécifier dans cette colonne quelle référence a été utilisée.

.. image:: images/import_mesures_fiches.png
  :width: 400

.. note::
	Il n'est pas possible d'importer des mesures de campagne d'indicateur.

.. warning::
	Attention pour les mesures d'indicateurs de type "liste", il faut insérer le chiffre indiqué dans la liste des valeurs pour qu'il y ait une bonne adéquation. Par exemple, si vous avez défini que la valeur 100 voulait dire "Bon état", la valeur 50 = "moyen" et la valeur 0 = "mauvais" il faudra indiquer une de ces trois valeurs numériques exactement et non les équivalents texte.

Import contacts
###############

Colonnes obligatoires : Prénom, Nom

Autres colonnes possibles : Adresse email, Téléphone, Portable, Adresse, ligne 1, Adresse, ligne 2, Code postal, Ville, Pays

\+ les mots clés et groupe de champs additionnels

.. warning::
	Bien choisir le "Nom" avec astérisque dans l'interface EVA pour la colonne Nom* et ne pas choisir "Nom-Prénom".

+----------------+---------+---------+---------+-----------+-----------+---------+
|Civilité        | Prénom* | Nom*    | Adresse | Téléphone | Adresse   | Code    |
|                |         |         |         |           |           |         |
|                |         |         | email   |           | ligne 1   | postal  |
+================+=========+=========+=========+===========+===========+=========+
| **M.** ou      | *Texte* | *Texte* | *Texte* | *Texte*   | *Texte*   | *Texte* |
|                |         |         |         |           |           |         |
| **Mme.** ou    | *libre* | *libre* | *libre* | *libre*   | *libre*   | *libre* |
|                |         |         |         |           |           |         |
| **Non binaire**|         |         |         |           |           |         |
+----------------+---------+---------+---------+-----------+-----------+---------+


Import structures
#################

Colonnes obligatoires : Nom

Autres colonnes possibles : Adresse email, Sigle, Numéro de téléphone, SIRET, Site web, « Adresse, ligne 1 », « Adresse, ligne 2 », Code postal, Ville, Pays

\+ les mots clés 

.. warning::
	Ne pas indiquer la colonne « Téléphone secondaire », elle ne fonctionne pas.

+---------+---------+---------+---------+-----------+-----------+---------+
| Nom*    | Adresse | Sigle   | SIRET   | Numéro de | Adresse   | Code    |
|         |         |         |         |           |           |         |
|         | email   |         |         | téléphone | ligne 1   | postal  |
+=========+=========+=========+=========+===========+===========+=========+
| *Texte* | *Texte* | *Texte* | *Texte* | *Texte*   | *Texte*   | *Texte* |
|         |         |         |         |           |           |         |
| *libre* | *libre* | *libre* | *libre* | *libre*   | *libre*   | *libre* |
+---------+---------+---------+---------+-----------+-----------+---------+


Import temps
############

Colonnes obligatoires : Utilisateur, Début, Fin, Heures, Type, Fiche

Autres colonnes possibles : Titre, Description, Territoire

\+ les mots clés 

.. warning::
	- La fiche n'est pas indiquée comme obligatoire mais elle l'est dans le formulaire par la suite. 
	- Tout comme le type d'absence s'il est paramétré dans votre EVA (le champ ne marche pas du tout à l'import). 
	- Si les heures de début et de fin ne sont pas insérées, EVA prendra l'heure à laquelle l'import est effectué.
	- Si le nombre d'heure n'est pas indiqué, EVA indiquera 0h par défaut

.. note::
	- Le nombre d'heures peut être différent de la différence entre début et fin (moins élevé comme plus élevé)
	- Le type peut être indiqué en français : "Temps prévu", "Temps passé", "Temps d'absence", ou en anglais respectivement "target", "done", "absence"


+---------------------+--------------+---------+------------------+------------------+---------+---------+
| Type*               | Utilisateur* | Fiche*  | Début*           | Fin*             | Heures* | Titre   |
+=====================+==============+=========+==================+==================+=========+=========+
| **Temps passé**     | Prénom       | Code ou | Date au format   | Date au format   | Chiffre | *Texte* |
|                     |              |         |                  |                  |         |         |
| **Temps d'absence** |              |         |                  |                  |         |         |
|                     |              |         |                  |                  |         |         |
| **Temps prévu**     | Nom          | titre   | JJ/MM/AAAA HH:MM | JJ/MM/AAAA HH:MM |         | *libre* |
+---------------------+--------------+---------+------------------+------------------+---------+---------+

*Le tableau ci-dessus est plus large que la page, vous pouvez le faire glisser de gauche à droite*

Import fiches
#############

Colonnes obligatoires : Titre

Autres colonnes possibles (en fonction des paramètres) : Statut, Code analytique, Chef(s) de projet, Validateur(s), Membres de l'équipe (+ rôle si paramétré), Acteurs (+ rôle si paramétré), Rattachement arboresence initiale (fiche qui doit déjà exister), Objectifs, Etat d'avancement du projet, Contexte et motif, Activité et livrables (en fonction du paramétrage des blocs dans les fiches), Maîtrise d'ouvrage externe, Accessible au réseau, Modèle de fiche (le nombre présent dans l’URL lorsque l’on consulte ce modèle), Statut financier (ID), Date de programmation, Date de démarrage prévue, Date de fin prévue, Date de démarrage effective, Date de fin effective, Territoires

\+ les mots clés 


.. warning::
	Le niveau sera déduit en fonction du rattachement à l’arborescence initiale.
	Ne pas indiquer la colonne « équipe », elle ne se remplit pas avec les membres de l’équipe.


+---------------+------------+---------+---------------+--------------+-----------+
| Statut        | Code       | Titre*  | Chef(s)       | Rattachement | Objectifs |
|               |            |         |               |              |           |
|               |            |         | de            |              |           |
|               |            |         |               |              |           |
|               | Analytique |         | projet        | arborescence |           |
+===============+============+=========+===============+==============+===========+
| **Brouillon** |*Texte*     | *Texte* | Nom de        | Nom exact    | *Texte*   |
|               |            |         |               |              |           |
| **A valider** |            |         | l'utilisateur | d'une fiche  |           |
|               |            |         |               |              |           |
| **Validée**   |            |         | \-\-          | qui doit     |           |
|               |            |         |               |              |           |
| **Votée**     |            |         | Autre nom     | déjà         |           |
|               |            |         |               |              |           |
| **Refusée**   |            |         |               | exister      |           |
|               |            |         |               |              |           |
| **Archivée**  |*libre*     | *libre* |               |              | *libre*   |
+---------------+------------+---------+---------------+--------------+-----------+

+-----------+------------+---------+---------------+-------------+
| Maîtrise  | Accessible | Modèle  | Date          | Territoires |
|           |            |         |               |             |
| d'ouvrage | au         | de      | de            |             |
|           |            |         |               |             |
| externe   | réseau     | fiche   | programmation |             |
+===========+============+=========+===============+=============+
| **Oui**   | **Oui**    | Nombre  | Date au       | Nom exact   |
|           |            |         |               |             |
| **Non**   | **Non**    | présent | format        | du          |
|           |            |         |               |             |
| (défaut   | (défaut    | dans    | JJ/MM/AAAA    | territoire  |
|           |            |         |               |             |
| non)      | non)       | URL     |               | dans        |
|           |            |         |               |             |
|           |            | (ID)    |               | EVA         |
+-----------+------------+---------+---------------+-------------+

.. Note::
	Exemple URL du modèle de fiche : dans « Administration » puis « Modèles de fiches », cliquer sur le modèle souhaité, l’URL qui s’affiche ressemble à celui-ci « parc.evaparc.net/project/template/form/20 », dans ce cas indiquer « 20 » dans la case modèle de fiche. On peut maintenant aussi obtenir les ID dans une colonne dédiée.

La fonctionnalité d'importer les **membres de l'équipe** et les **acteurs** est nouvelle. Voici comment procéder :

Ils peuvent être ajoutés avec leur rôle. Deux séparateurs sont donc nécessaires : la virgule et les tirets. La virgule permet de séparer le nom du rôle et les tirets de séparer deux entités différentes. Une erreur apparaitra si les noms, prénoms et rôles ne correspondent pas aux données dans EVA.

Le « rôle » est ici défini dans les mots clés : mot clé rattaché à « Membre » et mot clé rattaché à « Acteur ». Il est recommandé de rattacher un seul mot clé à membre. Si aucun rôle n’est spécifié, le rôle « membre » sera associé aux membres de l’équipe par défaut et aucun rôle ne sera associé aux acteurs.

.. Note::
	Les variables Chefs de projet ou Validateur qui sont nommées par défaut dans le logiciel ont pu être renommées pour le parc en Pilote par exemple pour Chef de projet. Dans ce cas, l’import permet maintenant d’indiquer le nouveau terme (depuis février 2023).

Ces colonnes doivent être formatées comme ceci :

+------------+---------+---------------------------------+-----------------------+
| Code       | Titre*  | Membres de                      | Acteurs               |
|            |         |                                 |                       |
| Analytique |         | l'équipe                        |                       |
+============+=========+=================================+=======================+
|*Texte*     | *Texte* | Nom et prénom d'un utilisateur, | Nom d'un acteur, rôle |
|            |         |                                 |                       |
|            |         | rôle \-\-  Nom et prénom d'un   | \-\- Nom d'un acteur, |
|            |         |                                 |                       |
|*libre*     | *libre* | utilisateur, rôle               | rôle                  |
+------------+---------+---------------------------------+-----------------------+

Par exemple le fichier csv peut ressembler à celui-ci :

	| Code analytique;Titre;Chef(s) de projet;Validateur(s);Membres de l'Équipe;Acteurs
	| IMPTESTACTMEMB;Test import fiches acteurs membres;Lea Roumazeilles;Lea Roumazeilles -- Anne Levacher;Marie Berlon,Coordination -- Louis BALDON,Assistance Technique -- Antoine Mellager -- Isabelle Dadon; Communes,Financeur -- Conseil départemental,Appui Technique – FPNRF

Dans cet exemple, on importe une fiche « Test import fiches acteurs membres » avec comme membre de l’équipe :
	* Chef(s) de projet : Léa Roumazeilles
 	* Validateur(s) : Léa Roumazeilles et Anne Levacher
	* Membres de l’équipe : Marie Berlon (rôle de coordination), Louis Baldon (rôle d’assistance technique), Antoine Mellager (rôle de membre par défaut), Isabelle Dadon (rôle de membre par défaut)
	* Acteurs : Communes (rôle de financeur), Conseil départemental (rôle d’appui technique), FPNRF (pas de rôle attitré)

Les rôles « coordination » et « assistance technique » sont des mots clés associés à membres, les rôles « financeur » et « appui technique » sont des mots clés associés à acteurs. (Attention le rôle financeur ici est différent de la case à cocher financeur dans les acteurs)

Import convention
#################

Colonnes obligatoires : Nom

Autres colonnes possibles : Contractant, Accessible réseau, Description, N°, N° arrêté, Début, Fin, Avancement, Date de décision, Date de notification, Montant, Montant subventionnable, Membres, ID Fiches, Type de convention, Territoire

\+ les mots clés 

+---------+-------------+-------------+------------------+------------------+---------+------------+
| Nom*    | Contractant | Description | Début            | Fin              | Montant | ID Fiches  |
+=========+=============+=============+==================+==================+=========+============+
| *Texte* | Nom ou      | *Texte*     | Date au format   | Date au format   | Chiffre | ID1 -- ID2 |
|         |             |             |                  |                  |         |            |
| *libre* | ID          | *libre*     | JJ/MM/AAAA HH:MM | JJ/MM/AAAA HH:MM |         |            |
+---------+-------------+-------------+------------------+------------------+---------+------------+

.. Note::
	Les fiches rattachées en import seront affectées automatiquement à 100% à la convention. Pour rattacher plusieurs fiches, il faut indiquer dans la colonne ID Fiches ID1 -- ID2 (deux ID séparés par deux tirets et un espace de chaque côté des tirets).

Sauvegarder au format csv
#########################

Enregistrer le tableau au format **csv** avec des séparateurs en **points-virgules**. Le format **CSV UTF-8** est à privilégier.

Vous pouvez vérifier le format en ouvrant le fichier csv avec un éditeur de texte simple (ex : TextEdit, WordPad, NotePad…).

Les colonnes doivent être séparées par des points-virgules, les lignes par des retours à la ligne.

Ex : 
``Statut;Code analytique;Titre``

``Brouillon;001;Fiche numéro 1``

Importer dans EVA
#################


Dans EVA, cliquer sur le bouton rouge dans le coin inférieur droit pour importer les csv |bouton_3_traits|.

Choisir le fichier csv préparé précédemment, le délimiteur point-virgule, et cocher « La première ligne contient les en-têtes des colonnes ? » puis cliquer sur « **Envoyer** ».

.. image:: images/interface_import.png
  :width: 400

Les données devraient apparaître, chaque ligne correspondant à chaque élément.

.. image:: images/tableau_import.png
  :width: 600

Vérifier les en-têtes des colonnes, certains auront déjà été trouvés, d’autres non, il faudra les indiquer grâce au menu déroulant.

.. image:: images/déroulé_import.png
  :width: 200


Dans les suggestions d’en-tête du menu déroulant, on peut vérifier quels mots clés et référentiels peuvent être associés. Cliquer sur « **Vérifier ou Valider** ».

Si votre tableau est correct il sera surligné en vert, les lignes incorrects seront rouges.

.. image:: images/tableau_import_rouge.png
  :width: 600

(Ici par exemple il faut indiquer « Mme. » au lieu de « mm » dans la colonne civilité pour corriger la ligne)

Vous pouvez les corriger ou si vous ne souhaitez pas importer ces lignes cliquer sur « **Importer** ». Seules les lignes qui étaient surlignées en vert seront importées dans EVA.

**Une bonne pratique est de vérifier si l’import a bien eu lieu correctement.**


Procédure budget
~~~~~~~~~~~~~~~~

La précédure pour les imports budget suit la logique suivante :

1. Créer un fichier tableur avec l’outil de tableur privilégié (Excel, Numbers, Google Sheet, Calc…) et remplir les données avec les en-têtes de colonnes correspondantes
2. Sauvegarder au format csv
3. Importer dans EVA

* Des **exemples de fichiers Excel et csv sont disponibles** `ici <https://fpnrf-my.sharepoint.com/:f:/g/personal/lroumazeilles_parcs-naturels-regionaux_fr/ElO1DP6dPJ1Mm2rn9hXL_MIBlJX3-IA-uYKlfkxfk9xGwA?e=QuNBOP>`_
* L’ordre des colonnes n’a pas d’importance, certaines cases peuvent être vides si elles ne sont pas dans les colonnes de champs obligatoires.
* Dans certaines colonnes, on peut indiquer un texte librement, pour d’autres seulement certains mots sont acceptés (indiqué en **gras** dans les tableaux ci-dessous) ou seulement des chiffres, les majuscules/minuscules sont importantes.
* Les montants doivent être au format numérique sans espace, un point ou une virgule peuvent être indiqué pour les décimales

Import budget en général
########################

Il faut préparer des fichiers csv séparés pour les recettes et dépenses et pour chaque type, par exemple prévu, engagé, payé. Il faut avoir défini au préalable les comptes auxquels rattacher les recettes et dépenses, qui peuvent eux aussi être importés. Les enveloppes peuvent elles aussi être importées.

Import Comptes
##############

Colonnes obligatoires : Code, Nom, Type de mouvement

Autres colonnes possibles : Description, Parent

.. note::
	S'il y a une arborescence dans les comptes, il faudra d'abord importer tous les comptes parents, puis tous le niveau d'arborescence suivant et ainsi de suite pour pouvoir les rattacher.

.. warning::
	Attention pour le parent à bien donner un compte parent recette si le type de mouvement est recette et un compte parent dépense si le type de mouvement est dépense. Le logiciel ne peut pas le vérifier au moment de l’import mais cela produit des bugs plus tard.

+---------+---------+-------------+------------+--------+
| Code*   | Nom*    | Type de     | Description| Parent |
|         |         |             |            |        |
|         |         | Mouvement*  |            |        |
+=========+=========+=============+============+========+
| *Texte* | *Texte* | **Recette** | *Texte*    | ID du  |
|         |         |             |            |        |
| *libre* | *libre* | **Dépense** | *libre*    | parent |
+---------+---------+-------------+------------+--------+


Import Enveloppes
#################

Colonnes obligatoires : Nom, Financeur
Autres colonnes possibles : Code, Début, Fin, Montant

.. note::
	Les financeurs sont ajoutés via le module structure.

+---------+---------+------------+-------------+-------------+------------------+
| Code    | Nom*    | Financeur* | Début       | Fin         | Montant          |
|         |         |            |             |             |                  |
|         |         |            |             |             |                  |
+=========+=========+============+=============+=============+==================+
| *Texte* | *Texte* | ID         | Date format | Date format | Format numérique |
|         |         |            |             |             |                  |
| *libre* | *libre* | Financeur  | JJ/MM/AAAA  | JJ/MM/AAAA  | sans espace      |
+---------+---------+------------+-------------+-------------+------------------+


Import Recettes
###############

Colonnes obligatoires : Rattachement à la fiche (soit par code analytique, soit par code financier, soit par le titre), Compte, Date, Montant
Autres colonnes possibles : Nom, Montant HT, Tiers, Exercice, Bordereau du mandatement, Mandat, Engagement, Compléments, Évolution, Unité de gestion, Série, Convention (non lié au module convention)

.. warning ::
	Attention le champ convention ici n'est pas rattaché à au module convention.


+-------------+---------+------------+-----------------+---------+------------------+
| Code        | Compte* | Date*      | Montant*        | Nom     | Montant HT       |
|             |         |            |                 |         |                  |
| Analytique* |         |            |                 |         |                  |
+============++=========+============+=================+=========+==================+
| Code de     | Code du | Date format| Format numérique| *Texte* | Format numérique |
|             |         |            |                 |         |                  |
| la fiche    | compte  | JJ/MM/AAAA | sans espace     | *libre* | sans espace      |
+-------------+---------+------------+-----------------+---------+------------------+

Import Dépenses
###############

Colonnes obligatoires : Rattachement à la fiche (soit par code analytique, soit par code financier, soit par le titre), Compte, Date, Montant
Autres colonnes possibles : Nom, Montant HT, Tiers, Exercice, Bordereau du mandatement, Mandat, Engagement, Compléments, Évolution, Unité de gestion, Date facture.


+-------------+---------+------------+-----------------+---------+------------------+
| Code        | Compte* | Date*      | Montant*        | Nom     | Montant HT       |
|             |         |            |                 |         |                  |
| Analytique* |         |            |                 |         |                  |
+============++=========+============+=================+=========+==================+
| Code de     | Code du | Date format| Format numérique| *Texte* | Format numérique |
|             |         |            |                 |         |                  |
| la fiche    | compte  | JJ/MM/AAAA | sans espace     | *libre* | sans espace      |
+-------------+---------+------------+-----------------+---------+------------------+


Import Budget dans EVA
######################

La procédure d'import dans EVA est similaire à celle décrite dans la procédure générale, certains aspects sont légèrement différents.

Dans EVA cliquer sur « **Budget** » puis « **Import financier** ».

Choisir le type de mouvement : recette ou dépense.

**Import Recettes**

Choisir le type de recette (sollicité, notifié, attribué ou perçu) et le type d’import (ajout, écrasement total, écrasement des fiches concernées). 

.. note::
	Pour les écrasements, il faudra préciser l’année ou « toutes les années ».

.. image:: images/import_recette_EVA.png
  :width: 400

**Import Dépenses**

Choisir le type de dépense (prévu, engagé, payé, libéré, engagé payé, AE ouvert, AE prévu, AE engagé, CP prévu, CP ouvert, CP mandaté) et le type d’import (ajout, écrasement total, écrasement des fiches concernées). 

.. note::
	Pour les écrasements, il faudra préciser l’année ou « toutes les années ». L’écrasement n’écrase que les écritures précédemment importées, si un agent a fait des saisies manuelles, elles ne seront pas supprimées par l’import. Si une donnée importée a été modifiée, elle ne sera pas supprimée non plus.

.. warning::
	ATTENTION : l'écrasement total écrasera toutes les données importées précédemment même sur d'autres fiches.

.. image:: images/import_dépense_EVA.png
  :width: 600


**Dans les deux cas**

Choisir le Statut financier des fiches modidiées : si on choisit un statut ici (défini dans |budget| > |statuts_financiers|), les fiches qui sont modifiées par l'import seront ensuite passées au statut choisi.

Si l'on coche la case "Les mouvements se mettent dans les postes ayant un compte parent si aucun poste ayant le même compte n'est présent" : les mouvements se mettent en effet sous un poste avec un compte parent du compte indiqué s'il y en a un dans la fiche. 
S'il n'y en a pas ou la case n'est pas cochée, les mouvements qui n'ont pas encore de poste de dépense/recette seront rajoutés dans un nouveau poste de dépense/recette nommé par le nom du compte.
Si un poste de dépense/recette existe avec le même compte, le mouvement sera rattaché sous ce poste de dépense/recette.

.. image:: images/Imports_budget_param.png
  :width: 400

Choisir le fichier csv préparé précédemment, le délimiteur point-virgule, et cocher « La première ligne contient les en-têtes des colonnes ? » puis cliquer sur « **Envoyer** ».

.. image:: images/interface_import.png
  :width: 400

Les données devraient apparaître, chaque ligne correspondant à chaque élément.

.. image:: images/tableau_import.png
  :width: 600

Vérifier les en-têtes des colonnes, certains auront déjà été trouvés, d’autres non, il faudra les indiquer grâce au menu déroulant.

Les colonnes choisies peuvent être enregistrées pour un prochain import.

.. image:: images/Choix_colonnes_import_budget.png
  :width: 500


Cliquer sur « **Valider** ».

Si votre tableau est correct il sera surligné en vert, les lignes incorrects seront rouges.

.. image:: images/tableau_import_rouge.png
  :width: 600

Les lignes peuvent apparaître rouges pour plusieurs raisons :
*	Un champ obligatoire n’est pas rempli
*	Un code analytique n’existe pas
*	Un format n’est pas respecté

Vous pouvez les corriger ou si vous ne souhaitez pas importer ces lignes cliquer sur « *Importer* ». Seules les lignes qui étaient surlignées en vert seront importées dans EVA. Les lignes avec un montant vide ou égal à zéro ne sont pas importées.
Une bonne pratique est de vérifier si l’import a bien eu lieu correctement.

Exporter depuis un logicel comptable pour import dans EVA
#########################################################

Il est possible d’exporter des fichiers dans un format tableur pour les dépenses et les recettes depuis votre logiciel comptable. La procédure a été expérimentée avec le logiciel **Berger-Levrault**, mais elle devrait être possible avec d’autres logiciels comptables. Les agents peuvent indiquer leur budget prévisionnel et l’équipe comptable peut par la suite importer les données du logiciel comptable dans EVA, ce qui facilite le suivi du budget par les agents. Cette partie permet d’élaborer les tableurs pour les **imports recettes et dépenses** comme décrit plus haut.

**Pré-requis :**

* Un *code* de rattachement aux fiches donc le code de la fiche doit se retrouver dans les lignes comptables (code analytique).
* Avoir créé ou importé les différents *comptes et enveloppes* utilisés.

**Dans le logiciel comptable :**

Depuis votre logiciel, faîte un premier tri de ce que vous souhaitez importer dans EVA, par exemple : une certaine période, tri en fonction des objets, du statut de la dépense… Faîtes un export du tableau qui vous convient, il doit à minima contenir les colonnes indiquées comme obligatoire dans la partie import dépenses et recettes de ce guide.

.. note::
	*Conseil* : importer dans EVA seulement les mouvements financiers stabilisés (par exemple les dépenses soldées) pour éviter d’avoir à modifier par la suite.

	*Colonnes obligatoires pour recettes* : Code analytique, Compte, Date, Montant

	*Colonnes obligatoires pour dépenses* : Code analytique, Compte, Date, Montant

**Dans Excel (ou autre outil de tableur) :**

L’export du tableau depuis le logiciel comptable ne sera surement pas directement importable dans EVA, il faudra le modifier pour que les colonnes correspondent à la description faite plus haut (dans la partie import recettes et import dépenses).
Il faudra sauvegarder le fichier en csv.

.. note::
	*Conseil* : utiliser la fonction de tri d’Excel s’il y a des lignes à modifier par bloc.

**Dans EVA :**

Importer le csv dans EVA en choisissant le type de mouvement, le type de dépense ou recette et le type d’import (dans ce cas souvent un ajout).

Les lignes importées vont se répartir sur les différentes fiches (grâce au code) et dans les différents comptes.


Procédure mots clés et référentiels
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Pour faciliter la création des nouveaux mots clés et référentiels, une fonction d’import en csv est maintenant disponible comme dans les autres modules. Le bouton rouge en bas à droite permet d’importer les mots clés ou référentiels. 

.. image:: images/Imports_motsclés.png
  :width: 300

Préparer le csv des mots clés et référentiels
#############################################

Le csv doit être construit comme suit (CVS UTF-8 délimité par des points virgules) :

+-------------------------+----------+-------------------+----------------+
| Nom Premier référentiel |          |                   |                |
+-------------------------+----------+-------------------+----------------+
|                         | 1. Axe 1 |                   |                |
+-------------------------+----------+-------------------+----------------+
|                         |          | 1.1 Orientation 1 |                |
+-------------------------+----------+-------------------+----------------+
|                         |          |                   | 1.1.1 Mesure 1 |
+-------------------------+----------+-------------------+----------------+
|                         |          |                   | 1.1.2 Mesure 2 |
+-------------------------+----------+-------------------+----------------+
|                         |          | 1.2 Orientation 2 |                |
+-------------------------+----------+-------------------+----------------+
|                         |          |                   | 1.2.1 Mesure 3 |
+-------------------------+----------+-------------------+----------------+
|                         | 2. Axe 2 |                   |                |
+-------------------------+----------+-------------------+----------------+
+-------------------------+----------+-------------------+----------------+
| Nom Deuxième référentiel|          |                   |                |
+-------------------------+----------+-------------------+----------------+
|                         | 1. QE 1  |                   |                |
+-------------------------+----------+-------------------+----------------+
|                         | 2. QE 2  |                   |                |
+-------------------------+----------+-------------------+----------------+
+-------------------------+----------+-------------------+----------------+
|                         |          | Sous QE 2.1       |                |
+-------------------------+----------+-------------------+----------------+
|                         |          | Sous QE 2.1 2     |                |
+-------------------------+----------+-------------------+----------------+

Le csv resesemble donc à ceci :
	| Nom Premier référentiel;;;
	| ;1. Axe 1;;
	| ;;1.1 Orientation 1;
	| ;;;1.1.1 Mesure 1
	| ;;;1.1.2 Mesure 2
	| ;;1.2 Orientation 2;
	| ;;;1.2.1 Mesure 3
	| ;2. Axe 2;;
	| Nom Deuxième référentiel;;;
	| ;1. QE 1;;
	| ;2. QE 2;;
	| ;;Sous QE 2.1;
	| ;;Sous QE 2.2;


Import dans EVA des mots clés et référentiels
#############################################

Choisir le fichier csv préparé précédemment et le délimiteur point-virgule puis cliquer sur « **Envoyer** ».

.. image:: images/interface_import_motsclés.png
  :width: 400


Si votre fichier a été bien paramétré, vos référentiels ou mots clés s’affichent (vous pouvez les déployer en appuyant sur les dossiers) :

.. image:: images/import_référentiel.png
  :width: 300

Si tout est conforme à vos attentes, cliquer ensuite sur « **Importer** ».

Vos référentiels ou mots clés sont importés dans les tableaux correspondants.

.. warning::
	Les référentiels et mots clés importés ne s'efface pas de l'écran comme indiqué dans le message EVA.

Il vous reste simplement à choisir s’ils peuvent être multiples ou non et l’association aux différents modules pour les mots clés.

.. note::
	**Multiples** ou non réfère au fait de pouvoir associer plusieurs parties d’un référentiel ou mot clé (exemple : axe 1 et mesure 3), cette option est à cocher lorsque l’on modifie un mot clé ou référentiel (cliquer sur le crayon en fin de ligne du référentiel ou mot clé à modifier).


.. warning::
	Pour les référentiels et mots clés des instances réseaux (OFB, FPNRF), pour qu'ils se propagent aux comptes EVA rattachés il faut aller les enregistrer une nouvelle fois dans les paramètres.

Procédure lien contact structure
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Il fortement recommandé **d’UTILISER LES ID** pour cet import même si les noms exacts peuvent aussi être utilisés. En effet, pour les contacts, il est souvent le cas que deux personnes se nomment de la même façon (nom et prénom) ou bien que l’on ait enregistré la même structure deux fois et dans ce cas, l’import se fera aléatoirement pour l’une des deux structures. Cela permet aussi de résoudre tous les problèmes de correspondance qui arrivent avec les typos. Pour les ID, il faut manipuler les tableurs en amont dans Excel pour bien préparer l’import.

Les ID sont accessibles dans les colonnes de chaque tableau de données dans EVA et sont présentes à l’export également. C’est un nombre attribué automatiquement par le logiciel en base de données mais qui est unique pour chaque élément.

Création du fichier csv
##########################

Pour créer un fichier csv, partons d’un cas d’usage. Vous souhaitez importer vos contacts et vos structures et le lien entre elles via un fichier Excel qui regroupe toutes ces informations. Ceci est votre fichier cible :

+--------------+--------+------------------+-----------------------------------------+
| Nom          | Prénom | Fonction         | Structure                               |
+==============+========+==================+=========================================+
| Roumazeilles | Léa    | Chargé de mission| Fédération des parcs naturels régionaux |
+--------------+--------+------------------+-----------------------------------------+
| Durand       | Jean   | Géomaticien      | PNRPC                                   |
+--------------+--------+------------------+-----------------------------------------+
| Dupont       | Jeanne | Directeur        | PN Cévennes                             |
+--------------+--------+------------------+-----------------------------------------+

**Il faut d’abord importer toutes les informations qui concernent les contacts avec l’import contacts et toutes les informations qui concernent les structures avec l’import structures** (voir la `documentation plus haut <https://documentation-eva.readthedocs.io/fr/latest/Fonctionnalit%C3%A9s-g%C3%A9n%C3%A9rales/Imports.html#import-contacts>`_ à ce sujet). **Vous devez également, soit créer les fonctions à la main si elles sont peu nombreuses soit les importer également.**

Si vous avez un nombre faible de liaison à importer, vous pouvez rechercher à la main, l’ID correspondant à vos contacts, structures et fonctions. Ils sont présents dans la première colonne.

Si vous avez un nombre conséquent de liaison à faire il y a deux façons de procéder : les ID (conseillé) ou les intitulés.

**Méthode recommandée avec les ID :**

1. Dans EVA afficher les colonnes ID et Nom et Prénom pour contact, les colonnes ID et Nom pour structure et ID et Fonction pour fonction. Exporter vos contacts, structures et fonctions via l’icône Excel en haut des tableaux |export_tableau| 

Vous obtenez trois tableaux Excel

**Contact**

+-------------+--------------+--------+
| Identifiant | Nom          | Prénom |
+=============+==============+========+
| 2111        | Dupont       | Jeanne |
+-------------+--------------+--------+
| 2110        | Durand       | Jean   |
+-------------+--------------+--------+
| 25          | Roumazeilles | Léa    |
+-------------+--------------+--------+

**Structure**

+-------------+-----------------------------------------+
| Identifiant | Nom                                     |
+=============+=========================================+
| 11          | PNRPC                                   |
+-------------+-----------------------------------------+
| 21          | PN Cévennes                             |
+-------------+-----------------------------------------+
| 24          | Fédération des parcs naturels régionaux |
+-------------+-----------------------------------------+

**Fonction**

+-------------+-------------------+
| Identifiant | Fonction          |
+=============+===================+
| 5           | Chargé de mission |
+-------------+-------------------+
| 12          | Directeur         |
+-------------+-------------------+
| 13          | Géomaticien       |
+-------------+-------------------+

2. Quelques réorganisations des fichiers est nécessaire : 

- Il faut concaténer le nom et le prénom pour les contacts en mettant bien le prénom en premier -> sur Excel utiliser 

``=CONCAT(Cellule-Prénom;" ";Cellule-Nom)``

Cette concaténation est aussi à effectuer dans le fichier cible.

-	Couper-coller en première colonne la colonne Prénom-Nom des contacts, Nom des structures et Fonction des fonctions, en laissant la colonne ID en deuxième colonne

3. Faire la liaison entre ID et noms dans votre fichier cible-> sur Excel utiliser 

``=RECHERCHV(Cellule Prénom-Nom;Matrice du fichier contact;2;FAUX)``

Cette fonction recherche dans la première colonne de la matrice du fichier contact exportée le Prénom Nom correspondant au Prénom Nom dans le fichier cible et insère l’ID correspond (qui se trouve en colonne 2). Faîtes de même pour les structures et fonction.
Vous obtenez ceci dans votre fichier cible :

+--------------+--------+------------------+--------------------------+------------------+-------------+---------------+--------------+
| Nom          | Prénom | Fonction         | Structure                | Prénom Nom       | Contact EVA | Structure EVA | Fonction EVA |
+==============+========+==================+==========================+==================+=============+===============+==============+
| Roumazeilles | Léa    | Chargé de mission| Fédération des parcs ... | Léa Roumazeilles | 25          | 24            | 5            | 
+--------------+--------+------------------+--------------------------+------------------+-------------+---------------+--------------+
| Durand       | Jean   | Géomaticien      | PNRPC                    | Jean Durand      | 2110        | 11            | 13           | 
+--------------+--------+------------------+--------------------------+------------------+-------------+---------------+--------------+
| Dupont       | Jeanne | Directeur        | PN Cévennes              | Jeanne Dupont    | 2111        | 21            | 12           | 
+--------------+--------+------------------+--------------------------+------------------+-------------+---------------+--------------+

Les trois dernières colonnes sont les colonnes avec les ID à transformer en fichier Excel puis csv et importer.

**Méthode avec les intitulés :**

Si votre fichier Excel initial est déjà bien calibré, que vous ne pensez pas avoir de doublons ou de typos, vous pouvez essayer d’importer avec les intitulés exacts. Pour cela dans votre fichier initial il faudra tout de même concaténer les noms et prénoms en une colonne « Prénom Nom » (voir point 2 de la méthode précédente). Puis transformer en format csv les trois colonnes Prénom Nom, Fonction et Structure.

**Méthode mixte :**

Il est aussi possible de faire un mixte ID et intitulés, par exemple, utiliser les ID pour les contacts et structures et les intitulés pour les fonctions.

Importer le fichier csv
#######################

Pour importer le fichier csv de lien entre contact et structure, dans le module annuaire, cliquer sur « Importer des liens entre contacts – structures – fonctions » via la pastille rouge en bas à droite.

.. image:: images/Import_liaison_annuaire.png
  :width: 500

Choisissez votre csv, le délimiteur et cocher la case des en-têtes et cliquer sur « Envoyer ».

.. image:: images/interface_import.png
  :width: 400

Vos données apparaissent, cliquer ensuite sur Valider pour bien vérifier les correspondances. Si vous essayer d’importer plusieurs fois les mêmes liens contacts-structures, cela sera notifié par une erreur.

.. image:: images/erreur_import_annuaire.png
  :width: 600

Si vous êtes satisfait, cliquer sur « importer ».
