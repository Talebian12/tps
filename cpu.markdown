---
layout: page
title: Central Processing Unit
permalink: /cpu
---

# Central Processing Unit

La **CPU** è una delle componenti hardware fondamentali del PC. Essa è necessaria per l'esecuzione di qualsiasi istruzione dettata alla macchina, l'interpretazione del linguaggio macchina, il calcolo aritmetico e le operazioni logiche, la gestione dell'I/O tra le componenti hardware, le funzionalità di sicurezza critiche, sono tutte operazioni della CPU.

## Struttura di una CPU

La CPU è costituita da diverse componenti, le cui principali sono i Registri, la Control Unit, la Arithmetic Logic Unit, la Memory Management Unit e la Memoria Cache.

### Registri
I registri sono la più piccola unità di lavoro della computer, su di essi si svolgono tutte le operazioni sui dati.

Nei moderni processori abbiamo 3 tipologie di registri, i registri specifici, i registri generali e i registri di estensione. Vediamoli:

* **Registri specifici**: Sono registri il cui scopo è definito, tra questi abbiamo l'IP o Instruction Pointer, un registro che contiene l'indirizzo dell'istruzione corrente. Un altro registro è FLAGS, mappato secondo uno schema ben preciso, ogni bit di questo indirizzo ha un suo significato e indica determinati stati. Ad esempio se il bit 0 ha valore 1, allora l'ultima operazione eseguita dalla ALU ha avuto un riporto (Carry Flag), esistono flag per ogni operazione o stato della CPU, come ad esempio l'Overflow.
* **Registri generali**: Sono registri generali tutti quelli su cui noi possiamo operare direttamente per eseguire operazioni. I principali sono l'Accumulatore (AX), la Base (BX), il Contatore (CX) e il Data (DX, spesso usato come supporto per AX). Poi abbiamo tutti i registri generali il cui uso è scelto dall'utente, senza quindi una propria nomenclatura. I registri con una nomenclaura la hanno per ragioni storiche, non tutte le architetture danno un nome ai registri (Come ad esempio ARM).
* **Estensioni della CPU**: Sono i registri facenti parte delle estensioni della CPU tutti quei registri che non fanno parte della categoria generale, ma sono appunto estensione dell'architettura origiale. Sono estensioni ad esempio SSE, che fornisce 8 registri aggiuntivi a 64-bit (MMX), questa estensione è usata per il calcolo in virgola mobile, appunto sono lunghi 64-bit, le nuove versioni di SSE (come SSE4) hanno anche registri lunghi fino a 128-bit (XMM).

_La lettera R prima dei nomi dei registri è dovuta al fatto che l'immagina parla implicitamente dell'architettura x86-64, la quale distingue i registri dalle precedenti dalla dicitura R-NOMEREGISTRO_

![CPUREG](assets/images/8664registers.jpg)

### Control Unit

La Control Unit (CU) è l'unità che si occupa di comprendere e dirigere le azioni della CPU in base all'istruzione data. 