---
title: Generare documenti elettronici e aggiornare i dati dell'applicazione utilizzando lo strumento di creazione di report elettronici
description: "È possibile progettare i formati di report elettronici (ER) utilizzabili nell'applicazione Finance and Operations per generare i documenti elettronici in uscita. È inoltre possibile progettare i formati di ER che analizzano i documenti elettronici in entrata e utilizzano il contenuto di questi documenti per aggiornare i dati dell'applicazione."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7378c1d205b9a9cd61044dc33fc52ff75c6b94b7
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="generate-electronic-documents-and-update-application-data-using-the-electronic-reporting-tool"></a>Generare documenti elettronici e aggiornare i dati dell'applicazione utilizzando lo strumento di creazione di report elettronici

È possibile progettare i formati di report elettronici (ER) utilizzabili nell'applicazione Finance and Operations per generare i documenti elettronici in uscita. È inoltre possibile progettare i formati di ER che analizzano i documenti elettronici in entrata e utilizzano il contenuto di questi documenti per aggiornare i dati dell'applicazione. 

Grazie a questa funzionalità, un unico formato di ER può essere utilizzato per generare i documenti elettronici in uscita quindi aggiornare i dati dell'applicazione. Questa funzionalità può essere utilizzata negli scenari seguenti:

- Per impedire l'utilizzo ripetuto dei dati dell'applicazione nei successivi processi, è possibile contrassegnare i dati di un'applicazione subito dopo essere stati utilizzati per generare i documenti elettronici. Ad esempio, è possibile contrassegnare le transazioni di pagamento come già elaborate subito dopo che sono state importate in un messaggio di pagamento generato.
- Per archiviare i dettagli di elaborazione di documenti elettronici generati mediante la logica ER. Ad esempio, un ID univoco del messaggio di pagamento generato utilizzando l'espressione ER. L'espressione è basata sulle informazioni immesse nella finestra di dialogo ER quando il formato di ER viene eseguito per generare documenti.

Per ulteriori informazioni su questa funzionalità, utilizzare il set di Guide attività sulla generazione dei documenti ER mediante l'aggiornamento dei dati dell'applicazione (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)), che include i dettagli sul reporting e l'archiviazione Intrastat. I seguenti file sono necessari per completare alcuni passaggi in queste Guide attività. Scaricare e salvare i file nel computer locale.

- [Configurazione del modello dati di ER: Intrastat (modello)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configurazione del mapping del modello di ER: Intrastat (mapping)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configurazione del formato di ER: Intrastat (formato)](https://go.microsoft.com/fwlink/?linkid=849038)

