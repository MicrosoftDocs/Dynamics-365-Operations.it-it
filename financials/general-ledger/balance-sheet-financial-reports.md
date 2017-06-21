---
title: Report finanziari del conto patrimoniale
description: In questo articolo viene descritto i report predefiniti per gli stati patrimoniali. Sono descritti inoltre i blocchi predefiniti associati a questi report.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1cb7ef4b1b08caff39f0693eef6743bbe5d3892e
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="balance-sheet-financial-reports"></a>Report finanziari del conto patrimoniale

[!include[banner](../includes/banner.md)]


In questo articolo viene descritto i report predefiniti per gli stati patrimoniali. Sono descritti inoltre i blocchi predefiniti associati a questi report. 

<a name="default-balance-sheet-reports"></a>Report predefiniti del conto patrimoniale
-----------------------------

Sono disponibili due report predefiniti del conto patrimoniale. In un report, le sezioni sono in pila. Nell'altro report, le sezioni sono affiancate.

| Report predefinito                       | Funzionamento                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Stato patrimoniale - Predefinito              | Fornisce una visualizzazione della posizione finanziaria dell'organizzazione per l'anno.                                                                 |
| Stato patrimoniale affiancato – Predefinito | Fornisce una visualizzazione della posizione finanziaria dell'organizzazione per l'anno. I cespiti e le passività e il capitale netto dell'azionista sono affiancati. |

## <a name="building-blocks"></a>Blocchi predefiniti
I report finanziari del conto patrimoniale utilizzano i seguenti blocchi predefiniti.

| Report predefinito                       | Definizione riga                       | Definizione colonna             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Conto patrimoniale - Predefinito              | Conto patrimoniale - Predefinito              | Da inizio anno e scostamento - Predefinito    |
| Stato patrimoniale affiancato – Predefinito | Stato patrimoniale affiancato – Predefinito | Colonna da inizio anno - Predefinito |

### <a name="row-definition"></a>Definizione riga

Le definizioni di riga per entrambi i report del conto patrimoniale contengono le sezioni per ogni parte del conto patrimoniale tradizionale. Il report affiancato include un'interruzione di colonna, in modo che le passività e il capitale netto del proprietario siano visualizzati accanto ai cespiti. La dimensione Categoria di conti principali viene utilizzata per creare entrambi le definizioni di riga. Di conseguenza, chiunque può generare i report senza dover apportare eventuali modifiche.

### <a name="column-definition"></a>Definizione colonna

Le definizioni di colonna contengono i diversi tipi di colonna per fornire diversi livelli di dettagli e dati finanziari.

-   **Da inizio anno e scostamento - Tipi predefiniti di colonna:**
    -   **DESC** - Descrizione della definizione di riga.
    -   **FD** I dati finanziari da inizio anno per l'anno corrente
    -   **FD** I dati finanziari da inizio anno per l'anno precedente
    -   **CALC** Lo scostamento della sottrazione dell'anno precedente dall'anno corrente

<!-- -->

-   **Colonna da inizio anno - Predefinito:**
    -   **DESC** - Descrizione della definizione di riga.
    -   **FD** I dati finanziari da inizio anno per l'anno corrente

 

<a name="see-also"></a>Vedere anche
--------

[Creazione di report finanziari](financial-reporting-getting-started.md)

[Visualizza report finanziari](view-financial-reports.md)

[Blog sui report finanziari di Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




