---
title: Analizzare i documenti ricevuti in Microsoft Excel
description: In questo argomento vengono fornite informazioni sulla progettazione di formati di report elettronici (ER) per analizzare il contenuto nei file di Microsoft Excel ricevuti.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 001e287590b9f43ed38de803bcace3a25a6f6637
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2018

---

# <a name="parse-incoming-microsoft-excel-files"></a>Analizzare i file ricevuti di Microsoft Excel

[!include[banner](../includes/banner.md)]

È possibile progettare formati di report elettronici per analizzare file ricevuti di Microsoft Excel che rappresentano i dati nelle cartelle di lavoro di Microsoft Excel (file nel formato XLSX). È quindi possibile utilizzare il contenuto di tali file per aggiornare i dati dell'applicazione. Questa procedura è utile per:

-   Progettare un nuovo modello e formato e testarli in fase di esecuzione. In questo caso, Excel simula i dati dell'applicazione effettivi.
-   Gestire i dati oltre la domanda in Excel e importarli per inviare un report specifico.

Per ulteriori informazioni su questa funzionalità, riprodurre le guide attività **ER Importare dati da un file di Microsoft Excel (Parte 1: progettare il formato)** e **ER Importare dati da un file di Microsoft Excel (Parte 1: importare i dati)** (parti del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)). Queste guide attività illustrano in dettaglio come analizzare il file di Excel ricevuto utilizzando il formato di ER per importare le informazioni dai documenti ricevuti e aggiornare i dati dell'applicazione. È possibile scaricare i file delle guide attività dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).

Scaricare i file seguenti per completare le guide attività sopra menzionate.

| Descrizione contenuto                        | File                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| File ricevuto nel formato XLSX - modello   | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)  |
| File ricevuto nel formato XLSX - dati di esempio| [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Se non è stata ancora riprodotta la guida attività seguente, [ER Creare le configurazioni necessarie per importare dati da un file esterno](./tasks/er-required-configurations-import-data.md) nell'applicazione Dynamics 365 for Finance and Operation corrente, scaricare il file seguente.

| Descrizione contenuto                        | File                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| Configurazione modello di ER                     | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266)            |


