---
layout: page
title: Multitasking
permalink: /multitasking/
---

# Multitasking
Il **Multitasking**, o _Multiprogrammazione_, è la capacità di un sistema operativo di eseguire più processi contemporaneamente. Con il multitasking possiamo così eliminare i tempi morti di esecuzione, come durante l'attesa di una processo di I/O.

## Tipologie di multitasking

Esistono due tipi di multitasking, i _sistemi multitasking batch_ e i _sistemi time-sharing_.

### Batch
Nei sistemi _batch_ non ci si prende in considerazioni situazioni multiutente, con interattività, ma si cerca il modo migliore di sfruttare tutte le risorse hardwre.

### Time Sharing
Nei sistemi _time-sharing_ si permette invece un corretto funzionamento della multiutenza, rendendo il sistema interattivo alle azioni degli utenti. Questo tipo è quello predominante nei sistemi moderni.

![multitasking](assets/images/multitasking.png)

Come possiamo vedere, in un sistema sequenziale, quindi monoprogrammato, i task vengono eseguiti uno per volta; nei momenti di uso della CPU non avvengono operazioni di I/O, viceversa durante i momenti di uso dell'I/O. Questa cosa non avviene nei sistemi multiprogrammati, dove le operazioni vengono eseguite in simultanea tra CPU e I/O, così da poter ridurre i tempi e massimizzare l'efficienza.

## CPU e I/O Bound
Si dice CPU bound un processo che esegue una grande quantità di operazioni computazionali e poche, se non alcuna operazione di I/O, viceversa si dice I/O bound un processo che esegue molte operazioni di I/O rispetto ad un basso uso della CPU. In questo caso possiamo vedere i vantaggi del multitasking, dove si eliminano i tempi morti dove durante operazioni CPU bound l'I/O non viene usato e viceversa per l'I/O bound.

## Prelazione
In un sistema multitasking, la **prelazione** è l'azione che compie un sistema per bloccare l'esecuzione di un programma, senza considerare la volontà dello stesso. In un sistema senza prelazione invece i programmi cedono su loro scelta il controllo al sistema a fine operazione. Nei sistemi moderni predomina la tipologia di **multitasking preemptive**, cioè con prelazione.