---
title: Generare documenti elettronici e aggiornare i dati dell&quot;applicazione utilizzando lo strumento di creazione di report elettronici
description: "È possibile progettare i formati di report elettronici (ER) utilizzabili nell&quot;applicazione Finance and Operations per generare i documenti elettronici in uscita. È inoltre possibile progettare i formati di ER che analizzano i documenti elettronici in entrata e utilizzano il contenuto di questi documenti per aggiornare i dati dell&quot;applicazione."
author: kfend
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: Lifecycle Services
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.2, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d37d20b26d8ae755a6c5a688afd1ad0541d1f693
ms.openlocfilehash: 7e4e0acb374fe091c0e099355204116345c62997
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---


È possibile progettare i formati di report elettronici (ER) utilizzabili nell'applicazione Finance and Operations per generare i documenti elettronici in uscita. È inoltre possibile progettare i formati di ER che analizzano i documenti elettronici in entrata e utilizzano il contenuto di questi documenti per aggiornare i dati dell'applicazione. 

Grazie a questa funzionalità, un unico formato di ER può essere utilizzato per generare i documenti elettronici in uscita quindi aggiornare i dati dell'applicazione. Questa funzionalità può essere utilizzata negli scenari seguenti:

- Per impedire l'utilizzo ripetuto dei dati dell'applicazione nei successivi processi, è possibile contrassegnare i dati di un'applicazione subito dopo essere stati utilizzati per generare i documenti elettronici. Ad esempio, è possibile contrassegnare le transazioni di pagamento come già elaborate subito dopo che sono state importate in un messaggio di pagamento generato.
- Per archiviare i dettagli di elaborazione di documenti elettronici generati mediante la logica ER. Ad esempio, un ID univoco del messaggio di pagamento generato utilizzando l'espressione ER. L'espressione è basata sulle informazioni immesse nella finestra di dialogo ER quando il formato di ER viene eseguito per generare documenti.

Per ulteriori informazioni su questa funzionalità, utilizzare il set di Guide attività sulla generazione dei documenti ER mediante l'aggiornamento dei dati dell'applicazione (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)), che include i dettagli sul reporting e l'archiviazione Intrastat. I seguenti file sono necessari per completare alcuni passaggi in queste Guide attività. Scaricare e salvare i file nel computer locale.

- [Configurazione del modello dati di ER: Intrastat (modello)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configurazione del mapping del modello di ER: Intrastat (mapping)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configurazione del formato di ER: Intrastat (formato)](https://go.microsoft.com/fwlink/?linkid=849038)

