# Q1 : Décrire ce que renvoie la méthode qui liste les questions ?
Réponse:
L'API permet de lister les questions via l'endpoint /quizz/questions. Les questions sont retournées sous forme de liste JSON.
# Q2 : Décrire ce que renvoie la méthode qui liste les propositions d'une question ?
Réponse:
Pour récupérer les propositions, il suffit d'appeler l'endpoint /quizz/questions/{id}/proposals où {id} est l'ID de la question.
# Q3 : Décrire ce que renvoie la méthode qui évalue des réponses ?
Réponse:
L'évaluation des réponses est réalisée via l'endpoint /quizz/proposals/evaluate, qui prend un tableau d'IDs de propositions et renvoie le résultat.
# Q4 : Quelle est la valeur de la RSS utilisée par l'api quarkus en mode JVM ?
Réponse:
RSS : 2332 Ko
Cette valeur représente la mémoire physique utilisée par le processus Quarkus exécuté en mode JVM.
# Q5: Quel est le temps et la taille de la réponse  de la méthode qui liste les questions
Temps : 26.86092 secondes
Taille : 883 bytes

# Q6: Quel est le temps et la taille de la réponse  de la méthode qui liste les propositions d'une question
Temps : 14.67699 secondes
Taille : 767 bytes

# Q7: Quel est le temps et la taille de la réponse  de la méthode qui évalue les réponses
Temps : 0.019194 secondes
Taille : 1 byte

# Q8 : Empreinte mémoire en mode natif ?
Réponse:
La taille de l'exécutable natif api-quarkus-1.0.0-SNAPSHOT-runner est d'environ 12.3 Mo (ou autre taille affichée via ls -lh).
# Q9: Temps et  taille  réponse   liste les questions
Temps : 18.853543 secondes
Taille : 883 bytes

# Q10: Temps et  taille  réponse  liste des propositions
Temps : 11.533135 secondes
Taille : 609 bytes
# Q11: Temps et  taille  réponse  évaluation les réponses
Temps : 0.002474 secondes
Taille : 1 byte

# Q12:  Proposition 1
Description: L'objectif est de réduire la consommation mémoire de l'application Quarkus. J'ai modifié la configuration de la base de données H2 pour optimiser son utilisation en mémoire en utilisant le mode léger.
Temps: 0.123s
Taille:
Avant l'optimisation : 2388 Ko (PID : 8175).
Après l'optimisation : 2232 Ko (PID : 9995).
Réduction : 156 Ko.

# Q13:  Proposition 2
Description:
Temps:
Taille:

# Q14:  Proposition 3
Description:
Temps:
Taille:

# Q15:  Proposition 4
Description:
Temps:
Taille: