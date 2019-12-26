---
layout: post
section-type: post
title: Hébergement de pages en local sous linux
category: exploitation web
tags: [ 'reverse shell', 'hébergement en local sous linux', 'hacking', 'ctf' ]
---


#### Mise en garde
> Le but de cet article est de vous apprendre à héberger votre "shell code" en local pour pouvoir demander à une machine distante de se connecter à la vôtre et non pas vous apprendre à mettre en place "un serveur d'hébergement multiutilisateur sous Linux"!
<br/><br/>

#### Pré requis 
> Avoir installer et configurer le serveur web Apache2
> Avoir installer et configurer l'interpreteur PHP
> Avoir installer et configurer le seveur de base de données MySQL

<br/><br/>
#### Méthode 1: Serveur Apache2
**Etape 1**: placer ses pages dans le répertoire: /var/www/ <br/>
**Etape 2**: démarrer les services d'Apache2
  <pre><code data-trim class="yaml">
    #méthode 1
    sudo /etc/init.d/apache2 restart  
    #méthode 2
    sudo /etc/init.d/apache2 restart
  </code></pre>
**Etape 3**: naviguer vers l'adresse IP de sa machine linux [http://1.23.201.17](http://1.23.201.17)
  
<br/><br/>
#### Méthode 2: Serveur python
**Etape 1**: se placer dans le répertoire où se trouve les pages à héberger 
<pre><code data-trim class="yaml">
    #exemple du repertoire par défaut de kali linux
    cd /usr/share/webshell/php
  </code></pre>
**Etape 2**: lancer la commande
<pre><code data-trim class="yaml">
    #se mettre à l'écoute sous le port 2020 
    sudo python -m SimpleHTTPServer 2020
  </code></pre>
**Etape 3**: naviguer vers l'adresse IP de sa machine linux [http://1.23.201.17:2020](http://1.23.201.17:2020)
  
