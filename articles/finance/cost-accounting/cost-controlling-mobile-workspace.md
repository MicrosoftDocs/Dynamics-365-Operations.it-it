---
title: Area di lavoro mobile di controllo costi
description: In questo articolo vengono fornite informazioni sull'area di lavoro mobile Controllo costi. Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque.
author: AndersGirke
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 2d6d3fdcc0b0387a92f138b0ba7cf537f473b91a
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069565"
---
# <a name="cost-controlling-mobile-workspace"></a>Area di lavoro mobile di controllo costi

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

In questo articolo vengono fornite informazioni sull'area di lavoro mobile **Controllo costi**. Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque.

Questa area di lavoro mobile può essere utilizzata con l'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365).

## <a name="overview"></a>Panoramica
L'area di lavoro mobile **Controllo costi** fornisce una visualizzazione immediata delle prestazioni correnti dei centri di costo confrontando i costi effettivi rispetto ai costi a budget. È possibile eseguire il drill-down per visualizzare lo stato dei singoli elementi di costo.

Ad esempio, un dipendente riceve un invito a una conferenza internazionale, ma l'organizzazione deve coprire tutte le spese di viaggio. Il dipendente chiede al responsabile se può partecipare alla conferenza. Il responsabile apre rapidamente l'area di lavoro mobile **Controllo costi** sul dispositivo mobile per verificare se dispone del budget per consentire al dipendente di partecipare alla conferenza.

### <a name="data-security"></a>Sicurezza dei dati
I dati nell'area di lavoro **Controllo costi** sono protetti mediante l'uso di credenziali dell'utente. I responsabili del centro di costo possono visualizzare solo i dati relativi al proprio centro di costo. La protezione a livello di accesso viene gestita nel modulo **Contabilità industriale**.

I contabili definiscono la configurazione dell'area di lavoro mobile **Controllo costi** nel modulo **Contabilità industriale**. Una volta che l'area di lavoro è stata pubblicata nell'app mobile, sarà disponibile nell'app. Pertanto, tutti i responsabili del centro di costo dell'organizzazione visualizzano i dati nello stesso formato.

### <a name="actions-views-and-links"></a>Azioni, visualizzazioni e collegamenti
L'area di lavoro mobile **Controllo costi** fornisce le azioni, le visualizzazioni e i collegamenti seguenti:

-   **Azioni**:

    -   Utilizzare **Seleziona configurazione** per selezionare un layout.
    -   Utilizzare **Seleziona oggetto di costo** per selezionare i centri di costo in base a cui filtrare i dati.
    
        > [!NOTE]
        > I centri di costo visualizzati nell'elenco dipendono dall'accesso assegnato nel modulo **Contabilità industriale**.

-   **Visualizzazioni**: in base alle azioni selezionate e alla configurazione nel modulo **Contabilità industriale**, è possibile visualizzare le seguenti informazioni nelle schede:

    -   Effettivi rispetto al budget (periodo corrente)
    -   Effettivi rispetto al budget rivisto (periodo corrente)
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
    
    [![Scheda per un elemento costo.](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Prerequisiti
I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a>Prerequisiti per l'utilizzo di Microsoft Dynamics 365 Finance
Se Finance è stato distribuito nell'organizzazione, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Controllo costi**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>Prerequisiti se si usa la versione 1611 con Aggiornamento piattaforma 3 o versione successiva
Se nell'organizzazione è stato distribuita la versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti.

<table>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementare l'articoloo KB 4013633.</td>
<td>Amministratore di sistema</td>

<td>L'articolo KB 4013633 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Controllo costi</strong>. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Applicare il pacchetto distribuibile</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Pubblicare l'area di lavoro mobile <strong>Controllo costi</strong>.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app per dispositivi mobili
Scarica e installa l'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365):

-   [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile

1.  Avviare l'app sul dispositivo mobile.
2.  Immettere il proprio URL Dynamics 365.
3.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
4.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

[![Trascinare verso il basso.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

