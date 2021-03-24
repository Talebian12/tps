---
layout: page
title: System Call
permalink: /syscall/
parent: Sistemi Operativi
nav_order: 5
---

# Le System Call
 
Le System Call (o in Italiano Chiamate di Sistema), sono funzioni del Sistema Operativo, che permettono ad un programma di richiamare un servizio fornito dal Sistema. Una System Call può essere ad esempio la funzione per creare un nuovo processo o per eseguire operazioni di I/O.

## Come si esegue una System Call

Per richiamare una System Call prendiamo come esempio una funzione `call(args)`. Questa è per noi una System Call, quando verrà chiamata possiamo vedere dal codice della funzione come questa chiama una generica funzione `syscall(N_CALL, args);`; questa prende come argomento un valore *N_CALL*, che è il numero della System Call nel nostro Sistema Operativo, *args* sono gli argomenti inizialmente passati a `call(args)`. Questa funzione `syscall()` è un _interrupt_, che cambiando un valore in un determinato registro della CPU, ci porta in **Hypervisor Mode (Kernel Mode)**. Qui in Hypervisor Mode verrà chiamata la nostra System Call dalla tabella delle System Call.

Nell'immagine qua sotto, le frecce gialle indicano il percorso di esecuzione della System Call, le frecce blu i return.

![syscall](assets/images/syscall.svg)

