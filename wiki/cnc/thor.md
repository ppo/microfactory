# CNC – Thor


## 💾 Resources

### Post-processeur

Fichier de configuration: [download](assets/cnc-thor.post-processor.v40867.cps)

* Vendor: [RepRap](http://reprap.org)
* Revision: 40867 (2015-10-14 17:29:32)
  * ❓ _New revision available: 43731 (2022-03-31 22:03:56)_


## 💰 Coûts

* 24€/heure, ❓facturé à la minute d'usinage.
  * À payer via le site: [Boutique › MF Utilisation CNC /15’](https://www.microfactory.be/shop/mf-utilisation-cnc-15-247)
* Martyr: MDF 4 ou 6mm
  * Soit on utilise le sien.
  * S'il y a un défoncé sans nom de dessus, on peut l'utiliser.
  * Soit on en prend un neuf (4mm). Voir panneau d'affichage à côté.
    * À payer via ❓.


## 📝 Procédures

### Procédure générale

1. **Allumer la CNC:**
   1. Allumer la CNC avec l'interrupteur principal.
   2. Attendre que la CNC démarre.
   3. (Message d'alerte, juste cliquer sur OK.)
2. **Vérifications préalables:**
   1. Vérifier le taux de remplissage de l'aspirateur. Voir ci-dessous.
   2. Le spindle est censé être rangé au loin à gauche.
3. **Délimitation de la zone de vide:**
   1. Objectif: Délimiter une zone fermée pour créer une zone étanche où un vide sera créé.
   2. Les bandes en caoutchouc se trouvent dans le tiroir supérieur gauche.
   3. La pièce doit être placée sur et le plus près du trou unique d'aspiration.
   4. Placer les bandes pour délimiter une zone un peu plus petite que la pièce.
   5. S'assurer que les bandes soient bien enfoncées dans le quadrillage.
4. **Test d'aspiration de la pièce:**
   1. Placer le martyr.
   2. Placer la pièce à usiner.
   3. Allumer la pompe à vide.
   4. Tester si la pièce tient bien.
   5. Éteindre la pompe à vide.
5. **Initialiser la CNC:**
   1. Désactiver l'arrêt d'urgence.
   2. Allumer le moteur XY.
   3. Home (cf. cadre vert sur la photo)\
      _(Le spindle monte puis redescend un peu. Le chariot se rapproche au max. Le spindle va à droite au max puis à gauche au max.)_
6. **Installation de la fraise:**
   1. Déplacer le spindle vers le centre (`X+`) afin de pouvoir y accéder facilement.
   2. Monter le spindle au maximum (`Z-`).
   3. Prendre l'écrou et le bon collet en fonction de la fraise à utiliser (cf. diamètre).
   4. Bien les nettoyer (en le tapotant ou avec la soufflette).
   5. Enclencher le collet dans l'écrou. {❓ truc cf. la demi-partie surélevée}
   6. Viser légèrement l'écrou sur le spindle.
   7. Placer la fraise dans le collet. {❓ Pourquoi ne pas mettre la fraise dans le collet avant de le placer dans l'écrou, et ensuite placer le tout sur le spindle?}
   8. Serrer l'écrou:
      1. D'abord au maximum à la main.
      2. Placer la clé plate sur le spindle (en haut).
      3. Placer la clé anglais sur l'écrou (en bas).
      4. Serrer en poussant les 2 clés (au loin, `Y+`). Bien serrer mais sans forcer.
   9. Faire tourner le spindle.
   10. Vérifier que la fraise tourne bien droit.
   11. Arrêter le spindle.
7. **Définition du `Z0`:**
   1. Conseil: Toujours faire le `Z0` au niveau du martyr (et pas sur la pièce) => pas de risque que la fraise plonge plus bas que ça. Attention à être cohérent en plaçant correctement l'origine dans le fichier Fusion 360/G code.
   2. Méthode 1, "capteur":
      1. Prendre le capteur qui se trouve à droite du panneau de contrôle.
      2. Attacher la pince crocodile sur la fraise.
      3. Placer la capteur sur le martyr, dans un premier temps à côté de la fraise.
      4. Descendre la fraise (`Z+`) jusque un peu plus haut que la hauteur du capteur.\
         ⚠️ _Sans mettre le capteur en-dessous pour ne pas risquer de l'abîmer._
      5. Placer le capteur en-dessous de la fraise.
      6. Allumer la pompe à vide (afin que tout soit bien en position réelle).
      7. Cliquer sur le bouton `Work Position/Measure Height` (voir tour du propriétaire › logiciel: 8e bouton en partant du haut, ou 3e du bas, dans le menu à gauche).
      8. Attendre que la fraise entre en contact avec le capteur et remonte.
      9. Éteindre la pompe à vide.
      10. Détacher la pince crocodile.
      11. Ranger le capteur.
   3. Méthode 2, "manuelle":
      1. Activer le spindle.
      2. Descendre manuellement (`Z+`, ensuite avec `Step`) jusqu'à entrer légèrement dans le martyr (⚠️ le spindle doit tourner afin d'entrer dans le martyr, ne pas faire le `Z0` en éffleurant le martyr avec la fraise qui ne tourne pas).
      3. Cliquer sur le `Z` à gauche des coordonnées.
8. **Placement de la pièce:**
   1. Déplacer la fraise afin qu'elle ne gêne pas.
   2. Placer la pièce en position de travail.
   3. Allumer la pompe à vide.
   4. Vérifier qu'elle tient bien.
9. **Définition du `XY0`:**
   1. Positionner le fraise en hauteur (`Z+/-`, ensuite avec `Step`) un peu au-dessus de la pièce (1cm).
   2. Positionner la fraise à l'origine XY (`X+/-` et `Y+/-`, ensuite avec `Step`). ⚠️ La référence est le centre de la fraise.
   3. Cliquer le bouton "Work Position/Axis To Zero/XY" (voir tour du propriétaire › logiciel: 6e bouton en partant du haut, ou 5e du bas, dans le menu à gauche). Ou sur le `X` et le `Y` à gauche des coordonnées.
10. **Fixation de la brosse d'aspiration:**
   1. TODO
11. **Chargement du job:**
    1. Insérer sa clé USB (à droite de la machine).
    2. Cliquer sur le bouton "Open…" (voir tour du propriétaire › logiciel: 1er bouton à gauche dans le menu horizontal).
    3. Sélectionner le fichier du job.
    4. Régler le zoom pour voir la table et son job.
    5. S'assurer que le job a l'air bien positionné sur la table.
    6. Vérifier que la vitesse d'avance est bien à 100%.
12. **Dernières vérifications:**
    1. Home?
    2. XY0?
    3. Fraise?
    4. Brosse?
    5. Pompe à vide?
    6. Vitesse d'avance à 100%?
13. **Exécution du job:**
    1. Allumer l'aspiration.
    2. Activer le spindle (⚠️ Le spindle ne s'allume pas automatiquement quand on lance le job, il faut le faire manuellement avant).
    3. Régler la vitesse de rotation du spindle (par incrément de 2400rpm => 1=2400rmp, 2=4800, …).
    4. Cliquer sur `play` pour exéuter le job.
    5. Rester près du bouton d'arrêt d'urgence le temps de s'assurer que le job fonctionne correctement.
14. **Terminaison du job:**
    1. Cliquer sur stop (car le job se met en pause à la fin)
    2. Désactiver le spindle. {TODO: Appuyer le bouton "stop" du spindle… mais pour l'instant il est cassé.}
    3. Éteindre la pompe à vide.
    4. Éteindre l'aspiration.
    5. Positionner le spindle hors des pièces.
    6. Enlever les pièces.
    7. Jeter les chutes dans le bac à chutes.
15. **Rangment:**
    1. Positionner le spindle pour détacher la fraise (`Z-` au max, `XY` à un endroit accessible, au-dessus de la table au cas où la fraise tombe en la détachant).
    2. Démonter la fraise (cf. installation de la fraise mais en sens inverse).
    3. Nettoyer le collet et l'écrou (en les tapotant et/ou en utilisant la souflette).
    4. Ranger le collet, l'écrou et les clés.
    5. Ranger le spindle au loin à gauche, à hauteur max (`X-`, `Y+` et `Z-` au max).
    6. Ranger le martyr.
    7. Ranger les bandes caoutchouc dans le tiroir.
    8. (Laisser la table de CNC vide en partant.)
16. **Nettoyage:**
    1. Passer la soufflette sur toute la machine (chariot et table).
    2. Balayer par terre, ramasser et jeter dans le bac à chute.
17. **Quitter les lieux:**
    1. N'éteindre la CNC que si personne ne va l'utiliser dans la journée/les ?X? heures à venir. Pour l'éteindre:
       1. Activer le bouton d'arrêt d'urgence.
       2. Éteindre la CNC avec l'interrupteur principal.
    2. Éteindre la lumière.

#### Remarques

* Lorsque les coordonnées XYZ sont en orange, on peut modifier la vitesse en court de route.
  * Toujours mettre initialement à 100% (cf. 1er bouton).
  * Les 2 autres boutons permettent de ralentir ou accélérer (par 10%).
* Ne pas toucher aux boutons sur le chariot de la CNC.
* **⚠️ Débutants:**
  * Ne jamais descendre directement dans la matière {Pourquoi?}. Soit faire une rampe, soit commencer en-dehors de la pièce (afin que le spindle ait le temps d'arriver à la bonne vitesse d'avance).
  * Ne pas commencer avec le cache d'aspiration car on ne voit pas la fraise et donc ce qui se passe.

#### Cas particuliers

* Arrêt prématuré du job: TODO
* Mise en pause du job: uniquement quand la fraise est en dehors de la matière. Éventuellement, si elle est dans la matière, mettre la vitesse de rotation du spindle sur 0.

### Procédure sac aspirateur

Vider le sac s'il est rempli à plus de 3/4.

1. Détacher la buse… TODO
2. Détacher le sac… TODO
3. Aller le vider dans le container dehors.
4. Vérifier que le sac n'est pas troué. Si oui:
   1. Nettoyer la surface autour du trou… TODO
   2. Coller du papier collant… TODO
5. Attacher le sac… TODO
6. Attacher la buse… TODO


## 🛺 Visite guidée

### Local

1. Portes
2. Lumière
3. Outils
4. Armoire

### CNC

1. Chariot
2. Spindle
3. Brosse
4. Table et "gaufrier"
5. Trou d'aspiration
6. T-tracks

### Panneau de contrôle

1. Rouge: Interrupteur principal
2. Bleu: Interrupteur du spindle
3. Jaune: Interrupteur du moteur XY
4. Vert: Home
5. Bouton d'arrêt d'urgence
6. Boutons XY (+ = droite/éloigner, - = gauche/rapprocher)
7. Boutons Z (+ = descendre, - = monter)
8. Bouton step

### Pompe à vide

1. Moteur
2. Interrupteur

### Aspirateur

1. Interrupteur
2. Brosse
3. Conduits
4. Moteur
5. Sac


## ⚙️ Spécifications techniques

### Panneau de contrôle

* Hardware: Raspberry Pi
* Système d'exploitation: [Raspbian](https://www.raspbian.org/)
* Logiciel CNC: [PlanetCNC](https://planet-cnc.com/)

### Spindle

* ❓

{% hint style="info" %}
[_Old Wiki_](https://deprecated.microfactory.be/wiki/index.php?title=CNC\_Router\_-\_Thor)
{% endhint %}
