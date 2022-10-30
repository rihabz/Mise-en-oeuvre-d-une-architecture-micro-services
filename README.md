# Mise-en-oeuvre-d-une-architecture-micro-services!

Structure du projet :

![Capture d’écran 2022-10-30 201837](https://user-images.githubusercontent.com/85801662/198897415-2405e7fa-93d2-40d8-94b3-9101d12b55e4.jpg)


# Etape 1 : Création du projet Customer-Service :!

  Dans ce projet nous avons créée plusieurs packages et des classes notamment :
  	
   La classe Customer dans le package entité
    
   La classe CustomerRepository dans le package repositories 
   
   Les classes CustomerResponseDTO et CustomerRequestDTO dans le package DTO.
	
   L’interface CustomerService ainsi que l’implémentation de cette classe (CustomerServiceImpl) dans le package service.

   La classe CustomerMapper dans le package Mapper.

Et maintenant nous allons ajouter 2 clients pour tester :

![image](https://user-images.githubusercontent.com/85801662/198897480-052330cd-afb4-4183-96e2-4fa8f7705d1e.png)


 
 
Passons maintenant au test avec Postman :
 
 ![image](https://user-images.githubusercontent.com/85801662/198897555-2ba914d5-9fff-46c9-a401-e3f0cb1ac6c0.png)

 
Utilisons open-api pour voir la documentation de notre application web :

![image](https://user-images.githubusercontent.com/85801662/198897569-06efb95f-19ac-4d46-9b07-794e134fea2e.png)

 
Swagger :

![image](https://user-images.githubusercontent.com/85801662/198897595-c23af1a8-28ea-440c-a233-1e3c694ba8fa.png)

 
 
#Etape 2 : création du projet Billing service

-Nous allons suivre les mêmes étapes que le projet précédent sauf que nous allons ajouter la dépendance openFeign pour qu’il puisse communiquer avec l’autre micro-service Customer-Service.
 
![image](https://user-images.githubusercontent.com/85801662/198897623-946fdf4c-e016-4a35-a15a-1f460a9c3565.png)


![image](https://user-images.githubusercontent.com/85801662/198897650-0466a44b-ad2e-4aa2-a692-668f6db157a7.png)

 
Testons maintenant notre projet :
 
 ![image](https://user-images.githubusercontent.com/85801662/198897672-ec01ad32-e5b2-4982-a439-8248d7e58e3c.png)

![image](https://user-images.githubusercontent.com/85801662/198897685-d83fa4c6-2619-48b5-b66a-f5dd9a2597b5.png)


#Etape 3 : la création du projet adria-Eureka-service

On ajoute l’annotation dans la classe main :
 
![image](https://user-images.githubusercontent.com/85801662/198897704-57f62648-1156-45db-b784-4658ff06a2be.png)

 
Puis on démarre l’application et on consulte localhost :8761 :
 
La registration des 2 services que nous avons créé :

![image](https://user-images.githubusercontent.com/85801662/198897723-05fe0ded-2ac0-4eeb-a04f-1414955a8afe.png)

 
Essayons Maintenant de visualiser les informations d’une facture :

![image](https://user-images.githubusercontent.com/85801662/198897747-1f201fa1-dec7-4776-9edf-64b6611d6489.png)

 
La liste de tous les factures :

![image](https://user-images.githubusercontent.com/85801662/198897759-0b211cd5-a4f8-477c-a06b-4ecce8ce431d.png)


Les Factures d’un client :

![image](https://user-images.githubusercontent.com/85801662/198897793-005f9c3a-bf63-42a2-9533-5baf8a18eee7.png)

 
#Etape 4 :la création de la Gateway :
 
![image](https://user-images.githubusercontent.com/85801662/198897865-4364ff95-df9e-420b-99cf-23668c0de94a.png)


Désormais nous pouvons grâce à la Gateway d’envoyer des requêtes à travers le nom du service : 

 ![image](https://user-images.githubusercontent.com/85801662/198897873-9802b6bd-f83c-4ca2-bbbd-836890ec8376.png)

 
Consulter le client ayant l’ID C01 :

![image](https://user-images.githubusercontent.com/85801662/198897883-f9484322-388e-4029-9853-08362c5fb759.png)

 
Consulter la liste des factures :

![image](https://user-images.githubusercontent.com/85801662/198897898-ee156e4c-369a-4c1b-85b2-018298f0d811.png)
 
 
Consulter une facture :

![image](https://user-images.githubusercontent.com/85801662/198897913-b4a4f07f-8e42-4fec-bdce-08d157529604.png)

 
Essayons d’ajouter une nouvelle facture au client ayant l’id C01 :
 
 ![image](https://user-images.githubusercontent.com/85801662/198897924-b22e6fdd-cf5d-4589-b630-0352f97b2064.png)


Et quand nous essayons de créer une facture d’un client qui n’existe pas une exception est généré :

![image](https://user-images.githubusercontent.com/85801662/198897934-71de6066-2b1f-43b4-b40d-9c2f9e684227.png)

 


