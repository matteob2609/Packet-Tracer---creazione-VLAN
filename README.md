# Creazione di una semplice VLAN

:heavy_exclamation_mark: **Prerequisito**: avere Packet Tracer (risorsa Cisco) installato sul computer.

La creazione della VLAN avverrà tramite **tre step** diversi:

  1. [VLAN base](https://github.com/matteob2609/Packet-Tracer-creazione-VLAN#ghost-step-1---vlan-base);

  1. [VLAN trunking](https://github.com/matteob2609/Packet-Tracer-creazione-VLAN#ghost-step-2---vlan-trunking);

  1. [VLAN routing](https://github.com/matteob2609/Packet-Tracer-creazione-VLAN#ghost-step-3---vlan-routing).

:heavy_exclamation_mark: **N.B. in questo caso sarà utilizzata la rete 192.168.0.0/24.** :heavy_exclamation_mark:

---

### :heavy_check_mark: RISULTATO FINALE

![image](https://user-images.githubusercontent.com/61114792/109317443-02386f80-784d-11eb-8fc5-6efd618fe54d.png)

---

### :ghost: STEP 1 - VLAN BASE

Creare il modello di partenza utilizzando 1 **Switch 2960**, 4 **PC** ed effettuare il collegamento tra loro selezionando la connessione automatica.

Disporre in questo modo i device:

![image](https://user-images.githubusercontent.com/61114792/109380809-58ea8b80-78d7-11eb-9278-679ef19f5659.png)

(Per visualizzare le etichette delle porte selezionare _Options -> Preferences -> Show port labels_).

Verranno create 3 VLAN, chiamate Amministrazione (VLAN10), Vendite (VLAN20) e Gestione (VLAN30).

Ai PC dell'amministrazione assegnare i seguenti IP e la seguente subnet mask:

  - **PC10_1** - IP: _192.168.10.1_ Subnet mask: _255.255.255.0_
 
  - **PC10_2** - IP: _192.168.10.2_ Subnet mask: _255.255.255.0_

Al PC delle vendite assegnare il seguente IP e la seguente subnet mask:

  - **PC20_1** - IP: _192.168.20.1_ Subnet mask: _255.255.255.0_

Al PC della gestione assegnare il seguente IP e la seguente subnet mask:

  - **PC30_1** - IP: _192.168.30.1_ Subnet mask: _255.255.255.0_

:pushpin:`Checkpoint: eseguire tramite il prompt del PC10_1 il comando 'ping 192.168.10.2' per controllare se i PC comunicano tra loro, confermando il corretto assegnamento degli indirizzi.`

Per creare le VLAN ed abilitarle bisognerà accedere allo Switch, selezionado la schermata _Config_ e successivamente su _VLAN Database_:

  - VLAN Number: _10_, VLAN Name: _Amministrazione_;

  - VLAN Number: _20_, VLAN Name: _Vendite_;

  - VLAN Number: _30_, VLAN Name: _Gestione_.

Dopo aver fatto quest'operazione, individuare quali interfacce dello Switch sono collegate alle diverse VLAN e assegnarle.

Per fare questo bisognerà selezionare lo Switch, spostarsi su _Config_ e selezionare l'interfaccia:

  - **FastEthernet 0/1**, impostarla su _Access_ e selezionare la VLAN 10, escludendo le altre;
 
  - **FastEthernet 0/2**, come la FastEthernet 0/1, in quanto le due interfacce appartengono alla stessa VLAN;

  - **FastEthernet 0/3**, impostarla su _Access_ e selezionare la VLAN 20, escludendo le altre;

  - **FastEthernet 0/4**, impostarla su _Access_ e selezionare la VLAN 30, escludendo le altre;

:pushpin:`Checkpoint: per verificare che le porte siano state impostate correttamente e che siano state assegnate alle diverse VLAN eseguire il comando 'show vlan brief' dalla riga di comando dello Switch. L'output dovrà essere:`

    10   Amministrazione                  active    Fa0/1, Fa0/2
    20   Vendite                          active    Fa0/3
    30   Gestione                         active    Fa0/4
    1002 fddi-default                     active    
    1003 token-ring-default               active    
    1004 fddinet-default                  active    
    1005 trnet-default                    active    

[Torna su](https://github.com/matteob2609/Packet-Tracer-creazione-VLAN#creazione-di-una-semplice-vlan)

---

### :ghost: STEP 2 - VLAN TRUNKING

[Torna su](https://github.com/matteob2609/Packet-Tracer-creazione-VLAN#creazione-di-una-semplice-vlan)

---

### :ghost: STEP 3 - VLAN ROUTING

[Torna su](https://github.com/matteob2609/Packet-Tracer-creazione-VLAN#creazione-di-una-semplice-vlan)
