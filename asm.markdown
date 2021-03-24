---
layout: page
title: Linguaggio Macchina e Assembly 
permalink: /assembly/
parent: Struttura ed Architettura del PC
nav_order: 4
---

# Il linguaggio Macchina

Il linguaggio macchina è l'insieme di tutte le istruzioni codificate in binario facenti parte dell'**Instruction Set** del processore. Queste istruzioni compiono operazioni semplici di tipo matematico (operazioni logiche ed aritmetiche).

## Instruction Set

Gli Instruction Set di un processore possono essere principalmente di due tipologie, _RISC_ e _CISC_. La prima, che sta per _Reduced Instruction Set Computer_, si basa sul principio di avere poche istruzioni semplici, questo porta ad avere programmi più lunghi, ma che compiono istruzioni molto più veloci da eseguire. Il secondo invece sta per _Complex Instruction Set Computer_, che in modo opposto a RISC, punta ad avere un maggior numero di istruzioni complesse, così da avere programmi con meno istruzioni, ma più complesse da eseguire. I limiti di RISC si trovano soprattutto nella dimensione dei programmi in memoria, avere più istruzioni vuol dire più memoria, soprattutto cache necessaria; questo problema non è poi così influente nel computer moderni, dove la memoria cache di primo livello arriva nei sistemi classici ad 1MiB, con il terzo livello che arriva persino a 128MiB. RISC è attualmente impiegato nella quasi totalità dei dispositivi mobile su architettura ARM.

# Assembly
Il linguaggio Assembly è il primo gradino sopra il linguaggio macchina binario. Questo non implica il livello di astrazione dei linguaggi ad alto livello, ma è una semplice traduzione degli _opcodes_ (i codici macchina) in simboli (per simboli si intende una istruzione che noi scriviamo come testo), come ad esempio `MOV`, `ADD`, `SUB`, che corrispondono direttamente ad opcodes binari.

Un esempio di programma Assembly può essere ad esempio:

```as
1 | _start:
2 |   mov r1, 5
3 |   mov r2, 10
4 |
5 |   add r3, r2, r1
6 |   sub r3, r3, r1
```

Esploriamo questo programma.
L'esecuzione inizia a `_start`, la prima istruzione eseguita sarà `mov r1, 5`, _mov_ è l'istruzione **move**, muove nel primo valore dopo l'istruzione, che è la _destinazione_ `r1`, il valore _source_ 5. Stessa cosa con `mov r1, 10`. 
Ora abbiamo una nuova istruzione, `add`, questa non fa altro che salvare nella destinazione `r3` la somma di `r2, r1`. Stessa logica per la successiva `sub`, salva nel registro `r3` la sottrazione tra `r3, r1`.

Questo è un semplice esempio di programma in istruzioni assembly per processori ARM, quindi sistemi RISC.

## Principali istruzioni

Le principali istruzioni assembly sono:

* `mov` - move `dest` < `src` 
* `add` - add `dest` < `srcs` 
* `sub` - sub `dest` < `srcs` 
* `push` - push to stack `src` 
* `pop` - pop first stack element to `dest` 
* `jmp` - force jump to `addr`
* `call` - call `function`

Prendendo in considerazione che il programma inizi a `0xF000`:
```as
mov r1, 5
mov r2, 10
add r3, r2, r1
sub r3, r1
push r3
call print
pop r3
jmp $0xF000
```

Come il precedente esempio, le prime 4 istruzioni eseguono operazioni di copia, addizione e sottrazione.

Poi abbiamo l'istruzione `push`, che invia nello stack il valore di `r3`, successivamente chiamiamo una fantomatica funzione _print_, la quale salverà lo stato attuale dei registri e l'instruction pointer prima della chiamata, e successivamente passerà ad eseguire la funzione. Questa funzione stamperà a schermo l'ultimo valore salvato nello stack, in questo caso quello di `r3`, finita l'esecuzione di print, l'esecuzione tornerà al programma principale, quindi rimuoveremo l'ultimo elemento inserito nello stack (quindi il primo nell'elenco), e lo inseriamo in r3. Alla fine faremo un salto incondizionato a `0xF000` (preceduto da _$_, per dire che è un indirizzo), quindi il programma reinizierà con un ciclo infinito, finché quindi non sarà l'utente ad fermare l'esecuzione.