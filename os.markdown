---
layout: page
title: Sistemi Operativi
permalink: /os
---
# Il Sistema Operativo

Il Sistema Operativo è un software di base, cioè uno dei software fondamentali per l'uso di un elaboratore. Esso è composto da svariate componenti software, le quali hanno a se le principali funzioni operative:
- Bootloader: primo componente avviato dal firmware durante la fase di avvio. Esso ha il compito di inizializzare l'hardware base (memory layout, configurare la protected mode a 32bit, ecc.) e infine caricare il Kernel.
- Kernel: è il nucleo di un sistema operativo, mette in comunicazione le parti più superficiali del sistema con l'hardware, esempi di kernel sono il Kernel Linux, Windows NT e XNU (MacOS Kernel).
- Memory Management: è la componenten del sistema che gestisce la RAM, l'allocazione e la deallocazione dei programmi e dei suoi dati nella stessa e della configurazione della memoria (Paging o Segmentation). Del Memory Management fa parte anche la Memory Protection, gestita da specifiche funzioni del processore (Memory Management Unit), permette di assegnare determinati permessi di lettura e scrittura ai diversi indirizzi, così da evitare che programmi non autorizzati leggano o scrivano parti di memoria a cui non dovevano accedere.
- Scheduler: lo scheduler CPU gestisce i processi e il momento in cui devono essere eseguiti. Esistono vari tipi di Scheduler e per i diversi sistemi.
- File System: il File System è responsabile per l'organizzazione, mantenimento e memorizzazione dei file su disco. Lo schema di file, directory e subdirectory è dato dal File System.

Abbiamo poi dei componenti più di alto livello come:
- Gestore delle Periferiche: esso gestisce le periferiche di input e output come mouse e tastiera, sfrutta i driver e le funzioni del kernel per comunicare con la macchina
- Interfaccia Utente: essa può essere testuale o grafica, la prima utilizzabile su monitor o console seriale, la seconda invece sfrutta tutte le funzioni grafiche di una scheda video per "disegnare" il video sul monitor. Le interfacce grafiche sono ad esempio Explorer su Windows, Quartz su macOS e i desktop environment come GNOME o KDE su GNU/Linux.

Il Sistema Operativo fornisce poi strumenti utili ai programmi, le API, che in altro caso potrebbero utilizzare solo funzioni basilari della macchina, invece grazie al Sistema Operativo hanno accesso alle così dette System Call, funzioni con cui un programma può chiamnare direttamente funzionalità del kernel, come Write e Read. Questi set di System Call si chiama ABI (Application Binary Interface).   