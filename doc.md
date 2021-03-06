# Temps réel avec les websokets

## Problématique

Avec l'arrivée d'applications web de plus en plus interactives et réactives, il étais nésaisaire de développer un protocole full-duplex qui permette de comuniquer entre un serveur des des clients (navigateurs) web. L'objectif est principalement de pouvoir pousser des données vers les clients en temps réel (pas de rechargement de pages, pas d'autoload). Et de permettre au client de streamer du contenu vers le serveur.

Exemple : les applications de messagerie (whatsapp web, telegram) utilisent ce protocole pour récupérer et pousser des messages sans rechargement.

Pourquoi ne pas utiliser de l'ajax ?? L'ajax ne permet pas d'ouvrir un canal entre client serveur, on effectue juste des applels http asynchrones vers le serveur. Le serveur ne peut pas non plus pousser de données vers le client.

## Technologies

Pour remédier a la problématique, on protocole a été développé et standardisé, les [websokets](https://developer.mozilla.org/fr/docs/WebSockets).

Le protocole websocket permet d'ouvrir un canal de comunication **client <-> serveur**. Il va permettre d'envoyer et recevoir des messages sous forme d'événements. Tout ça sans avoir a consulter le serveur pour récupérer les nouveaux messages, ils sont poussés depuis le serveur via le protocole.

## Librairies / implémentations

Il existe un certian nombre d'implémentations des websokets coté serveur, qui viennent la plupart avec une petite librairie javascript pour facilement utiliser les websokets depuis le client.

* **[ActionCable](http://guides.rubyonrails.org/action_cable_overview.html)** : est l'implémentation pour [Ruby](https://www.ruby-lang.org/fr/) fournie avec [Rails](http://rubyonrails.org/).
* **[soket.io](https://socket.io/)** : une implémentation pour [node.js](https://nodejs.org/en/) très polyvalente et pérformante.
* **[Phoenix.Socket](https://hexdocs.pm/phoenix/Phoenix.Socket.html#content)** : une implémentation en [Elixir](https://elixir-lang.org/) livrée avec le framework [Phoenix](http://phoenixframework.org/). Très intéresante car on bénéficie de grandes capacités (millions de connexions simultanées sur un seul serveur), du au langage elixir qui est conçu pour la gestion de très grand concurence.
* **[Gorilla WebSocket](https://github.com/gorilla/websocket)** : Une implémentation en [golang](https://golang.org/).
* ...et plein d'autres

## Support par les navigateurs

Tous les navigateurs récents suportent les websokets : [tableau ici](https://caniuse.com/#feat=websockets). Attention cependant, certians navigateurs mobiles ne le suporte pas encore.

## Lien avec le module RIA

L'utilisation de temps réel permet d'apporter des fonctionnalités très intérésantes pour une application web riche. Mise a jour de contenu en direct, retours plus réactifa a l'utilisateur...

## Exemple

Une exemple de petit chat : [ici](example/README.md).

## Exercice

Faire boujer un petit cube en temps réel dans un svg entre plusieurs navigateurs : [ici](exercice/README.md).

## En bref !

Les websokets permettent d'ouvrir un canal de comunication full-duplex entre client et serveur. On va ensuite pouvoir envoyer/recevoir des messages via un systeme de cannaux et d'événements.

## Pour aller plus loin

* [Firebase](https://firebase.google.com/) : une base de données temps réel utilisant les websokets.
* [Laravel Echo](https://laravel.com/docs/5.6/broadcasting) : Permet de lier facilement un serveur de websokets (socket.io) a une application laravel, en utilisant [redis](https://redis.io/) pour comuniquer entre laravel et node.
* [Pusher](https://pusher.com/) : une API toute prete pour travailler avec les websokets.

## Références / sources

* [fr.wikipedia.org/wiki/WebSocket](https://fr.wikipedia.org/wiki/WebSocket)
* [developer.mozilla.org/fr/docs/WebSockets](https://developer.mozilla.org/fr/docs/WebSockets)
* [developer.mozilla.org/fr/docs/WebSockets/Writing_WebSocket_client_applications](https://developer.mozilla.org/fr/docs/WebSockets/Writing_WebSocket_client_applications)
* [www.websocket.org/](https://www.websocket.org/)