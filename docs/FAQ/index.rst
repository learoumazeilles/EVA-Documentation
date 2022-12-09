FAQ
===

*Foire aux questions*

Taille des colonnes
-------------------
La largeur des colonnes peut soit être figée soit s'adapter lorsque l'on passe la souris dessus. C'est un paramétrage pour le profil de chaque personne, il faut cocher ou déchocher la case « tableau redimensionnable » dans votre profil. Elle se trouve à côté de votre choix de couleur. Vous pouvez cliquer sur votre nom en haut à droite dans EVA pour y accéder.

.. image:: images/Taille_colonnes.png
   :width: 600

Problème d'accès, roue qui mouline
----------------------------------
Lorsque vous êtes face à une roue qui mouline indéfiniement ou n'avez plus accès à un module pour lequel vous aviez accès précédemment, deux explications sont fréquentes:

- la définition du rôle utilisateur a été modifiée : sur certains rôles il y a des dépendances pas toujours logiques qui vont empêcher les accès (nous sommes en train de corriger ces éléments) -> il faudra donc vérifier les rôles

- il y a un ancien filtre ou un tri de colonne qui bloquent : dans ce cas enlever tous les filtres ou réinitialiser les colonnes (en cliquant sur les petites flèches à côté du nom des colonnes)

Liste des territoires
---------------------
Dans une fiche, dans l'onglet territoire, en cliquant sur le petit plus la liste des territoires n'apparait pas, ceci est normal. Il faut taper au moins deux lettres puis la loupe et les territoires correspondants pourront s'afficher. Sinon, directement dans la zone de texte intial, en commençant à taper le nom de votre territoire, l'autocomplétion pourra avoir lieu.


Différence entre référentiels et mots clés
------------------------------------------
Techniquement les référentiels et mots clés sont la même chose (possibilité d’arborescence, de rattachement...).

- **Les référentiels** vont correspondre aux arborescences de type contractuel la charte ou le plan de gestion, ils sont rattachés automatiquement aux fiches et indicateurs.

- **Les mots clés** sont à définir plus finement pour les analyses et à rattacher à chaque type d’information.


Différence entre modèles de fiche et niveaux de fiches
------------------------------------------------------
Les modèles et niveaux sont dissociés dans les fiches EVA, un modèle ne s’applique pas automatiquement à un niveau.

- **Modèles de fiches** : Les modèles permettent de choisir le contenu à saisir pour certains types de projet et non pour d’autres. Par exemple des champs spécifiques pour les fiches Natura 2000 qui ne seront pas dans les fiches par défaut. Ils sont paramétrables dans la partie administration

- **Niveaux de fiches** : Les niveaux de fiche s’appliquent automatiquement en fonction du rattachement à un parent fiche (rattachement arborescence initiale dans la fiche). Par exemple si on a des niveaux tels que : Projet > Action > Sous-action. Une fiche créée sera par défaut un projet, elle deviendra une action si elle est rattachée à une fiche projet.


Rattachement d'une fiche à plusieurs mesures
--------------------------------------------
Si on rattache une fiche à plusieurs mesures, comment les éléments sont-ils comptabilisés ? Par exemple si on a une fiche avec un budget à 10 000 euros rattachés à deux mesures de la charte, dans les analyses comment est comptabilisé le budget pour chaque mesure ?

Par défaut les éléments vont être répétés dans les deux mesures, donc les 10 000 euros sont comptabilisés deux fois, pour bien faire apparaître les proportions. Par contre dans les totaux, on ne les comptabilise pas deux fois.

Lors de certaines analyses, il y a la possibilité de diviser les éléments à parité lorsqu’ils sont rattachés à plusieurs entités d’un référentiel (dans l’exemple attribuer 5 000 euros à chaque mesure), il faut cocher une case pour l’indiquer.



