---
title: Area di lavoro mobile di controllo costi
description: In questo argomento vengono fornite informazioni sull&quot;area di lavoro mobile di controllo costi, disponibile per l&quot;app mobile Microsoft Dynamics 365 for Operations. Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque.
author: YuyuScheller
manager: AnnBe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 31a9650774b2ddb70827ffa210154ca10c761236
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="cost-controlling-mobile-workspace"></a>Area di lavoro mobile di controllo costi

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sull'area di lavoro mobile di controllo costi, disponibile per l'app mobile Microsoft Dynamics 365 for Operations. Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque. 

<a name="overview-of-the-cost-controlling-mobile-workspace"></a>Panoramica dell'area di lavoro mobile di controllo costi
-------------------------------------------------

L'area di lavoro mobile **Controllo costi** fornisce una visualizzazione immediata delle prestazioni correnti dei centri di costo confrontando i costi effettivi rispetto ai costi a budget. È possibile eseguire il drill-down per visualizzare gli stati di singoli elementi di costo. Ad esempio, un dipendente riceve un invito a una conferenza internazionale, ma l'organizzazione deve coprire tutte le spese di viaggio. Il dipendente chiede al responsabile se può partecipare alla conferenza. Il responsabile apre rapidamente l'area di lavoro mobile **Controllo costi** sul dispositivo mobile per verificare se dispone del budget per consentire al dipendente di partecipare alla conferenza.

### <a name="data-security"></a>Sicurezza dei dati

I dati nell'area di lavoro **Controllo costi** sono protetti mediante l'uso di credenziali dell'utente. I responsabili del centro di costo possono visualizzare solo i dati relativi al proprio centro di costo. La protezione a livello di accesso viene gestita nel modulo **Contabilità industriale**. I contabili definiscono la configurazione dell'area di lavoro mobile **Controllo costi** nel modulo **Contabilità industriale**. Una volta che l'area di lavoro è stata pubblicata nell'app mobile Microsoft Dynamics 365 for Operations, sarà disponibile nell'app mobile. Pertanto, tutti i responsabili del centro di costo dell'organizzazione visualizzano i dati nello stesso formato.

### <a name="actions-views-and-links"></a>Azioni, visualizzazioni e collegamenti

L'area di lavoro mobile **Controllo costi** per l'app Dynamics 365 for Operations fornisce le seguenti azioni, visualizzazioni e collegamenti:

-   **Azioni**:
    -   Utilizzare **Seleziona configurazione** per selezionare un layout.
    -   Utilizzare **Seleziona oggetto di costo** per selezionare i centri di costo in base a cui filtrare i dati. **Nota**: i centri di costo visualizzati nell'elenco dipendono dall'accesso assegnato nel modulo **Contabilità industriale**.
-   **Visualizzazioni**: in base alle azioni selezionate e alla configurazione nel modulo **Contabilità industriale**, è possibile visualizzare le seguenti informazioni nelle schede.
    -   Effettivo rispetto al budget (periodo corrente)
    -   Effettivo rispetto al budget rivisto (periodo corrente)
    -   Effettivo rispetto al budget (periodo precedente)
    -   Effettivo rispetto al budget rivisto (periodo precedente)
    -   Effettivo rispetto al budget (da inizio anno a oggi)
    -   Effettivo rispetto al budget rivisto (da inizio anno a oggi)

    Gli importi verranno visualizzati in tutte le schede: Effettivo, Budget, Scostamento e % scostamento.
-   **Collegamenti**:
    -   Dettagli per periodo corrente
    -   Dettagli per periodo precedente
    -   Dettagli per anno fino a oggi

    Quando si seleziona un collegamento, viene visualizzata una scheda per ciascun elemento di costo. In ogni scheda vengono visualizzati i seguenti importi: Effettivo, Budget, Scostamento budget, % scostamento budget, Budget rivisto, Scostamento budget rivisto e % scostamento budget rivisto. 
    
    [![Scheda per un elemento costo ](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="prerequisites"></a>Prerequisiti
Prima di utilizzare l'area di lavoro mobile **Controllo costi**, è necessario verificare che l'amministratore di sistema abbia predisposto i seguenti prerequisiti.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Deve essere stato implementato Dynamics 365 for Operations versione 1611 con aggiornamento alla piattaforma 3 o versione successiva.</td>
<td>Amministratore di sistema</td>
<td>Se Dynamics 365 for Operations non è ancora stato distribuito nell'organizzazione, l'amministratore di sistema deve vedere <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Distribuire un ambiente di dimostrazione di Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Deve essere stato implementato l'articolo KB 4013633.</td>
<td>Amministratore di sistema</td>
<td>KB 4013633 (un aggiornamento X++ o aggiornamento rapido dei metadati) contiene quattro aree di lavoro mobili per la gestione della supply chain. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li>Eseguire il download di KB 4013633 da Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Applicare il pacchetto distribuibile</a> al sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'area di lavoro mobile <strong>Controllo costi</strong> deve essere pubblicata nell'app mobile Dynamics 365 for Operations.</td>
<td>Amministratore di sistema</td>
<td><ol>
<li>Avviare Dynamics 365 for Operations nel browser.</li>
<li>Nella pagina <strong>Paramenti di sistema</strong> selezionare <strong>Gestisci aree di lavoro mobili</strong>.</li>
<li>Selezionare l'area di lavoro mobile <strong>Panoramica oggetto di costo</strong>.</li>
<li>Fare clic su <strong>Pubblica area di lavoro mobile</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Scaricare e installare l'app mobile Microsoft Dynamics 365 for Operations.
Scaricare e installare l'app mobile Microsoft Dynamics 365 for Operations dall'App Store mobile.

-   Per Android: [Dynamics 365 for Operations in Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Per iPhone: [Dynamics 365 for Operations nell'app store iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Accedere all'app mobile Microsoft Dynamics 365 for Operations
1.  Avviare l'app sul dispositivo mobile.
2.  Immettere l'URL per Dynamics 365 for Operations.
3.  Immettere la società a cui accedere. Ad esempio, immettere **USMF**.
4.  La prima volta che si accede, verrà richiesto di specificare il nome utente e la password per l'account Dynamics 365 for Operations. Immettere le proprie credenziali.
5.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è possibile effettuare il pull per aggiornare l'elenco delle aree di lavoro mobili. 

    [![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Visualizzare le prestazioni del centro di costo tramite l'area di lavoro mobile Controllo costi
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Controllo costi**.
2.  Selezionare **Controllo oggetto di costo**.
3.  Selezionare **Azioni**.
4.  Selezionare **Seleziona configurazione** per selezionare un layout di controllo dei costi.
5.  Selezionare **Fine**.
6.  Selezionare **Azioni**.
7.  Selezionare **Seleziona oggetto di costo** per selezionare i centri di costo a cui si ha accesso.
8.  Selezionare **Fine**.
9.  Visualizzare le prestazioni complessive del centro di costo.
10. Selezionare il collegamento **Dettagli per periodo corrente**.
11. Visualizzare le prestazioni dei singoli elementi di costo.
12. È inoltre possibile cercare elementi di costo specifici.





