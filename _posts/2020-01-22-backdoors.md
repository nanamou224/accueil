---
layout: post
section-type: post
title: Les portes dérobées (backdoors)
category: exploitation web
tags: [ 'reverse_shell',, 'backdoor', 'web', 'hacking', 'ctf' ]
---

---------------------------------------------
##### shell
Un shell est un interpréteur de commandes servant d'interface entre l'OS et son utilisateur

##### web shell
Un web shell est un shell qui s'exécute dans le navigateur (soit dans l'URL soit avec des clics), permettant l'accès à distance au serveur Web 

##### shellcode
Un shellcode est est une chaîne de caractères qui représente un code binaire exécutable, injectée en mémoire grâce à l'exploitation d'un dépassement de tampon (overflow)
<pre><code data-trim class="yaml">
  #Exemple de shellcode
  char shellcode[] = "\xeb\x1f\x5e\x89\x76\x08\x31\xc0\x88\x46\x07\x89\x46\x0c\xb0\x0b\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80\x31\xdb\x89\xd8\x40\xcd\x80\xe8\xdc\xff\xff\xff/bin/sh";
</code></pre> <br/>

##### reverse TCP shell
Un reverse TCP shell est un invite de commandes, sans utilisateur et qui permet de s'évader du firewall. Dans ce cas là, on va utiliser notre propre machine en mode serveur et faire en sorte que la machine attaquée se connecte dessus

##### bind TCP shell
Un bind TCP shell lie l'invite de commande à un port d'écoute. Dans ce cas là on va utiliser la machine cible en mode serveur et se connecter dessus depuis notre machine attaquante.

NB: Le choix entre un reverse TCP shell et un blind TCP shell dépend de la situation et de la configuration réseau. 
- Si la machine attaquée est derrière un routeur qui fait du NAT et n'est pas routable depuis l’extérieur, l’utilisation du bind shell est impossible. 
- Si, par exemple en ctf, vous attaquez une IP publique mais que n’avez que votre connexion avec votre box qui fait du NAT, c’est beaucoup plus indiqué d’utiliser un bind shell.

---------------------------------------------
