---
title: Analizzare i documenti in entrata in formato Excel
description: In questo argomento vengono fornite informazioni sulla progettazione di formati di report elettronici (ER) per analizzare il contenuto nei file di Microsoft Excel ricevuti.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0c41a062d817307adb2889d3678764f1ea4066e2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755182"
---
# <a name="parse-incoming-documents-in-excel-format"></a>Analizzare i documenti in entrata in formato Excel

[!include[banner](../includes/banner.md)]

È possibile progettare formati di report elettronici per analizzare file ricevuti di Microsoft Excel che rappresentano i dati nelle cartelle di lavoro di Microsoft Excel (file nel formato XLSX). È quindi possibile utilizzare il contenuto di tali file per aggiornare i dati dell'applicazione. Questa procedura è utile per:

- Progettare un nuovo modello e formato e testarli in fase di esecuzione. In questo caso, Excel simula i dati dell'applicazione effettivi.
- Gestire i dati oltre la domanda in Excel e importarli per inviare un report specifico.

Per ulteriori informazioni su questa funzionalità, riprodurre le guide attività **ER Importare dati da un file di Microsoft Excel (Parte 1: progettare il formato)** e **ER Importare dati da un file di Microsoft Excel (Parte 2: importare i dati)** (parti del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)). Queste guide attività illustrano in dettaglio come analizzare il file di Excel ricevuto utilizzando il formato di ER per importare le informazioni dai documenti ricevuti e aggiornare i dati dell'applicazione. È possibile scaricare i file delle guide attività dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).

Scaricare i file seguenti per completare le guide attività sopra menzionate.

| Descrizione contenuto                         | File                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| File ricevuto nel formato XLSX - modello    | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266) |
| File ricevuto nel formato XLSX - dati di esempio | [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Se non è stata ancora riprodotta la guida attività seguente, [ER Creare le configurazioni necessarie per importare dati da un file esterno](./tasks/er-required-configurations-import-data.md) nell'applicazione Finance and Operations corrente, scaricare il file seguente.

| Descrizione contenuto    | File                                                            |
|------------------------|-----------------------------------------------------------------|
| Configurazione modello di ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]