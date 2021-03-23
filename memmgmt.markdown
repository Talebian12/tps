---
layout: page
title: Memory Management
permalink: /memmgmt/
---

# Memory Management

Il Memory Management (o in italiano Gestione della Memoria) è quella funzione del Sistema Operativo che permette appunto la gestione della memoria. Nella gestione della memoria ricadono tutte quelle funzionalità di allocazione e deallocazione, registrazione delle attività e gestione dell'I/O sulla memoria e molto altro.

## Memory Management nei Processi

Il Memory Management possiamo ritrovarlo ad esempio alla creazione di un processo. Quando un processo viene creato, la funzionalità di Memory Management creerà uno spazio in memoria RAM dedicato a quel programma, con i vari segmenti necessari, per il codice, per i dati (segmento _data_ per variabili globali e costanti locali inizializzate, segmento _bss_ per quelle non inizializzate, _stack_ per le variabili locali e le funzioni chiamate) e per le allocazioni dinamiche (_heap_).
Il Memory Management si occuperà poi di gestire ogni allocazione, deallocazione e modifica dei dati.

![memlayout](assets/images/processmemlayout.jpg)


## Memory Management nella Sicurezza

Il Memory Management ha anche funzioni di sicurezza. Ad esempio permette, tramite la **MMU** (Memory Management Unit, componente di supporto per la gestione della memoria della CPU, per non impegnarla in questo compito) di settare i vari permessi per lettura e scrittura degli indirizzi di memoria. Ad esempio si può fare in modo che un determinato indirizzo o blocco di memoria possa essere modificabile solo in Hypervisor Mode, oppure che solo l'utente che ha creato quella allocazione possa modificare quella parte di memoria.