---
title: Area di lavoro mobile di controllo costi
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Controllo costi. Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 5b57bf268ac9e91c98a0b8709061e695ebf482c6
ms.contentlocale: it-it
ms.lasthandoff: 12/01/2017

---

# <a name="cost-controlling-mobile-workspace"></a>Area di lavoro mobile di controllo costi

[!include[banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Controllo costi**. Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque.

Questa area di lavoro mobile può essere utilizzata con l'app mobile Microsoft Dynamics 365 for Unified Operations.

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
    
    [![Scheda per un elemento costo ](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Prerequisiti
I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Prerequisiti per l'utilizzo di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition
Se Microsoft Dynamics 365 for Finance and Operations, Enterprise edition è stato distribuito nell'organizzazione, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Controllo costi**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Prerequisiti se si usa Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva
Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti.

<table>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementare l'articoloo KB 4013633.</td>
<td>Amministratore di sistema</td>

<td>L'articolo KB 4013633 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Controllo costi</strong>. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Pubblicare l'area di lavoro mobile <strong>Controllo costi</strong>.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app mobile
Scaricare e installare l'app mobile Dynamics 365 for Unified Operations:

-   [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile

1.  Avviare l'app sul dispositivo mobile.
2.  Immettere il proprio URL Dynamics 365.
3.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
4.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

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


