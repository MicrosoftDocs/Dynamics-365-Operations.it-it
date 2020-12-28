---
title: Attribuire permessi in base alle ore lavorate
description: Questo argomento descrive come configurare i piani di congedo per attribuire permessi in base alle ore lavorate.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-09-17
ms.dyn365.ops.version: ''
ms.openlocfilehash: 229ae14b9e2dedcd0ade094a772f16c0524d32a7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461664"
---
# <a name="accrue-time-off-based-on-hours-worked"></a>Attribuire permessi in base alle ore lavorate

## <a name="overview"></a>Panoramica

Le organizzazioni con dipendenti a ora possono assegnare i permessi in base alle ore di lavorate anziché in base alla durata del rapporto con l'organizzazione. I dati sulle ore lavorate vengono in genere archiviati in un sistema di gestione dell'orario e delle presenze. 

## <a name="leave-plans"></a>Piani di congedo

Nel piano di congedo il tipo di attribuzione può essere basato sui mesi di servizio o sulle ore lavorate. Quando viene selezionata l'opzione delle ore lavorate, esistono due tipi di ore da usare per l'attribuzione: regolari e di straordinario.

Per impostare un piano di congedo che usa le ore lavorate, seguire questi passaggi:

1. Nella pagina **Piani di congedo e assenza** fare clic su **Crea nuovo piano**.
2. Immettere un nome per il piano di congedo.
3. Selezionare la frequenza di attribuzione per il piano di congedo.
5. Selezionare la data di inizio per il piano.
6. Scegliere la base del periodo di attribuzione e selezionare la data specifica del dipendente, se applicabile.
7. Per la programmazione dell'attribuzione, selezionare **Ore lavorate** per il tipo di attribuzione.
8. Selezionare il tipo di ore da usare per l'attribuzione.
9. Immettere il numero di ore lavorate e l'importo di attribuzione associato, il saldo minimo, il riporto massimo o l'importo sovvenzione.

L'elaborazione dell'attribuzione dei piani basati sulle ore lavorate utilizza la frequenza di attribuzione, insieme alla base del periodo di attribuzione, per determinare le ore da attribuire.

## <a name="annual-accrual-frequency"></a>Frequenza di accumulo annuale

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2000                | 0                 |


## <a name="monthly-accrual-frequency"></a>Frequenza di accumulo mensile

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 1/8/2018-31/8/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 1/8/2018-31/8/2018   | 184                 | 3                   |

## <a name="semi-monthly-accrual-frequency"></a>Frequenza di accumulo semestrale

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 75                  | 0                   |

## <a name="weekly-accrual-frequency"></a>Frequenza di accumulo settimanale

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 35                  | 0                   |

## <a name="employee-assigned-leave-plans"></a>Piani di congedo assegnati del dipendente

Nei piani di congedo assegnati del dipendente la base del livello e il tipo di ore viene visualizzato per i piani in cui le ore lavorate sono definite come tipo di attribuzione. Per i piani attivi, anche le ore lavorate effettive per i periodi di attribuzione a partire dalla data corrente vengono visualizzate per riferimento. 

## <a name="loading-data"></a>Caricamento dati in corso

Le ore effettive possono essere importate utilizzando l'entità Ore di assenza e di congedo lavorate nella gestione dei dati. Se si utilizzano i calendari orario di lavoro, l'importazione convaliderà che le ore di lavoro normali non superano le ore previste in un giorno definito dal calendario. L'importazione convalida anche che le ore lavorate in un determinato giorno non superino le 24 ore. 

Le seguenti informazioni sono necessarie per importare le ore effettive da utilizzare nel processo di attribuzione per il congedo:

+ Numero dipendente 
+ Data lavorata
+ Tipo
+ Ore

Una singola data può avere solo uno di ogni tipo associato.

| PERSONNELNUMBER       | DATEWORKED           | TIPO                  | HOURS                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Regolare               | 8                    |       
| 000337                | 8/7/2018             | Regolare               | 8                    |
| 000337                | 8/7/2018             | Straordinario              | 3                    |
| 000337                | 8/8/2018             | Regolare               | 8                    |
| 000337                | 8/7/2018             | Regolare               | 8                    |
| 000337                | 8/9/2018             | Regolare               | 8                    |
