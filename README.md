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

Creare il modello di partenza utilizzando 1 Switch 2960 e 4 PC ed effettuare il collegamento tra loro selezionando la connessione automatica.

Disporre in questo modo i device:

![image](https://user-images.githubusercontent.com/61114792/109363296-84945400-788c-11eb-818c-348960178085.png)

(Per visualizzare il nome e il numero delle porte selezionare Options -> Preferences -> Show port labels).

Verranno create 3 VLAN, chiamate Amministrazione (VLAN10), Vendite (VLAN20) e Gestione (VLAN30).

Ai PC dell'amministrazione assegnare i seguenti IP e la seguente subnet mask:

  - PC10 - IP: _192.168.0.10_ Subnet mask: _255.255.255.0_
 
  - PC11 - IP: _192.168.0.11_ Subnet mask: _255.255.255.0_

Al PC delle vendite assegnare il seguente IP e la seguente subnet mask:

  - PC20 - IP: _192.168.0.20_ Subnet mask: _255.255.255.0_

Al PC della gestione assegnare il seguente IP e la seguente subnet mask:

  - PC30 - IP: _192.168.0.30_ Subnet mask: _255.255.255.0_

:pushpin:`Checkpoint: Eseguire tramite il prompt del PC10 il comando ping 192.168.0.30 per controllare se i PC comunicano tra loro, confermando il corretto assegnamento degli indirizzi.`

Per creare le VLAN ed abilitarle bisognerà accedere allo Switch, selezionado la schermata Config e successivamente su VLAN Database:

  - VLAN Number: 10, VLAN Name: Amministrazione;

  - VLAN Number: 20, VLAN Name: Vendite;

  - VLAN Number: 30, VLAN Name: Gestione.

Dopo aver fatto quest'operazione, individuare quali interfacce dello Switch sono collegate alle diverse VLAN e assegnarle.

Per fare questo bisognerà selezionare lo Switch, spostarsi su Config e selezionare l'interfaccia:

  - FastEthernet 0/1, impostarla su Access e selezionare la VLAN 10, escludendo le altre;
 
  - FastEthernet 0/2, come la 0/1;

  - FastEthernet 0/3, impostarla su Access e selezionare la VLAN 20, escludendo le altre;

  - FastEthernet 0/4, impostarla su Access e selezionare la VLAN 40, escludendo le altre;

:pushpin:`Checkpoint: Per verificare che le porte siano state impostate correttamente e che siano state assegnate alle diverse VLAN eseguire il comando show vlan brief dalla riga di comando dello Switch. L'output dovrà essere:`

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
