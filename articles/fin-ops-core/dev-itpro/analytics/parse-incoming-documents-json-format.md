---
title: Analizzare i documenti in entrata in formato JSON
description: In questo argomento viene descritto come impostare i formati di report elettronici (ER) per analizzare i documenti in arrivo in formato JavaScript Object Notation (JSON).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 8be4e225507a18a92d642ff0f3a6ca3d0ff68564
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772537"
---
# <a name="parse-incoming-documents-in-json-format"></a>Analizzare i documenti in entrata in formato JSON

[!include[banner](../includes/banner.md)]

È possibile progettare formati di report elettronici (ER) per analizzare i documenti elettronici in arrivo che rappresentano dati in un formato di testo basato su JavaScript (in altre parole, file in formato \[JSON\]).

Per ulteriori informazioni su questa funzionalità, scaricare i file nella seguente tabella e quindi riprodurre la guida attività ER Creare una configurazione di formato per importare dati da un file JSON esterno. Questa guida attività illustra come utilizzare un formato ER per analizzare un file JSON in arrivo per aggiornare i dati dell'applicazione.

| Funzione                                  | Nome file |
|----------------------------------------|-----------|
| Configurazione di formato ER                | [Formato per importare il file trans_JSON.xml dei fornitori](https://go.microsoft.com/fwlink/?linkid=874111) |
| Esempio del file in arrivo in formato csv | [1099entries_JSON.txt](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a>Requisiti

Prima di completare la guida attività ER Creare una configurazione di formato per importare dati da un file JSON esterno, è necessario soddisfare il requisito seguente:

- Gli elementi padre nel file JSON possono essere solo elementi di oggetti.
- Gli elementi nidificati di un oggetto devono essere elementi di proprietà, di modo che venga creata una struttura JSON valida.
- Le matrici JSON possono essere solo elementi nidificati di elementi di proprietà di un oggetto.
- Le matrici JSON possono contenere solo oggetti JSON. Non possono contenere valori numerici/stringa diretti e matrici nidificate. Gli elementi in queste matrici saranno analizzati nell'ordine, in quanto sono specificati nel formato. Le impostazioni di molteplicità in ogni oggetto JSON verranno prese in considerazione.

Inoltre, è necessario completare la guida attività [ER Creare le configurazioni necessarie per importare dati da un file esterno](tasks/er-required-configurations-import-data.md) se non lo si è ancora fatto. Scaricare il seguente file per completare la guida attività.

| Funzione                  | Nome file |
|------------------------|-----------|
| Configurazione del modello ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=874111) |
