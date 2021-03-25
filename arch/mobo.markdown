---
layout: page
title: Scheda Madre
permalink: /arch/mobo/
parent: Computer Architecture
nav_order: 2
---

# Scheda Madre
La Scheda Madre di un PC è una _piastra_, la quale ha su di essa gli slot per le _memorie_, il _socket della CPU_, il _chipset_, il _firmware_ (BIOS o UEFI) e tutti i _bus_ e sistemi di controllo per gestire e coordinare i componenti hardware elettronici. Ora vediamo singolarmente quel che abbiamo sulla Scheda Madre:

## Socket
Il **Socket** è uno zoccolo, il quale può essere piedinato sul socket (_Intel LGA_) o piedinato sulla CPU (_AMD PGA_). Il Socket fornisce alimentazione alla CPU, e tutti i pin per interconnettere i bus di ogni componente della scheda, alla CPU.

### **LGA Socket**
Come già detto, il socket LGA possiede i pin sullo zoccolo, quindi la CPU avra le zone di 'collegamento'.

![lga](../assets/images/lgasocket.jpg)

### **PGA Socket**
Con i socket PGA invece abbiamo la piedinatura sulla CPU, quindi il socket avrà i fori per collegare la CPU.

![pga](../assets/images/pgasocket.png)

## DIMM Slot
Gli slot **DIMM** (_Dual In-line Memory Module_) sono gli slot per memorie RAM _DIMM_, la piedinatura dipende dalla versione dello standard _JEDEC DDR_ (DDR, ..., DDR5), questo slot fornisce un _bus_ per trasferire i dati tra CPU e Memoria RAM, un _segnale di Clock_ e l'alimentazione per la RAM.

## Chipset
Il **Chipset** è una componente fondamentale della scheda madre, esso gestisce la comunicazione tra i diversi bus delle componenti, CPU, RAM, PCI e tutte le Periferiche, tramite i vari controller, device controller, interrupt controller, ecc.

## Firmware
Il **Firmware**, _UEFI o BIOS_ è il primo software che viene caricato in un computer. Il principio di avvio è semplice, il firmware è contenuto in una piccola memoria ROM sulla scheda madre, all'avvio il processore è impostato di fabbrica per caricare tutto quel che c'è in quella ROM dentro la RAM ed avviare l'esecuzione. Questo non è una cosa fatta dall'utente, ma detta _hardcoded_, cioè è codificata dentro la CPU, una procedura standard comune a tutte le CPU x86. Il firmware poi si occupa del _POST_ (Power On Self Test), il quale testa tutte le componenti hardware connesse. Poi troverà tutti i dischi e cercherà un bootloader dentro i dischi, così da poter avviare successivamente un sistema operativo.