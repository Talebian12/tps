---
layout: page
title: Sistemi Operativi
permalink: /os/
has_children: true
has_toc: false
---
# Il Sistema Operativo

Il Sistema Operativo è un software di base, cioè uno dei software fondamentali per l'uso di un elaboratore. Esso è composto da svariate componenti software, le quali hanno a se le principali funzioni operative:

### Bootloader
Primo componente avviato dal firmware durante la fase di avvio. Esso ha il compito di inizializzare l'hardware base (memory layout, protected mode a 32bit e la long mode 64bitt, ecc.) e infine caricare il Kernel.

### Kernel
E' il nucleo di un sistema operativo, mette in comunicazione le parti più superficiali del sistema con l'hardware, esempi di kernel sono il Kernel Linux, Windows NT e XNU (MacOS Kernel).
  
### Memory Management
Il Memory Management è la funzionalità che gestisce la RAM, l'allocazione e la deallocazione dei programmi e dei suoi dati nella stessa e della configurazione della memoria (Paging o Segmentation). Del Memory Management fa parte anche la Memory Protection, gestita da specifiche funzioni del processore (Memory Management Unit), permette di assegnare determinati permessi di lettura e scrittura ai diversi indirizzi, così da evitare che programmi non autorizzati leggano o scrivano parti di memoria a cui non dovevano accedere.
  
### Scheduler
Lo scheduler CPU gestisce i processi e il momento in cui devono essere eseguiti. Esistono vari tipi di Scheduler e per i diversi sistemi.
  
### File System
Il File System è responsabile per l'organizzazione, mantenimento e memorizzazione dei file su disco. Lo schema di file, directory e subdirectory è dato dal File System.

![os](/assets/images/operating_systems.svg) 

Abbiamo poi dei componenti più di alto livello come:

### Gestore delle Periferiche
Esso gestisce le periferiche di input e output come mouse e tastiera, sfrutta i driver e le funzioni del kernel per comunicare con la macchina

### Shell dei comandi

La shell dei comandi è il livello più alto di astrazione del sistema per comunicare con l'utente. Tramite la shell dei comandi l'utente può avviare, chiudere ed interagire con gli applicativi ed il sistema. Una shell può essere grafica, quindi utilizzare una GUI, oppure testuale, utilizzando quindi una CLI accessibile via terminale fisico od emulatore di terminale.

### Interfaccia Utente
Essa può essere testuale o grafica, la prima utilizzabile su monitor o console seriale, la seconda invece sfrutta tutte le funzioni grafiche di una scheda video per "disegnare" il video sul monitor. Le interfacce grafiche sono ad esempio Explorer su Windows, Quartz su macOS e i desktop environment come GNOME o KDE su GNU/Linux.

Tutti queste componenti fanno parte di determinati livelli del sistema operativo, lo schema che rappresenta questo sistema a livelli è chiamato _onion-skin_, buccia di cipolla, quindi a partire dal livello più interno, il Kernel, si arriva al più esterno, il livello applicativo.

![onionskin](assets/images/onionskingarch.jpg)

Il livello più interno è appunto il kernel, che ha i massimi privilegi (_Hypervisor Mode_), e verso l'esterno arrviamo al livello applicativo (_User Mode_) dove si hanno i privilegi più bassi.