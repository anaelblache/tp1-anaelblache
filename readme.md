# TP 1 - Installation d’Ubuntu Server et prise en main du shell
## EXERCICE 1
**Installation de Ubuntu Server** (voir TP)
## EXERCICE 2
### Manuel
**1.** La commande **which** permet de localiser une commande dans l'arborescance.
Par exemple : **which man** retourne **/usr/bin/man**
**2.** Une fois le fichier ouvert, appuie sur **/** puis on entre le mot recherché.
**3.** Pour quitter le manuel on a juste a appuyer sur **q**.
**4.** On utilise la commande **man 6 which** qui affiche la sixième section. Dans ce cas elle n'existe pas.
### Navigation dans l’arborescence des fichiers
**1.** Pour se déplacer on utilise **cd /var/log**.
**2.** Puis pour se déplacer dans le dossier parent, on utilise **cd . .** (. . étant un chemin relatif).
**3.** On utilise ensuite **cd** pour aller dans le dossier personnel.
**4.** Pour retourner dans le dossier ou l'on était précédamment on utilise **cd -**.
**5.** On ne peut accéder au fichiers root car nous n'avons pas les droits.
**6.** On peut pas utiliser **sudo** car sudo ne peut pas utiliser sudo pour **cd**.
**7.** Pour créer cette arborescance, on utilise les commandes :
**cd**
**mkdir Dossier1**
**touch Dossier1/Fichier1**
**mkdir Dossier2**
**mkdir Dossier2/Dossier2.1**
**mkdir Dossier2/Dossier2.2**
**touch mkdir Dossier2/Dossier2.1/Fichier2**
**touch mkdir Dossier2/Dossier2.1/Fichier3**
**8.** Avec **rm Dossier1/Fichier1** on supprime le Fichier1, avec **rmdir Dossier1** on supprime le Dossier1. On utilise une commande différente pusique Fichier1 est un fichier et Dossier1 est un dossier.
**9.** Avec la commande **rmdir [Dossier]**
**10.** On ne peut pas car le dossier n'est pas vide.
**11.** On utilise la commande **rm -r**
### Commandes importantes
**1.** Pour afficher l'heure on utililse la commande **date**. La commande **time** va permettre de chronométrer le déroulement d'une commande.
**2.** On remarque que avec **ls** rien ne s'affiche et avec **la** des fichiers commençant par un point s'affichent. Les fichiers commençant par un point sont des fichiers cachés.
**3.** Avec la commande **which ls**, on voit que la commande se situe dans **/usr/bin/ls**
**4.** La commande **ll** affiche de manière détaillé le contenu du répertoire. C'est enfaite un alias de la commande **ls** utilisant les options **-alF**, donc elle n'a pas d'entrée de manuel.
**5.** La commande **ls /bin** affiche le contenu du répertoire **/bin**.
**6.** La commande **ls . .** affiche le contenu du répertoire parent.
**7.** C'est la commande **pwd**.
**8.** Cela créer un fichier nommé **plop** dans lequel est écrit **yo**.
**9.** Cela créer un fichier nommé **plop** dans lequel **yo** est écrit deux fois.
**10.** L'ordinateur va attendre **10** secondes puis affihcer **toto** dans le terminal.
**11.** La commande **file [fichier]** va donner des informations sur le type d'un fichier.
**12.** Pour faire, on utilise les commandes :
**touch toto**
**echo Hello Toto ! > toto**
**ln toto titi**
**echo Goodbye Titi ! > toto**
**cat titi**
(La commande cat retourne **Goodbye Titi !**)
**rm toto**
**cat titi**
(La commande cat retourne **Goodbye Titi !**)
On voit donc que malgrés la supression le texte de **toto** est toujours dans **titi**
**13.** Pour faire on utilise les commandes :
**ln -s titi tutu**
**echo Farewell Tutu ! > titi**
**cat tutu**
(La commande cat retourne **Farewell Tutu !**)
**rm titi**
**cat tutu**
(La commande cat retourne qu'elle ne trouche pas tutu)
On voit que l'arguement **-s** lors de la création du lien a changé le comportement du lien en cas de supression de la cible.
**14.** On utilise **CTRL+S** pour stopper et **CTRL+Q** pour repprendre.
**15.** On utilises la commande **head -5 /var/log/syslog** pour les cinq premières, **tail -15 /var/log/syslog** pour les quinze dernières et **awk "NR >= 10 && NR <= 20 " /var/log/syslog**.
**16.** La commadne ouvre la mémoire tampon du noyau avec **less**.
**17.** Il affiche différentes informations sur les utilisateurs du PC. Pour voir la page de manuel on  utilise la commande **man passwd**.
**18.** Pour ceci on utilise la commande **cut -d: -f1 /etc/passwd | sort -rd**.
**19.** On utilise la commande : **cat /etc/passwd | wc -l**, elle retourne 33. Il y a donc 33 utilisateurs.
**20.** On utilises la commande **man -k conversion**.
**21.** On retourne à la racine et on utilise la commande **sudo find -name passwd**.
**22.** A partir de la commande précédente on créer la commande : **sudo find -name passwd > ~/list_passwd_files.txt & sudo find -name passwd 2> /dev/null**.
**23.** On utilise la commande **grep -r "alias ll"**, et la console retourne des parties d'un fichier à propos de cette alias.
**24.** On utilise **locate history.log** pour retrouver le chemin, c'est à dire : **/var/log/apt/history.log**.
**25.** Si on créer un fichier **touch discret** puis qu'on le recherche avec **locate discret**, il ne sera pas trouvé car **locate** utilise une base de données qui n'a pas intégrer le ficher que l'on vient de créer. Si on utilise la commande **sudo updatedb** on met à jour la base de données et on peut trouver le fichier avec **locate**.
## Exercice 3
**Découverte de l’éditeur de texte nano** (voir TP)
## Exercice 4
**3.** En utilisant la commande **source .bashrc**, on peut voir le style du terminal changer.
**4.** Pour obtenir la forme demandé il faut écrire : **PS1='{$ debian_chroot:+($ debian_chroot)}\[\033[91m\][\A]\[\033[00m\] - \[\033[01;32m\]\u@\h\[\033[00m\\]:\[\033[36m\]\w\[\033[00m\]\$ '**
