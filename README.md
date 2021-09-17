
## Exemple test unitaire des API REST Spring Boot
Ce projet montrera comment implémenter des tests unitaires pour les API REST dans un environnement Spring Boot. 
Ce projet se concentre sur le test de la couche métier qui se compose des API, des points de terminaison 
et des contrôleurs au sein de la base de code.<br/>
Nous écrirons des cas de test pour les opérations de base de données telles que CRUD 
(Create, Read, Update et Delete) d'une entité - `PatientRecord`.<br/>

### Introduction
---
Le test du système est une phase importante dans un cycle de vie de développement logiciel (SDLC) . 
Les tests favorisent la fiabilité et la robustesse du code et garantissent des logiciels de haute qualité livrés 
aux clients s'ils sont correctement mis en œuvre.<br/>

Les tests ont gagné en importance depuis que le développement piloté par les tests (TDD) est devenu un processus 
important dans le développement de logiciels. Le développement piloté par les tests implique la conversion des 
exigences en cas de test et l'utilisation de ces cas de test pour contrôler la qualité du code.<br/>

Les API REST sont généralement testées rigoureusement lors des **tests d'intégration**. 
Cependant, un bon développeur doit tester les points de terminaison REST avant même l'intégration dans leurs tests unitaires , 
car ils constituent une partie vitale du code car il s'agit du seul point d'accès de chaque entité souhaitant utiliser 
les services du serveur.

### Prérequis
---
Pour ce projet, vous auriez besoin des spécifications suivantes :<br/>
- Spring Boot v2.0+
- JDK v1.8+
- **JUnit 5** - Le framework de test le plus populaire et le plus utilisé pour Java.
- **Mockito** - Cadre à usage général pour les services et objets de moquerie et de stub.
- **MockMVC** - Module de Spring pour effectuer des tests d'intégration lors des tests unitaires.
- Maven 3+ ou Gradle 4+ - outil de construction
- Tout IDE prenant en charge Java et Spring Boot (Spring Tool Suite (STS), IntelliJ, VSC, NetBeans, etc.)
- SGBD PostgreSQL
- Postman, curl ou n'importe quel client HTTP

### Dependances Maven de tests unitaires
---
Dans ce projet nous allons utiliser les dependances Maven suivants :<br/>
- **Spring Web** - Pour inclure Spring MVC et utilise le tomcat comme conteneur intégré par défaut.
- **Spring Data JPA** - API de persistance Java et Hibernate pour persister les données dans la base de données.
- **Spring Boot DevTools** - dépendance pour les rechargements automatiques ou le rechargement en direct des applications.
- Pilote **PostgreSQL** - Pilote JDBC pour la base de données.
- **spring-boot-starter-test « Starter »** - Bibliothèques pour les tests unitaires des applications Java.
- **junit-jupiter-engine** - Pour exclure JUnit 4 de la dépendance `springboot-starter-test`.
- **mockito-core** - Dépendances pour activer Mockito dans votre système.

### Annotations utiliséss
---
* `@WebMvcTest` annotation pour que les dépendances qui seront chargées lorsque vous exécuterez la classe de test soient celles qui affectent directement la classe du contrôleur.
* `@Test` afin que JUnit puisse les récupérer et les mettre dans une liste de tous les tests à exécuter.

### Exécuter les tests
---
**MockMVC** est une solution pour permettre les tests unitaires de la couche Web.<br/>
MockMVC permet de tester la couche Web (couche métier AKA ou couche de contrôleur) lors des tests unitaires 
avec les configurations appropriées, mais sans avoir à déployer l'application.<br/>

À l'intérieur de `src/test/java` on crée `PatientRecordControllerTest.java`, où nous écrirons des cas de test unitaires pour l'entité `PatientRecord`.

`$ mvn clean test` - Exécutez toutes les classes de test unitaire.<br/>

- **Test unitaire des gestionnaires de requêtes GET** - test la capacité des API à récupérer des enregistrements individuels et identifiables, ainsi qu'une liste de tous les enregistrements.
- **Test unitaire des gestionnaires de requêtes POST** - test sa capacité à conserver les enregistrements.
- **Test unitaire des gestionnaires de requêtes PUT** - mettre à jour un enregistrement dans la base de données, si l'ID ne l'est pas nullet qu'il appartient à un enregistrement..
- **Test unitaire des gestionnaires de requêtes DELETE** - supprimer un enregistrement dans la base de données.

### Installation
---
`$ git clone https://github.com/darvin-rakotomalala/spring-boot-rest-api-unitTesting.git` <br/>
`$ cd spring-boot-rest-api-unitTesting.git` <br/>
`$ mvn clean test`
