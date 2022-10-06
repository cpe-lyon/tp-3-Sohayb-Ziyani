# TP 3 - Utilisateurs, groupes et permissions

## Exercice 1. Gestion des utilisateurs et des groupes 

### 1. Utilisez la commande groupadd pour créer deux groupes dev et infra

groupadd dev et groupadd infra m'ont pemrit de créer ces deux groupes et la commande grep de les visualiser 

![image](https://user-images.githubusercontent.com/80455771/191514345-b7a5f22b-84d8-4718-a353-f0b8544de7ac.png)

### 2. Créez ensuite 4 utilisateurs alice, bob, charlie, dave avec la commande useradd, en demandant la création de leur dossier personnel et avec bash pour shell

La commande `useradd -m` m'a permit de créer l'utilisateur avec son dossier personnel et la commande `usermod -s` de leur attribuer bash comme shell 

![image](https://user-images.githubusercontent.com/80455771/191516962-655be3a0-5dba-4241-977d-8c052fdd993f.png)

### 3. Ajoutez les utilisateurs dans les groupes créés : - alice, bob, dave dans dev 
- bob, charlie, dave dans infra

L'ajout des utilisateurs dans leur groupe réspectifs 

![image](https://user-images.githubusercontent.com/80455771/191517490-59d9c6a2-a574-43a9-9c4c-1bac367efa08.png)

### 4. Donnez deux moyens d’afficher les membres de infra

Les commandes `getent` et `grep` permettent d'afficher les membres d'un groupe 

![image](https://user-images.githubusercontent.com/80455771/191518392-f9e05c05-0b87-42bd-9359-34bf51915e8f.png)

### 5. Faites de dev le groupe propriétaire des répertoires /home/alice et /home/bob et de infra le groupe propriétaire de /home/charlie et /home/dave

La commande `chgrp -R` permet de ùettre un groupe propriétaire d'un répertoire

![image](https://user-images.githubusercontent.com/80455771/191520299-657908ce-3337-463d-9fae-1482fe91c8cd.png)

### 6. Remplacez le groupe primaire des utilisateurs : - dev pour alice et bob - infra pour charlie et dave

La commande `usermod ... -g ...` permet de remplacez le groupe primaire des utilisateurs 

![image](https://user-images.githubusercontent.com/80455771/191522071-00a80fdf-a736-4b4d-9746-322813b7f3aa.png)

### 7. Créez deux répertoires /home/dev et /home/infra pour le contenu commun aux membres de chaque groupe, et mettez en place les permissions leur permettant d’écrire dans ces dossiers.

Création des deux répértoires :

![image](https://user-images.githubusercontent.com/80455771/191522794-e9f6f9d0-a2db-4f29-9337-0fdd99b23ae3.png)

Attribution des groupes à leur répértoires :

![image](https://user-images.githubusercontent.com/80455771/191523804-fda28cc0-f225-483b-a321-044db5629d53.png)

Attribution des droits aux groupes :

![image](https://user-images.githubusercontent.com/80455771/191524454-8840ccb6-8a74-4483-a236-a5931b1624d4.png)

### 8.  Comment faire pour que, dans ces dossiers, seul le propriétaire d’un fichier ait le droit de renommer ou supprimer ce fichier ?

Pour que seul le prorpiétaire d'un fichier ait le droit de renommer ou supprimer ce fichier il faut faire chmod u+rwx 

### 9. Pouvez-vous ouvrir une session en tant que alice ? Pourquoi ?

Oui car je suis en admin 

![image](https://user-images.githubusercontent.com/80455771/191526398-570d2b2c-5a4b-4269-904e-4a815dda9fa1.png)

### 10. Activez le compte de l’utilisateur alice et vérifiez que vous pouvez désormais vous connecter avec son compte.

Pour activer un compte d'utilisateur il faut lui attribuer un mot de passe 

![image](https://user-images.githubusercontent.com/80455771/191527438-d6205229-85f5-46f0-a6a6-0ddb9112b39a.png)

### 11.  Comment obtenir l’uid et le gid de alice ?

On obtient l'uid et le gid d'Alice grâce à la commande `id` 

![image](https://user-images.githubusercontent.com/80455771/191603785-3aef65e6-c0ac-464d-996b-f3b029ae515a.png)

### 12. Quelle commande permet de retrouver l’utilisateur dont l’uid est 1003 ?

Tout comme la question précédente, on utilise la commande `id` mais cette fois en précisant l'uid 

![image](https://user-images.githubusercontent.com/80455771/191604080-8e2c4982-7add-4a87-b9a9-689c5a564800.png)

### 13. Quel est l’id du groupe dev ?

Avec la commande `grep` il est possible de retroyver l'id d'un groupe 

![image](https://user-images.githubusercontent.com/80455771/191606454-03417704-0b96-48f9-a0fa-d84566b3f802.png)

### 14. Quel groupe a pour gid 1002 ?

Le groupe qui a pour id 1002 est le groupe dev

![image](https://user-images.githubusercontent.com/80455771/191606104-1818be7f-e260-4588-aa50-f93a52b7b11f.png)

### 15. Retirez l’utilisateur charlie du groupe infra. Que se passe-t-il ? Expliquez.

Avec la commande `gpasswd --delete` il est possible de retirer un utilisateur d'un groupe 

![image](https://user-images.githubusercontent.com/80455771/191606782-e0bb0165-c65e-4737-8ccb-a6e47ced5115.png)

16. Modifiez le compte de Dave :

### Il expire au 1er juin 2021
- Il expire au 1er juin 2021 :
```
usermod --expiredate 2021-06-01 dave
```
### Il faut changer de mot de passe avant 90 jours
- Il faut changer le mot de passe avant 90 jours :
```
chage -M 90 dave
```
### Il faut attendre 5 jours pour modifier un mot de passe
- Il faut attendre 5 jours pour modifier un mot de passe :
```
chage -m 5 dave
```
### L’utilisateur est averti 14 jours avant l’expiration de son mot de passe
- L' utilisateur est averti 14 jours avant l'expiration de son mot de passe :
```
chage -W 14 dave 
```
### Le compte sera bloqué 30 jours après expiration du mot de passe
- Le compte sera bloqué 30 jours après expiration du mot de passe :
```
chage -I 30 dave
```

### 17.  Quel est l’interpréteur de commandes (Shell) de l’utilisateur root ?

On peut vérifier ca avec la commande grep 

![image](https://user-images.githubusercontent.com/80455771/191675106-eff1a755-68c7-4321-a6d3-1d42f9478e7d.png)

### 18. Si vous regardez la liste des comptes présents sur la machine, vous verrez qu’il en existe un nommé nobody. A quoi correspond-il ?

Nobody est le nom conventionnel d'un compte d'utilisateur à qui aucun fichier n'appartient, qui n'est dans aucun groupe qui a des privilèges et dont les seules possibilités sont celles que tous les "autres utilisateurs" ont.

### 19. Si vous regardez la liste des comptes présents sur la machine, vous verrez qu’il en existe un nommé nobody. A quoi correspond-il ?

La commande sudo garde le mot de passe pendant 15 minutes

Pour forcer à oublier le mot de passe on peut utiliser :
```
sudo -k 
```

## Exercice 2. Gestions des permissions 

### 1. Dans votre $HOME, créez un dossier test, et dans ce dossier un fichier fichier contenant quelques lignes de texte. Quels sont les droits sur test et fichier ?

![image](https://user-images.githubusercontent.com/80455771/191679157-9ddd8e51-270a-4933-b23d-a253633d9ff0.png)

### 2. Retirez tous les droits sur ce fichier (même pour vous), puis essayez de le modifier et de l’afficher en tant que root. Conclusion ?

On peut quand même modifier et affichier le fichier avec l'utilisateur root, il ne perd jamais les droits

![image](https://user-images.githubusercontent.com/80455771/191681068-384d49c5-d1a7-4d9c-ad7c-6c34a6668afb.png)

### 3. Redonnez vous les droits en écriture et exécution sur fichier puis exécutez la commande echo "echo Hello" > fichier. On a vu lors des TP précédents que cette commande remplace le contenu d’un fichier s’il existe déjà. Que peut-on dire au sujet des droits ?

On redonnes les droits :
```
chmod 777 ~/test/fichier
```
Il est possible de modifier le fichier sans l'utilisateur root 

### 4. Essayez d’exécuter le fichier. Est-ce que cela fonctionne ? Et avec sudo ? Expliquez.

Il est possible d'éxécuter de nouveau car nous avons donné les droits juste avant 

### 5. Placez-vous dans le répertoire test, et retirez-vous le droit en lecture pour ce répertoire. Listez le contenu du répertoire, puis exécutez ou affichez le contenu du fichier fichier. Qu’en déduisez-vous ? Rétablissez le droit en lecture sur test

Il n'est pas possible de lister le contenu du répertoire car nous avons retirer les droits 

### 6. Créez dans test un fichier nouveau ainsi qu’un répertoire sstest. Retirez au fichier nouveau et au répertoire test le droit en écriture. Tentez de modifier le fichier nouveau. Rétablissez ensuite le droit en écriture au répertoire test. Tentez de modifier le fichier nouveau, puis de le supprimer. Que pouvezvous déduire de toutes ces manipulations ?

Création d'un fichier nouveau et d'un répertoire sstest :
```
touch nouveau
mkdir sstest
chmod u-w nouveau
chmod u-w sstest
```
Quand on enlève les droits en écriture, il n'est pas possible de modifier les documents

### 7. Positionnez vous dans votre répertoire personnel, puis retirez le droit en exécution du répertoire test. Tentez de créer, supprimer, ou modifier un fichier dans le répertoire test, de vous y déplacer, d’en lister le contenu, etc…Qu’en déduisez vous quant au sens du droit en exécution pour les répertoires ?

Sans les droits d'éxecution il est impossible d'effectuer une seule manipulation

### 8. Rétablissez le droit en exécution du répertoire test. Positionnez vous dans ce répertoire et retirez lui à nouveau le droit d’exécution. Essayez de créer, supprimer et modifier un fichier dans le répertoire test, de vous déplacer dans ssrep, de lister son contenu. Qu’en concluez-vous quant à l’influence des droits que l’on possède sur le répertoire courant ? Peut-on retourner dans le répertoire parent avec ”cd ..” ? Pouvez-vous donner une explication ?

L'influence des droits que l'on possède sur le répertoire courant n'influe pas les droits que nous avons sur les fichiers, ils ne sont pas dépendant l'un de l'autre 

Parcontre depuis le répertoire courant il ne sera pas possible de le modifier 

### 9. Rétablissez le droit en exécution du répertoire test. Attribuez au fichier fichier les droits suffisants pour qu’une autre personne de votre groupe puisse y accéder en lecture, mais pas en écriture 
```
chmod g+r fichier
```
### 10. Définissez un umask très restrictif qui interdit à quiconque à part vous l’accès en lecture ou en écriture, ainsi que la traversée de vos répertoires. Testez sur un nouveau fichier et un nouveau répertoire.

```
umask 077 
touch test2
-rw------- root root 0 Sep 22 8:53 test2
```
### 11. Définissez un umask très permissif qui autorise tout le monde à lire vos fichiers et traverser vos répertoires, mais n’autorise que vous à écrire. Testez sur un nouveau fichier et un nouveau répertoire.
 
``` 
umask 022 
touch test3
mkdir test4
-rw-r--r-- 1 root root 0 Sep 22 8:59 test3
drwxr-xr-x 2 root root 6 Sep 22 8:59 test4
```
### 12. Définissez un umask équilibré qui vous autorise un accès complet et autorise un accès en lecture aux membres de votre groupe. Testez sur un nouveau fichier et un nouveau répertoire.

```
umask 037
umask -S
u=rwx,g=r,o=
```
### 13. Transcrivez les commandes suivantes de la notation classique à la notation octale ou vice-versa (vous pourrez vous aider de la commande stat pour valider vos réponses) :
```
chmod u=rx,g=wx,o=r fic / chmod 534 fic
```
```
chmod uo+w,g-rx fic en sachant que les droits initiaux de fic sont r--r-x--- / chmod 602 fic
```
```
chmod 653 fic en sachant que les droits initiaux de fic sont 711 / chmod rw-r-x--wx fic 
```
```
chmod u+x,g=w,o-r fic en sachant que les droits initiaux de fic sont r--r-x--- / chmod 520  fic 
```

### 14. Affichez les droits sur le programme passwd. Que remarquez-vous ? En affichant les droits du fichier /etc/passwd, pouvez-vous justifier les permissions sur le programme passwd ?

Avec la commande ci-dessous on peut voir qu'il y a seulement root qui a le droit de le modifier car il contient la liste de tous les utilisateurs. 
```
stat /etc/passwd
```
