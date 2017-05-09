---
title: Area di lavoro mobile Controllo costi per l&quot;app Microsoft Dynamics 365 for Operations
description: Nell&quot;area di lavoro mobile Controllo costi, i responsabili del centro di costo possono esaminare le prestazioni del centro di costo in qualsiasi momento e ovunque si trovino.
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Area di lavoro mobile Controllo costi per l'app Microsoft Dynamics 365 for Operations

Nell'area di lavoro mobile Controllo costi, i responsabili del centro di costo possono esaminare le prestazioni del centro di costo in qualsiasi momento e ovunque si trovino. 

<a name="prerequisites"></a>Prerequisiti
-------------

| Prerequisito                                                         | descrizione                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Informazioni sulla piattaforma mobile Microsoft Dynamics 365 for Operations | [Piattaforma mobile di Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Assicurarsi di utilizzare un ambiente con Microsoft Dynamics 365 for Operations versione 1611 e l'aggiornamento 3 della piattaforma di Microsoft Dynamics for Operations (novembre 2016). |
| Hotfix KB 3215650                                                    | Impostare l'hotfix per abilitare le aree di lavoro che vengono fornite in Microsoft Dynamics 365 for Operations.                                                                       |
| Dispositivo mobile con l'app Dynamics 365 for Operations installata | Scaricare l'app Dynamics 365 for Operations dall'App Store mobile.                                                                                                      |

## <a name="introduction"></a>Introduzione
L'area di lavoro mobile Controllo costi fornisce una visualizzazione immediata delle prestazioni correnti dei centri di costo confrontando i costi effettivi rispetto ai costi a budget. È possibile eseguire il drill-down per visualizzare gli stati di singoli elementi di costo.

### <a name="example"></a>Esempio

Un dipendente riceve un invito a una conferenza internazionale. L'organizzazione dovrà coprire tutte le spese di viaggio. Il dipendente chiede al responsabile se può partecipare alla conferenza. Il responsabile apre rapidamente l'area di lavoro mobile Controllo costi sul suo telefono cellulare per verificare se dispone del budget per consentire al dipendente di partecipare alla conferenza.

### <a name="data-security"></a>Sicurezza dei dati

I dati nell'area di lavoro Controllo costi sono protetti mediante l'uso di credenziali dell'utente. Un responsabile del centro di costo può visualizzare solo i dati per il proprio centro di costo. La protezione a livello di accesso viene gestita nel modulo Contabilità industriale. I contabili definiscono la configurazione dell'area di lavoro mobile Controllo costi nel modulo Contabilità industriale. Una volta che l'area di lavoro è stata pubblicata nell'app Microsoft Dynamics 365 for Operations, è disponibile nell'app mobile Microsoft Dynamics 365 for Operations. Ciò garantisce che tutti i responsabili del centro di costo dell'organizzazione visualizzino i dati nello stesso formato.

### <a name="actions-views-and-links"></a>Azioni, visualizzazioni e collegamenti

L'area di lavoro mobile Controllo costi per l'app Dynamics 365 for Operations fornisce le seguenti azioni, visualizzazioni e collegamenti:

-   Azioni 
    -   Selezionare **Configurazioni** per scegliere un layout.
    -   Selezionare **Oggetti di costo** per scegliere i centri di costo nei quali si desidera filtrare i dati. **Nota:** l'elenco viene visualizzato in base all'accesso assegnato nel modulo Contabilità industriale.

<!-- -->

-   In base a quanto selezionato in **Azioni** e quanto configurato nel modulo Contabilità industriale, è possibile visualizzare le seguenti informazioni nelle schede. Tenere presente che l'importo è visualizzato nello stesso formato: Effettivo, Budget, Scostamento e % scostamento. 
    -   Effettivo rispetto a Budget (periodo corrente)
    -   Effettivo rispetto a Budget rivisto (periodo corrente)
    -   Effettivo rispetto a Budget (periodo precedente)
    -   Effettivo rispetto a Budget rivisto (periodo precedente)
    -   Effettivo rispetto a Budget (anno fino a oggi)
    -   Effettivo rispetto a Budget rivisto (anno fino a oggi)

<!-- -->

-   Collegamenti
    -   Dettagli per periodo corrente.
    -   Dettagli per periodo precedente.
    -   Dettagli per anno fino a oggi.

Quando si seleziona uno dei collegamenti, viene visualizzata una scheda per elemento di costo. L'importo nelle schede viene visualizzato nel formato seguente: Effettivo, Budget, Scostamento budget, % scostamento budget, Budget rivisto, Scostamento budget rivisto e % scostamento budget rivisto.  [![controllo-costi](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Per iniziare
Seguire questi passaggi per iniziare a utilizzare l'app mobile Controllo costi sul proprio dispositivo mobile.

1.  Nell'App Store mobile, scaricare e installare l'app Microsoft Dynamics 365 for Operations.
2.  Avviare l'app sul dispositivo.
3.  Immettere il proprio URL Dynamics 365.
4.  Immettere la società a cui accedere. Ad esempio, immettere **USMF**.
5.  La prima volta che si accede, verrà richiesto di specificare il nome utente e la password per l'account Microsoft Dynamics 365 for Operations. Immettere le proprie credenziali. Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.

Per visualizzare le aree di lavoro nell'app mobile, è necessario innanzitutto pubblicare le aree di lavoro desiderate nell'app Dynamics 365 for Operations.

1.  Avviare Dynamics 365 for Operations.
2.  Passare ad **Amministrazione sistema** &gt; **Impostazioni** &gt; **Parametri di sistema**.
3.  Selezionare **Gestisci app per dispositivi mobili**.
4.  Selezionare l'area di lavoro **Controllo costi** per pubblicare nella piattaforma mobile.
5.  Selezionare **Pubblica area di lavoro**.
6.  Aggiornare il dispositivo per visualizzare le aree di lavoro pubblicate.

## <a name="view-the-performance-of-your-cost-center"></a>Visualizzare le prestazioni del centro di costo
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Controllo costi**.
2.  Selezionare **Controllo oggetto di costo**.
3.  Fare clic su **Azioni**.
4.  Fare clic su **Seleziona configurazione** per selezionare un layout di controllo dei costi.
5.  Fare clic su **Fine**.
6.  Fare clic su **Azioni**.
7.  Fare clic su **Seleziona oggetto di costo** per selezionare i centri di costo a cui si ha accesso.
8.  Fare clic su **Fine**.
9.  Visualizzare le prestazioni complessive del centro di costo.
10. Fare clic su **Dettagli per periodo corrente**.
11. Visualizzare le prestazioni dei singoli elementi di costo.
12. È inoltre possibile cercare elementi di costo specifici.



