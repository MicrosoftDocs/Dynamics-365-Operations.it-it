---
title: Report rollforward cespiti
description: In questo argomento viene descritto come utilizzare il report rollforward cespiti.
author: saraschi2
manager: 
ms.date: 01/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: 0a78df4ede8fd57afbc3e9a7e5a38b840f479cdf
ms.contentlocale: it-it
ms.lasthandoff: 01/25/2018

---
# <a name="fixed-assets-roll-forward-report"></a>Report rollforward cespiti

[!include[banner](../includes/banner.md)]

Il report **rollforward cespiti** fornisce, in un formato Microsoft Excel di facile lettura, i dati dettagliati dei cespiti necessari per la chiusura di periodi, rendiconti finanziari e rendiconti fiscali. Il report include i saldi di inizio e di fine per i cespiti, unitamente ai movimenti di valutazione del periodo e a qualsiasi nuova acquisizione e dismissione di cespiti verificatasi nel periodo. I dati sono riportati per i singoli cespiti e sono inoltre riepilogati per gruppi di cespiti e persona giuridica.

Nel report **rollforward cespiti** viene utilizzato il framework di report elettronici (ER). Prima di poter eseguire il report, è necessario importare il modello di cespiti e le configurazioni di roll-forward dei cespiti da Microsoft Dynamics Lifecycle Services (LCS). Per istruzioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).

Il report è disponibile in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, oppure come correzione rapida di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (luglio 2017). Agli ambienti con la versione di luglio 2017, devono essere applicate tre correzioni rapide:

- **KB 4041754**: impossibile scaricare la configurazione ER da LCS poiché non applicabile per la versione dell'applicazione corrente dopo l'applicazione del pacchetto di aggiornamento della piattaforma
- **KB 4056107**: aggiornamento cumulativo 5 per i report elettronici (GER)
- **KB 4056353**: il rendiconto cespiti e i report note non soddisfano i requisiti GAAP e IFRS

Nella seguente tabella vengono illustrati i campi disponibili nel report.

| Campo                                       | descrizione |
|---------------------------------------------|-------------|
| Saldi: apertura                           | Il valore contabile netto del cespite alla data "da" specificata nel report. |
| Saldi: chiusura                           | Il valore contabile netto del cespite alla data "a" specificata nel report. |
| Acquisizioni: valore di apertura                 | La somma di tutte le transazioni di tipo **Acquisizione** e **Rettifica acquisizione** fino alla data "da" specificata nel report. |
| Acquisizioni: acquisizioni periodo           | La somma di tutte le transazioni di tipo **Acquisizione** e **Rettifica acquisizione** registrate durante l'intervallo di date specificato per il report. |
| Acquisizioni: dismissioni periodo              | La somma di tutte le transazioni di storno acquisizione con una transazione di dismissione registrate durante l'intervallo di date specificato per il report. |
| Acquisizioni: valore di chiusura                 | La somma di tutte le transazioni di tipo **Acquisizione** e **Rettifica acquisizione** fino alla data "a" specificata nel report. |
| Ammortamenti: valore di apertura                | La somma di tutte le transazioni tipo **Ammortamento**, **Rettifica ammortamento**, **Fondo di ammortamento speciale** e **Ammortamento straordinario** fino alla data "da" specificata nel report. |
| Ammortamenti: ammortamenti periodo         | La somma di tutte le transazioni di tipo **Ammortamento**, **Rettifica ammortamento** e **Ammortamento straordinario** registrate durante l'intervallo di date specificato per il report. |
| Ammortamenti: ammortamenti speciali periodo | La somma di tutte le transazioni di tipo **Fondo di ammortamento speciale** registrate durante l'intervallo di date specificato per il report. |
| Ammortamenti: dismissioni del periodo             | La somma di tutti gli storni di ammortamento con una transazione di dismissione registrati durante l'intervallo di date specificato per il report. |
| Ammortamenti: valore di chiusura                | La somma di tutte le transazioni tipo **Ammortamento**, **Rettifica ammortamento**, **Fondo di ammortamento speciale** e **Ammortamento straordinario** fino alla data "a" specificata nel report. |
| Rettifiche di rivalutazione/svalutazione: valore di apertura        | La somma di tutte le transazioni di tipo **Rettifica di rivalutazione**, **Rettifica di svalutazione** e **Rivalutazione** fino alla data "da" specificata nel report. |
| Rettifiche di rivalutazione/svalutazione: rettifiche di rivalutazione periodo     | La somma di tutte le transazioni di tipo **Rettifica di rivalutazione** registrate durante l'intervallo di date specificato per il report. |
| Rettifiche di rivalutazione/svalutazione: rettifiche di svalutazione periodo   | La somma di tutte le transazioni di tipo **Rettifica di svalutazione** registrate durante l'intervallo di date specificato per il report. |
| Rettifiche di rivalutazione/svalutazione: rivalutazioni periodo  | La somma di tutte le transazioni di tipo **Rivalutazione** registrate durante l'intervallo di date specificato per il report. |
| Rettifiche di rivalutazione/svalutazione: dismissioni periodo     | La somma di tutte le transazioni di storno di rettifiche di rivalutazione/svalutazione e di rivalutazioni con una transazione di dismissione registrati durante l'intervallo di date specificato per il report. |
| Rettifiche di rivalutazione/svalutazione: valore di chiusura        | La somma di tutte le transazioni di tipo **Rettifica di rivalutazione**, **Rettifica di svalutazione** e **Rivalutazione** fino alla data "a" specificata nel report. |
| Dismissioni: data dismissione                    | La data di dismissione per il libro cespiti. |
| Dismissioni: valore contabile netto alla dismissione       | Il valore contabile netto del libro cespiti al momento della dismissione. |
| Dismissioni: valore di vendita                       | Il valore di vendita del libro cespiti con una transazione di dismissione di vendita. |
| Dismissioni: valore di scarto                      | Il valore di scarto del libro cespiti con una transazione di dismissione di scarto. |
| Dismissioni: profitti/perdite                      | Valore dei profitti o delle perdite calcolato come parte della transazione di dismissione per il libro cespiti. |

