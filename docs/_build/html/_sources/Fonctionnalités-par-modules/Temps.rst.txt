.. include:: ../substitutions.rst
Temps
=====

Les temps sont necessairement rattachés aux fiches, ils peuvent être ajoutés de plusieurs façon :

- En remplissant un formulaire
- En faisant un import de tableur
- En important des feuilles de temps via fichier .ics
- En remplissant des semaines types (ajout hebdomadaire)
- En paramétrant une synchronisation avec un autre agenda (synchronisation automatique ou manuelle).

Feuilles de temps
---------------------------

La liste des feuilles de temps s'affichent par défaut en vue calendrier avec un double filtre temps passés et utilisateur courant. Pour avoir accès à la vue tableau il faut cliquer sur |vue_liste| en haut et sur |vue_calendrier| pour revenir en vue calendrier. Les requêtes et filtres sont les mêmes en vue calendrier et liste.

.. image:: images/Filtre_temps.png
  :width: 500

Vue Calendrier
~~~~~~~~~~~~~~

On peut choisir une vue Mois, Semaine ou Jour.

.. image:: images/Mois_semaine_jour.png
  :width: 200

Et faire défiler le temps en cliquant sur les flèches ou revenir aujourd'hui.

.. image:: images/Défilement_temps.png
  :width: 200

Pour ajouter une feuille de temps en vue calendrier on peut cliquer directement sur le calendrier, le formulaire d'ajout s'affiche à la date cliquée.

Vue Liste
~~~~~~~~~

Les fonctionnalités de tableau et d'ajout sont détaillées dans la partie :ref:`Fonctionnalités générales`.

Dans cette vue liste il y a quelques particularités de tableau :

- En cochant la case des lignes, on a la possibilité de **supprimer** plusieurs feuilles de temps d'un coup, l'icône |supprimer_ligne| apparaît au dessus des cases à cocher
- En cochant la case des lignes on a la possibilité de **modifier** plusieurs lignes d'un coup l'icône |crayon_modif_ligne| apparaît au dessus des cases à cocher, on peut modifier le **type** (passé, prévu ou absence) et le nombre d'heures. (Il faut cocher la case *Utiliser* de chaque champ si on veut les modifier).
- Dans ce module, il y a la particularité d'avoir accès aux **mots clés et référentiels reliés aux fiches** auxquelles sont reliées les feuilles de temps. Donc si on préfère ajouter les mots clés au niveau des fiches plutôt qu'au niveau de chaque feuille de temps, on peut les retrouver en sélectionnant les colonnes correspondantes (pas de filtre possible mais on peut voir à quels mots clés et référentiels sont reliées les fiches des feuilles de temps)

.. image:: images/Tableau_temps.png
  :width: 700

Formulaire ajout feuille de temps
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Les champs utilisateur, fiche rattachée, dates de début et de fin, nombre d'heures et type de temps sont obligatoires. 

.. image:: images/Formulaire_temps.png
  :width: 700

- Le champs **Utilisateur** est rempli par défaut avec l'utilisateur courant mais on peut le modifier
- Le champ **Fiche** permet d'attribuer le temps à une fiche
- On peut renseigner les dates de **début** et de **fin** en les écrivant ou en cliquant sur le |vue_calendrier| pour choisir un jour.
- Une fois les dates de début et de fin remplies, en appuyant sur |calculatrice|, le nombre d'**heures** est calculée automatiquement (différence entre date de début et de fin), s'il n'est pas le bon, on peut insérer un nombre différent. Le nombre d'heures peut être différent de la différence entre début et fin (moins élevé comme plus élevé).
- Le champ **Type** permet de choisir entre **temps passé**, **temps prévu** et **temps d'absence**.
- En choisissant **temps d'absence**, un autre champ s'affiche avec le **Type d'absence** s'il a été paramétré. Il peut être paramétré dans |administration| > |temps_param|.
- Des **mots clés** peuvent être ajoutés aux feuilles de temps, la case "Feuille de temps" doit être cochée dans le mot clé
- Des **Territoires** peuvent aussi être ajoutés aux temps

.. warning::
	Si le pramétrage des types d'absence n'a pas été paramétré, l'ajout des temps d'absence ne fonctionnera pas.

Formulaire import avec fichier .ics
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En cliquant sur |bouton_3_traits|, dans ce module on peut aussi ajouter des feuilles de temps en important un ficher .ics (aussi disponible depuis la partie synchronisation du module temps). C'est le même principe que pour les synchronisations mais il faut remplir les champs à chaque import. Si vous faites cet import couramment et que vous pouvez partager un lien d'agenda public, il sera plus pratique de paramétrer une synchronisation.

Les fichiers .ics peuvent être exportés depuis vos agendas type google, outlook ou autres. 

.. image:: images/Jointure_ics.png
  :width: 700

Les temps dans les agendas doivent pouvoir être reliés aux fiches, ce sont les champs **Jointure à la fiche** qui permettent de les relier :

- **Champ utilisé** correspond au champ dans votre agenda ou il y aura l'élément de rattachement à la fiche : titre, description, localisation, tags pour Zimbra
- **Caractère(s) d'entourage** correspond aux caractères entourant l'élément de rattachement à la fiche : crochet [] ou hashtag # ou aucun. Il est préférable de choisir les [].
- **Champs de jointure fiche** correspond au champ dans la fiche qui permet de faire le rattachement, il doit être un champ unique pour chaque fiche : Code, Titre, Champ personnalisé (personalisé dans |administration| > |champs|), Aucun (ne rattachera pas les fiches)

.. warning::
	Catégories pour Outlook ne fonctionnent plus car Outlook ne les exporte plus.

.. note::
	Si le **hashtag** est utlisé comme caractère d'entourage, il ne peut pas y avoir d'espace dans l'élément rattaché car le rattachement s'arrête au premier espace.
	Si **Aucun** est utilisé comme caractère d'entourage, l'élément de rattachement devra être présent seul dans le titre, localisation ou tags et pourra être accompagné d'autres éléments dans la description.

Dans les agendas
################

Donc dans les agendas, il faut indiquer un élément de rattachement à la fiche avec les caractères d'entourage.

Vous pouvez également indiquer les **mots clés** et **territoires** dans vos agendas. Pour les **mots clés**, vous pouvez les indiquer dans la description avec des caractères d'entourage ou non si en un seul mot, mais si le mot clé est en plusieurs mots il faudra utiliser les crochets. Dans le cas des **territoires**, il faut les insérer dans la partie localisation/lieu du rendez-vous.

.. note::
	Si le **champs utilisé** pour la jointure à la fiche est localisation/lieu, il ne pourra pas être utilisé pour rattacher les territoires.

Exemple de temps inséré dans l'agenda google pour import :

.. image:: images/Ex_agenda_google.png
  :width: 300

Dans EVA
########

Remplir **champ utilisé**, **caractère(s) d'entourage** et **champ de jointure** (champs détaillés plus haut).

Pour l'exemple ci-dessus :

.. image:: images/Jointure_fiche_ex.png
  :width: 500

La période à synchroniser permet de choisir la partie du calendrier à importer dans EVA. 

.. image:: images/Période_synchro.png
  :width: 200

.. note::
	Si une période a été importée deux fois, les temps ne seront pas importés deux fois s'ils n'ont pas été modifiés entre temps.

Cliquer sur **Importer**.

Indiquer l'utilisateur à qui rattacher les temps (un seul possible), puis vérifier les temps importés dans le tableau en dessous :

- Le **type** sera par défaut temps passé mais on peut le modifier ici
- Si la **fiche** n'a pas pu être trouvé dans le rattachement automatique, vous pouvez la rattacher ici
- Vérifier les **heures de début et de fin** et le nombre d'**heures** total
- Vérifier les **mots clés** et **territoires**

Dans l'exemple, voici la ligne qui apparaît :

.. image:: images/Synchro_EVA_ex.png
  :width: 700

Seul les temps rattachés à une fiche seront importés, donc si vous avez des temps personnels indiqués dans votre agenda (type RDV médicaux) s'ils ne contiennent pas de code fiche, il ne seront pas conservés.

Pour les **mots clés** et **territoires**, on peut les rajouter dans cette interface également :

- soit sur chaque ligne en cliquant sur |icone_tag| ou |icone_lieu| pour en ajouter ou remplacer
- soit pour éditer plusieurs lignes avec les mêmes mots clés ou territoires, cocher les cases des lignes concernées puis en haut du tableau cliquer sur |icone_tag| ou |icone_lieu| pour ajouter (ou remplacer) les mêmes mots clés ou territoires sur toutes les lignes cochées

Une fois importée, vous pouvez vérifier la ligne dans l'onglet temps de la fiche associée, par exemple (mode d'intervention est le mot clé) :

.. image:: images/Temps_synchro_fiche.png
  :width: 700

Ajout hebdomadaire
------------------

|Temps| > |ajout_hebdo_module|

L'ajout hebdomadaire permet d'ajouter toute la semaine de temps d'un coup. C'est particulièrement utile si vous avez des semaines qui se ressemblent.

Lorsque l'on appuie sur ajouter une ligne, on peut ajouter des feuilles de temps avec le même titre, la même fiche associée, le même type (passé, prévu, absence), les mêmes mots clés et territoires pour toute la semaine. On peut choisir un nombre d'heure différent pour chaque jour.

.. image:: images/Ajout_hebdo.png
  :width: 700

Pour les **mots clés** et **territoires**, on peut les rajouter de deux façons :

- soit sur chaque ligne en cliquant sur |icone_tag| ou |icone_lieu| pour en ajouter, remplacer ou enlever
- soit pour éditer plusieurs lignes avec les mêmes mots clés ou territoires, cocher les cases des lignes concernées puis en haut du tableau cliquer sur |icone_tag| ou |icone_lieu| pour ajouter (ou remplacer ou enlever) les mêmes mots clés ou territoires sur toutes les lignes cochées

La ligne peut être **supprimée** grâce au bouton poubelle rouge en bout de ligne.

Sur la partie du haut de l'interface :

.. image:: images/Ajout_hebdo_haut.png
  :width: 700

- On peut choisir la **requête** de fiche que l'on souhaite afficher, ces requêtes correspondent à celles enregistrées dans le module fiche. Ceci permet d'afficher toutes les fiches qui répondent à cette requête si on a besoin d'ajouter du temps pour un certain type de fiche.
- On peut faire **défiler** les semaines concernés par l'ajout
- On peut choisir **l'utilisateur** concerné par l'ajout hebdomadaire (par défaut utilisateur courant)
- En cliquant sur |signet| après avoir calibré une semaine, on peut **sauvegarder** cette semaine en appuyant sur "+ enregistrer la semaine" (il faut recharger la page après pour la voir apparaître). Cela permet de pouvoir appliquer des **modèles de semaines type**, car en cliquant sur le nom de la semaine enregistrée, on peut ensuite la réappliquer.
- Pour enregistrer les feuilles de temps, cliquer sur |Enregistrer_ligne|.

En dessous s'affiche le temps passé déjà renseigné pour la semaine affichée, s'il y en a (Historique temps passé).

Synchronisations
----------------

|Temps| > |synchro_module|

La synchronisation est utile pour importer automatiquement plusieurs feuilles de temps depuis votre agenda. On peut paramétrer des synchronisations automatiques ou choisir de lancer la synchronisation quand on le souhaite. Le fonctionnement des synchronisations est similaire au fonctionnement des imports de ficher .ics détaillé plus haut.

Les fonctionnalités de tableau et d'ajout sont détaillées dans la partie :ref:`Fonctionnalités générales`.

Dans EVA
########

.. image:: images/Ajout_synchro.png
  :width: 700

Il faut donner un **titre** à la synchronisation et ajouter le **lien** qui permettra de récupérer les données. Ce lien peut être trouvé dans les paramètre de partage de votre boîte mail (sous le nom d'adresse privée ou lien de partage, en .ics ou .ical...).

Choisissez ensuite le **type** en fonction de votre agenda (Google, Phénix, Zimbra, Outlook) et voter fuseau horaire.

Les temps dans les agendas doivent pouvoir être reliés aux fiches, ce sont les champs **Jointure à la fiche** qui permettent de les relier :

- **Champ utilisé** correspond au champ dans votre agenda ou il y aura l'élément de rattachement à la fiche : titre, description, localisation, tags pour Zimbra
- **Caractère(s) d'entourage** correspond aux caractères entourant l'élément de rattachement à la fiche : crochet [] ou hashtag # ou aucun. Il est préférable de choisir les [].
- **Champs de jointure fiche** correspond au champ dans la fiche qui permet de faire le rattachement, il doit être un champ unique pour chaque fiche : Code, Titre, Champ personnalisé (personalisé dans |administration| > |champs|), Aucun (ne rattachera pas les fiches)

.. warning::
  Catégories pour Outlook ne fonctionnent plus car Outlook ne les exporte plus.

.. note::
  Si le **hashtag** est utlisé comme caractère d'entourage, il ne peut pas y avoir d'espace dans l'élément rattaché car le rattachement s'arrête au premier espace.
  Si **Aucun** est utilisé comme caractère d'entourage, l'élément de rattachement devra être présent seul dans le titre, localisation ou tags et pourra être accompagné d'autres éléments dans la description.

Dans les agendas
################

Donc dans les agendas, il faut indiquer un élément de rattachement à la fiche avec les caractères d'entourage.

Vous pouvez également indiquer les **mots clés** et **territoires** dans vos agendas. Pour les **mots clés**, vous pouvez les indiquer dans la description avec des caractères d'entourage ou non si en un seul mot, mais si le mot clé est en plusieurs mots il faudra utiliser les crochets. Dans le cas des **territoires**, il faut les insérer dans la partie localisation/lieu du rendez-vous.

.. note::
  Si le **champs utilisé** pour la jointure à la fiche est localisation/lieu, il ne pourra pas être utilisé pour rattacher les territoires.

Exemple de temps inséré dans l'agenda google pour import :

.. image:: images/Ex_agenda_google.png
  :width: 300

Dans EVA
########

Remplir **champ utilisé**, **caractère(s) d'entourage** et **champ de jointure** (champs détaillés plus haut).

Pour l'exemple ci-dessus :

.. image:: images/Jointure_fiche_ex.png
  :width: 500

Il est ensuite possible d' **enregistrer** la synchronisation telle quelle ou bien de paramétrer la partie de **synchronisation automatique**.

Dans ce cas il faudra indiquer l'**utilisateur** auquel appartient le calendrier à synchroniser et la **cadence** de synchronisation : quotidienne, hebdomadaire, mensuelle ou trimestrielle puis enregistrer.

.. image:: images/Synchro_auto.png
  :width: 200

Dans les deux cas (synchronisation automatique remplie ou non), on peut lancer la synchronisation manuellement depuis le tableau des synchronisations, en cochant la synchronisation à lancer et en cliquant sur |bouton_synchro| en haut du tableau.

Il faudra alors choisir la **période** à synchroniser et l'**utilisateur** concerné et cliquer sur **synchroniser**.

.. image:: images/Synchro_période.png
  :width: 500

Vérifier ensuite les temps importés dans le tableau en dessous :

- Le **type** sera par défaut temps passé mais on peut le modifier ici
- Si la **fiche** n'a pas pu être trouvé dans le rattachement automatique, vous pouvez la rattacher ici
- Vérifier les **heures de début et de fin** et le nombre d'**heures** total
- Vérifier les **mots clés** et **territoires**

Dans l'exemple, voici la ligne qui apparaît :

.. image:: images/Synchro_EVA_ex.png
  :width: 700

Seul les temps rattachés à une fiche seront importés, donc si vous avez des temps personnels indiqués dans votre agenda (type RDV médicaux) s'ils ne contiennent pas de code fiche, il ne seront pas conservés.

La **Description** de votre rendez-vous est aussi récupérée et insérée dans le champs **Description**.

Pour les **mots clés** et **territoires**, on peut les rajouter dans cette interface également :

- soit sur chaque ligne en cliquant sur |icone_tag| ou |icone_lieu| pour en ajouter ou remplacer
- soit pour éditer plusieurs lignes avec les mêmes mots clés ou territoires, cocher les cases des lignes concernées puis en haut du tableau cliquer sur |icone_tag| ou |icone_lieu| pour ajouter (ou remplacer) les mêmes mots clés ou territoires sur toutes les lignes cochées

Une fois importée, vous pouvez vérifier la ligne dans l'onglet temps de la fiche associée, par exemple (mode d'intervention est le mot clé) :

.. image:: images/Temps_synchro_fiche.png
  :width: 700

Exports temps
-------------

