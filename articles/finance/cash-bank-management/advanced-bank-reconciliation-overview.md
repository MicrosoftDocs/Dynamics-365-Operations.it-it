---
title: Panoramica sulla riconciliazione bancaria avanzata
description: Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato. La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie.
author: angelad116
ms.date: 10/24/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: kfend
ms.custom:
- "22104"
- intro-internal
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 677a032ce77fbe57393c85235a1c64dba3958f2d
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715151"
---
# <a name="advanced-bank-reconciliation-overview"></a>Panoramica sulla riconciliazione bancaria avanzata

[!include [banner](../includes/banner.md)]

Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato. La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie.

La funzionalità di riconciliazione bancaria avanzata consente di includere i rendiconti bancari. Il rendiconto bancario importato può automaticamente essere riconciliato dalle transazioni bancarie. Di seguito sono riportati i passaggi del flusso di riconciliazione bancaria avanzata.

1.  Impostare un'importazione dell'estratto conto bancario.
    -   Importare i rendiconti bancari tramite il framework dell'entità di dati.
    -   I formati tipici di rendiconto bancario sono incorporati: ISO20022, BAI2 e MT940.
    -   La funzionalità può essere estesa a qualsiasi formato.

2.  Impostare una sequenza numerica da utilizzare per la riconciliazione bancaria avanzata e definire le regole di abbinamento della riconciliazione estratti conto.
    -   Una regola di abbinamento della riconciliazione è un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe di transazione bancaria di Microsoft Dynamics 365 Finance durante il processo di riconciliazione. A seconda della procedura aziendale, è possibile impostare più regole di abbinamento per automatizzare e ottimizzare il processo di riconciliazione.

3.  Riconciliare i rendiconti bancari con le transazioni bancarie di Finance.
    -   Eseguire la corrispondenza automatica e la creazione dei giornali di registrazione riconciliazione.
    -   Visualizzare i rendiconti bancari e le transazioni bancarie di Finance in modalità affiancata.
    -   Registrare automaticamente le transazioni bancarie di Finance se vengono visualizzate in un rendiconto bancario ma non nell'app Finance.
    -   Generare un rendiconto riconciliazione.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
