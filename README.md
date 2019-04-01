# Reseau-2019-TP3

## I. Manipulation de switches et de VLAN

 ### 2/ Configuration des VLANs : 
 
 
 
 
 ## II. Manipulation simple de routeurs
 
 
 
 
 ## III. Mise en place d'OSPF
 
 
 
 ### 1/ Mise en place du lab :
 
 On configure les IP des routeurs et des machines 
 
  ```
 R1#show ip int br
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            10.2.102.254    YES manual administratively down down
FastEthernet1/0            10.2.100.1      YES manual administratively down down
FastEthernet2/0            unassigned      YES unset  administratively down down
FastEthernet3/0            10.2.100.22     YES manual administratively down down
```


 ### 2/ Configuration de OSPF :
 
 On configure OSPF pour les routeurs et les routes par défaut pour les machines 

```
R1#show ip protocols
Routing Protocol is "ospf 1"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Router ID 1.1.1.1
  Number of areas in this router is 2. 2 normal 0 stub 0 nssa
  Maximum path: 4
  Routing for Networks:
    10.3.100.0 0.0.0.3 area 0
    10.3.100.20 0.0.0.3 area 0
    10.3.102.0 0.0.0.255 area 2
 Reference bandwidth unit is 100 mbps
  Routing Information Sources:
    Gateway         Distance      Last Update
  Distance: (default is 110)
```

```
sudo ip route add 10.3.102.0/24 via 10.3.102.254 dev enp0s3
```

On fait un pin entre server1 et client1 pour tout vérifier que tout marche ( je n'ai pas screen le ping avant d'éteindre mon pc du coup toutes les ip et et les routes sont parties quand je l'ai rallumé, je ne peux donc pas montrer le ping final, seulement les étapes intermédiaires ). 
