---
title: Panoramica sulla riconciliazione bancaria avanzata
description: "Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato. La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 00f022da597b1de2454e93123de31731c6a65962
ms.openlocfilehash: 20363ef1917f7d0796cb0d5cd8e623c598b5ee01
ms.lasthandoff: 03/31/2017


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
    -   Una regola di abbinamento della riconciliazione è un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe di transazione bancaria di Microsoft Dynamics 365 for Operations durante il processo di riconciliazione. A seconda della procedura aziendale, è possibile impostare più regole di abbinamento per automatizzare e ottimizzare il processo di riconciliazione.

3.  Riconciliare i rendiconti bancari con le transazioni bancarie di Microsoft Dynamics 365 for Operations.
    -   Eseguire la corrispondenza automatica e la creazione dei giornali di registrazione riconciliazione.
    -   Visualizzare i rendiconti bancari e le transazioni bancarie di Microsoft Dynamics 365 for Operations in modalità affiancata.
    -   Registrare automaticamente le transazioni bancarie di Microsoft Dynamics 365 for Operations se vengono visualizzate in un rendiconto bancario ma non in Microsoft Dynamics 365 for Operations.
    -   Generare un rendiconto riconciliazione.






