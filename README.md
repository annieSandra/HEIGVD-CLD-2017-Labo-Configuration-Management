
# LABORATOIRE 7 - Configuration management

Dans ce laboratoire nous nous intéressons au gestionnaire de configuration. En effet, nous allons nous familiariser avec les outils de gestion de configuration comme ansible, déployer une application web dans un mode automatisé et enfin se familiariser avec un état de configuration voulu. 

## ETUDIANTS 

* FRANCHINI Fabien
* DONGMO NGOUMNAI Annie Sandra

## TABLE DES MATIERES 
1. [Tâche 1: Installation d'ansible](#t%C3%82che-1-installation-ansible)
2. [Tâche 2: Création d'une machine virtuelle dans amazon web service](#t%C3%82che-2-creation-machine-virtuelle-dans-amazon-web-service)
3. [Tâche 3: Configuration d'ansible pour la connection au gestionnaire de la VM](#t%C3%82che-3-configuration-ansible-connection-a-la-vm)
4. [Tâche 4: Installation de l'application web](#t%C3%82che-4-installation-application-web)
5. [Tâche 5: Test de l'état voulue de la configuration principale](#t%C3%82che-5-test-etat-voulue-de-la-configuration-principale)
6. [Tâche 6: Ajout d'un gestionnaire pour redemarrage de NGINX](#t%C3%82che-6-ajout-d-'-un-gestionnaire-pour-redemarrage-de-nginx)
7. [Tâche 7: Ajouter plus de gestionnaire de serveur](#t%C3%82che-7-ajouter-plus-de-gestionnaire-de-serveur)

## TÂCHE 1: INSTALLATION ANSIBLE
Nous avons choisi de travailler avec la machine linux version 14.04 LTS, ainsi nous avons installer python (necessaire pour installer ansible) et ansible comme vous pouvez le constater sur l'image suivante 
![installation d'ansible](assets/images/Tache1_1_installationAsible.png)

## TÂCHE 2: CREATION MACHINE VIRTUELLE DANS AMAZON WEB SERVICE

Nous avons déjà vu lors du laboratoire sur Amazon web service comment faire pour créer une instance EC2 et s'y connecté en ssh ou http.

-creation de la clé paire public/privé si elle existe pas déjà : dans notre cas nous avions déjà une clé dans la région de Virginie du nord voire screenshort
![creation VM](assets/images/Tache2_1_cle_paire.png)

-creation du sécurity groupe autorisant les connections SSH, HTTP et HTTPS entrant
![creation VM](assets/images/Tache2_2_creation_security_Groupe.png)

-creation de l'instance ec2(t2.medium, Ubuntu 16.04) et attribution de la clé, du security groupe à l'instance 
![creation VM](assets/images/Tache2_3_creation_vm.png)

-après création de lancement et verification de la connection ssh
![creation VM](assets/images/Tache2_4_connection_ssh_instance.png)


## TÂCHE 3: CONFIGURATION ANSIBLE POUR CONNECTION A LA VM
Pour connecter ansible à la VM nous avons:
-crée un repertoire playbooks contenant un fichier de configuration hosts dans lequel nous allons spécifier les information utiles à la connection en ssh de l'instance (la clé privée, adresse public et type de la machine). Dans notre cas en plus de ces informations nous avons dû spécifier la version de python(version 3) qu'ansible devrais utilisé (ne marchait pas avec la version 2.7 ).Verification du bon fonctionnement de la config avec un ping
![configuration ansible](assets/images/Tache3_3_verification_fonctionnement_ansible.png)

Pour faciliter la configuration d'ansible nous allons utiliser un vrai fichier de config ansible.cfg qui nous permettre de modifier certaine valeures par défaut. Après ce changement on n'aura plus besoin de spécifier l'inventaire dans la commande on obtient donc les resultats suivant après les manipulations:
![configuration ansible](assets/images/Tache3_4_test_success.png)

## TÂCHE 4: INSTALLATION APPLICATION WEB 
ici, pour installer l'application web nous avons suivit les étapes données pour la creation, construction du playbooks et obtenu le resultat suivant lors de son premier lancement:
![configuration ansible](assets/images/Tache4_1_installation_web_application.png)
![configuration ansible](assets/images/Tache4_2.png)

Et le test du bon focntionnement de l'installation à partir d'un browser nous a donné le résultat suivant: 
![configuration ansible](assets/images/Tache4_3_testing_new_website.png)


## TÂCHE 5: TEST ETAT VOULUE DE LA CONFIGURATION PRINCIPALE

## TÂCHE 6: AJOUT D'UN GESTIONNAIRE POUR REDEMARRAGE DE NGINX

## TÂCHE 7: AJOUTER PLUS DE GESTIONNAIRE DE SERVEUR
