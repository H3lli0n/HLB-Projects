Ce projet est open-source, tous les fichiers nécessaires pour commander un lot de PCB-A sont gratuits et libres d'utilisation. Ce projet est également sponsorisé par PCBWay.

PCBWay est un service en ligne de fabrication de PCB/PCB-A (PCB avec assemblage, ce qui signifie que tous les composants sont soudés).

Si vous avez besoin de leurs services, n'hésitez pas à utiliser le lien suivant pour soutenir l'équipe ! https://pcbway.com/g/4Gd3AJ
![PCBWay](PCBWay-logo-new.png)

# Description
- 40% ANSI / ISO
  - Hotswap *HLB40-H*
    - STM32F MCU
    - Indicateur de Verrouillage Majuscule / Couches (Capslock/Layers)
  - EC (Électro-Capacitif) *HLB40-EC*
    - STM32F MCU
- Rangée inférieure (Bottom row)
  - 6U
  - 2.75U/1U/2.25U
- QMK / VIAL firware
  - Gestion du RGB sous mon userspace (HLB40-H)

# Layout

# Fichiers
## HLB40-H
*Les fichiers seront disponibles une fois testés*
## HLB40-EC
*Les fichiers seront disponibles une fois testés*

# Comment commander
Commander un PCB via PCBWay est simple, mais certaines étapes peuvent être déroutantes. Nous allons donc vous guider tout au long du processus.

## Fichiers nécessaires
Une fois la version du PCB souhaitée téléchargée, décompressez l'archive dans un dossier. Vous devez y trouver les fichiers suivants :
![Files](tuto/001.png)
- *hlb40_h.kicad_pcb_gerber.zip*: le fichier principal contenant toutes les données du PCB, les couches, les pistes... Tout ce dont le service a besoin pour remplir le formulaire de données.
- *hlb40_h.kicad_pcb_bom.csv*: la liste de tous les composants à assembler sur le PCB. Chaque composant est identifié par un code et le service sait exactement quoi commander.
- *hlb40_h.kicad_pcb_positions.csv*: les positions de chaque composant sur le PCB pour l'assemblage.

### Couleurs des sockets Hotswap
Les sockets Hotswap de la marque Kailh sont parfois difficiles à trouver chez les prestataires en ligne. Nous sommes contraints d'utiliser une marque générique, mais après de nombreux tests, ils s'avèrent tout à fait fiables. Ils sont disponibles en 3 couleurs (blanc/noir/violet) et le stock global dépend également du contexte économique mondial.
Dans le fichier BOM (.csv) que vous pouvez ouvrir avec le bloc-notes, vous les trouverez avec la mention `Value = Keyswitch`.

Regardez la colonne `LCSC` et vous trouverez un code que vous pouvez modifier en fonction de la couleur souhaitée et des stocks disponibles :
- Violet = C41430893
- Blanc = C49352235
- Noir (Kailh) = C5156480

## Création d'un compte PCBWay
L'étape suivante consiste à créer un compte sur PCBWay en utilisant notre lien affilié : https://pcbway.com/g/4Gd3AJ. Une fois votre compte créé, vous recevrez plus tard un coupon de réduction de 5 $.

## Demande de devis
Il est maintenant temps de commander en téléversant tous les fichiers et en sélectionnant les bonnes options. L'un des facteurs clés du prix final est la quantité : plus vous commandez, moins vous payez à l'unité.
Pour cet exemple, nous allons commander 5 PCB (la carte brute avec ses couches de cuivre) et demander l'assemblage de ces 5 cartes (les composants soudés sur le PCB).

### Menu de devis du PCB (PCB Quote)
Avant de passer à l'assemblage, nous devons obtenir le devis pour le PCB lui-même. Pour ce faire, cliquez sur *PCB Instant Quote*.

![Step1](tuto/002.jpg)
And *Quick Order*

![Step2](tuto/003.jpg)

C'est ici que vous pouvez téléverser le fichier Gerber de notre archive (comme mentionné précédemment).
Notre PCB est composé de 4 couches, vous devez donc spécifier leur ordre :
- L1 : F.Cu
- L2 : In1.Cu
- L3 : In2.Cu
- L4 : B.Cu
![Step3](tuto/004.jpg)

Vous pouvez même jeter un œil à l'aperçu du PCB grâce à leur outil de visualisation en ligne *Gerber Online Viewer*.
![Step4](tuto/005.jpg)

### Options de commande
#### Quantité
Nous devons maintenant vérifier les options et modifier certains éléments. Comme décrit plus haut, le prix final de la commande dépend fortement de la quantité, car la fabrication de quelques pièces nécessite le même effort technique que pour un grand lot. Ce coût humain est divisé par le nombre d'articles achetés.

![Step5](tuto/006.jpg)
![Step5b](tuto/006b.jpg)

N'hésitez pas à passer une annonce sur notre Discord, vous trouverez peut-être des personnes intéressées pour se joindre à la commande et partager les frais.
Sachez également que même si cela peut sembler onéreux, les services de PCBWay effectuent de nombreuses vérifications sur la commande pour éviter les erreurs.

#### Esthétique du PCB
Notre PCB a une épaisseur de 1,6 mm et vous pouvez personnaliser sa couleur grâce à l'option *Solder mask* (Vernis d'épargne). Ici, nous sélectionnons le rouge (on va taper plus vite, c'est sûr !).
![Step6](tuto/007.jpg)

#### Option de soudure
Puisque nous vivons en Europe et que nous sommes "respectueux de l'environnement", merci d'éviter le plomb qui est désormais interdit sur notre continent.
Prenez soin de sélectionner *HASL lead free* (sans plomb), ce qui signifie que la soudure est réalisée à base de pâte d'argent.
![Step7](tuto/008.jpg)

Note : pour les PCB à souder (non hotswap), il est préférable de sélectionner l'option basée sur l'ENIG pour avoir des pads de switches plus résistants.

Par défaut, un numéro de série sera imprimé sur le PCB. Vous pouvez supprimer cette impression avec l'option ci-dessous.
![Step8](tuto/009.jpg)

#### Assemblage (Assembly)
Nous activons maintenant la partie assemblage de la commande. Avec cette étape, chaque composant électronique sera commandé et soudé. Cette étape est obligatoire.
![Step9](tuto/010.jpg)
Il vous suffit de cocher *Bottom side*, ce qui signifie que tous nos composants seront soudés sur la face arrière.

#### Options personnalisées (Custom options)
Cette option n'est pas essentielle, mais elle permettra de gagner de la place dans la boîte et d'éviter de devoir découper vous-même les panneaux de routage (panels) nécessaires au glissement des PCB dans les machines. Cette option n'ajoute pas grand-chose au coût final.
![Step10](tuto/011.jpg)

Une fois terminé, il vous suffit de cliquer sur *Save to Cart* (Ajouter au panier).
![Step11](tuto/012.jpg)

### Panier (Cart)
Nous y sommes presque, avec deux commandes distinctes dans notre panier : une pour la fabrication du PCB et une pour l'assemblage.

![Step12](tuto/013.jpg)

Comme vous pouvez le voir, nous avons des fichiers à téléverser pour l'assemblage, à savoir les deux fichiers `.csv` restants décrits plus tôt.
L'un pour les positions (cliquez sur *Upload Centroid file* dans le formulaire) et l'autre pour la liste des composants (*Parts Lists (BOM) upload*).

![Step13](tuto/014.jpg)

Et voilà, c'est fait ! Vous pouvez valider votre panier, qui va maintenant être vérifié par l'équipe.

![Step14](tuto/015.jpg)

Vous n'avez plus aucune démarche à faire, votre contact commercial ainsi que toute l'équipe de PCBWay prendront en charge vos fichiers et souderont tout aux bonnes positions. Cela est rendu possible grâce aux empreintes (footprints) utilisées et à tous les repères obligatoires présents sur le PCB.