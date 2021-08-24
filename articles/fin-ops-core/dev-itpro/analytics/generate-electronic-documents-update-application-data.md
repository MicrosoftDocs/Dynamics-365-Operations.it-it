---
title: Generare documenti elettronici con aggiornare i dati dell'applicazione utilizzando la creazione di report elettronici (ER)
description: È possibile progettare i formati di report elettronici (ER) utilizzabili nell'applicazione per generare i documenti elettronici in uscita.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5f78f3b36a1aebfb263d64ccf2293097eb9af6e6de1ab49de39b18e1c318950
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765810"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Generare documenti elettronici e aggiornare i dati dell'applicazione con la creazione di report elettronici

[!include [banner](../includes/banner.md)]

È possibile progettare i formati di report elettronici (ER) utilizzabili nell'applicazione per generare i documenti elettronici in uscita. È inoltre possibile progettare i formati di ER che analizzano i documenti elettronici in entrata e utilizzano il contenuto di questi documenti per aggiornare i dati dell'applicazione.

Grazie a questa funzionalità, un unico formato di ER può essere utilizzato per generare i documenti elettronici in uscita quindi aggiornare i dati dell'applicazione. Questa funzionalità può essere utilizzata negli scenari seguenti:

- Per impedire l'utilizzo ripetuto dei dati dell'applicazione nei successivi processi, è possibile contrassegnare i dati di un'applicazione subito dopo essere stati utilizzati per generare i documenti elettronici. Ad esempio, è possibile contrassegnare le transazioni di pagamento come già elaborate subito dopo che sono state importate in un messaggio di pagamento generato.
- Per archiviare i dettagli di elaborazione di documenti elettronici generati mediante la logica ER. Ad esempio, un ID univoco del messaggio di pagamento generato utilizzando l'espressione ER. L'espressione è basata sulle informazioni immesse nella finestra di dialogo ER quando il formato di ER viene eseguito per generare documenti.

Per ulteriori informazioni su questa funzionalità, utilizzare il set di Guide attività sulla generazione dei documenti ER mediante l'aggiornamento dei dati dell'applicazione (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)), che include i dettagli sul reporting e l'archiviazione Intrastat. I seguenti file sono necessari per completare alcuni passaggi in queste Guide attività. Scaricare e salvare i file nel computer locale.

- [Configurazione del modello dati di ER: Intrastat (modello)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [Configurazione del mapping del modello di ER: Intrastat (mapping)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [Configurazione del formato di ER: Intrastat (formato)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
