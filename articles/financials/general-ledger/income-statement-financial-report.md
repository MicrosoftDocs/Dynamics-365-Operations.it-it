---
title: Report finanziario conto economico
description: In questo articolo viene descritto il report predefinito per i conti economici. Sono descritti inoltre i blocchi predefiniti associati a questo report.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9310508082ff710cd040b74519044f5a90c23988
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

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

[Creazione di report finanziari](financial-reporting-getting-started.md)

[Visualizzare i report finanziari](view-financial-reports.md)

[Blog sui report finanziari di Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




