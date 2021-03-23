---
layout: page
title: System Resources
permalink: /memmgmt/
---

# System Resources

Per risorse del sistema si intende ogni parte del sistema gestibile ed utilizzabile dal sistema nel suo complesso.

Le risorse possono essere la memoria RAM, le capacità di calcolo della CPU, i file su disco e le periferiche del computer.

## Gestione delle risorse

Il **Resource Management** è compito del Kernel, il quale governa le risorse hardware e fornisce i servizi per l'uso delle risorse da parte degli strati superiori del sistema.

### **Governor e Frequency Scaling**
Uno degli esempi di funzionalità di "governo" (in inglese _Governor_), è ad esempio il _Frequency Scaling_. Il Frequency Scaling è un servizio del kernel che permette lo _scaling_, cipè la regolazione, in modo dinamico attraverso l'algoritmo governatore, della frequenza di lavoro dei componenti hardware, come CPU, GPU e RAM. Ad esempio, senza carico sulla CPU, quindi a riposto, il sistema tenderà a mantenere una frequenza di lavoro più bassa, per risparmiare energia; invece in casi di lavoro pesante la frequenza aumenterà dinamicamente, fino ad arrivare, nei carichi massimi, alla massima frequenza dei componenti.

