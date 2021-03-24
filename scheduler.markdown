---
layout: page
title: Scheduler
permalink: /os/scheduler/
parent: Sistemi Operativi
---

# Scheduler della CPU

Lo Scheduler della CPU come detto nella sezione _Sistemi Operativi_, essi servono per decidere che processi eseguire e gestire quindi la process queue.
Gli Scheduler dipendono dal tipo di sistema in uso, se Interactive, Batch o Real-Time.

### Interactive Systems
Gli Interactive Systems sono i più diffusi, i moderni sistemi operativi per PC e Smartphone sono Interactive. Questi hanno vari sistemi per lo scheduling, alcuni sono:
- Shortest Process Next Scheduler: il processi vengono ordinati per la durata di essi, prima i più corti.
- Scheduling "Round-robin": qui si definisce il tempo che si assegna per l'esecuzione di un processo e alla fine di questo, se completato verrà quindi superato, sennò verrà spostato alla fine della catena di esecuzione, gli stati dei registri verranno salvati e l'esecuzione passerà al processo successivo. Lo scheduler I/O invece gestisce la priorità della scrittura in memoria da parte dei processi.
  
![round](/assets/images/round_robin.png)

- Scheduling basato su priorità: è la tipologia più diffusa, perché più efficiente e adeguata ai nuovi sistemi, ad esempio dedicando ogni classe di priorità ad un core, la priorità dei processi viene decisa dinamicamente dal sistema in base alla durata stimata per l'esecuzione, la priorità di uso (se in background o un processo in uso) e sui moderni sistemi, il sistema riconosce gli usage pattern dell'utente grazie all'intelligenza artificiale.
  
![priority](/assets/images/priority.png)

### Real-Time Systems
I Real-Time Systems hanno una specifica richiesa, non devono esserci tempi morti, quindi i programmi vengono divisi in tanti processi ed il sistema deve essere in grado di predirre il prossimo processo da eseguire, così da sapere in anticipo cosa fare successivamente. Gli eventi in questi sistemi possono essere periodici e non periodici; nel caso di eventi periodici essi accadono quindi ad intervalli regolari, nel caso di eventi non periodici non sappiamo quando potranno accadere. Un sistema Real-Time che rispetta la periodicità è considerato Schedulable, un processo che utilizza più tempo della CPU di quello che può, non verrà gestito dallo Scheduler.

---

## Nei sistemi recenti
Nei moderni sistemi solitamente non si usa un solo algoritmo, ma si usano più algoritmi. Ad esempio, i sistemi Linux dividono la priorità dei processi in 140 livelli (da 0 a 139).
Le classi di priorità Real-time e System thread si trovano nei livelli da 0 a 99, qui troviamo i processi critici in uso e i processi di sistema. Invece nei livelli da 100 a 139 troviamo i processi Utente.