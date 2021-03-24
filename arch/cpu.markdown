---
layout: page
title: Central Processing Unit
permalink: /arch/cpu/
parent: Computer Architecture
nav_order: 2
---

# Central Processing Unit

La **CPU** è una delle componenti hardware fondamentali del PC. Essa è necessaria per l'esecuzione di qualsiasi istruzione dettata alla macchina, l'interpretazione del linguaggio macchina, il calcolo aritmetico e le operazioni logiche, la gestione dell'I/O tra le componenti hardware, le funzionalità di sicurezza critiche, sono tutte operazioni della CPU.

## Struttura di una CPU

La CPU è costituita da diverse componenti, le cui principali sono i Registri, la Control Unit, la Arithmetic Logic Unit, la Memory Management Unit e la Memoria Cache.

### Registri
I registri sono la più piccola unità di lavoro della computer, su di essi si svolgono tutte le operazioni sui dati.

Nei moderni processori abbiamo 3 tipologie di registri, i registri specifici, i registri generali e i registri di estensione. Vediamoli:

* **Registri specifici**: Sono registri il cui scopo è definito, tra questi abbiamo l'IP o Instruction Pointer, un registro che contiene l'indirizzo dell'istruzione corrente. Un altro registro è FLAGS, mappato secondo uno schema ben preciso, ogni bit di questo indirizzo ha un suo significato e indica determinati stati. Ad esempio se il bit 0 ha valore 1, allora l'ultima operazione eseguita dalla ALU ha avuto un riporto (Carry Flag), esistono flag per ogni operazione o stato della CPU, come ad esempio l'Overflow. Esistono poi registri per impostare modalità speciali della CPU, come la _Hypervisor Mode_.
* **Registri generali**: Sono registri generali tutti quelli su cui noi possiamo operare direttamente per eseguire operazioni. I principali sono l'Accumulatore (AX), la Base (BX), il Contatore (CX) e il Data (DX, spesso usato come supporto per AX). Poi abbiamo tutti i registri generali il cui uso è scelto dall'utente, senza quindi una propria nomenclatura. I registri con una nomenclaura la hanno per ragioni storiche, non tutte le architetture danno un nome ai registri (Come ad esempio ARM).
* **Estensioni della CPU**: Sono i registri facenti parte delle estensioni della CPU tutti quei registri che non fanno parte della categoria generale, ma sono appunto estensione dell'architettura origiale. Sono estensioni ad esempio SSE, che fornisce 8 registri aggiuntivi a 64-bit (MMX), questa estensione è usata per il calcolo in virgola mobile, appunto sono lunghi 64-bit, le nuove versioni di SSE (come SSE4) hanno anche registri lunghi fino a 128-bit (XMM).

_La lettera R prima dei nomi dei registri è dovuta al fatto che l'immagina parla implicitamente dell'architettura x86-64, la quale distingue i registri dalle precedenti dalla dicitura R-NOMEREGISTRO_

![CPUREG](../assets/images/8664registers.jpg)

### Control Unit

La Control Unit (CU) è l'unità che si occupa di comprendere e dirigere le azioni della CPU in base all'istruzione data. Possiamo paragonarla ad un Primo Ministro; essa detiene il potere esecutivo, prende le istruzioni e le esegue, coordinando i suoi rami (ALU, Registri, ecc.).

Un esempio, prendiamo un esempio di codice 
```as
mov ax, 5
mov dx, ax 
```
La CU prima decodificherà la prima istruzione, quindi copierà nel registro AX il valore 5; eseguita questa istruzione, sarà sempre compito della CU incrementare l'IP (Instruction Pointer) e passare quindi all'istruzione successiva, dove copierà il valore di AX dentro DX.

![execute](../assets/images/execution.svg)

Quindi si inizia l'esecizione da _Start_, quindi la _CU_ prenderà il controllo, dalla prima istruzione, quindi dove è stato settato l'_IP_ allo Start. la prima istruzione verrà quindi trovata `mov ax, 5`, verrà decodificata ed eseguita. Finita l'esecuzione la CU eseguirà lo step di incremento del _IP_, così la CU passerà all'istruzione successiva; questa sequenza cambia in caso di salto incondizionato.

![execjmp](../assets/images/execjmp.svg)

### Arithmetic Logic Unit

Il funzionamento della **ALU** è semplicemente eseguire le operazioni aritmetiche di Addizione e Sottrazione e le operazioni logiche AND, OR e NOT (con tutte le combinazioni e varianti, come XOR, NAND, ecc.).

### Memory Management Unit

La _Memory Management Unit_ o **MMU** è una componente della CPU che si occupa della gestione della memoria tra sistema e hardware (Virtual Memory e Physical Memory) e la sicurezza, gestendo i permessi di accesso alla memoria e di read/write. La _MMU_ si occupa poi anche della gestione dello spostamento dei dati tra CPU e Memoria Centrale e di conseguenza del buffer dati.