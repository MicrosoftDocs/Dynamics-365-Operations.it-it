---
title: Panoramica sulla riconciliazione bancaria avanzata
description: "Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato. La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: ff59250b836a73986848109ce48f843fed1d71a9
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="advanced-bank-reconciliation-overview"></a>Panoramica sulla riconciliazione bancaria avanzata

[!include[banner](../includes/banner.md)]


Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato. La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie.

La funzionalità di riconciliazione bancaria avanzata consente di includere i rendiconti bancari. Il rendiconto bancario importato può automaticamente essere riconciliato dalle transazioni bancarie. Di seguito sono riportati i passaggi del flusso di riconciliazione bancaria avanzata.

1.  Impostare un'importazione dell'estratto conto bancario.
    -   Importare i rendiconti bancari tramite il framework dell'entità di dati.
    -   I formati tipici di rendiconto bancario sono incorporati: ISO20022, BAI2 e MT940.
    -   La funzionalità può essere estesa a qualsiasi formato.

2.  Impostare una sequenza numerica da utilizzare per la riconciliazione bancaria avanzata e definire le regole di abbinamento della riconciliazione estratti conto.
    -   Una regola di abbinamento della riconciliazione è un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe di transazione bancaria di Microsoft Dynamics 365 for Finance and Operations durante il processo di riconciliazione. A seconda della procedura aziendale, è possibile impostare più regole di abbinamento per automatizzare e ottimizzare il processo di riconciliazione.

3.  Riconciliare i rendiconti bancari con le transazioni bancarie di Finance and Operations.
    -   Eseguire la corrispondenza automatica e la creazione dei giornali di registrazione riconciliazione.
    -   Visualizzare i rendiconti bancari e le transazioni bancarie di Finance and Operations in modalità affiancata.
    -   Registrare automaticamente le transazioni bancarie di Finance and Operations se vengono visualizzate in un rendiconto bancario ma non in Finance and Operations.
    -   Generare un rendiconto riconciliazione.






