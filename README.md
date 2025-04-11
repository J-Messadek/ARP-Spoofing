⚠️ ARP Spoofing Attack Simulation Script (Scapy)

    Ce script est strictement à but pédagogique et ne doit être utilisé que dans un environnement de test isolé. Il permet de simuler une attaque ARP Spoofing pour rediriger le trafic réseau entre une cible et une passerelle, à des fins d’analyse réseau locale.

❗ AVERTISSEMENT IMPORTANT
🚨 Interdiction d’usage sur des réseaux publics

Ce script envoie des paquets ARP spoofés (spoofing d'IP + MAC) entre une cible et une passerelle. Il peut interférer avec le fonctionnement normal du réseau et détourner le trafic, rendant la cible vulnérable à des attaques de type "Man-in-the-Middle".

⚠️ Son exécution en dehors d’un environnement local (lab, VM, réseau isolé) constitue une violation éthique et légale.

L’auteur de ce dépôt décline toute responsabilité en cas de mauvaise utilisation.
🎯 Objectif pédagogique

    Comprendre le fonctionnement de l'ARP Spoofing (attaque par falsification d'adresse ARP).

    Observer les effets du détournement de trafic réseau dans un laboratoire local.

    Apprendre à rediriger le trafic réseau entre la cible et la passerelle à l'aide de Scapy.

📦 Dépendances

    Python 3.x

    Scapy

    Threading pour gérer les tâches simultanées.

pip install scapy

🔧 Exécution du script

    Préparez l'environnement : Utilisez un réseau isolé, comme une machine virtuelle ou un réseau local dédié à l’expérimentation.

    Lancez le script :

    sudo python3 arp_spoofing.py

Le script fonctionne en envoyant des paquets ARP falsifiés pour interférer avec le trafic entre une cible (target_ip) et la passerelle (gateway_ip). Il utilise également un mécanisme pour rediriger le trafic de la cible vers l'attaquant.
