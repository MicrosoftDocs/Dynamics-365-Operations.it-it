---
title: Report finanziario conto economico
description: In questo articolo viene descritto il report predefinito per i conti economici. Sono descritti inoltre i blocchi predefiniti associati a questo report.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fab0e9d5e550b1848c3483b3172836e258353ebb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249073"
---
# <a name="income-statement-financial-report"></a>Report finanziario conto economico

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto il report predefinito per i conti economici. Sono descritti inoltre i blocchi predefiniti associati a questo report. 

<a name="default-income-statement-report"></a>Report predefinito conto economico
-------------------------------

| Report predefinito             | Funzionamento                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Conto economico - Predefinito | Fornisce una visualizzazione della redditività dell'organizzazione per il periodo corrente e da inizio anno. |

## <a name="building-blocks"></a>Blocchi predefiniti
Il report finanziario del conto economico utilizza i seguenti blocchi predefiniti.

| Report predefinito             | Definizione riga                     | Definizione colonna          |
|----------------------------|------------------------------------|----------------------------|
| Conto economico - Predefinito | Conto economico riepilogativo - Predefinito | Periodico e da inizio anno - Predefinito |

### <a name="row-definition"></a>Definizione riga

La definizione di riga, Conto economico riepilogativo - Predefinito, contiene una sezione per ogni parte del conto economico tradizionale. La dimensione Categoria di conti principali viene utilizzata per creare la definizione di riga. Di conseguenza, chiunque può generare il report senza dover apportare eventuali modifiche.

### <a name="column-definition"></a>Definizione colonna

Le definizioni di colonna contengono i diversi tipi di colonna per fornire diversi livelli di dettagli e dati finanziari.

-   **Periodico e da inizio anno - Tipi predefiniti di colonna:**
    -   **DESC** - Descrizione della definizione di riga.
    -   **FD** I dati finanziari per il periodo corrente
    -   **FD** I dati finanziari da inizio anno



<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica sulla creazione di report finanziari](financial-reporting-getting-started.md)

[Visualizzare report finanziari](view-financial-reports.md)

[Blog sui report finanziari di Dynamics](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]