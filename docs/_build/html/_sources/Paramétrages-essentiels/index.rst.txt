.. include:: ../substitutions.rst
Paramétrages essentiels
=======================

Mots clés et référentiels
-------------------------

Techniquement les référentiels et mots clés sont la même chose (possibilité d’arborescence, de rattachement…).

- **Les référentiels** vont correspondre aux arborescences de type contractuel comme la charte ou le plan de gestion, Natura 2000, le plan d'actions... ils sont rattachés automatiquement aux fiches et indicateurs.

- **Les mots clés** sont à définir plus finement pour les analyses et à rattacher à chaque type d’information. Par exemple des types de partenaire à rattacher aux acteurs, des types d'indicateur à rattacher aux indicateurs, des thématiques à rattacher aux fiches...

Les mots clés et référentiels se trouvent dans le module |administration| > |mots_cles|, il y a un onglet pour les Mots-clés et un onglet pour les Référentiels.

Paramétrages
~~~~~~~~~~~~

Les mots clés et référentiels sont à paramétrer par le référent EVA **au début** de l'utilisation du logiciel. Ils sont à paramétrer en fonction des besoins en **analyses et en export identifiés**. 

Il est important de faire de la **sensibilisation** dans les équipes pour que les mots clés et référentiels soient bien remplis, il est possible de mettre en place une **notice d’utilisation** de ces mots clés.

Il est utile **d’évaluer fréquemment** l’utilisation des mots clés pour s’assurer que l’on couvre les besoins, on peut rapidement se rendre compte avec les filtres et analyses si certains mots clés sont trop peu ou trop largement utilisés (il est alors possible de les archiver ou fusionner).

Onglet Mots-clés
~~~~~~~~~~~~~~~~

Les mots-clés se présentent sous forme de tableau avec l'intitulé du mot-clé dans la colonne **Nom**. En cliquant sur |dossier|, on peut déroulé l'intitulé pour voir les attributs du mot clé :

Exemple ici pour le mot-clé **Thématiques** :

.. image:: images/Mots_clés_ex.png
	:width: 300


Les autres colonnes indiquent à quel élément du logiciel le mot clé est rattaché. Si la colonne fiche pour un mot clé est coché alors ce mot clé sera accessible dans les fiches.

Pour créer un mot clé il faut cliquer sur le |ajout_plus| en haut à droite, pour importer un mot clé il faut cliquer sur |bouton_3_traits| (voir `documentation import mots clés <https://documentation-eva.readthedocs.io/fr/latest/Fonctionnalit%C3%A9s-g%C3%A9n%C3%A9rales/Imports.html#procedure-mots-cles-et-referentiels>`_)


.. image:: images/Mots_clés_creation.png
	:width: 500


Lors de la création d'un mot clé, on indique :
- s'il est multiple en cochant la case, cela permet de rattacher un même élément à plusieurs attribut du mot clé. Par exemple, si une fiche traite de plusieurs thématiques, si le mot clé **Thématiques** est multiple on pourra rattacher la fiche à plusieurs thématiques

.. warning ::
	Quand un mot clé est multiple et une fiche est rattachée à plusieurs attributs il faut faire attention dans les analyse car la totalité de l'action sera prise en compte pour chaque attribut :
	Par exemple si on a une fiche avec un budget à 10 000 euros rattachés à deux thématiques dans les analyses comment est comptabilisé le budget pour chaque thématique ?
	-> Par défaut les éléments vont être répétés dans les deux thématiques, donc les 10 000 euros sont comptabilisés deux fois, pour bien faire apparaître les proportions. Par contre dans les totaux, on ne les comptabilise pas deux fois.
	Lors des analyses, il y a la possibilité de diviser les éléments à parité lorsqu’ils sont rattachés à plusieurs entités d’un mot clé ou référentiel (dans l’exemple attribuer 5 000 euros à chaque thématique), il faut cocher une case pour l’indiquer.


- le nom du mot clé (le nom chapeau donc par exemple Thématiques)

- à quel élément du logiciel il doit être attribué


Après enregistrement de ces éléments le mot clé apparaît dans la liste des mots-clés.

.. warning ::
	Après le premier enregistrement, il apparaît tout en bas de la page, puis il apparaitra dans l'ordre alphabétique.

Il est possible de :

- modifier le mot clé avec |crayon_modif_ligne|

- archiver le mot clé avec |archiver_ligne|, cela le retire de la liste de choix dans l'élément rattaché (fiche si on a coché fiche) mais ne supprime pas l’historique des données rattachées et le laisse dans la liste des mots-clés pour pouvoir le réactiver plus tard si besoin en cliquant sur |reactive|.

- supprimer avec |supprimer_ligne|

- On peut lui ajouter des attributs (exemple : les différentes thématiques) en cliquant sur le |ajout_plus| à côté du nom.

Les attributs sont définis par :

- un nom

- une description

- Un parent : les mots clés étant arborescents on peux rattacher des attributs d'un niveau inférieur à un niveau supérieur, par exemple dans la thématique Biodiversité on peut avoir des sous-thématiques, biodiversité terrestre et biodiversité marine.

- L'ordre dans lequel il doit appraître, sachant que le premier à apparaître sera celui avec un ordre 0. Si plusieurs mots clés ont un ordre 0, l'ordre sera par ordre alphabétique.


Après enregistrement de l'attribut il apparaît dans la liste si on clique sur le |dossier|.

Il est possible de :

- modifier l'attribut avec |crayon_modif_ligne|

- archiver l'attribut avec |archiver_ligne|, cela le retire de la liste de choix lors du remplissage du mot clé mais ne supprime pas l’historique des données rattachées et le laisse dans la liste pour pouvoir le réactiver plus tard si besoin en cliquant sur |reactive|.

- supprimer avec |supprimer_ligne|

- fusionner en cliquant sur |fusion| : Une boîte de dialogue s’ouvre

Documentation en cours de construction


Exemples de mots clés et référentiels
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~





Création de comptes utilisateurs
--------------------------------

Gestion des rôles
-----------------