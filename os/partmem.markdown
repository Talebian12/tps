---
layout: page
title: Partitioned Memory
permalink: /os/mempart/
parent: Sistemi Operativi
nav_order: 6
---

# Memoria Partizionata

Quando viene generato un processo, questo deve essere allocato in memoria, con i suoi vari segmenti. Viene quindi deciso uno spazio di una certa dimensione in memoria. In questo spazio, chiamata partizione viene allocato il programma, con quindi i suoi segmenti, stack e heap.

## Partizionamento Fisso

Con il partizionamento fisso, semplicemente lo spazio di memoria utente viene diviso in partizioni di una certa dimensione ed in ogni partizione viene allocato un programma. 

Due dei problemi principali del partizionamento fisso sono:
* **Internal Memory Fragmentation**: essendo il partizionamento fisso, la memoria di un programma sarà `SIZE_PROC <= SIZE_PART`, quindi i processi devono avere una dimensione minore, lasciando di conseguenza possibile spazio inutilizzato, frammentando la memoria.
* **Size Limitation**: la dimensione di un processo non può essere più grande della dimensione più ampia.

## Partizionamento dinamico

Il vantaggio delle partizioni dinamiche è il fatto che la memoria utente viene utilizzata come un unico blocco nel quale i processi vengono allocati. Anche qui troviamo vari problemi:
* **External Memory Fragmentation**: risolvendo i problemi interni, però ora abbiamo comunque problemi di frammentazione esterni alla allocazione dei processi. Questo può essere risolto con la compattazione della memoria, sconsigliata perché dovendo spostare grandi masse di dati nella memoria, abbiamo una grande uso di risorse.