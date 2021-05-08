# Projet_flood_serveur

### Comment recréer le projet : 

Notre projet (Flood servuer) est constitué de 2 machines virtuelles. La première est une débian 10 et la seconde une kali. La debian 10 sera donc la machine "cible" et la kali sera la machine "attaquante".

### Debian 10 :

Notre machine debian 10 sera ici considéré comme un serveur, par conséquent nous avons installé une base de donnés deçu (mysql) et également un serveur web (apache 2 qui est le logiciel de serveur web le plus utilisé).

### Kali :

Comme seconde machine nous avons ici choisi une kali car hping3 et wireshark sont installer deçu par defaut. Hping3 va nous servir à envoyer les paquets sur la machine cible et wireshark va nous permettre de voir si les paquets sont bien envoyés et ce qu'il se passe plus en détail.

### Communication des 2 VM :

Une fois les 2 VM réalisé il faut ensuite les connecter sur un même réseau (configuration --> réseau) pour que les deux machines puissent communiqués (test avec un ping).

### Envoyer l'attaque :

Une les VM installés et configurer il est temps d'envoyer les paquets sur la machine debian 10 grâce à hping3 pour voir comment elle réagie. Pour cela nous ouvrons sur kali hping3 et wireshark. Pour mieux voir les effets de l'attaque on peut également lancer un ping depuis debian vers kali et observer le temps de réponse. Une fois tout cela mis en place, nous pouvons lancer l'attaque en tapant la ligne de commande suivante : 

- sudo hping3 -S --flood -V -p 80 192.168.1.5

L'adresse IP à la fin est celle de la machine cible (debian).

### Résultat :

![Screenshot](https://cdn.discordapp.com/attachments/760983046539182090/839229552647208960/flood.jpg)
&nbsp;

Comme on peut le voir sur cette image, le temps de réponse de ping entre les 2VM est inférieur à 1ms quand on ne fait rien et quand l'attaque est lancé il atteint un pic à 779ms.

![](https://cdn.discordapp.com/attachments/760983046539182090/839231232339869706/flood.jpg)
&nbsp;

Et sur cette image on peut voir grâce au wireshark que les paquets sont bien envoyés.
