# Exercices 2- TP2

## Rétrospective sur le processus
### Combien de temps (moyenne, minimum, maximum ) votre équipe prenait-elle pour implémenter une issue?
Moyenne : 3 heures

Minimum : 30 minutes

Maximum : 6 heures

### Combien de temps (moyenne, minimum, maximum ) votre équipe prenait-elle pour intégrer une pull-request? (review + correctifs)
Moyenne : 30 minutes

Minimum : 10 minutes

Maximum : 6 heures

### Combien de personnes (moyenne, minimum, maximum ) travaillaient sur chaque issue? (individuel, paire, équipe, etc )
Moyenne : paire

Minimum : individuel

Maximum : équipe (5 personnes)

### Combien de personnes (moyenne, minimum, maximum ) reviewaient chaque pull-request ?
Moyenne : 2 personnes

Minimum : 1 personnes

Maximum : 3 personnes

### Combien d’issue (moyenne, minimum, maximum ) étaient en cours d’implémentation en même temps?
Moyenne : 2 issues

Minimum : 1 issues

Maximum : 3 issues

### Combien de pull request (moyenne, minimum, maximum ) étaient en cours de review en même temps?
Moyenne : 1 pull-requests

Minimum : 0 pull-requests

Maximum : 3 pull-requests

#### Selon vous, est-ce que les issues/pull-requests prenaient trop de temps à être terminer? Ou pas assez? Quel serait le temps idéal (approximatif) pour chacun ?

Non, les pull-request et les issues ne prenaient pas trop de temps à être implémentés. Le temps idéal pour les issues devrait être de 4 heures et de 2 heures pour les pull-requests. Les 2 heures pour les pulls-requests permettent à l’équipe de faire un bon code-review et de s’assurer que tout fonctionne.

#### Quel est le lien entre la taille de ces issues/pull-requests et le temps que ça prenait à les terminer?

Il est évident qu'il existe une corrélation entre la taille des tâches et le temps nécessaire pour les terminer. Les tâches plus grandes demandent plus de temps pour être complétées, tandis que les tâches plus petites peuvent être achevées plus rapidement. Cependant, la fragmentation excessive des tâches peut également entraîner une perte de temps due à la gestion accrue des transitions entre les tâches.

#### Donnez au moins 3 trucs pour améliorer votre processus (tailles des issues/pr, communication, code-reviews, uniformisation, etc)
Code-reviews:  Il faut impliquer au moins trois personnes dans les revues de code pour permettre d'apporter différents points de vue et de détecter des erreurs ou des améliorations potentielles. Par exemple, si seulement une ou deux personnes examinent le code, il y a un risque que des erreurs ou des problèmes potentiels passent inaperçus. De même, si les revues de code ne sont pas effectuées régulièrement ou de manière cohérente, cela peut entraîner des retards dans la détection et la correction des problèmes, ce qui peut affecter la qualité globale du logiciel.

Communication: Le problème de communication que nous rencontrons affecte notre capacité à rester organisés et à respecter nos engagements. Bien que nous ayons prévu des réunions hebdomadaires le vendredi à 15h pour discuter de nos progrès et de nos plans, nous avons du mal à respecter cette routine. Souvent, nous déplaçons ces réunions ou en planifions de nouvelles à la dernière minute pour discuter des tâches en cours ou des remises imminentes. Pour améliorer cette situation, nous devons nous engager à respecter nos réunions régulières, à communiquer de manière proactive sur notre progression et nos besoins, et à planifier nos activités de manière plus stratégique pour éviter les rushes de dernière minute.

Dépendances des issues et PR: Le problème avec les dépendances entre les issues et les pull requests, c'est qu'elles peuvent souvent entraîner des retards dans notre progression. Par exemple, lorsque quelqu'un veut commencer à travailler sur sa partie du projet, il se rends compte qu'il y a une tâche dont il a besoin qui est toujours en cours par un autre membre de l'équipe. Cela signifie qu'il doit attendre que cette tâche soit terminée avant de pouvoir commencer, ce qui peut ralentir le rythme de travail global. De plus, cela peut rendre difficile la planification des activités et des échéances, car nous dépendons souvent des autres pour achever leurs tâches avant de pouvoir avancer. .

## Architecture
### Diagramme
![image](https://github.com/DABER364/TP2-screenshot/assets/91430760/e310b0f9-ca1a-408f-b648-71222f178d6d)
### Décrire les rôles de classes principales:
#### RestaurantService :
Rôle : 
Gère les opérations liées aux restaurants. Il sert de contrôleur associé aux classes liées à l'infrastructure, à l'application et aux entités.

Responsabilités :
- Implémenter la logique métier liée à la gestion des restaurants.
- Se connecter à la couche d'infrastructure pour interagir avec les données liées aux restaurants.
- Orchestrer le flux des opérations dans le domaine des restaurants.

#### ReservationService :
Rôle : 
Gère les opérations de réservation de tables au sein du restaurant.

Responsabilités :
- Implémenter la logique métier liée aux réservations de tables.
- Interagir avec la couche d'infrastructure pour stocker et récupérer les données de réservation.
- Coordonner les actions et événements liés aux réservations dans le système du restaurant.

### ReservationRessource:
Rôle : 
Gère les demandes de réservation entrantes et dirige le flux de contrôle vers les ressources appropriées, telles que la classe ReservationResponse.

Responsabilités :
- Recevoir et gérer les demandes de réservation entrantes des appels API.
- Acheminer les demandes vers les services appropriés, tels que ReservationService, pour les traiter.
- Convertir et formater les données liées aux réservations pour les réponses.

#### RestaurantRessource
Rôle : 
Gère les demandes liées aux restaurants entrantes et dirige le flux de contrôle vers les ressources appropriées, telles que les classes RestaurantResponse et RestaurantResponseAssembler.

Responsabilités :
- Gérer les demandes entrantes liées aux restaurants des appels API.
- Acheminer les demandes vers les services appropriés, tels que RestaurantService, pour les traiter.
- Formater et assembler les données liées aux restaurants pour les réponses.
- Gérer éventuellement des tâches telles que l'authentification, la validation et la gestion des erreurs liées aux demandes de restaurants.

### RestaurantFactory:

Rôle : 
Responsable de créer des instances d'entités de restaurant à partir du service.

Responsabilités :
- Créer de nouvelles instances d'entités de restaurant en utilisant les données fournies par le service de restaurant.
- Gérer la création et l'initialisation des objets d'entités de restaurant conformément aux spécifications définies.

### ReservationFactory:

Rôle : 
Responsable de créer des instances d'entités de réservation à partir du service de réservation.

Responsabilités :
- Créer de nouvelles instances d'entités de réservation en utilisant les données fournies par le service de réservation.
- Gérer la création et l'initialisation des objets d'entités de réservation conformément aux spécifications définies.
- Peut implémenter des logiques spécifiques liées à la création de réservations, telles que la vérification des disponibilités, la validation des données, etc.

### Expliquer vos choix d’architecture:
Dans cette architecture, nous adoptons une approche de découpage horizontal où chaque couche (services, ressources, repositories) est structurée en fonctionnalités spécifiques. Par exemple, dans la couche de services, chaque service est dédié à une fonctionnalité du système, comme la gestion des restaurants ou des réservations. De même, dans la couche de ressources, chaque ressource gère les requêtes liées à une fonctionnalité particulière exposée par l'API.

Dans le choix de cette architecture, plusieurs considérations ont été prises en compte pour garantir la robustesse et la maintenabilité du système. Tout d'abord, la séparation claire des responsabilités à travers les différentes couches (services, ressources, repositories) permet une meilleure organisation du code. Chaque couche est dédiée à des fonctionnalités spécifiques, comme la gestion des restaurants ou des réservations, ce qui rend le code plus lisible et plus compréhensible.

En structurant l'architecture de cette manière, nous favorisons également la maintenabilité du système. Les modifications ou les ajouts de fonctionnalités peuvent être effectués de manière plus fluide, car chaque partie du système est isolée et peut être modifiée sans impacter les autres parties. De plus, cette modularité facilite également les tests unitaires et les tests d'intégration, ce qui contribue à la fiabilité du système.

### Notez les endroits ou les relations semblent suspectes et trouver des solutions potentielles

Dans l'architecture proposée, quelques problèmes potentiels peuvent être identifiés :

Complexité accrue d'intégration :

- Problème : Avec de nombreuses fonctionnalités distinctes, l'intégration du code peut devenir plus complexe et nécessiter une gestion plus minutieuse.
- Solution potentielle : Utiliser des outils d'automatisation d'intégration et des pratiques de déploiement continu pour simplifier et accélérer le processus de déploiement.

Difficultés de test :
- Problème : 
Tester chaque fonctionnalité individuellement peut être simple, mais tester les interactions entre les fonctionnalités peut devenir complexe.
- Solution potentielle : 
Mettre en place des tests d'intégration pour vérifier les interactions entre les fonctionnalités et utiliser des outils de test automatisés pour améliorer l'efficacité des tests.

Surévaluation de la modularité :
- Problème : Trop de découpage horizontal peut entraîner une sur-modularité, ce qui rend le système complexe et difficile à comprendre.
- Solution potentielle : Évaluer régulièrement la pertinence de la modularisation et regrouper les fonctionnalités similaires lorsque cela est approprié pour simplifier le système.

Difficulté à maintenir la cohérence globale :
- Problème : Avec de nombreuses fonctionnalités autonomes, il peut être difficile de maintenir une cohérence globale dans le système.
- Solution potentielle : Établir des normes et des conventions de codage claires, ainsi que des processus de revue de code pour garantir une cohérence dans l'ensemble du système.




# Screenshot
## GitHub Project
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/ffc075b2-c64e-4538-9b34-f692de724f4c)

## Milestone
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/fc97a4d8-188b-4bcf-9cbc-9d5f80d75902)

## Issues
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/26bc7b20-aaae-4865-8259-7455fe122fc4)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/78f7c8cb-721f-4191-8959-f3b41558c77d)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/b31d406c-be30-4aab-bfd4-738bd2421cd5)


## Pull request

![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/72586f69-1432-455d-9ecf-c5423f62742e)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/f800eebf-60a4-4ab6-8c43-e2f52915c189)

![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/e01ec3e8-9248-47b8-99c6-d1a40bbf91cb)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/4a1cb473-80e4-450d-a6f5-6f91e1f44f2d)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/e73b05b1-8578-4d10-97c6-0ed76408ea14)

![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/820ff181-2d4a-4371-a0dc-d2d74340a232)

## Arbre de commits
![image](https://github.com/DABER364/TP2-screenshot/assets/91430760/87220caf-bf65-45bf-8470-c632c4a67f1f)
![image](https://github.com/DABER364/TP2-screenshot/assets/91430760/a8544f3f-797b-4765-9732-e604ade2fed0)


