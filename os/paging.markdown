---
layout: page
title: Memory Paging
permalink: /os/paging/
parent: Sistemi Operativi
nav_order: 7
---

# Il Paging

La gestione della memoria sfruttando il paging è una importante perché il metodo più comune e sfruttato praticamente da tutti i sistemi moderni.

Il paging sfrutta spazi di memoria virtuali, di determinate dimensioni, allocati mappati nella memoria fisica, in questo modo un processo può avere i suoi dati allocati in più punti liberi della memoria fisica, ma dati che nella memoria virtuale sono in un unico blocco.

<div style="background-color: #DDD;
            padding: 20px; 
            text-align: center; 
            border-radius: 20px"> 
<img src="../assets/images/paging-fragmentation.svg">
</div>

Creando spazi di memoria virtuali, è possibile aumentare anche la sicurezza, assegnando ad ogni spazio virtuale flags specifici per il tipo di operazioni che su di esso si possono eseguire. Viene quindi creata una tabella che contiene il numero della pagina (_page_), dove è presente essa nella memoria fisica (_frame_) e gli attributi della pagina (_flags_).

<div style="background-color: #DDD;
            padding: 20px; 
            text-align: center; 
            border-radius: 20px"> 
<img src="../assets/images/page-tables.svg">
</div>

## Vantaggi del Paging e Page Fault

Il paging permette di avere pagine caricate in memoria, contenenti le parti del processo che servono nel momento corrente, e quelle non necessarie che rimangono in cache sul disco. Per avere la pagina disponibile è necessario eseguire una operazione, lo **swapping**, con le operazioni _swap in_ e _swap out_. Un processo però non sa quando caricare una pagina, quindi quando tenta di accedere ai dati in questo momento non in memoria, ma in una pagina sul disco, si verifica un errore di _Page Fault_.

Page Fault è un errore che si genera quando si tenta di leggere o scrivere una pagina che in quel momento non esiste.

Uno dei problemi più frequenti (e divertenti) riguardanti il Page Fault, è quando, su Windows, un programma critico (ad esempio un driver) tenta di accede ad una pagina inesistente, questo genera una interruzione che, nella Interrupt Descriptor Table è assegnata all'esecuzione dell'handler del page fault. Questo interrompe quindi qualsiasi cosa il Windows stesse facendo, con l'error code PAGE_FAULT_IN_NONPAGED_AREA ed eseguendo il dump della memoria. A questo link un dump generato da Windows dopo l'errore, [premi qui]().

![page_fault_in_nonpaged_area](../assets/images/page_fault_in_nonpaged_area.png)