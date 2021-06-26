# seffari.f.lamini.a
Installation:

        pour installer Curl sur votre machine virtuelle vous pouvez suivre les étapes suivantes:
        
                              1-tapez la commande suivante: sudo apt update 
                    il va vous donner l'output suivant:
                    
[sudo] password for student: (entrez votre password)
Get:1 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
Hit:2 http://us.archive.ubuntu.com/ubuntu bionic InRelease
Get:3 http://us.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]       
Get:4 http://us.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]                  
Get:5 http://security.ubuntu.com/ubuntu bionic-security/main amd64 DEP-11 Metadata [48.4 kB]
Get:6 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [2,127 kB]
Get:7 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 DEP-11 Metadata [60.6 kB]
Get:8 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 DEP-11 Metadata [2,464 B]
Get:9 http://us.archive.ubuntu.com/ubuntu bionic-updates/main i386 Packages [1,309 kB]                                                       
Get:10 http://us.archive.ubuntu.com/ubuntu bionic-updates/main amd64 DEP-11 Metadata [294 kB]                                                
Get:11 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe i386 Packages [1,568 kB]                                                  
Get:12 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [1,738 kB]                                                 
Get:13 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 DEP-11 Metadata [290 kB]                                            
Get:14 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe DEP-11 48x48 Icons [217 kB]                                               
Get:15 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe DEP-11 64x64 Icons [497 kB]                                               
Get:16 http://us.archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 DEP-11 Metadata [2,468 B]                                         
Get:17 http://us.archive.ubuntu.com/ubuntu bionic-backports/universe amd64 DEP-11 Metadata [9,272 B]                                         
Fetched 8,415 kB in 49s (171 kB/s)                                                                                                           
Reading package lists... Done
Building dependency tree       
Reading state information... Done
493 packages can be upgraded. Run 'apt list --upgradable' to see them.

                              2-tapez la commande: sudo apt install curl
                              
                    il va vous donner l'output suivant:
[sudo] password for student: (entrez votre password)
Reading package lists... Done
Building dependency tree       
Reading state information... Done
curl is already the newest version (7.58.0-2ubuntu3.13).
0 upgraded, 0 newly installed, 0 to remove and 493 not upgraded.

                             pour installer iptables sur votre machine vous pouvez suivre les étapes en bas:
                                              1-tapez la commande: sudo apt-get install iptables
                             il va vous donner l'output suivant:
                             
Reading package lists... Done
Building dependency tree       
Reading state information... Done
iptables is already the newest version (1.6.1-2ubuntu2).
0 upgraded, 0 newly installed, 0 to remove and 493 not upgraded.

Extraction des adresses IP à partir d'un fichier log:

                 1-tapez les commandes suivants:
                           - wget https://safhi.me/uemf/Projet/projet.log (pour télécharger fichier log)
                           - grep -Eo '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' projet.log (extraire les adresses IP du fichier log)
                           
l'utilisation de l'API AbuselPDB pour vérifier la réputation d'une adresses IP:

                 2-tapez les commandes suivants:
                           -curl -G https://api.abuseipdb.com/api/v2/check \
> --data-urlencode "ipAddress=118.25.6.39" \
> -d maxAgeInDays=90 \
> -d verbose \
> -H "Key:24e3e65211041dae64bfb027c01171d6abec513c2126e8b1980c3b7cf214ae5d3cb271f3dc5bce88" \
> -H "Accept:application/json"
> 
                  pour avoir votre personnel Key vous pouvez créer un compte sur https://www.abuseipdb.com/account/api 
                  
l'ajout des régles de blocage dans le pare-feu pour les adresses malvaillantes:

                 -  sudo iptables -A INPUT -s 192.168.1.3 -j DROP (bloquer/autoriser les connexions).
                 -  sudo iptables -I  OUTPUT -d 192.168.1.3 -j DROP( filtrer les paquets sortants).
                 -  sudo iptables -A  FORWARD  -d 192.168.1.3 -j DROP( filtrer les paquets entrants).
                 
    remplacer "192.168.1.3" avec l'adresse de protocole internet que vous souhaitez bloquer.
    

                 
