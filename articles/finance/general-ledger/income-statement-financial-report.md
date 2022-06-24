---
title: Report finanziario conto economico
description: In questo articolo viene descritto il report predefinito per i conti economici. Sono descritti inoltre i blocchi predefiniti associati a questo report.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9a1f20ed5e2a84e0d18101ede46ffffef4230c7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868462"
---
# <a name="income-statement-financial-report"></a>Report finanziario conto economico

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto il report predefinito per i conti economici. Sono descritti inoltre i blocchi predefiniti associati a questo report. 

## <a name="default-income-statement-report"></a>Report predefinito conto economico

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



## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sulla creazione di report finanziari](financial-reporting-getting-started.md)

[Visualizzare report finanziari](view-financial-reports.md)

[Blog sui report finanziari di Dynamics](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
