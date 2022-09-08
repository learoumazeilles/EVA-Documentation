Fonctionnalités générales
=========================

Tableaux
--------

Ajout
-----

Imports
-------

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
* Dans certaines colonnes, on peut indiquer un texte librement, pour d’autres seulement certains mots sont acceptés (indiqué en **gras** dans les tableaux ci-dessous) ou seulement des chiffres, les majuscules/minuscules sont importantes
* Les mots clés et référentiels peuvent s’ajouter dans des colonnes supplémentaires s’ils ont été paramétrés précédemment

Import utilisateurs
###################

Colonnes obligatoires : Prénom, Nom, Nom d’utilisateur, Rôle, Mot de passe
Autres colonnes possibles : Civilité, Adresse email, Couleur 
+ les mots clés

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



Procédure budget
~~~~~~~~~~~~~~~~

