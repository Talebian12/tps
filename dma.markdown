---
layout: page
title: Direct Memory Access
permalink: /dma/
parent: Struttura ed Architettura del PC
nav_order: 3
---

# Direct Memory Access

Il **DMA** o _Direct Memory Access_ è un controller hardware che permette di eseguire operazioni I/O senza occupare la CPU.

Ogni operazione di I/O sulle periferiche genera un _interrupt_, quando noi ad esempio scriviamo, per ogni tasto generiamo un _keyboard interrupt_, quindi la CPU blocca l'esecuzione di qualsiasi programma in quel momento e passa alla gestione di quell'interrupt. Una grande quantità di interrupt bloccano spesso l'esecuzione nella CPU, per questo è esiste il DMA, così da alleggerire la CPU dalla gestione di questi interrupt.

## SPOOL

Lo **SPOOL** o _Simultaneous Peripheral Operations On-line_ è l'operazione di salvataggio in un buffer, di dati in attesa di essere indirizzati alla destinazione dove dovranno essere elaborati.

Un _buffer_ è una porzione di memoria dove vengono salvati i dati finché non è possibile gestirli. Un esempio di buffer è il buffer dell'input della tastiera (_stdin_) e dell'output (_stdout_).

Esempi di SPOOL è ad esempio lo Spooler di stampa.

### Spooler di stampa

Lo Spooler di stampa si occupa di caricare in un buffer i documenti da stampare, così da liberare la CPU dalla gestione dei documenti da stampare, gestendoli in un buffer separato.