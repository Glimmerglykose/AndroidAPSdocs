# Générateur de configuration

Selon vos paramètres, vous pouvez ouvrir le générateur de configuration via un onglet situé en haut de l'écran ou via le menu hamburger.

![Ouvrir le générateur de configuration](../images/ConfBuild_Open_AAPS30.png)

Le Générateur de configuration (Conf) est l'onglet dans lequel vous activez et désactivez les fonctions modulaires. Les cases du côté gauche (A) vous permettent de choisir celles à utiliser, les cases du côté droit (C) vous permettent de les visualiser sous forme d'onglet (E) dans AndroidAPS. Si la case de droite n'est pas cochée, vous pouvez atteindre la fonction en utilisant le menu hamburger (D) en haut à gauche de l'écran.

Lorsque des paramètres supplémentaires sont disponibles dans le module, vous pouvez cliquer sur la roue crantée (B) qui vous amènera a des paramètres spécifiques dans les préférences.

**Première configuration :** Depuis lAPS 2.0, un assistant de configuration vous guide à travers le processus de configuration de AndroidAPS. Appuyez sur le menu 3 points en haut à droite de l'écran (F) et sélectionnez 'Assistant de configuration' pour l'utiliser.

![Sections du générateur de configuration et roue crantée](../images/ConfBuild_ConfigBuilder_AAPS30.png)

(Config-Builder-tab-or-hamburger-menu)=

## Onglet ou menu hamburger

Avec la case à cocher sous le symbole de l'oeil, vous pouvez décider comment ouvrir la section correspondante du programme.

![Onglet ou menu hamburger](../images/ConfBuild_TabOrHH_AAPS30.png)

(Config-Builder-profile)=

## Profil

* Sélectionnez le profil de basal que vous souhaitez utiliser. Voir la page [Profils](../Usage/Profiles.md) pour plus d'informations sur la configuration.
* A partir d'AAPS 3.0, seul le profil local est disponible.

Cependant, il est possible de synchroniser un profil Nightscout dans un profil local. Pour cela, cependant, il est important de cloner toute la base de données composée de plusieurs profils dans l'éditeur Nightscout. Veuillez consulter les instructions ci-dessous. Cela peut être utile si des modifications majeures d'un profil peuvent être introduites plus facilement via l'interface web, par ex. pour copier manuellement les données d'une feuille de calcul.

(Config-Builder-local-profile)=

### Profil Local

Le profil local utilise le profil de basal entré manuellement sur le téléphone. Dès qu'il est sélectionné, un nouvel onglet apparaît dans AAPS, où vous pouvez modifier les données de profil lues à partir de la pompe si nécessaire. Avec le changement de profil suivant, les données sont ensuite écrites dans la pompe dans le profil 1. Ce profil est recommandé car il ne dépend pas de la connectivité Internet.

Vos profils locaux font partie des [paramètres exportés](../Usage/ExportImportSettings.md). Donc assurez vous d'avoir une sauvegarde dans un endroit sûr.

![Paramètres profil local](../images/LocalProfile_Settings.png)

Boutons :

* Plus vert : ajouter
* X rouge : supprimer
* Flèche bleue : dupliquer

Si vous apportez des modifications à votre profil, assurez-vous que vous éditez le profil correct. Dans l'onglet Profil, ce n'est pas toujours le profil actuellement utilisé qui est affiché. Par ex. si vous avez fait un changement de profil à partir du bouton de l'écran d'accueil, il peut être différent du profil affiché dans l'onglet Profil car il n'y a pas de connexion entre les deux.

#### Dupliquer un changement de profil

Vous pouvez facilement créer un profil local à partir d'un changement de profil. Dans ce cas, le décalage temporel et le pourcentage seront appliqués au nouveau profil local.

1. Cliquez sur le menu 3 points en haut à droite de l'écran d'accueil.
2. Sélectionnez 'Traitements'.
3. Cliquez sur l'icone en forme d'étoile pour accéder à la page de changement de profil.
4. Sélectionnez le changement de profil souhaité et appuyez sur "Dupliquer".
5. Vous pouvez éditer le nouveau profil local dans l'onglet Profil local (PL) ou via le menu hamburger.

![Dupliquer un changement de profil](../images/LocalProfile_ClonePS_AAPS30.png)

(Config-Builder-upload-local-profiles-to-nightscout)=

#### Remonter les profils locaux sur Nightscout

Les profils locaux peuvent également être téléchargés sur Nightscout. Les paramètres peuvent être trouvés dans [les préférences NSClient](Preferences-nsclient).

![Télécharger profil local sur NS](../images/LocalProfile_UploadNS_AASP30.png)

#### Changer de profil dans l'éditeur de profil Nighscout

Vous pouvez synchroniser les modifications du profil depuis l'éditeur de profil Nighscout vers les profils locaux. Les paramètres peuvent être trouvés dans [les préférences NSClient](Preferences-nsclient).

Il est nécessaire de cloner toute la base de données Nightscout active pour les profils, et pas seulement le profil avec la flèche bleue ! Les nouveaux enregistrements de la base de données portent ensuite la date courante et peuvent être activés via l'onglet "Profil local".

![Cloner les enregistrements de la base de données](../images/Nightscout_Profile_Editor.PNG)

### Assistant Profil

L'assistant profil a deux fonctions :

1. Trouver un profil pour les enfants
2. Comparer deux profils ou changements de profil pour cloner un nouveau profil

Les détails sont expliqués sur la [page d'aide des profils](../Configuration/profilehelper.md).

(Config-Builder-insulin)=

## Insuline

![Type d'insuline](../images/ConfBuild_Insulin_AAPS30.png)

* Sélectionnez le type de courbe d'insuline que vous utilisez.
* Les options 'Insuline à Action rapide Oref', 'Insuline à action Ultra Rapide Oref', 'Lyumjev' et 'Profil d'insuline ajustable Oref' ont toutes une forme exponentielle. Vous trouverez plus d'informations dans la [Documentation OpenAPS](https://openaps.readthedocs.io/en/latest/docs/While%20You%20Wait%20For%20Gear/understanding-insulin-on-board-calculations.html#understanding-the-new-iob-curves-based-on-exponential-activity-curves). 
* Les courbes varient en fonction de la DAI et le temps du pic.
    
    * La ligne ROSE montre la quantité **d'insuline restante** dans le corps après avoir été injectée car elle se dégrade avec le temps.
    * La ligne BLUE montre de **combien l'insuline est active**.

### DAI

* La DAI n'est pas la même pour chaque personne. C'est pourquoi vous devez la tester par vous-même. 
* Mais elle doit toujours être au minimum de 5 heures.
* Pour beaucoup de personnes utilisant des insulines ultra rapide comme la FIASP, il n'y a pratiquement pas d'effet notable après 3-4 heures tout au plus, même si 0.0 xx unités sont disponibles en tant que règle. Cette quantité résiduelle peut encore être perceptible pendant le sport, par exemple. Par conséquent, AndroidAPS utilise au moins 5h comme DAI.
* Vous pouvez en savoir plus à ce sujet dans la section Profil d'Insuline de [cette page](Screenshots-insulin-profile).

### Différences entre les types d'insuline

* Pour l'insuline à "Action Rapide", "Ultra-Rapide" et "Lyumjev", la DAI est la seule variable que vous pouvez ajuster vous-même, le temps du pic est fixé. 
* Le Profil d'insuline ajustable vous permet d'ajuster à la fois la DAI et le temps du pic, et ne doit être utilisé que par les utilisateurs confirmés qui connaissent les effets de ces paramètres. 
* Le [graphique de courbe d'insuline](Screenshots-insulin-profile) vous aide à comprendre les différentes courbes.
* Vous pouvez le voir en activant la case à cocher pour l'afficher sous forme d'onglet, sinon il se trouve dans le menu hamburger.

#### Insuline à Action Rapide Oref 

![Insuline à action rapide Oref](../images/ConfBuild_Insulin_RAO.png)

* recommandé pour Humalog, Novolog et Novorapid
* DAI = au moins 5.0h
* Pic maxi = 75 minutes après l'injection (fixe, non réglable)

#### Insuline Ultra Rapide Oref

![Insuline Ultra Rapide Oref](../images/ConfBuild_Insulin_URO.png)

* recommendé pour FIASP
* DAI = au moins 5.0h
* Pic maxi = 55 minutes après l'injection (fixe, non réglable)

(Config-Builder-lyumjev)=

#### Lyumjev

![Insuline Lyumjev](../images/ConfBuild_Insulin_L.png)

* profil d'insuline spécifique pour Lyumjev
* DAI = au moins 5.0h
* Pic maxi = 45 minutes après l'injection (fixe, non réglable)

#### Profil d'insuline ajustable Oref

![Insuline ajustable Oref](../images/ConfBuild_Insulin_FPO.png)

* Avec le "Profil d'insuline ajustable 0ref" vous pouvez entrer individuellement l'heure du pic. Pour cela, cliquez sur la roue crantée pour entrer dans les paramètres avancés.
* La DAI est automatiquement définie à 5 heures s'il n'est pas spécifié plus haut dans le profil.
* Ce profil est recommandé si une insuline non soutenue ou un mélange d'insulines différentes est utilisé.

(Config-Builder-bg-source)=

## Source GLY

Sélectionnez la source de glycémie que vous utilisez - consultez la page [Source Gly](BG-Source.md) pour plus d'informations sur la configuration.

![Générateur de Configuration Source de Glycémie](../images/ConfBuild_BGSource_AAPS30.png)

* [Construisez votre propre application Dexcom (BYODA)](https://docs.google.com/forms/d/e/1FAIpQLScD76G0Y-BlL4tZljaFkjlwuqhT83QlFM5v6ZEfO7gCU98iJQ/viewform?fbzx=2196386787609383750&fbclid=IwAR2aL8Cps1s6W8apUVK-gOqgGpA-McMPJj9Y8emf_P0-_gAsmJs6QwAY-o0).
* [xDrip+](https://xdrip-plus-updates.appspot.com/stable/xdrip-plus-latest.apk) est déconseillé comme récepteur pour Dexcom G6 depuis AAPS 3.0 (voir [Notes de version](Releasenotes-important-hints-3-0-0) pour plus de détails.
* [Medtronic 640g](https://github.com/pazaan/600SeriesAndroidUploader/releases)
* [Glimp](https://play.google.com/store/apps/details?id=it.ct.glicemia&hl=de) - seule la version 4.15.57 et plus récentes sont prise en charge
* [Poctech](https://www.poctechcorp.com/en/contents/268/5682.html)
* [Application Tomato](http://tomato.cool/) pour les transmetteurs MiaoMiao
* [Application Glunovo](https://infinovo.com/) pour le système MGC Glunovo
* Glycémie NSClient - non recommandé car la boucle fermée repose sur la couverture des données mobiles / wifi dans ce cas. Les données MGC ne seront reçues que s'il y a une connexion en ligne à votre site NS. Mieux vaut utiliser la diffusion locale de l'une des autres sources de données de la MGC.
* Gly Aléatoire : Génère des données de glycémie aléatoires (mode Démo uniquement)

(Config-Builder-pump)=

## Pompe

Sélectionner la pompe que vous utilisez.

![Sélection de la pompe dans le Générateur de configuration](../images/ConfBuild_Pump_AAPS30.png)

* [DanaR](DanaR-Insulin-Pump.md)
* DanaR coréenne (pour la pompe DanaR domestique)
* DanaRv2 (pompe DanaR avec mise à niveau du firmware non officiel)
* [Dana-i/RS](DanaRS-Insulin-Pump.md)
    
    * Pour les pompes Dana, utilisez **Paramètres avancés** pour activer le "Watchdog BT" si nécessaire. Il éteint le Bluetooth pendant une seconde si aucune connexion à la pompe n'est possible. Cela peut être utile sur certains téléphones où la puce bluetooth se bloque.
    * [Le mot de passe pour les pompes Dana RS](../Configuration/DanaRS-Insulin-Pump.md) doit être entré correctement. Le mot de passe n'était vérifié dans les versions précédentes.

* [Accu Chek Insight](Accu-Chek-Insight-Pump.md)

* [Accu Chek Combo](Accu-Chek-Combo-Pump.md) (nécessite l'installation de ruffy)
* [Omnipod Eros](OmnipodEros.md)
* [Omnipod Dash](OmnipodDASH.md)
* [Medtronic](MedtronicPump.md)
* [Diaconn G8](DiaconnG8.md)
* MIQ (Permet de recevoir des suggestions de AAPS pour des thérapies avec de Multiples Injection Quotidiennes)
* Pompe virtuelle (boucle ouverte pour les pompes qui n'ont pas encore de pilote - suggestions AAPS uniquement)

## Estimation de Sensibilité

Sélectionnez le type de calcul pour la sensibilité. Pour plus de détails sur la conception, veuillez [lire ceci](../Configuration/Sensitivity-detection-and-COB.md). Cela analysera les données historiques au fur et à mesure et fera des ajustements si elle détecte que vous réagissez de façon plus sensible (ou plus résistante) à l'insuline que d'habitude. Plus de détails sur l'algorithme de la Sensitibilité peuvent être lus dans la [documentation OpenAPS](https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/autosens.html).

Vous pouvez voir votre sensibilité sur l'écran d'accueil en sélectionnant Sensibilité dans les paramètres du graphique et en observant la ligne blanche. Remarque, vous devez être à l'[Objectif 8](Objectives-objective-8-adjust-basals-and-ratios-if-needed-and-then-enable-autosens) pour que la détection de sensibilité / [Autosens](Open-APS-features-autosens) ajuste automatiquement la quantité d'insuline délivrée. Avant d'atteindre cet objectif, le poucentage Autosens ainsi que la ligne dans votre graphique ne sont affichés que pour information.

(Config-Builder-absorption-settings)=

### Paramètres d’absorption

Si vous utilisez le type Oref1 avec les SMB, vous devez modifier **min_5m_carbimpact** à 8. La valeur n'est utilisée que pendant les lacunes dans les lectures de MGC ou lorsque l'activité physique "utilise" l'augmentation de la glycémie qui autrement aurai permis la décomposition des GA par AAPS. Parfois, lorsque l'[absorption de glucides](../Usage/COB-calculation.md) ne peut pas être déterminée de façon dynamique en fonction des glycémies, AAPS intègre une décomposition par défaut à vos glucides. De base, c'est une sécurité intégrée.

(Config-Builder-aps)=

## APS

Sélectionnez l'algorithme APS souhaité pour les ajustements de thérapie. Vous pouvez afficher le détail actif de l'algorithme choisi dans l'onglet OpenAPS (OAPS).

* OpenAPS AMA (Assistance Améliorée Repas, état de l'algorithme en 2017) En termes simples, les avantages sont après un bolus de repas le système peut faire une temporaire haute plus rapidement SI vous entrez les glucides de manière fiable.
* [OpenAPS SMB](../Usage/Open-APS-features.md) (Super Micro Bolus, l'algorithme le plus récent pour les utilisateurs avancés)  
    Notez que vous devez être à l'[Objectif 9](Objectives-objective-9-enabling-additional-oref1-features-for-daytime-use-such-as-super-micro-bolus-smb) pour utiliser OpenAPS SMB et min_5m_carbimpact doit être mis à 8 dans le Générateur de configuration > Sensitivity detection > Estimation de Sensibilité > paramètres Oref1.

## Boucle

* Basculer entre Boucle Ouverte, Boucle Fermée et Arrêt Glycémie Basse (AGB).

![Configuration - mode boucle](../images/ConfigBuilder_LoopLGS.png)

(Config-Builder-open-loop)=

### Boucle Ouverte

* AAPS évalue en permanence toutes les données disponibles (IA, GA, Gly ...) et fait des propositions de traitement pour ajuster votre thérapie si nécessaire. 
* Les suggestions ne seront pas exécutées automatiquement (comme dans la boucle fermée) doivent être entrées manuellement dans la pompe ou en utilisant un bouton si vous utiliserez une pompe compatible (Dana R/RS, Accu Chek Combo, Insight...). 
* Cette option permet de savoir comment AndroidAPS fonctionne ou si vous utilisez une pompe non prise en charge.

(Config-Builder-closed-loop)=

### Boucle Fermée

* AAPS évalue en permanence toutes les données disponibles (IA, GA, Gly ...) et ajuste automatiquement le traitement si nécessaire (c'est-à-dire sans intervention de votre part) pour atteindre la plage ou la valeur cible fixée (bolus, débit de basal temporaire, arrêt de l'insuline pour éviter l'hypo, etc.). 
* La boucle fermée fonctionne avec de nombreuses limites de sécurité, que vous pouvez définir individuellement.
* La boucle fermée n'est possible que si vous êtes à l'[Objectif 6](Objectives-objective-6-starting-to-close-the-loop-with-low-glucose-suspend) ou plus et si vous utilisez une pompe prise en charge.
* Remarque : En mode boucle fermée, une cible unique au lieu de la plage cible (par ex. 5,5 mmol ou 100 mg/dl au lieu de 5,0 - 7,0 mmol ou 90 - 125 mg/dl) est recommandée.

### Arrêt Glycémie Basse (AGB)

* maxIA est fixé à zéro
* Cela signifie que si le taux de glycémie chute, il peut réduire le débit de basal pour vous.
* Mais si la glycémie augmente, aucune correction automatique ne sera apportée. Vos débits de basal resteront les mêmes que votre profil sélectionné.
* Ce n'est que si l'insuline basale active est négative (à cause d'un arrêt glycémie basse antérieur), que de l'insuline additionnelle sera administrer pour faire baisser la glycémie.

### Changement minimum

* Lorsque vous utilisez le mode boucle ouverte, vous recevrez des notifications chaque fois que le programme AAPS vous recommande d'ajuster le débit de basal. 
* Pour réduire le nombre de notifications, vous pouvez utiliser une plage cible de glycémie plus étendue ou augmenter le pourcentage de changement minimal.
* Ce paramètre défini le changement relatif minimum qui déclenchera une notification.

## Objectifs (programme d'apprentissage)

AAPS a un programme d'apprentissage (objectifs) que vous devez réaliser étape par étape. Cela devrait vous guider en toute sécurité à travers la mise en place d'un système de boucle fermée. Ce programme d'apprentissage garantit que vous avez tout mis en place correctement et que vous comprenez ce que le système fait exactement. C'est la seule façon pour vous de faire confiance au système.

Vous devez [exporter régulièrement vos paramètres](../Usage/ExportImportSettings.md) (y compris la progression des objectifs). Au cas où vous devrez remplacer votre smartphone plus tard (nouvel achat, problème d'écran, etc.) vous pouvez simplement importer ces paramètres.

Voir la page [Objectifs](../Usage/Objectives.md) pour plus d'informations.

## Traitements

Si vous affichez les traitements, vous pouvez voir ceux qui ont été téléchargés dans Nightscout. Si vous voulez modifier ou supprimer une entrée (par ex. vous avez mangé moins de glucides que prévu), alors sélectionnez 'Supprimer' et entrez la nouvelle valeur (changes l'heure si nécessaire) via le [bouton Glucides de l'écran d'accueil](Screenshots-carb-correction).

## Généralités

### Aperçu

Affiche l'état en cours de votre boucle et les boutons de la plupart des actions courantes (voir la section [Ecran d'accueil](../Getting-Started/Screenshots.md) pour plus de détails). Vous pouvez accéder aux paramètres en cliquant sur la roue crantée.

#### Garder l'écran allumé

L'option 'Garder l'écran allumé' forcera Android à garder l'écran allumé en permanence. C'est utile par ex. pour des présentations, etc. Mais cela consomme beaucoup d'énergie. Par conséquent, il est recommandé dans ce cas de connecter le smartphone à un chargeur.

#### Boutons

Définissez quels boutons sont affichés sur l'écran d'accueil.

* Traitements
* Assistant
* Insuline
* Glucides
* MGC (ouvre xDrip+)
* Étalonnage

De plus, vous pouvez définir des raccourcis pour l'insuline et les incréments de glucides et décider si le champ de notes doit être affiché dans les boites de dialogues des traitements.

#### Assistant Rapide

Créez un bouton pour un repas standard (Glucides et méthode de calcul pour le bolus) qui sera affiché sur l'écran d'accueil. C'est à utiliser pour des repas standards souvent consommés. Si des heures différentes sont renseignées pour les différents repas, vous aurez toujours le bouton de repas standard approprié sur l'écran d'accueil, en fonction de l'heure de la journée.

Remarque : Le bouton ne sera pas visible si vous êtes en dehors de la plage de temps spécifiée ou si vous avez suffisamment d'IA pour couvrir les glucides définis dans le bouton d'assistant rapide.

![Bouton Assistant rapide](../images/ConfBuild_QuickWizard.png)

#### Cibles Temporaires par défaut

Choisissez les cibles temporaires par défaut (durée et cible). Les valeurs prédéfinies sont :

* Repas imminent : cible 72 mg/dl / 4,0 mmol/l, durée 45 min
* Activité : cible 140 mg/dl / 7,8 mmol/l, durée 90 min
* Hypo : cible 125 mg/dl / 6,9 mmol/l, durée 45 min

#### Insuline par défaut pour Amorcer/Remplir

Choisissez la quantité par défaut des trois boutons de la boite de dialogue Amorcer/Remplir, selon la longueur de votre cathéter.

#### Fourchette de visualisation

Choisissez les valeurs de glycémies hautes et basses du graphique principal sur l'écran d'accueil AAPS et la montre. Il ne s'agit que de la visualisation, pas de la plage cible de votre glycémie. Par exemple : 70 - 180 mg/dl ou 3,9 - 10 mmol/l

#### Raccourcir les titres des onglets

Choisissez si les titres des onglets dans AndroidAPS sont longs (ex: ACTIONS, PROFIL LOCAL, AUTOMATION) ou courts (ex: ACT, PL, AUTO)

#### Affiche les notes dans les dialogues

Choisissez si vous voulez avoir un champ Notes lors de la saisie des traitements ou non.

#### Voyants d'état

Choisissez si vous voulez avoir des [voyants d'état](Preferences-status-lights) sur l'écran d'accueil avec l'âge de la canule, l'âge du capteur, l'âge de la batterie, le niveau du réservoir ou de la batterie. Lorsque le seuil d'avertissement est atteint, la couleur du voyant d'état passe à jaune. Le seuil critique s'affichera en rouge.

#### Paramètres Avancés

**Injecter cette partie de Bolus calculée par l’assistant** : Avec l'utilisation des SMB, beaucoup de personnes ne font pas de bolus repas avec 100% de l'insuline nécessaire, mais seulement une partie de celle-ci (par ex. 75 %) et laissent les SMB avec les RNS (repas non signalés) faire le reste. Avec ce paramètre, vous pouvez choisir une valeur par défaut pour le pourcentage que l'assistant bolus doit prendre. Si ce paramètre est de 75 % et que vous avez besoin d'un de bolus 10U, l'assistant de bolus proposera un bolus repas de seulement 7,5 unités.

**Activer la fonction super bolus dans l'Assistant** (c'est différent des *super micro bolus* !) : à utiliser avec prudence et ne l'activez pas tans que vous n'avez pas appris ce qu'il fait vraiment. En gros, l'insuline correspondant au débit de basal des deux heures suivantes est ajoutée au bolus et deux heures de zéro-temp sont activées. **Les fonctions de boucle AAPS seront désactivées - c'est donc à utiliser avec prudence ! Si vous utilisez OpenAPS SMB, les fonctions de la boucle seront désactivées selon le paramètre ["Max. minutes de basal pour limiter le SMB"](Open-APS-features-max-minutes-of-basal-to-limit-smb-to), si vous n'utilisez pas les SMB les fonctions de la boucle seront désactivées pendant deux heures.** Plus de détails sur le super bolus peuvent être trouvés [ici](https://www.diabetesnet.com/diabetes-technology/blue-skying/super-bolus).

(Config-Builder-actions)=

### Actions

* Quelques boutons pour accéder rapidement aux fonctions communes.
* Voir les [captures d'écran AAPS](Screenshots-action-tab) pour plus de détails.

### Automatisation

Tâches d'automatisation définies par l'utilisateur (si-alors-sinon). Veuillez [lire ici](../Usage/Automation.md).

(Config-Builder-sms-communicator)=

### Communicateur SMS

Permet aux aidants à distance de contrôler certaines fonctionnalités d'AAPS via SMS, voir [Commandes SMS](../Children/SMS-Commands.md) pour plus d'informations sur la configuration.

### Aliments

Affiche les préréglages alimentaires définis dans la base de données Nightscout, voir [Nightscout Lisez-moi](https://github.com/nightscout/cgm-remote-monitor#food-custom-foods) pour plus d'informations sur la configuration.

Remarque : Les entrées ne peuvent pas être utilisées dans la calculatrice AAPS. (Affichage uniquement)

(Config-Builder-wear)=

### Wear

Contrôler et contrôler AAPS à l'aide de votre montre Android Wear (voir la page [AAPS sur montres Wear OS](../Configuration/Watchfaces.md)). Utilisez les paramètres (roue crantée) pour définir quelles variables doivent être prises en compte lors du calcul du bolus donné par votre montre (par ex. tendance de 15min, GA...).

Si vous voulez commander AAPS depuis la montre (bolus etc) alors dans les "Paramètres Wear" vous devez activer "Commandes depuis la montre".

![Paramètres Wear](../images/ConfBuild_Wear.png)

Via l'onglet Wear ou le menu hamburger (en haut à gauche de l'écran, si l'onglet n'est pas affiché), vous pouvez

* Renvoyer toutes les données. Cela peut être utile si la montre n'est pas connectée pendant un certain temps et que vous voulez envoyer toutes les informations à la montre.
* Ouvrez le menu Paramètres de votre montre directement depuis votre téléphone.

### Barre d'état pour xDrip (Montre)

Affiche les informations de la boucle sur votre cadran xDrip+ (si vous n'utilisez pas les cadrans AAPS/[cadran AAPSv2](../Configuration/Watchfaces.md)

### NSClient

* Configurer la synchronisation de vos données AndroidAPS avec Nightscout.
* Les paramètres dans les [préferences](Preferences-nsclient) peuvent être ouverts en cliquant sur la roue crantée.

### Maintenance

E-mail et le nombre de journaux à envoyer. Normalement pas de changement nécessaire.

### Générateur de configuration

Utilisez l'onglet pour le générateur de configuration au lieu du menu hamburger.