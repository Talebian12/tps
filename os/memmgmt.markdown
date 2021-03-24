---
layout: page
title: Memory Management
permalink: /os/memmgmt/
parent: Sistemi Operativi
nav_order: 5
---

# Memory Management

Il Memory Management (o in italiano Gestione della Memoria) è quella funzione del Sistema Operativo che permette appunto la gestione della memoria. Nella gestione della memoria ricadono tutte quelle funzionalità di allocazione e deallocazione, registrazione delle attività e gestione dell'I/O sulla memoria e molto altro.

## Memory Management nei Processi

Il Memory Management possiamo ritrovarlo ad esempio alla creazione di un processo. Quando un processo viene creato, la funzionalità di Memory Management creerà uno spazio in memoria RAM dedicato a quel programma, con i vari segmenti necessari, per il codice, per i dati (segmento _data_ per variabili globali e costanti locali inizializzate, segmento _bss_ per quelle non inizializzate, _stack_ per le variabili locali e le funzioni chiamate) e per le allocazioni dinamiche (_heap_).
Il Memory Management si occuperà poi di gestire ogni allocazione, deallocazione e modifica dei dati.

![memlayout](assets/images/processmemlayout.jpg)


## Memory Management nella Sicurezza

Il Memory Management ha anche funzioni di sicurezza. Ad esempio permette, tramite la **MMU** (Memory Management Unit, componente di supporto per la gestione della memoria della CPU, per non impegnarla in questo compito) di settare i vari permessi per lettura e scrittura degli indirizzi di memoria. Ad esempio si può fare in modo che un determinato indirizzo o blocco di memoria possa essere modificabile solo in Hypervisor Mode, oppure che solo l'utente che ha creato quella allocazione possa modificare quella parte di memoria.

## Memoria virtuale e fisica

Un sistema operativo, durante l'esecuzione, non lavora su indirizzi di memoria fisici, ma la memoria centrale è mappata in uno spazio detto memoria virtuale. La memoria virtuale ha molti vantaggi, alcuni sono ad esempio il paging della memoria, il mapping di varie porzioni fisiche in diverse posizioni virtuali.
La traduzione degli indirizzi di memoria virtuale ad indirizzi fisici spetta alla **MMU**.

## Caching

Il caching è quella operazione che permette di salvare in una porzione di memoria velocemente accessibile dati utili sul momento o richiesti con frequenza. Il tipo di cache più importante è la CPU cache, divisa su 3 livelli e solitamente di piccole dimensioni (il livello 3 non supera i 128MiB solitamente e il livello 1 non raggiunge 1MiB nella maggior parte dei casi).

L'accesso alla memoria cache si è un accesso associativo, cioè al valore corrisponde la porzione di memoria cache che lo contiene, quindi si dice che il blocco di memoria è associato al valore.

## Principio di Località

Dopo aver parlato di Caching e Memoria Virtuale possiamo parlare del principio di località. Questo principio afferma che quando si accede ad un dato in memoria, il quale può essere una variabile o una istruzione, il prossimo valore sarà probabilmente vicino al valore precedente. Quindi possiamo in un ad esempio prevedere quale è il prossimo blocco di memoria da modificare (ad esempio durante il caricamento di un array).

Questo principio si adatta molto bene con la Memoria Virtuale. Mappando la memoria in pagine (paging) di memoria per ogni programma. Quindi noi sappiamo che i dati del programma si trovano dentro questa pagina, velocizzandone il ritrovamento.