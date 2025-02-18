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


Synchronisations des temps 022025
---------------------------------

Modification des titres de synchronisations
###########################################

`Ticket 666 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/666>`_

Certains titres de synchronisations des temps n'étaient pas modifiables depuis la vue tableau, leur modification et sauvegarde donnait une erreur. Il est maintenant possible de les modifier sans erreur.

**Corrigé**

D'autres corrections sont à venir sur les synchronisations.

Autres corrections
------------------

`Ticket 679 <https://gitlab.com/logiciel-eva/logiciel-eva/-/issues/679>`_

Certains éléments étaient issus d'anciennes versions mais n'avaient plus de sens dans EVA, ils ont été retirés :

- fiche -> onglet budget -> poste de dépense saisie simplifiée
- dans le modèle de fiche -> les champs project_field_coordinatesLongitude et project_field_coordinatesLattitude
