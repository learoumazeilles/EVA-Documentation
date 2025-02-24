.. include:: ../../substitutions.rst
Développements 2025 02
======================

Contexte 2025 02
----------------

Un déploiement des derniers développements sur le logiciel EVA est prévu en février 2025. Il comprend des **résolutions d’anomalies** liés au précédent déploiement et des corrections sur le logiciel. Des corrections sur les synchronisations notamment ont pu avoir lieu directement depuis le dernier déploiement en décembre.

Les développements sont détaillés ci-après, avec le détail du ticket GitLab associé et un mode d’emploi pour les nouveautés.


Rappel nouveautés indicateurs
#############################

Une première partie des développements sur le module indicateur a été livrée en avril 2024 et une deuxième partie plutôt corrective en juillet 2024 incluant :

- groupement des indicateurs en "groupe" 
- création de campagne de recueil des donnnées pour associer une date de saisie attendue et un référent par indicateur
- import des mesures d'indicateur
- association de pièce-jointes aux mesures

**N'hésitez pas à me faire remonter toutes remarques ou anomalies sur ces nouvelles fonctionnalités indicateurs par mail lroumazeilles@parcs-naturels-regionaux.fr**


Indicateurs 022025
------------------

1. Liaison mesure cible réalisée lors de la suppression hors campagne
#####################################################################

`Ticket 650 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/650>`_

Pour un indicateur présent dans une campagne, si dans le module indicateur on supprime juste la mesure cible par exemple, toute la mesure est supprimée dans la campagne. Par contre dans l'indicateur il restera la mesure réalisée alors qu'elle n'existe plus dans la campagne

**Corrigé : la suppression du couple cible/réalisé est effective aussi dans la partie indicateur**


2. Liaison indicateurs réseau et parcs
######################################

`Ticket 579 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/579>`_

Les dysfonctionnements entre compte réseau et compte parc ont été résolus. Voici le fonctionnement de la liaison pour les indicateurs :

Pour des indicateurs hors campagne locale :

+----------------+----------------------------------+----------------------------------+
|Action          | action parc -> impact national   | Action national -> impact parc   |
|                |                                  |                                  |
+================+==================================+==================================+
| Ajout          | Oui                              | Oui                              |
+----------------+----------------------------------+----------------------------------+
| Modification   | Oui                              | Oui                              |
+----------------+----------------------------------+----------------------------------+
| Suppression    | Oui                              | Oui                              |
+----------------+----------------------------------+----------------------------------+


Mais pas possible de supprimer ou modifier une mesure insérée au niveau nationale depuis le locale


Pour des indicateurs inclus dans une campagne locale :

+----------------+----------------------------------+----------------------------------+
|Action          | action parc -> impact national   | Action national -> impact parc   |
|                |                                  |                                  |
+================+==================================+==================================+
| Ajout          | Oui                              | Oui                              |
+----------------+----------------------------------+----------------------------------+
| Modification   | Oui                              | Oui                              |
+----------------+----------------------------------+----------------------------------+
| Suppression    | Oui                              | Oui                              |
+----------------+----------------------------------+----------------------------------+


Les données non transmises entre locale et nationale (car pas de liaison là-dessus) :

- créé le
- modifié le
- territoire
- fiche
- document
- campagne de mesures
- date attendues

**-> Il reste quelques dysfonctionnements à corriger sur le nom donné aux parcs entre parc et réseau**

Synchronisations des temps et analyses temps
--------------------------------------------

Modification des titres de synchronisations
###########################################

`Ticket 666 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/666>`_

Certains titres de synchronisations des temps n'étaient pas modifiables depuis la vue tableau, leur modification et sauvegarde donnait une erreur. Il est maintenant possible de les modifier sans erreur.

**Corrigé**

Bugs sur les synchronisations
#############################

`Ticket 608 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/608>`_ & `Ticket 684 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/684>`_

Des bugs sur les synchronisations étaient apparus lors du dernier déploiement, ils ont maintenant été corrigés.

**Corrigé**

Latence sur les analyses temps
##############################

`Ticket 677 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/677>`_ & `Ticket 700 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/700>`_

Chez certains parcs qui ont beaucoup de temps insérés dans EVA, la latence de chargement des pages de temps et d'analyses temps pouvait être très longue voir bloquer complètement le logiciel. Le chargement de certaines pages a été améliorées :

- module temps : feuilles de temps
- module analyses : feuilles de temps, répartition par utilisateurs, répartition par mois, répartition par mots-clés

D'autres pages restent à reprendre :
- modules analyses : répartition par fiche, répartition par mots-clés fiches -> le tableau récapitulatif s'affiche, le graphique peut ne ne pas s'afficher chez certains parcs, ne pas hésiter à changer de graphique si besoin
- module analyses : répartition par territoire -> affichage à reprendre complètement

Cette reprise des analyses avait entraîné une suppression des filtres par défaut dans les feuilles de temps qui a été remis.

**Correction à compléter**

Autres corrections
------------------

`Ticket 679 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/679>`_

Certains éléments étaient issus d'anciennes versions mais n'avaient plus de sens dans EVA, ils ont été retirés :

- fiche -> onglet budget -> poste de dépense saisie simplifiée
- dans le modèle de fiche -> les champs project_field_coordinatesLongitude et project_field_coordinatesLattitude
