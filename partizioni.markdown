---
layout: page
title: Files
permalink: /os/partitions
---

# Partizioni

La partizione di un disco è una suddivisione logica del supporto fisico. Detto in modo più dettagliato, un disco non si può suddividere fisicamente, quindi viene suddiviso logicamente in più parti, questa suddivisione non è reale ma software. Su un disco, prima di essere partizionabile, bisogna scegliere uno schema per la Tabella Partizioni, (PTS, Partition Table Scheme), i principali schemi sono due, MBR o Master Boot Record, più vecchio e GPT o GUID Partition Table, più recente e compatibile con i nuovi firmware basati su EFI (Extensible Firmware Interface).

Un esempio di partizionamento sui sistemi Linux:
![partitions](/assets/images/partition_scheme.svg)

In pratica il nome del disco, fisico, è /dev/sda, la sua dimensione è 256GB, poi è partizionato in due dischi logici, /dev/sda1 e /dev/sda2, il primo 108GB e il secondo 148GB. Questi due dischi non esistono fisicamente ma solo logicamente.

Ogni Sistema Operativo ha i suoi strumenti per partizionare un disco, su Windows abbiamo Gestione Dischi per l'interfaccia grafica e Diskpart da linea di comando, su MacOS Disk Utility graficamente e diskutil da linea di comando e su Linux abbiamo varie scelte, le principali sono GParted con interfaccia grafica e da terminale fdisk o cgdisk.

Ogni partizione può avere il suo File System, un nome simbolico e alcune proprietà, come la possibilità di essere avviabile.