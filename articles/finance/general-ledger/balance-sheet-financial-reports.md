---
title: Report finanziari del conto patrimoniale
description: In questo articolo viene descritto i report predefiniti per gli stati patrimoniali. Sono descritti inoltre i blocchi predefiniti associati a questi report.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bcfb8e8fd28224ac9fe9a4919f4252dcd01ce360
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212399"
---
# <a name="balance-sheet-financial-reports"></a>Report finanziari del conto patrimoniale

[!include [banner](../includes/banner.md)]

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



<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica sulla creazione di report finanziari](financial-reporting-getting-started.md)

[Visualizzare report finanziari](view-financial-reports.md)

[Blog sui report finanziari di Dynamics](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]