# TP 3 - Utilisateurs, groupes et permissions

## Exercice 1. Gestion des utilisateurs et des groupes 

1. groupadd dev et groupadd infra m'ont pemrit de créer ces deux groupes et la commande grep de les visualiser 

![image](https://user-images.githubusercontent.com/80455771/191514345-b7a5f22b-84d8-4718-a353-f0b8544de7ac.png)

2. La commande useradd -m m'a permit de créer l'utilisateur avec son dossier personnel et la commande usermod -s de leur attribuer bash comme shell 

![image](https://user-images.githubusercontent.com/80455771/191516962-655be3a0-5dba-4241-977d-8c052fdd993f.png)

3. L'ajout des utilisateurs dans leur groupe réspectifs 

![image](https://user-images.githubusercontent.com/80455771/191517490-59d9c6a2-a574-43a9-9c4c-1bac367efa08.png)

4. Les commandes getent et grep permettent d'afficher les membres d'un groupe 

![image](https://user-images.githubusercontent.com/80455771/191518392-f9e05c05-0b87-42bd-9359-34bf51915e8f.png)

5. La commande chgrp -R permet de ùettre un groupe propriétaire d'un répertoire

![image](https://user-images.githubusercontent.com/80455771/191520299-657908ce-3337-463d-9fae-1482fe91c8cd.png)

6. La commande usermod ... -g ... permet de remplacez le groupe primaire des utilisateurs 

![image](https://user-images.githubusercontent.com/80455771/191522071-00a80fdf-a736-4b4d-9746-322813b7f3aa.png)

7. Création des deux répértoires :

![image](https://user-images.githubusercontent.com/80455771/191522794-e9f6f9d0-a2db-4f29-9337-0fdd99b23ae3.png)

Attribution des groupes à leur répértoires :

![image](https://user-images.githubusercontent.com/80455771/191523804-fda28cc0-f225-483b-a321-044db5629d53.png)

Attribution des droits aux groupes :

![image](https://user-images.githubusercontent.com/80455771/191524454-8840ccb6-8a74-4483-a236-a5931b1624d4.png)

8. Pour que seul le prorpiétaire d'un fichier ait le droit de renommer ou supprimer ce fichier il faut faire chmod u+rwx 

9. Oui car je suis en admin 

![image](https://user-images.githubusercontent.com/80455771/191526398-570d2b2c-5a4b-4269-904e-4a815dda9fa1.png)

10. Pour activer un compte d'utilisateur il faut lui attribuer un mot de passe 

![image](https://user-images.githubusercontent.com/80455771/191527438-d6205229-85f5-46f0-a6a6-0ddb9112b39a.png)

11. On obtient l'uid et le gid d'Alice grâce à la commande id 

![image](https://user-images.githubusercontent.com/80455771/191603785-3aef65e6-c0ac-464d-996b-f3b029ae515a.png)

12. Tout comme la question précédente, on utilise la commande id mais cette fois en précisant l'uid 

![image](https://user-images.githubusercontent.com/80455771/191604080-8e2c4982-7add-4a87-b9a9-689c5a564800.png)

13. Avec la commande grep il est possible de retroyver l'id d'un groupe 

![image](https://user-images.githubusercontent.com/80455771/191606454-03417704-0b96-48f9-a0fa-d84566b3f802.png)


14. Le groupe qui a pour id 1002 est le groupe dev

![image](https://user-images.githubusercontent.com/80455771/191606104-1818be7f-e260-4588-aa50-f93a52b7b11f.png)

15. Avec la commande gpasswd --delete il est possible de retirer un utilisateur d'un groupe 

![image](https://user-images.githubusercontent.com/80455771/191606782-e0bb0165-c65e-4737-8ccb-a6e47ced5115.png)



