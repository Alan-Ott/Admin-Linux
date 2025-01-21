**Introduction:**

Dans un système Linux, tout commence à partir du répertoire racine, désigné par **/**. Ce répertoire contient divers sous-répertoires qui ont des rôles spécifiques dans le fonctionnement du système. Chaque répertoire racine a une fonction précise, par exemple, **/bin**contient des exécutables essentiels, **/etc**des fichiers de configuration, et **/home** les répertoires personnels des utilisateurs.

**Questions de Réflexion:**

1. Pourquoi pensez-vous que Linux utilise une structure de répertoire racine hiérarchique?

> [!NOTE] Réponse :
> Pour pouvoir ce deplacer a lechelle et aller en arriere facilement

2. Quels problèmes pourraient survenir si tous les fichiers étaient stockés dans un seul répertoire sans organisation?

> [!NOTE] Réponse :
> Les etudiant pourais voir et editer ou delete les fichier des autre.


3. Comment la séparation des répertoires peut-elle affecter la sécurité du système?
    

> [!NOTE] Réponse :
> plus de point d'acces plus de possibilite d'entre forcer etc

**Exercice Pratique:**

**Partie A: Exploration**

1. Ouvrez un terminal sur votre système Linux.

2. Utilisez la commande **ls /** pour lister les répertoires à la racine de votre système. Notez ce que vous trouvez.

> [!NOTE] Réponse : BASH
> 
```Bash
ls /
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  lost+found  media  mnt  opt  proc  root  run  sbin  snap  srv  swapfile  sys  tmp  usr  var
```

3. Choisissez trois répertoires à partir de la liste obtenue, et pour chacun, utilisez la commande **ls -l** suivi du nom du répertoire pour voir leur contenu détaillé.

> [!NOTE] Coller le résultat de la commande ici :
```bash
$ ls -l /lib  
lrwxrwxrwx 1 root root 7 Nov  7  2022 /lib -> usr/lib

$ ls -l /home
total 4
drwxr-xr-x 3 ubuntu ubuntu 4096 Nov 13  2022 ubuntu

$ ls -l /snap
total 20
-r--r--r-- 1 root root  548 Nov  7  2022 README
drwxr-xr-x 2 root root 4096 May 17 08:30 bin
drwxr-xr-x 4 root root 4096 May 17 08:30 core20
drwxr-xr-x 4 root root 4096 May 17 08:30 lxd
drwxr-xr-x 3 root root 4096 Nov  7  2022 snapd
```

> [!NOTE] Commentez le résultat :
> ls -l  montre tout les documents dans le repertoire avec tout les authorities "user group world" 
> Le propriétaire du document   "user et group - root root" la taile du document quon peut changer de format avec -h 
> et le nom du document


**Partie B: Questions spécifiques**

1. Décrivez le contenu du répertoire **/etc**. Pourquoi est-il important pour le système?

> [!NOTE] Réponse :
> Il est le fichier de configuration du system

2. Quelle est la différence entre les répertoires **/bin** et **/usr/bin**?

> [!NOTE] Réponse :
> /bin contient les executable binaire du system 
> /usr/bin contient les executable binaire de l'utilisateur 

3. Pourquoi les répertoires personnels des utilisateurs sont-ils placés sous **/home**?

> [!NOTE] Réponse :
> Pour que les repertoire personnelle de chaque utilisateur soit séparé 
> par défaut chaque repertoire /home est accessible uniquement par c'est utilisateur et l’utilisateur root

**Maîtriser la Commande** **ls** **sous Linux**

**Objectif:**

Apprendre à utiliser la commande **ls** pour lister les fichiers et les répertoires dans le système de fichiers Linux, en explorant ses diverses options.

**Introduction:**

La commande **ls** est l'une des commandes les plus fréquemment utilisées sous Linux. Elle permet d'afficher les fichiers et répertoires dans le répertoire courant ou dans un répertoire spécifié. Cette commande possède plusieurs options qui permettent de modifier son comportement ou le format de la sortie.

**Questions de Réflexion:**

1. Quelle est l'importance de la commande **ls** dans la gestion quotidienne d'un système Linux ?

> [!NOTE] Réponse :
> Pour pouvoir afficher les document et repertoire dans un repertoire déclaré 
> peut aussi afficher les droit a c'est document, la taille, leur auteur et la date d'edition.
> 

2. Comment les options de la commande **ls** peuvent-elles améliorer votre productivité ou votre compréhension du système de fichiers ?

> [!NOTE] Réponse :
> En affichant plus d'information de c'est fichier 
> avec les paramétre -h - l - a -s -f -F

**Exercice Pratique:**

**Partie A: Découverte des options**

1. Ouvrez un terminal sur votre système Linux.

2. Tapez **ls** pour voir les fichiers dans votre répertoire courant.

> [!NOTE]  Afficher le résultat ici :
```bash
$ ls
filesystem  snap
```

3. Utilisez **ls -a** pour afficher tous les fichiers, y compris les fichiers **cachés**. Comparez la sortie avec la commande précédente.

> [!NOTE] Réponse :
```bash
ls -a
.  ..  .bash_history  .bashrc  .profile  .ssh  .theia  .vimrc  filesystem  snap
```

4. Essayez **ls -l** pour voir les détails des fichiers, comme les permissions, le propriétaire, la taille et la date de modification.

> [!NOTE]  Copier et coller le résultat de la commande ici :
```bash
$ ls -l
total 4
lrwxrwxrwx 1 root root    1 May 11 15:03 filesystem -> /
drwx------ 3 root root 4096 May 17 08:30 snap
```

> [!NOTE]  Où se trouvent les permissions dans ce résultat ?
> dans la premier colones 
> ***drwxr-xr-x***
> 
> la parti auteur et group affect aussi les droit
> ***root root***

5. Utilisez **ls -lh** pour afficher la taille des fichiers en format lisible (par exemple, en Ko, Mo).

> [!NOTE]  Copier et coller le résultat de la commande ici et mettez en surbrillance ce que l’option a donné comme résultat :
```bash
$ ls -lh
total 4.0K
lrwxrwxrwx 1 root root    1 May 11 15:03 filesystem -> /
drwx------ 3 root root 4.0K May 17 08:30 snap
```


**Partie B: Questions spécifiques**

1. Qu'affiche **ls -d */** Pourquoi utiliseriez-vous cette option ?

> [!NOTE] Afficher le résultat de la commande et réponse à la question :
```bash
$ ls -d /
/
```
> [!NOTE] 

2. Expliquez la différence entre **ls -l** et **ls -lt**. Quand **ls -lt** pourrait-il être particulièrement utile ?

> [!NOTE]  Réponse :
> ls -lt  organise les fichier de plus recament editer a celui editer y a plus longtemps
> 
> pour verifier quelle fichier ne sont plus utiliser ou trouver le vichier ajouter le plus recament 

3. Comment la commande **ls --color=auto** affecte-t-elle la visibilité des résultats ?

> [!NOTE]  Réponse :
> remet les couleur du resultat pour les couleur par défaut
>
>par defaut ls utilise toujours ls --color=auto cars ils est configurer en alias sous ls 
```bash
vi ~/.bashrc
alias ls='ls --color=auto'
```

**Pour aller plus loin:**

- Utilisez la combinaison des options **ls -alrt** dans différents répertoires pour observer comment vous pouvez obtenir des informations exhaustives sur les fichiers de manière ordonnée.

```bash
$ ls -alrt

total 36
-rw-r--r--  1 root root  161 Dec  5  2019 .profile
-rw-------  1 root root   20 Nov 13  2022 .bash_history
drwx------  2 root root 4096 May 11 15:01 .ssh
drwxr-xr-x 19 root root 4096 May 11 15:03 ..
lrwxrwxrwx  1 root root    1 May 11 15:03 filesystem -> /
-rw-r--r--  1 root root  109 May 11 15:03 .vimrc
-rw-r--r--  1 root root 3208 May 11 15:03 .bashrc
drwx------  3 root root 4096 May 17 09:20 snap
drwx------  5 root root 4096 May 17 09:20 .
drwxr-xr-x  4 root root 4096 May 17 09:22 .theia
```

**Naviguer avec la Commande** **cd** **sous Linux**

**Objectif:**

Apprendre à utiliser efficacement la commande **cd** pour changer de répertoires dans un système de fichiers Linux.

**Introduction:**

La commande **cd**(change directory) est une commande fondamentale en environnement Linux, utilisée pour naviguer entre les différents répertoires du système de fichiers. Maîtriser **cd** est crucial pour toute personne travaillant sous Linux, car cela facilite l'accès à différents fichiers et répertoires.

**Questions de Réflexion:**

1. Pourquoi la commande **cd** est-elle importante pour les utilisateurs de Linux?

> [!NOTE]  Réponse :
> pour pouvoir ce déplacer dans les repertoire désirer 

2. Quels défis pourriez-vous rencontrer sans une compréhension solide de **cd**?

> [!NOTE]  Réponse :
>  tu peut pas trouver les fichier que tu cherche 
>  ou une perte de temps 
>  et pas savoir revenir en arrière  

**Exercice Pratique:**

**Partie A: Utilisation Basique**

1. Ouvrez un terminal sur votre système Linux.

2. Utilisez **cd** pour aller au répertoire racine, tapez **cd /** et vérifiez votre répertoire courant avec **pwd**.

>[!note]  Afficher le résultat de la commande avec une capture d’écran :
```bash
$ cd /
$ pwd
/
```

3. Naviguez à votre répertoire personnel avec **cd ~** ou simplement **cd** sans argument, et utilisez **pwd** pour confirmer le changement.

Afficher le résultat avec une capture.
```bash
$ cd
$ pwd
/root
```

A quoi sert le symbole **~**   ? Comment se nomme ce symbole ?

> [!NOTE]  Réponse :
> **Tilde** ou **Tiltre**
> 
> home repertoire raccourcis 

A quoi vous sert la commande **pwd** ?

> [!NOTE]  Réponse :
> pour afficer le repositoir corrant
> ***Print Working Directory***

4. Essayez de naviguer à un répertoire spécifique en utilisant son chemin complet, par exemple **cd /usr/local**.

Avez-vous pu vous déplacer dans ce répertoire ? Si oui, donner la commande qui permet de certifier que vous êtes dans le répertoire « **local** »

> [!NOTE]  Réponse :
```bash
$ cd /usr/local
$ pwd
/usr/local
```

**Partie B: Utilisation Avancée**

4. Naviguez au répertoire parent en utilisant **cd ..**et observez comment le répertoire courant change avec **pwd**.
```bash
$ cd ..
$ pwd
/usr
```

5. Utilisez **cd -** pour basculer entre le répertoire courant et le dernier répertoire visité. Notez ce qui se passe et comment cela pourrait être utile.

> [!NOTE]  Réponse :
>retourne aux dernier repertoire
>si vous deplacer vers un fichier dans un emplacement completement different ou vous faite une erreur vous pouvais revenire au vous etais
```bash
$ cd -
/usr/local
```

**Questions spécifiques:**

6. Qu'arrive-t-il si vous essayez **cd** dans un répertoire qui n'existe pas? Quel message d'erreur obtenez-vous?

> [!NOTE]  Réponse :
```bash
bash: cd: rep21/: No such file or directory
```
7. Quelle est la différence entre un chemin relatif et un chemin absolu ?

> [!NOTE]  Réponse :
> un chemin absolut crée une copie du ficher que vous specifier , qui permet de protéger le fichier original
> 
> un chemin relatif crée un pointeur vers le vrai fichier, ce qui permet d’éditer le vrai document sans ce déplacer a ca location et assurer qu'il soit toujours a jour, tout modifications a l'intérieur du fichier sera effectuer sur le vrai qui peut être destructif.

8. Comment la commande **cd** aide-t-elle à gérer les chemins relatifs par rapport aux chemins absolus?

> [!NOTE]  Réponse :
> avec cd vous pouvais choisir aux placer votre chemin relatif 


9. Quelle est l'utilité de **cd ../..** et comment pourriez-vous l'utiliser dans votre navigation quotidienne?

>[!note] Réponse :
>permet de remonter deux repertoir

**Pour aller plus loin:**

10. Essayez de combiner **cd** avec d'autres commandes, comme **ls**, pour explorer les fichiers et sous-répertoires dès que vous changez de répertoire.

**Maîtrise de la Commande** **mv** **pour Déplacer et Renommer des Fichiers sous Linux**

**Objectif:**

Apprendre à utiliser la commande **mv** pour déplacer et renommer des fichiers et des répertoires dans un système de fichiers Linux.

**Introduction:**

La commande **mv** est utilisée pour déplacer des fichiers et des répertoires d'un endroit à un autre et pour renommer des objets. C'est une commande essentielle pour la gestion des fichiers sous Linux, permettant aux utilisateurs de restructurer efficacement leurs fichiers et dossiers sans créer de copies supplémentaires.

**Questions de Réflexion:**

11. Quelle est la différence entre déplacer et copier des fichiers sous Linux? Pourquoi **mv** est-elle une commande critique ?

>[!note] Réponse:
>copie créer une nouvelle version du document qui est identique 
>
>mv prendre le vrai document et le deplace et/ou le renom

12. Comment les permissions de fichiers affectent-elles l'utilisation de la commande **mv**?

>[!note] Réponse :
>users need to permission to move or rename files 
>moving files to a repository without restricted permissions the permissions my no longer apply

**Exercice Pratique:**

**Partie A: Déplacer des Fichiers**

13. Ouvrez un terminal sur votre système Linux.
    
14. Créez un répertoire de test dans votre répertoire personnel avec **mkdir ~/test-mv**.
    
15. À l'intérieur de ce répertoire, créez deux sous-répertoires, **src** et **dest**, avec **mkdir src dest**.
    

Faire une capture de vos répertoires créés et collez ici :

16. Créez un fichier test dans **src** avec **echo "Ceci est un test" > src/testfile.txt**.
    

17. Utilisez **mv src/testfile.txt dest/** pour déplacer le fichier de **src** à **dest**. Vérifiez le résultat avec **ls dest**.
    

>[!note] Afficher le résultat ici :
```bash
$ echo "Ceci est un test" > src/testfile.txt  
$ cat src/testfile.txt
Ceci est un test
```

**Partie B: Renommer des Fichiers**

18. Retournez dans le répertoire **src** et renommez **testfile.txt** en **newfile.txt** avec **mv testfile.txt newfile.txt**.

19. Vérifiez le changement avec **ls**.

>[!note] Afficher le résultat ici :
```bash
$ ls
testfile.txt
ubuntu $ mv testfile.txt newfile.txt
ubuntu $ ls
newfile.txt
```

**Questions spécifiques:**

20. Que se passe-t-il si vous essayez de déplacer un fichier dans un répertoire sans les permissions appropriées?

>[!note] Réponse :
```bash
mv: cannot move 'newfile.txt' to 'file.txt': Permission denied
```

21. Comment la commande **mv** est-elle utilisée pour renommer un répertoire?

>[!note] Réponse :
```bash
$ mv newfile.txt file.txt
$ ls
file.txt
```

22. Expliquez l'impact de l'option **-i** avec **mv**, et pourquoi pourrait-elle être utile?

>[!note] Réponse :
```bash
-i, --interactive
	prompt before overwrite.
```

**Pour aller plus loin:**

23. Explorez l'utilisation de **mv** avec des options comme **-u** pour ne déplacer les fichiers que s'ils sont plus récents que ceux de destination ou n'existent pas encore là.
```bash
NAME
       mv - move (rename) files

DESCRIPTION
       Rename SOURCE to DEST, or move SOURCE(s) to DIRECTORY.

       Mandatory arguments to long options are mandatory for short options too.

       --backup[=CONTROL]
              make a backup of each existing destination file

       -b     like --backup but does not accept an argument

       -f, --force
              do not prompt before overwriting

       -i, --interactive
              prompt before overwrite

       -n, --no-clobber
              do not overwrite an existing file

       If you specify more than one of -i, -f, -n, only the final one takes effect.

       --strip-trailing-slashes
              remove any trailing slashes from each SOURCE argument

       -S, --suffix=SUFFIX
              override the usual backup suffix

       -t, --target-directory=DIRECTORY
              move all SOURCE arguments into DIRECTORY

       -T, --no-target-directory
              treat DEST as a normal file

       -u, --update
              move only when the SOURCE file is newer than the destination file or when the destination file is missing

       -v, --verbose
              explain what is being done

       -Z, --context
              set SELinux security context of destination file to default type

       --help display this help and exit

       --version
              output version information and exit
```


**Utilisation Avancée de la Commande** **cp** **sous Linux**

**Objectif:**

Apprendre à utiliser la commande **cp** pour copier des fichiers et des répertoires, en explorant différentes options pour manipuler le système de fichiers de manière efficace.

**Introduction:**

La commande **cp** est utilisée pour copier des fichiers et des répertoires. Elle est essentielle pour la gestion des données dans Linux, permettant aux utilisateurs de dupliquer des informations sans affecter les originaux. Comprendre **cp** est crucial pour toute personne effectuant des tâches de gestion de fichiers.

**Questions de Réflexion:**

24. Quelles sont les différences fondamentales entre les commandes **cp** et **mv**?

>[! ] Réponse :


**Exercice Pratique:**

**Partie A: Copier des Fichiers Simples**

25. Ouvrez un terminal sur votre système Linux.
    
26. Créez un répertoire de travail **~/cp-exercise**avec **mkdir ~/cp-exercise**.
    
27. À l'intérieur, créez un fichier texte avec **echo "Ceci est un exemple de fichier" > ~/cp-exercise/file.txt**.
    

Afficher le résultat ici :

28. Copiez le fichier dans le même répertoire sous un nouveau nom avec **cp ~/cp-exercise/file.txt ~/cp-exercise/copy.txt**.
    

Afficher le résultat ici :

29. Vérifiez que les deux fichiers existent et comparez leur contenu avec **cat**.
    

Afficher le résultat ici :

**Partie B: Copier des Répertoires**

4. Créez un sous-répertoire **src**dans **~/cp-exercise** avec **mkdir ~/cp-exercise/src** et créez quelques fichiers à l'intérieur.
    

Afficher le résultat ici :

5. Utilisez **cp -r ~/cp-exercise/src ~/cp-exercise/dest** pour copier le répertoire entier **src**dans un nouveau répertoire appelé **dest**.
    

Afficher le résultat ici :

A quoi sert l’option –r ?

Réponse :

6. Vérifiez le contenu de **dest** pour s'assurer que tous les fichiers sont correctement copiés.
    

Afficher le résultat ici :

**Questions spécifiques:**

7. Que se passe-t-il si vous copiez un fichier dans un répertoire sans les permissions adéquates ?
    

Réponse :

8. Comment la commande **cp -u** peut-elle être utilisée pour mettre à jour des fichiers déjà existants ?
    

Réponse :

9. Expliquez l'importance de l'option **-a** (archive) lors de la copie de répertoires.
    

Réponse :

**Pour aller plus loin:**

10. Essayez d'utiliser l'option **--backup=numbered** pour créer des sauvegardes numérotées de fichiers lors de la copie pour éviter l'écrasement des fichiers existants.
    

Apprendre à utiliser la commande **rm** pour supprimer de manière sécurisée des fichiers et des répertoires dans un système de fichiers Linux.

**Introduction:**

La commande **rm**(remove) est utilisée pour supprimer des fichiers et des répertoires. Elle est puissante mais potentiellement dangereuse si elle n'est pas utilisée avec précaution. Comprendre **rm** et ses options permet d'éviter la suppression accidentelle de données importantes.

**Questions de Réflexion:**

11. Quels sont les risques associés à l'utilisation de la commande **rm** sans options?
    

Réponse :

12. Pourquoi est-il important de vérifier deux fois avant d'exécuter **rm** sur des fichiers ou des répertoires critiques?
    

Réponse :

**Exercice Pratique:**

**Partie A: Suppression de Fichiers**

13. Ouvrez un terminal sur votre système Linux.
    
14. Créez un répertoire de travail **~/rm-exercise**avec **mkdir ~/rm-exercise**.
    
15. À l'intérieur, créez quelques fichiers de test avec **touch ~/rm-exercise/file1.txt ~/rm-exercise/file2.txt**.
    

Afficher le résultat :

16. Supprimez un fichier spécifique avec **rm ~/rm-exercise/file1.txt**et vérifiez avec **ls ~/rm-exercise** que le fichier a bien été supprimé.
    

Afficher le résultat :

**Partie B: Suppression de Répertoires**

17. Créez un sous-répertoire **testdir**dans **~/rm-exercise** avec **mkdir ~/rm-exercise/testdir** et ajoutez un fichier dedans.
    
18. Essayez de supprimer le répertoire avec **rm ~/rm-exercise/testdir** et observez l'erreur.
    

Afficher le message d’erreur ici :

19. Supprimez correctement le répertoire avec **rm -r ~/rm-exercise/testdir** et vérifiez que le répertoire a été supprimé.
    

Afficher le résultat ici :

**Questions spécifiques:**

20. Expliquez ce que fait l'option **-f** avec **rm** et dans quelles situations elle pourrait être utile.
    

Réponse :

21. Quelle est la différence entre **rm -r** et **rm -rf**? Quels sont les dangers de **rm -rf**?
    

Réponse :

22. Comment pouvez-vous utiliser **rm**pour supprimer tous les fichiers d'un type spécifique dans un répertoire (par exemple, tous les fichiers **.txt**)?
    

Réponse :

**Pour aller plus loin:**

23. Expérimentez avec l'option **--preserve-root** pour comprendre comment elle protège le répertoire racine lors de l'utilisation de commandes de suppression récursive.
    

**Création de Répertoires avec la Commande** **mkdir** **sous Linux**

**Objectif:**

Apprendre à utiliser la commande **mkdir** pour créer des répertoires de manière efficace et à explorer les options disponibles pour répondre à différents besoins.

**Introduction:**

La commande **mkdir** (make directory) est utilisée pour créer un ou plusieurs répertoires. Elle est simple mais dispose de plusieurs options qui permettent de gérer efficacement la création de répertoires complexes, y compris la création de répertoires parents et la gestion des permissions.

**Questions de Réflexion:**

24. Pourquoi pourrait-il être nécessaire de créer des répertoires sur un système Linux ?
    

Réponse :

25. Quels problèmes pourraient survenir lors de la création de répertoires sans les bonnes permissions ?
    

Réponse :

**Exercice Pratique:**

**Partie A: Création Simple**

26. Ouvrez un terminal sur votre système Linux.
    
27. Utilisez **mkdir ~/test-mkdir**pour créer un répertoire nommé **test-mkdir** dans votre répertoire personnel.
    
28. Vérifiez que le répertoire a été créé avec **ls ~**.
    

Afficher le résultat ici :

**Partie B: Création de Structures de Répertoires**

4. Utilisez **mkdir -p ~/test-mkdir/subdir1/subdir2** pour créer une structure de répertoires imbriqués en une seule commande.
    

Afficher le résultat ici :

5. Vérifiez la création de la structure avec **ls -R ~/test-mkdir**.
    

Afficher le résultat :

**Questions spécifiques:**

6. Expliquez l'utilité de l'option **-p**avec **mkdir**. Quand est-elle particulièrement utile ?
    

Réponse :

7. Comment pouvez-vous utiliser **mkdir** pour créer simultanément plusieurs répertoires au même niveau ?
    

Réponse :

8. Quel est l'effet de combiner **mkdir** avec des commandes comme **chmod** pour définir les permissions dès la création du répertoire ?
    

Réponse :

**Pour aller plus loin:**

9. Explorez l'utilisation de **mkdir** dans des scripts pour automatiser la création de structures de répertoires pour des projets ou des configurations de serveur.
    

**Utiliser la Commande** **rmdir** **pour Supprimer des Répertoires Vides sous Linux**

**Objectif:**

Apprendre à utiliser la commande **rmdir**pour supprimer des répertoires vides, en comprenant ses limitations et quand il est préférable de l'utiliser plutôt que d'autres commandes comme **rm -r**.

**Introduction:**

La commande **rmdir**(remove directory) est utilisée pour supprimer des répertoires vides. Elle est plus sécuritaire que **rm -r** car elle ne permet pas de supprimer un répertoire contenant des fichiers ou d'autres répertoires, ce qui réduit le risque de suppression accidentelle de données importantes.

**Questions de Réflexion:**

10. Pourquoi est-il important d'avoir une commande spécifique pour supprimer des répertoires vides ?
    

Réponse :

11. Quels sont les avantages de **rmdir** par rapport à **rm -r** pour supprimer des répertoires ?
    

Réponse :

**Exercice Pratique:**

**Partie A: Suppression de Répertoires Vides**

12. Ouvrez un terminal sur votre système Linux.
    
13. Créez une structure de répertoires avec **mkdir -p ~/test-rmdir/emptydir**.
    
14. Essayez de supprimer le répertoire avec **rmdir ~/test-rmdir/emptydir**et vérifiez avec **ls ~/test-rmdir** pour s'assurer que le répertoire est supprimé.
    

Afficher le résultat :

**Partie B: Gestion d'Erreurs avec rmdir**

15. À l'intérieur de**~/test-rmdir**, créez un nouveau répertoire avec un fichier dedans: **mkdir ~/test-rmdir/notemptydir**et **touch ~/test-rmdir/notemptydir/file.txt**.
    

Afficher le résultat :

16. Essayez de supprimer **notemptydir** avec **rmdir ~/test-rmdir/notemptydir** et observez l'erreur générée.
    

Afficher le résultat :

17. Supprimez le fichier avec **rm ~/test-rmdir/notemptydir/file.txt**et ensuite supprimez le répertoire avec **rmdir**.
    

Afficher le résultat :

**Questions spécifiques:**

18. Que se passe-t-il si vous tentez de supprimer un répertoire non vide avec **rmdir** ?
    

Réponse :

19. Comment pouvez-vous vérifier qu'un répertoire est vide avant de tenter de le supprimer avec **rmdir** ?
    

Réponse :

20. Dans quel scénario est-il préférable d'utiliser **rmdir**plutôt que **rm -r** ?
    

Réponse :

**Pour aller plus loin:**

21. Explorez des scripts qui pourraient utiliser **rmdir** pour nettoyer des structures de répertoires après des opérations qui pourraient laisser des répertoires vides.
    

**Découverte du Chemin Actuel avec la Commande** **pwd** **sous Linux**

**Objectif:**

Apprendre à utiliser la commande **pwd** pour identifier le répertoire de travail courant et comprendre son importance dans la navigation et la gestion des fichiers sous Linux.

**Introduction:**

La commande **pwd** (print working directory) affiche le chemin complet du répertoire de travail courant. C'est un outil indispensable pour vérifier votre position actuelle dans l'arborescence du système de fichiers, surtout lorsque vous travaillez dans un environnement terminal.

**Questions de Réflexion:**

22. Pourquoi est-il utile de connaître le chemin du répertoire de travail courant lorsque vous utilisez un terminal ?
    

Réponse :

23. Comment la connaissance du chemin actuel peut-elle influencer l'exécution de commandes qui manipulent des fichiers ou des répertoires ?
    

Réponse :

**Exercice Pratique:**

**Partie A: Utilisation de Base**

24. Ouvrez un terminal sur votre système Linux.
    
25. Tapez **pwd** pour afficher le chemin de votre répertoire de travail courant.
    
26. Naviguez à votre répertoire personnel avec **cd ~**(ou simplement **cd**) et utilisez à nouveau **pwd** pour confirmer le changement de répertoire.
    

Afficher le résultat :

**Partie B: Exploration et Confirmation**

3. Créez un nouveau répertoire pour tester avec **mkdir ~/test-pwd**.
    
4. Naviguez dans ce nouveau répertoire avec **cd ~/test-pwd**et utilisez **pwd** pour vérifier que vous êtes dans le bon répertoire.
    
5. Retournez au répertoire parent avec **cd ..**et utilisez **pwd** pour confirmer que vous êtes revenu au répertoire précédent. ?
    

Afficher le résultat :

**Questions spécifiques:**

6. Que se passe-t-il si vous utilisez **pwd**après avoir changé de répertoire avec **cd**vers un lien symbolique? Comment le système traite-t-il les liens symboliques avec **pwd**?
    

Réponse :

7. Quelle commande pouvez-vous utiliser pour revenir directement au répertoire de travail d'origine après plusieurs déplacements?
    

Réponse :

**Pour aller plus loin:**

8. Expérimentez avec des liens symboliques et observez comment **pwd**affiche les chemins lorsqu'ils contiennent des liens. Utilisez l'option **-P** pour voir comment elle affecte la sortie.
    

**Maîtrise de la Commande** **ln** **pour Créer des Liens sous Linux**

**Objectif:**

Comprendre et pratiquer l'utilisation de la commande **ln** pour créer des liens physiques et symboliques, et explorer les implications de chaque type de lien dans la gestion des fichiers.

**Introduction:**

La commande **ln** permet de créer des liens vers des fichiers et des répertoires. Il existe deux types de liens : les liens physiques et les liens symboliques. Un lien physique crée une deuxième entrée pour le même fichier dans un autre emplacement, tandis qu'un lien symbolique crée un pointeur vers l'emplacement original du fichier.

**Questions de Réflexion:**

9. Quelles sont les différences entre un lien physique et un lien symbolique ?
    

Réponse :

10. Pourquoi utiliseriez-vous un lien symbolique plutôt qu'un lien physique ?
    

Réponse :

**Exercice Pratique:**

**Partie A: Création de Liens Physiques**

11. Ouvrez un terminal sur votre système Linux.
    
12. Créez un fichier test avec **echo "Ceci est un fichier de test" > ~/testfile.txt**.
    
13. Créez un lien physique nommé **linkfile.txt**pointant vers **testfile.txt** avec **ln ~/testfile.txt ~/linkfile.txt**.
    
14. Vérifiez que le lien a été créé avec **ls -l ~/** et observez la sortie pour voir les deux noms de fichier avec le même numéro d'inode.
    

Afficher le résultat et mettez en surbrillance les numéros d’inode :

**Partie B: Création de Liens Symboliques**

15. Créez un lien symbolique nommé **symlinkfile.txt**pointant vers **testfile.txt** avec **ln -s ~/testfile.txt ~/symlinkfile.txt**.
    
16. Vérifiez que le lien symbolique a été créé avec **ls -l ~/** et notez la différence dans la sortie par rapport à un lien physique.
    

Afficher le résultat :

**Questions spécifiques:**

17. Que se passe-t-il si vous modifiez le fichier original après avoir créé un lien physique et un lien symbolique ?
    

Réponse + affichage du résultat

18. Que se passe-t-il si vous supprimez le fichier original après avoir créé un lien physique et un lien symbolique ?
    

Réponse + affichage du résultat :

19. Comment la commande **ln** gère-t-elle la création de liens vers des répertoires ?
    

Réponse :

**Pour aller plus loin:**

20. Essayez de créer des liens dans des scripts pour automatiser des tâches, comme la gestion de versions de fichiers ou la création de raccourcis.
    

**Explorer et Maîtriser la Commande** **find** **sous Linux**

**Objectif:**

Apprendre à utiliser la commande **find** pour rechercher des fichiers et des répertoires en fonction de différents critères comme le nom, la taille, les permissions et les dates de modification.

**Introduction:**

La commande **find** permet aux utilisateurs de trouver des fichiers et des répertoires sur leur système en fonction de conditions telles que la structure des répertoires, les propriétés des fichiers, et des expressions régulières. Elle est indispensable pour la gestion efficace et automatisée des fichiers.

**Questions de Réflexion:**

21. Quels sont les avantages de la commande **find**par rapport à une recherche simple avec **ls** ?
    

Réponse :

**Exercice Pratique:**

**Partie A: Recherche de Base**

22. Ouvrez un terminal sur votre système Linux.
    
23. Créez un répertoire de travail **~/find-exercise** et plusieurs fichiers de test à l'intérieur.
    
24. Utilisez **find ~/find-exercise -name 'testfile*'** pour trouver tous les fichiers dont les noms commencent par **testfile**.
    

Afficher le résultat :

**Partie B: Recherche Avancée**

6. Utilisez **find ~/find-exercise -type f -mtime -10** pour trouver des fichiers modifiés dans les derniers 10 jours.
    

Afficher le résultat :

7. Cherchez des fichiers par taille avec **find ~/find-exercise -type f -size +100k** pour trouver des fichiers de plus de 100 kilobytes.
    

Afficher le résultat :

**Questions spécifiques:**

8. Comment pouvez-vous utiliser **find** pour rechercher des répertoires au lieu de fichiers ?
    

Réponse :

9. Quel est l'effet de combiner **find** avec des commandes comme **rm**? Donnez un exemple de commande qui pourrait être utilisée pour nettoyer des fichiers temporaires.
    

Réponse :

10. Expliquez comment utiliser les actions de **find**, comme **-exec**, pour exécuter des commandes sur les fichiers trouvés.
    

Réponse :

**Pour aller plus loin:**

11. Explorez l'utilisation de **find** pour identifier des fichiers avec des permissions spécifiques et les modifier en conséquence.
    

**Maîtrise de la Commande** **grep** **pour la Recherche de Texte sous Linux**

**Objectif:**

Apprendre à utiliser la commande **grep** pour rechercher des motifs de texte dans des fichiers ou des flux de données, en explorant différentes options et expressions régulières.

**Introduction:**

La commande **grep** (Global Regular Expression Print) permet de rechercher du texte dans des fichiers en utilisant des expressions régulières. Elle est essentielle pour filtrer et analyser les données ou les logs, et peut être utilisée pour des tâches simples ou complexes de recherche de texte.

**Questions de Réflexion:**

12. Pourquoi est-il utile de savoir utiliser des expressions régulières avec **grep** ?
    

Réponse :

13. Quels sont les avantages de **grep** pour l'analyse des fichiers log ?
    

Réponse :

**Exercice Pratique:**

**Partie A: Recherche Simple**

14. Ouvrez un terminal sur votre système Linux.
    
15. Créez un fichier texte **sample.txt** dans un répertoire de travail et ajoutez plusieurs lignes de texte varié.
    
16. Utilisez **grep 'motif' sample.txt** pour rechercher des lignes contenant un motif spécifique dans le fichier.
    

Afficher le résultat :

**Partie B: Recherche Avancée**

17. Utilisez **grep -i 'motif' sample.txt** pour effectuer une recherche insensible à la casse.
>[! ] Réponse :
```bash
$ grep -ib 'srb' comb.txt
55:srb
59:srb
64:srb
```

Afficher le résultat :

18. Explorez l'utilisation de **grep -v 'motif' sample.txt** pour afficher toutes les lignes qui ne contiennent pas le motif.
>[! ] Afficher le résultat :
```bash
$  grep -vb 'srb' comb.txt
0:part unoooo
12:oo
15:
16:ve
19:
20:srv
24:
33:
38:brs
42:
43:part dossss
ubuntu $ cat -b comb.txt
     1  part unoooo
     2  oo

     3  ve

     4  srv

     5  srb
     6  srb

     7  srb
     8  brs

     9  part dossss
```

19. Utilisez **grep -r 'motif' ~/** pour rechercher récursivement dans tous les fichiers sous votre répertoire personnel.

Afficher le résultat :
```bash
$ grep -r 'srb' ~/      
/root/cattest/comb.txt:srb
/root/cattest/comb.txt:srb
/root/cattest/comb.txt:srb
```

**Questions spécifiques:**

20. Comment **grep** peut-il être utilisé pour trouver des mots qui commencent par une lettre spécifique ?
    

Réponse :

21. Expliquez l'utilisation de **grep -l**par rapport à **grep -c**. Quelle option serait utile pour compter le nombre d'occurrences d'un motif ?
    

Réponse :

22. Comment pouvez-vous combiner **grep** avec d'autres commandes Unix pour filtrer des résultats plus complexes ?
    

Réponse :

Apprendre à utiliser la commande **cat** (concatenate) pour lire, combiner et manipuler des fichiers textuels dans un système de fichiers Linux.

**Introduction:**

La commande **cat** est principalement utilisée pour lire, combiner et rediriger le contenu de fichiers dans le terminal. Elle est extrêmement utile pour afficher rapidement le contenu des fichiers, ainsi que pour combiner plusieurs fichiers en un seul.

**Questions de Réflexion:**

23. Dans quels scénarios utiliseriez-vous **cat** pour afficher le contenu d'un fichier ?
    
24. Quelles sont les conséquences potentielles de l'utilisation de **cat** pour combiner de très grands fichiers ?
    

**Exercice Pratique:**

**Partie A: Affichage de Contenu**

25. Ouvrez un terminal sur votre système Linux.
    
26. Créez un fichier texte **example.txt** dans un répertoire de travail et ajoutez-y quelques lignes de texte.
    
27. Utilisez **cat example.txt** pour afficher le contenu du fichier dans le terminal.
    

**Partie B: Combinaison de Fichiers**

28. Créez deux fichiers, **part1.txt** et **part2.txt**, dans le même répertoire et écrivez du contenu différent dans chacun.
    
29. Utilisez **cat part1.txt part2.txt > combined.txt** pour combiner les contenus des deux fichiers dans un nouveau fichier **combined.txt**.
    
30. Affichez le contenu de **combined.txt** avec **cat** pour vérifier que les fichiers ont été combinés correctement.
    

**Questions spécifiques:**

4. Comment pouvez-vous utiliser **cat** pour afficher le contenu de plusieurs fichiers à la suite ?
    

Réponse :

5. Quelle commande **cat** utiliseriez-vous pour numéroter toutes les lignes lors de l'affichage d'un fichier ?
>[! ]  Reponse
```bash 
$ cat -b comb.txt
     1  part unoooo
     2  oo
     3  ve
```

6. Quel est l'effet de l'utilisation de l'option **-s** avec **cat** ? Pourquoi serait-elle utile ?
>[! ] Reponse
>ecrase les espace blank repeter
```bash
 $ cat -b comb.txt
     1  part unoooo
     2  oo





     3  ve


     4  srv




     5  srb
     6  srb

     7  srb
     8  brs



     9  part dossss
 $ cat -bs comb.txt
     1  part unoooo
     2  oo

     3  ve

     4  srv

     5  srb
     6  srb

     7  srb
     8  brs

     9  part dossss
```

Réponse :

**Pour aller plus loin:**

7. Explorez l'utilisation de **cat** avec des redirections pour créer des scripts ou des commandes qui automatisent la gestion des fichiers.
    

**Initiation à l'Éditeur de Texte** **vi** **sous Linux**

### **Objectif:**

>[!warning] 
>je conais deja vim
>c'est deja mon editeur de text a plain temps 

Apprendre les fonctionnalités de base de l'éditeur **vi**, y compris l'entrée et la sortie des modes, la navigation dans un fichier texte, et les opérations d'édition simples.

### **Introduction:**

**vi** est un éditeur de texte modal, ce qui signifie qu'il fonctionne en différents modes—principalement le mode normal et le mode insertion. Comprendre comment passer entre ces modes et comment les utiliser efficacement est essentiel pour travailler avec **vi**.

### **Questions de Réflexion:**

1. Pourquoi est-il utile de connaître un éditeur de texte basé en mode terminal comme **vi**?
    
2. Quels sont les avantages et les inconvénients de l'utilisation d'un éditeur modal comme **vi**?
    

### **Exercice Pratique:**

**Partie A: Prise en Main de** **vi**

1. Ouvrez un terminal sur votre système Linux.
    
2. Tapez **vi example.txt** pour ouvrir un nouveau fichier dans **vi**.
    
3. Pratiquez l'entrée en mode insertion en appuyant sur **i**. Tapez quelques lignes de texte, puis retournez au mode normal en appuyant sur **Esc**.
    

**Partie B: Édition et Navigation**

1. Dans le mode normal, pratiquez la navigation dans le texte avec les touches **h**, **j**, **k**, **l**.
    
2. Ajoutez du nouveau texte, supprimez du texte, et modifiez du texte existant. Par exemple, pour supprimer un caractère, utilisez **x**; pour supprimer une ligne, utilisez **dd**.
    
3. Sauvegardez les modifications en tapant **:w** et quittez **vi** en tapant **:q**.
    

### **Questions spécifiques:**

1. Comment passer du mode normal au mode insertion et vice versa ?
    
2. Quelle commande utiliseriez-vous pour sauvegarder les modifications et quitter **vi** en même temps ?
    
3. Comment rechercher un mot dans **vi** et le remplacer par un autre mot ?