---
layout: page
title: Il Kernel
permalink: /kernel/
---

# Il Kernel
Il Kernel è la componente fondamentale di un Sistema Operativo, il suo Nucleo. A se incorpora le principali funzioni base, inizializzare la gestione hardware per il sistema e l'accesso ad esso, lo Scheduling, le System Call per accedere a funzioni strettamente private del Kernel (in Hypervisor Mode, o anche chiamata appunto Kernel Mode).

## Kernel Mode
La **Kernel Mode**, o _Hypervisor Mode (talvolta anche Reserved Mode)_, è uno dei possibili anelli di esecuzione in un sistema; Kernel Mode è il _ring 0_, il più privilegiato, il meno privilegiato è il _ring 3_, o **User Mode**.
In Kernel Mode si ha quindi il massimo livello di permessi, questo implica quindi pieno accesso alla memoria, ai processi, ai dati del sistema e la possibilità di creare o interrompere qualsiasi processo. Si può accedere a funzioni in Kernel Mode da software in User Mode tramite le System Call.

### **Esempio di kernel, Windows NT**

![windowsnt](assets/images/windowsnt.png)

### Kernel Monolitici
In un kernel monolitico tutti iservizi di sistema e drivers girano nel kernel, questi vengono chiamati moduli. I moduli possono essere 
programmi per la gestione del multitasking, delle 
periferiche oppure proprio i driver. L’uso di questi moduli è possibile grazie ad una estesa tabella di System Call. Esempi di kernel monolitici 
sono Linux e BSD.

### Microkernel
Sono kernel i quali integrano solo un set di semplici chiamate di sistema utili per la gestione dei processi, indirizzamento e 
comunicazione fra i processi. Il resto delle 
funzionalità vengono gestite attraverso dei server che sfruttano le System Call per comunicare con il kernel. I server possono avere essere usati per la gestione periferiche, dell’interfaccia grafica, ecc. Un esempio di Microkernel è Mach.

### Kernel Ibridi
I kernel ibridi integrano caratteristiche sia dei Kernel Monolitici sia dei Microkernel. I kernel ibridi incapsulano servizi non essenziali dei Microkernel dentro il kernel, come fossero moduli del Kernel, non essendone però di fatto. Questa integrazione di questi componenti nel Kernel permette a questi servizi di girare più velocemente Esempi di Kernel Ibridi sono Windows NT e Apple XNU.