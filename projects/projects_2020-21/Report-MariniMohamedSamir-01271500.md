# Report : open source strategy project 

## Useful information

 >Author: Marini Mohamed Samir<br>
 >Noma : 0127-15-00<br>
 >Project : [IMAPClient](https://github.com/mjs/imapclient/) 

## Research and Selection of Project

#### Motivation

I had some open-source projects in mind that interested me but they were way too big or complicated. I didn't want to look for a project that I that wasn't interested in and I didn't know just to do my little pull request. 

#### How did I found IMAPClient?

As part of my master thesis, which consists of reducing the environmental impact of emails, I have to access mailboxes using IMAP and do some processing on them. I am using python and a native python solution to handle imap exists it's called imaplib. However, it is quite low level IMAP and I decided to look for something that would be higher level.

This is how I found IMAPClient which is a high level open source library for IMAP in python. Basically, I did not intend to contribute to this project because the available issues were way too complicated or required very specific knowledge of IMAP but it is by using the library every day for my master thesis that I found a problem in the library which was quite annoying.

## The problem

The  mailboxes folders (Trash, Sent, etc.) have a different IMAP access name depending on the server and the language used by the, the IMAPClient library has a method for finding the special name of these folders. This method did not work on Outlook for the TRASH folder which was quite a problem. It worked well with all the other mail providers, so I suspected a bug, I decided to look in the source code and it was indeed an oversight in the source code, which I offered to fix.

### Issue / Pull request

To find the problem I had to understand the code in depth, by doing that I understood where the problem came from. The 11/11/20 I decided to create an [issue](https://github.com/mjs/imapclient/issues/419#issue-741087303)  to talk about the problem.

I knew that if I made a pull request directly to fix the bug it would be accepted given the importance of the bug and the little code that needed to be modified to fix it. That's why I decided to directly add a [pull request](https://github.com/mjs/imapclient/pull/420) to my issue.

The next day the pull request was merged.


# Présentation finale (examen) : Fait d'actualité ElasticSearch n'est plus opensource

#### Introduction :
- Fait d'actualité qui a divisé la communauté open-source
- ElasticSearch passe d'une licence open-source à une licence qui ne l'est pas
#### Présentation :
- Qu'est-ce que le projet ElasticSearch ?
- Evolution du modèle, des licences et de l'activité de l'entreprise Elastic et du projet open-source
- Adoption par AWS (Amazon) du projet
#### Début des problèmes :
- Elastic ne veut pas s'associer au nom Amazon Elasticsearch Service
- Amazon se sent menacé par la direction que prend le projet open-source, notamment : 
  - Le mélange de code open-source (Apache 2.0) et de code propriétaire (Elastic licence) dans le github publique
  - Elastic concentre toute son énergie et ne fait progresser que le code propriétaire
- Amazon se sent lésé par rapport aux nombreux investissements fourni
#### Réaction d'Amazon :
- Lancement de Open Distro for ElasticSearch en partenariat avec Netflix et Expedia :
  - Ce n'est pas un fork
  - C'est le code open-source du projet ElasticSearch avec les plugins propriétaires qui ont été réécrit en open-source
  - Amazon continue d'envoyer ses contributions sur le vrai projet
- C'est Elastic qui se sent cette fois-ci attaqué
#### Réaction d'Elastic : 
- Passage du code open-source en licence SSPL
- L'OSI réagit en déclarant que la licence n'est pas une licence open-source parce qu'elle se veut discriminatoire
#### Analyse et prise de recul  :
- Quelles conséquences pour les autres compagnies ? 
- Qui sont les gagnants et les perdants ? 
- Est-ce que cette histoire montre les faiblesses de l'open-source ? L'open-source traverse-t-il sa première crise ?
- Problème récurrent en situation de dilemme de prisonnier 
#### Seconde réaction d'amazon (a eu lieu après l'examen):
- Fork total du projet pour créer un vrai projet open-source