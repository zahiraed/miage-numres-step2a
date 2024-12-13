

# Rappels

## Sujet : Faire Burger Quizz !
Vous avez 4 séances de TD/TP pour  produire un site web qui permettent de répondre à des questions et  donne le score.


## Environnement
L'ensemble des  4 TD/TP sont à réaliser sur **_Gitpod_**.
Vous devez réutiliser le compte que vous avez crée durant la première séance.

## Déroulement

Comme au premier TP, vous devez suivre le même processus que pour contribuer à un projet:
1. Dupliquer (**Forker**) le projet github
1. Modifier / compléter des fichier du repo. forké
1. Commiter vos modifs sur votre repo.
1. Proposer vos modifications sur le repo. parent (**PullRequest**)

## Architecture
L'architecture   générale de  l'application  Burger Quizz est la suivante :
![Capture d'écran](assets/Archi.png)

Une application web consomme une API Rest Quarkus  qui s'appuie sur une base de données relationnelles en  mémoire **H2**.

## TP2 - Implementation Back-End

La stack technique a été choisie durant le TD/TP1 : Quarkus.

Votre client  veut une api de quizz en français qui :
* Liste des questions
* Liste des propositions d'une question
* Evalue les réponses

**L'objectif de ce second TP est de produire une API Rest Quarkus qui réponde à ce besoin tout en appliquant un maximum de bonnes pratiques d'éco-conception.**
Vous partez d'un socle existant qu'il faut améliorer.

# Fork du projet
L'objectif est de créer une copie du projet 'miage-numres-step2a' sur votre compte github.

1. Se rendre sur le projet github [miage-numres-step2a] (https://github.com/aepsilon-tek/miage-numres-step2a)
1. Fork du projet grâce au bouton **Fork**
![Capture d'écran](assets/Fork.png)

# lancement de GitPod

Pour utiliser  **GitPod** avec votre projet forké, il suffit d'ouvrir  l'url suivant dans votre navigateur :
**https://gitpod.io/#** + **URL_REPO_GITHUB**

Avec un repo _https://github.com/miage3-ae/miage-numres-step2a_ alors l'url est : **https://gitpod.io/#https://github.com/miage3-ae/miage-numres-step2a**


# Tester l'existant
1. Lancer application `quarkus` en mode développement dans un Terminal
1. Tester dans un second Terminal que l'api répond : ```curl -w "\n" http://localhost:8080/quizz/questions ```
1. Modifier la valeur de la propriété `quarkus.rest-client.translate-client-api.url` dans le fichier application.properties
1. ReTester
1. Tester la recupération des propositions d'une question :  ```curl -w "\n" http://localhost:8080/quizz/questions/1/proposals ```
1. Tester l'evaluation des reponses : ```curl -w "\n" http://localhost:8080/quizz/proposals/evaluate  -H 'accept: application/json'  -H 'content-type: application/json; charset=UTF-8' --data-raw '[{"id":1},{"id":2}]' ```
1. Répondre aux questions Q1,Q2 et Q3 du fichier **_Questions.md_**
1. Commiter  & Pusher le fichier **_Questions.md_**

# Evaluer l'existant
## En mode JVM
1. Construire l'application en mode JVM
1. Lancer l'applicatif construit : `java -jar target/quarkus-app/quarkus-run.jar`
1. Mesure la mémoire consommée : `ps -e -o pid,rss,args | grep quarkus-run`
1. Tester les méthodes de l'api
    1. Liste des questions : `curl -w "\nTime: %{time_total}s\nSize: %{size_download} bytes\n" http://localhost:8080/quizz/questions`
    1. Liste des propositions : `curl -w "\nTime: %{time_total}s\nSize: %{size_download} bytes\n" http://localhost:8080/quizz/questions/1/proposals`
    1. Evaluation des réponses : `curl -w "\nTime: %{time_total}s\nSize: %{size_download} bytes\n" http://localhost:8080/quizz/proposals/evaluate  -H 'accept: application/json'  -H 'content-type: application/json; charset=UTF-8' --data-raw '[{"id":1},{"id":2}]'`
1. Répondre aux questions Q4,Q5,Q6 et Q7 du fichier **_Questions.md_**
1. Commiter  & Pusher le fichier **_Questions.md_**

## En mode Natif (Optionnel)
1. Construire l'application en mode Natif
1. Lancer l'applicatif construit : `./target/api-quarkus-1.0.0-SNAPSHOT-runner`
1. Répondre aux questions Q8 à Q11 du fichier **_Questions.md_**
1. Commiter  & Pusher le fichier **_Questions.md_**


# Amélioration

Vous devez désormais regarder / analyser / critiquer / améliorer le code existant en appliquant les bonnes pratiques d'éco-conception.
Pour faire vos tests,  vous pouvez lancer l'application en mode ** dev **.
Le log des requêtes SQL est activé.

Pour chacune des propositions que vous faites, vous devez :
  1. Decrire la proposition dans le fichier **_Questions.md_**
  1. Implementer votre proposition
  1. Tester la proposition
  1. Mesurer et tracer les mesures dans le fichier **_Questions.md_**
  1. Commiter  & Pusher le code et le  fichier **_Questions.md_**

## Proposition 1
Suivez les étapes ci-desus et répondre à Q12  du fichier fichier **_Questions.md_**

## Proposition 2
Suivez les étapes ci-desus et répondre à Q13  du fichier fichier **_Questions.md_**

## Proposition 3
Suivez les étapes ci-desus et répondre à Q14  du fichier fichier **_Questions.md_**

## Proposition 4
Suivez les étapes ci-desus et répondre à Q15  du fichier fichier **_Questions.md_**

# Pull Request
Une fois tous vos commits & Push réalisés sur votre repo, il est nécessaire de faire la **Pull Request** sur le repo **parent**.
Pour cela, il suffit de :
1. Se rendre sur votre compte personnel sur `GitHub`.
1. Sur la page principale, se rendre sur `Contribute` > `Open pull Request`
1. Remplir le titre de la pull request en précisant votre nom (vos noms) et `Create pull request`

# Bascule sur le projet 2b
Lire & suivre les instructions du fichier  README de https://github.com/aepsilon-tek/miage-numres-step2b

# Commandes Utiles
* ```./mvnw clean compile ``` : Compilation du projet
* ```./mvnw quarkus:dev``` : Lancement du projet en mode developpement
* ```./mvnw clean package``` : Construction du projet en mode JVM
* ```./mvnw clean package -P native``` : Construction du projet en mode Natif
