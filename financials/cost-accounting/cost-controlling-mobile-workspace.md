---
title: Area di lavoro mobile di controllo dei costi per Microsoft Dynamics 365 per il app di operazioni
description: Nell&quot;area di lavoro di cellulare di controllo costi, dirigenti del centro di costo possono visualizzare le prestazioni del centro di costo in qualsiasi momento e ovunque.
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

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Area di lavoro mobile di controllo dei costi per Microsoft Dynamics 365 per il app di operazioni

Nell'area di lavoro di cellulare di controllo costi, dirigenti del centro di costo possono visualizzare le prestazioni del centro di costo in qualsiasi momento e ovunque. 

<a name="prerequisites"></a>Prerequisiti
-------------

| Prerequisito                                                         | descrizione                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Letto di Microsoft Dynamics 365 per la presentazione di cellulare di operazioni | [Dynamics 365 per la presentazione mobile] di operazioni (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 per le operazioni                                          | Assicurarsi che si utilizza un ambiente con Microsoft Dynamics 365 per la versione 1611 delle operazioni e Microsoft Dynamics per l'aggiornamento 3 la piattaforma delle operazioni (novembre 2016). |
| 3215650 KB di Hotfix                                                    | Impostare il hotfix per abilitare le aree di lavoro che vengono fornite in Microsoft Dynamics 365 per le operazioni.                                                                       |
| Dispositivo mobile con Dynamics 365 per il app delle operazioni in | Scaricare Dynamics 365 per il app delle operazioni dalla memoria di cellulare del app.                                                                                                      |

## <a name="introduction"></a>Introduzione
L'area di lavoro di cellulare di controllo costi è disponibile una visualizzazione immediata delle prestazioni corrente di centri di costo confrontando i costi effettivi rispetto ai costi a budget. È possibile eseguire il drill-down negli stati di singoli elementi di costo.

### <a name="example"></a>Esempio

Un dipendente riceve un invito a una conferenza internazionale. Organizzazione dovrà coprire tutte le spese di viaggio. Il dipendente richiede la relativa mangiatoia se è possibile partecipare alla conferenza. Il responsabile aperto rapidamente l'area di lavoro mobile di controllo dei costi nel suo cellulare di verificare se in budget per il dipendente è possibile conferenza.

### <a name="data-security"></a>Sicurezza dei dati

I dati nell'area di lavoro di controllo costi vengono assicurati le credenziali dell'utente. Un responsabile del centro di costo è consentito visualizzare solo i dati per il proprio il centro di costo. La protezione a livello di accesso viene gestita nel modulo Contabilità industriale. I costi contabili definiscono la configurazione di cellulare di controllo costi dell'area di lavoro nel modulo Contabilità industriale. Al termine dell'area di lavoro viene emessa a Microsoft Dynamics 365 per il app operazioni, è disponibile in Dynamics 365 per il app di cellulare delle operazioni. Ciò garantisce che tutti i responsabili del centro di costo dell'organizzazione la i dati nello stesso formato.

### <a name="actions-views-and-links"></a>Azioni, visualizzazione e collegamenti

L'area di lavoro di controllo mobile per Dynamics di costo per il 365 dell'app Approvazioni delle operazioni sono disponibili le seguenti azioni, visualizzazione e collegamenti:

-   Azioni 
    -   Selezionare ** configurazioni ** per selezionare un layout.
    -   Selezionare ** costi gli oggetti ** per selezionare i centri di costo nel quale i dati di filtro. ** Nota: ** Nell'elenco vengono visualizzati in base all'accesso assegnato nel modulo Contabilità industriale.

<!-- -->

-   In base a quanto viene selezionato sotto ** ** azioni e delle transazioni viene configurato nel modulo Contabilità industriale, è possibile visualizzare le seguenti informazioni nelle schede. Tenere presente che l'importo visualizzato lo stesso formato: Le entrate, budget, scostamento e scostamento %. 
    -   Effettivi rispetto al budget (periodo corrente)
    -   Effettivi rispetto al budget rivisto (periodo corrente)
    -   Effettivi rispetto al budget (periodo precedente)
    -   Effettivi rispetto al budget rivisto (periodo precedente)
    -   Effettivi rispetto al budget (Data di fine anno)
    -   Effettivi rispetto al budget rivisto (Data di fine anno)

<!-- -->

-   Collegamenti
    -   Dettagli del periodo corrente.
    -   Dettagli del periodo precedente.
    -   Dettagli per Data di fine anno.

Quando si seleziona uno dei collegamenti, una scheda per visualizzare l'elemento di costo. Importo nelle schede visualizzate nel formato seguente: Scostamento valori effettivi, di budget, di budget, scostamento di budget %, scostamento di budget rivisto, del budget rivisto e scostamento di budget rivisto %.  [![che controlla (]. /media/cost-controlling.png)](. /media/cost-controlling.png)

## <a name="get-started"></a>Per iniziare
Seguire questi passaggi per iniziare nell'app Approvazioni di cellulare del controllo costi del dispositivo mobile.

1.  Nella memoria di cellulare del app, download e impostare Microsoft Dynamics 365 per il app delle operazioni.
2.  Inizia app Approvazioni sull'unità.
3.  Immettere il proprio Dynamics 365 URL.
4.  Immettere la società in per accedere a. Ad esempio, immettere USMF ** **.
5.  La prima volta che ha in, verrà chiesto di specificare il nome utente e password per il sistema Microsoft Dynamics 365 per l'account operazioni. Immettere le credenziali. Dopo avere accesso in, vengono visualizzate le aree di lavoro disponibili per la società.

Per visualizzare le aree di lavoro nell'app Approvazioni di cellulare, è necessario rilasciare le aree di lavoro desiderate in Dynamics 365 per il app delle operazioni.

1.  Avviare Dynamics 365 per le operazioni.
2.  ** Fare clic su Amministrazione sistema ** &gt; ** l'impostazione ** &gt; ** parametri di sistema **.
3.  Selezionare ** gestire il app mobile **.
4.  Selezionare l'area di lavoro ** ** di controllo per emettere la piattaforma spostato.
5.  ** Pubblicare Selezionare l'area di lavoro **.
6.  Aggiorna la propria unità per visualizzare le aree di lavoro generati.

## <a name="view-the-performance-of-your-cost-center"></a>Consente di visualizzare le prestazioni del centro di costo
1.  Nel dispositivo mobile, selezionare ** il controllo costi ** l'area di lavoro.
2.  ** Selezionare il controllo costi oggetti **.
3.  Fare clic su ** ** azioni.
4.  Fare clic su ** configurazione selezionata ** per selezionare un layout di controllo di costi.
5.  Click **Done**.
6.  Fare clic su ** ** azioni.
7.  Fare clic su ** oggetto di costo selezionato ** per selezionare i centri di costo a cui è stato assegnato l'accesso.
8.  Click **Done**.
9.  Consente di visualizzare le prestazioni complessive del centro di costo.
10. Fare clic su ** dettagli per il periodo corrente **.
11. Consente di visualizzare le prestazioni di singoli elementi di costo.
12. È inoltre possibile cercare gli elementi dei costi specifici.



