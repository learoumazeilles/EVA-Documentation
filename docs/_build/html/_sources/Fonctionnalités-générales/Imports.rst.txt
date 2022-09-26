.. include:: ../substitutions.rst
Imports
=======

Procédure générale
~~~~~~~~~~~~~~~~~~

La précédure pour les imports est similaire dans la majorité des cas (exeption des imports budgets et territoires) et suit la logique suivante :

1. Créer un fichier tableur avec l’outil de tableur privilégié (Excel, Numbers, Google Sheet, Calc…) et remplir les données avec les en-têtes de colonnes correspondantes
2. Sauvegarder au format csv
3. Importer dans EVA

Quelles colonnes pour chaque import ?
#####################################

* Des exemples de fichiers Excel et csv sont disponibles `ici <https://fpnrf-my.sharepoint.com/:f:/g/personal/lroumazeilles_parcs-naturels-regionaux_fr/ElO1DP6dPJ1Mm2rn9hXL_MIBlJX3-IA-uYKlfkxfk9xGwA?e=QuNBOP>`_
* L’ordre des colonnes n’a pas d’importance, certaines cases peuvent être vides si elles ne sont pas dans les colonnes de champs obligatoires.
* Dans certaines colonnes, on peut indiquer un texte librement, pour d’autres seulement certains mots sont acceptés (indiqué en **gras** dans les tableaux ci-dessous) ou seulement des chiffres, les majuscules/minuscules sont importantes.
* Les mots clés et référentiels peuvent s’ajouter dans des colonnes supplémentaires s’ils ont été paramétrés précédemment.

Import utilisateurs
###################

Colonnes obligatoires : Prénom, Nom, Nom d’utilisateur, Rôle, Mot de passe

Autres colonnes possibles : Civilité, Adresse email, Couleur 

\+ les mots clés

+---------+---------+----------------+------------------+----------+-----------+------------+------------+
|Nom*     | Prénom* | Nom            | Rôle             | Mot de   | Civilités | Adresse    | Couleur    |
|         |         |                |                  |          |           |            |            |
|         |         | d'utilisateur* |                  | passe    |           | email      |            |
+=========+=========+================+==================+==========+===========+============+============+
| *Texte* | *Texte* | *Texte*        | Nom du rôle      | *Texte*  | **Mr.** ou| *Texte*    | Code hex   |
|         |         |                |                  |          |           |            |            |
|         |         |                | prédéfini dans   |          |           | *format*   | example :  |
|         |         |                |                  |          |           |            |            |
| *libre* | *libre* | *libre*        | le module admin  | *libre*  | **Mme**   | *email*    | #fcba03    |
+---------+---------+----------------+------------------+----------+-----------+------------+------------+


Import indicateurs
##################

Colonnes obligatoires : Nom, Type, Opérateur de synthèse annuelle

Autres colonnes possibles : Archivé (oui ou non), Description, Définition, Méthode, Interprétation, Unité de mesure 

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


Import contacts
###############

Colonnes obligatoires : Prénom, Nom

Autres colonnes possibles : Adresse email, Téléphone, Portable, Adresse, ligne 1, Adresse, ligne 2, Code postal, Ville, Pays

\+ les mots clés et groupe de champs additionnels

.. warning::
	Bien choisir le "Nom" avec astérisque dans l'interface EVA pour la colonne Nom* et pas celui sans astérisque.

+---------+---------+---------+---------+-----------+-----------+---------+
|Civilité | Prénom* | Nom*    | Adresse | Téléphone | Adresse   | Code    |
|         |         |         |         |           |           |         |
|         |         |         | email   |           | ligne 1   | postal  |
+=========+=========+=========+=========+===========+===========+=========+
| **m** ou| *Texte* | *Texte* | *Texte* | *Texte*   | *Texte*   | *Texte* |
|         |         |         |         |           |           |         |
| **mme** | *libre* | *libre* | *libre* | *libre*   | *libre*   | *libre* |
+---------+---------+---------+---------+-----------+-----------+---------+


Import structures
#################

Colonnes obligatoires : Nom

Autres colonnes possibles : AAdresse email, Sigle, Numéro de téléphone, SIRET, Site web, « Adresse, ligne 1 », « Adresse, ligne 2 », Code postal, Ville, Pays

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


Import fiches
##################

Colonnes obligatoires : Titre

Autres colonnes possibles (en fonction des paramètres) : Statut, Code analytique, Chef(s) de projet, Validateur(s), (+ autre rôle si paramétré), Rattachement arboresence initiale (fiche qui doit déjà exister), Objectifs, Etat d'avancement du projet, Contexte et motif, Activité et livrables (en fonction du paramétrage des blocs dans les fiches), Maîtrise d'ouvrage externe, Accessible au réseau, Modèle de fiche (le nombre présent dans l’URL lorsque l’on consulte ce modèle), Statut financier (ID), Date de programmation, Date de démarrage prévue, Date de fin prévue, Date de démarrage effective, Date de fin effective, Territoires

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

*Exemple URL du modèle de fiche : dans « Administration » puis « Modèles de fiches », cliquer sur le modèle souhaité, l’URL qui s’affiche ressemble à celui-ci « parc.evaparc.net/project/template/form/20 », dans ce cas indiquer « 20 » dans la case modèle de fiche.*

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

