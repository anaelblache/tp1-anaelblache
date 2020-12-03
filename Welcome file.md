# TP 1 - Installation d’Ubuntu Server et prise en main du shell

## EXERCICE 2
### Manuel
**1.** La commande **which** permet de localiser une commande dans l'arborescance.
Par exemple : **which man** retourne **/usr/bin/man**
**2.** 
**3.** Pour quitter le manuel on a juste a appuyer sur **q**.
**4.**
### Navigation dans l’arborescence des fichiers
**1.** Pour se déplacer on utilise **cd /var/log**.
**2.** Puis pour se déplacer dans le dossier parent, on utilise **cd . .** (. . étant un chemin relatif).
**3.** On utilise ensuite **cd** pour aller dans le dossier personnel.
**4.** Pour retourner dans le dossier ou l'on était précédamment on utilise **cd -**.
**5.** On ne peut accéder au fichiers root car nous n'avons pas les droits.
**6.**
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
**13.**
Pour faire on utilise les commandes :
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
**17.** Il affiche différentes informations sur les utilisateurs du PC. Pour voir la page de manuel on  utilise la commande **man passwd**
**18.** Pour ceci on utilise la commande **cut -d: -f1 /etc/passwd | sort -rd**
**19.** On utilise la commande : **cat /etc/passwd | wc -l**, elle retourne 33. Il y a donc 33 utilisateurs.
**20.** On utilises la commande **man -k conversion**
**21.** 



# Files

StackEdit stores your files in your browser, which means all your files are automatically saved locally and are accessible **offline!**

## Create files and folders

The file explorer is accessible using the button in left corner of the navigation bar. You can create a new file by clicking the **New file** button in the file explorer. You can also create folders by clicking the **New folder** button.

## Switch to another file

All your files and folders are presented as a tree in the file explorer. You can switch from one to another by clicking a file in the tree.

## Rename a file

You can rename the current file by clicking the file name in the navigation bar or by clicking the **Rename** button in the file explorer.

## Delete a file

You can delete the current file by clicking the **Remove** button in the file explorer. The file will be moved into the **Trash** folder and automatically deleted after 7 days of inactivity.

## Export a file

You can export the current file by clicking **Export to disk** in the menu. You can choose to export the file as plain Markdown, as HTML using a Handlebars template or as a PDF.


# Synchronization

Synchronization is one of the biggest features of StackEdit. It enables you to synchronize any file in your workspace with other files stored in your **Google Drive**, your **Dropbox** and your **GitHub** accounts. This allows you to keep writing on other devices, collaborate with people you share the file with, integrate easily into your workflow... The synchronization mechanism takes place every minute in the background, downloading, merging, and uploading file modifications.

There are two types of synchronization and they can complement each other:

- The workspace synchronization will sync all your files, folders and settings automatically. This will allow you to fetch your workspace on any other device.
	> To start syncing your workspace, just sign in with Google in the menu.

- The file synchronization will keep one file of the workspace synced with one or multiple files in **Google Drive**, **Dropbox** or **GitHub**.
	> Before starting to sync files, you must link an account in the **Synchronize** sub-menu.

## Open a file

You can open a file from **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronize** sub-menu and clicking **Open from**. Once opened in the workspace, any modification in the file will be automatically synced.

## Save a file

You can save any file of the workspace to **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronize** sub-menu and clicking **Save on**. Even if a file in the workspace is already synced, you can save it to another location. StackEdit can sync one file with multiple locations and accounts.

## Synchronize a file

Once your file is linked to a synchronized location, StackEdit will periodically synchronize it by downloading/uploading any modification. A merge will be performed if necessary and conflicts will be resolved.

If you just have modified your file and you want to force syncing, click the **Synchronize now** button in the navigation bar.

> **Note:** The **Synchronize now** button is disabled if you have no file to synchronize.

## Manage file synchronization

Since one file can be synced with multiple locations, you can list and manage synchronized locations by clicking **File synchronization** in the **Synchronize** sub-menu. This allows you to list and remove synchronized locations that are linked to your file.


# Publication

Publishing in StackEdit makes it simple for you to publish online your files. Once you're happy with a file, you can publish it to different hosting platforms like **Blogger**, **Dropbox**, **Gist**, **GitHub**, **Google Drive**, **WordPress** and **Zendesk**. With [Handlebars templates](http://handlebarsjs.com/), you have full control over what you export.

> Before starting to publish, you must link an account in the **Publish** sub-menu.

## Publish a File

You can publish your file by opening the **Publish** sub-menu and by clicking **Publish to**. For some locations, you can choose between the following formats:

- Markdown: publish the Markdown text on a website that can interpret it (**GitHub** for instance),
- HTML: publish the file converted to HTML via a Handlebars template (on a blog for example).

## Update a publication

After publishing, StackEdit keeps your file linked to that publication which makes it easy for you to re-publish it. Once you have modified your file and you want to update your publication, click on the **Publish now** button in the navigation bar.

> **Note:** The **Publish now** button is disabled if your file has not been published yet.

## Manage file publication

Since one file can be published to multiple locations, you can list and manage publish locations by clicking **File publication** in the **Publish** sub-menu. This allows you to list and remove publication locations that are linked to your file.


# Markdown extensions

StackEdit extends the standard Markdown syntax by adding extra **Markdown extensions**, providing you with some nice features.

> **ProTip:** You can disable any **Markdown extension** in the **File properties** dialog.


## SmartyPants

SmartyPants converts ASCII punctuation characters into "smart" typographic punctuation HTML entities. For example:

|                |ASCII                          |HTML                         |
|----------------|-------------------------------|-----------------------------|
|Single backticks|`'Isn't this fun?'`            |'Isn't this fun?'            |
|Quotes          |`"Isn't this fun?"`            |"Isn't this fun?"            |
|Dashes          |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|


## KaTeX

You can render LaTeX mathematical expressions using [KaTeX](https://khan.github.io/KaTeX/):

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$

> You can find more information about **LaTeX** mathematical expressions [here](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).


## UML diagrams

You can render UML diagrams using [Mermaid](https://mermaidjs.github.io/). For example, this will produce a sequence diagram:

```mermaid
sequenceDiagram
Alice ->> Bob: Hello Bob, how are you?
Bob-->>John: How about you John?
Bob--x Alice: I am good thanks!
Bob-x John: I am good thanks!
Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

Bob-->Alice: Checking with John...
Alice->John: Yes... John, how are you?
```

And this will produce a flow chart:

```mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM2NzY2MzY2OV19
-->