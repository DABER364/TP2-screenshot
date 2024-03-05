# Exercices - TP1

## Rétrospective sur le processus
### Combien de temps (moyenne, minimum, maximum ) votre équipe prenait-elle pour implémenter une issue?
Moyenne : 2 heures

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
Moyenne : 3 issues

Minimum : 2 issues

Maximum : 4 issues

### Combien de pull request (moyenne, minimum, maximum ) étaient en cours de review en même temps?
Moyenne : 1 pull-requests

Minimum : 0 pull-requests

Maximum : 3 pull-requests

### Après avoir mesuré ces métriques, voici les réflexions que vous devez poser en équipe et répondre au document d’exercice : 

#### Selon vous, est-ce que les issues/pull-requests prenaient trop de temps à être terminer? Ou pas assez? Quel serait le temps idéal (approximatif) pour chacun ?

Non, les pull-request et les issues ne prenaient pas trop de temps à être implémentés. Le temps idéal pour les issues devrait être de 1 à 2 jours et de 1 jour pour les pull-requests.

#### Quel est le lien entre la taille de ces issues/pull-requests et le temps que ça prenait à les terminer?

Il est évident qu'il existe une corrélation entre la taille des tâches et le temps nécessaire pour les terminer. Les tâches plus grandes demandent plus de temps pour être complétées, tandis que les tâches plus petites peuvent être achevées plus rapidement. Cependant, la fragmentation excessive des tâches peut également entraîner une perte de temps due à la gestion accrue des transitions entre les tâches.

#### Donnez au moins 3 trucs pour améliorer votre processus (tailles des issues/pr, communication, code-reviews, uniformisation, etc)
Code-reviews: On devrait faire plus de code-reviews, l’équipe utilise beaucoup Prettier pour avoir du bon code. Au moins un membre de l’équipe devrait s’assurer que quand quelqu’un push le code en entier, on vérifie chaque ligne pour faire du bon code.

Communication: Notre communication n'est pas totalement optimale, nous avons planifié d’avoir une rencontre hebdomadaire le vendredi à 15h, mais nous ne respectons pas totalement cette règle, on la déplace souvent et on planifie souvent une rencontre dernière minute pour la remise.

Tailles des issues: Les grosses issues comme les tests unitaires, peuvent être fragmentées en  tâches plus petites et gérables pourrait accélérer le processus. Il est important de trouver un équilibre entre la taille des tâches pour éviter à la fois la surcharge de gestion et la fragmentation excessive.

## Architecture
### Décrire les rôles de classes principales:
#### RestaurantService :
Rôle : La classe RestaurantService est responsable de gérer les opérations liées aux restaurants. RestaurantService est un contrôleur associé aux classes Restaurant qui sont liées à l’infrastructure, l’application et les entities.

#### ReservationService :
Rôle : La classe ReservationService est chargée de gérer les réservations de tables au sein du restaurant. ReservationService est un contrôleur associé aux classes Restaurant qui sont liées à l’infrastructure, l’application et les entities.

### ReservationRessource:
Rôle : ReservationRessource gère les requêtes entrantes des réservations et dirige le flux de contrôle vers les ressources appropriées comme la classe ReservationResponse.
#### RestaurantRessource
Rôle :  Restaurant Ressources gère les requêtes entrantes des réservations et dirige le flux de contrôle vers les ressources appropriées comme les classes (RestaurantResponse et RestaurantResponseAssembler)

### Expliquer vos choix d’architecture:
Nous avons choisi l’architecture Horizontale Slicing pour notre projet. Le but est que chaque couche de la fonction est ensuite développée indépendamment et le système est construit de bas en haut. Cette approche permet de créer des parties entièrement fonctionnelles et utilisables du système, même si l'ensemble du système n'est pas complet.
### Notez les endroits ou les relations semblent suspectes et trouver des solutions potentielles
La création d'une réservation, la requête doit être dans restaurant, mais nous l’avons mis dans réservation, ce qui est suspect, car cela implique que la responsabilité de gérer la création des réservations est attribuée à la classe qui représente les réservations elles-mêmes. Une solution potentielle serait de déplacer la logique de création de réservation vers la classe ReservationService. Cela permettrait de clarifier les responsabilités de chaque classe et de rendre le code plus modulaire et plus facile à comprendre. De plus, cela favoriserait la réutilisation du code, car la logique de création de réservation pourrait être partagée entre différentes parties du système qui ont besoin de créer des réservations.




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
Pull request #39
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/72586f69-1432-455d-9ecf-c5423f62742e)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/f800eebf-60a4-4ab6-8c43-e2f52915c189)
Pull request #40
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/e01ec3e8-9248-47b8-99c6-d1a40bbf91cb)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/4a1cb473-80e4-450d-a6f5-6f91e1f44f2d)
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/e73b05b1-8578-4d10-97c6-0ed76408ea14)
Pull request #42
![image](https://github.com/DABER364/TP2-screenshot/assets/119546325/820ff181-2d4a-4371-a0dc-d2d74340a232)

## Arbre de commits
À faire
![image](https://github.com/Meleksebri/images/assets/91430760/8c72f6fc-de5b-4c42-bc3c-667eb585634f)