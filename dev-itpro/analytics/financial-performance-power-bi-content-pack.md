---
title: Di prestazioni finanziarie di contenuto Power BI
description: "In questo argomento viene descritto Microsoft Dynamics 365 per il collo del contenuto delle prestazioni finanziarie delle operazioni per Microsoft Power BI. Descrive il dashboard e i report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità che sono stati utilizzati per sviluppare un pacchetto di contenuto."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 227285720e7f28beeb135eea081940578531d458
ms.lasthandoff: 03/31/2017


---

# <a name="financial-performance-power-bi-content"></a>Di prestazioni finanziarie di contenuto Power BI

In questo argomento viene descritto Microsoft Dynamics 365 per il collo del contenuto delle prestazioni finanziarie delle operazioni per Microsoft Power BI. Descrive il dashboard e i report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità che sono stati utilizzati per sviluppare un pacchetto di contenuto.

<a name="accessing-the-content-pack"></a>Accesso al collo di contenuto
--------------------------

Due versioni del collo del contenuto delle prestazioni finanziarie sono disponibili. Una versione è disponibile da Servizi (LCS) del ciclo di vita di Microsoft Dynamics e l'altra è disponibile da PowerBI.com.

-   ** Versione disponibile nel LC: ** Il pacchetto del contenuto delle prestazioni finanziarie disponibile nel LC supporta Microsoft Dynamics 365 per la versione 1611 delle operazioni. Per trovare il collo di contenuto nella raccolta della risorsa condivisa in LC. Per ulteriori informazioni su come download del collo di contenuto e collegarlo al sistema Microsoft Dynamics 365 per le operazioni dati, vedere [di Power BI nel contenuto LC da Microsoft e dai partner power-bi-content-microsoft-partners.md] ().
-   ** Versione disponibile da PowerBI.com: ** Il pacchetto del contenuto delle prestazioni finanziarie disponibili da PowerBI.com supporta le versioni 7.0 e 7.0.1 di Microsoft Dynamics AX. Per ulteriori informazioni su come caricare e collegare il Dynamics 365 per le operazioni dati, vedere [Accesso di contenuto Power BI da PowerBI.com] () power-bi-home-page.md.

## <a name="main-account-setup"></a>Impostazione conto principale
Poiché le organizzazioni desiderano le passività e gli importi dei ricavi vengano visualizzate come importi di positività nei report, i conti principali in Dynamics 365 per le operazioni è importante. Affinché questi conti principali e verranno visualizzati come importi positivo, il tipo di conto principale deve essere impostato su ** passività ** o ** ricavi **. Quando questi tipi di conto vengono utilizzati, dichiarare con potenza di Microsoft BI invertirà i nomi e gli importi verranno visualizzati come positivo.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Dashboard e i report inclusi nel collo di contenuto
Dopo aver collegato il pacchetto di contenuti ai dati di Microsoft Dynamics 365 for Operations, nel dashboard e nei report vengono visualizzati i dati finanziari. Se non è stato utilizzato mai potenza BI prima, possono ottenere ulteriori informazioni sulla Guida [quattro pagina per Power BI] (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Il dashboard contiene riquadri di riepilogo di dati basati sui report sottostanti. Ogni riquadro contiene informazioni riepilogative per l'anno corrente per tutte le società in un'organizzazione. Di seguito vengono riportati alcuni di mattonelle:

-   In contanti
-   Ricavi totali anno in corso
-   Spese totali anno in corso
-   Reddito netto anno in corso
-   Indice rapido
-   Spese totali per l'anno in corso per la categoria di conti
-   Indice corrente
-   Rapporto debiti/totale attività
-   Ricavi effettivi rispetto ai ricavi previsti
-   Ricavo fatturato anno in corso
-   Indice spese operative anno in corso
-   Margine di profitto anno in corso
-   Spese effettive rispetto alle spese previste - tutte le società

Ogni mattonelle vengono appoggiate da un report di supporto. Questi report contengono i grafici e le tabelle che forniscono ulteriori informazioni. Nella seguente tabella vengono illustrati i report.

| Report                      | Informazioni contenute nel report                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Analisi di cassa               | Importo di cassa in base alla persona giuridica, cassa per trimestre, cassa totali e contanti al conto ** nota: ** ** Liquidità per trimestre ** il report non include i saldi iniziali in totale per il primo trimestre. Mostra il totale delle nuove transazioni registrate in ciascun trimestre.                                                                                |
| Analisi indice corrente      | Indice corrente in base alla persona giuridica e per trimestre e saldi per cespiti e passività correnti                                                                                                                                                                                                                              |
| Analisi indice rapido        | Report secco liquidità in base alla persona giuridica, report secco liquidità per trimestre e saldi in contanti, la contabilità clienti e le passività correnti                                                                                                                                                                                                                      |
| Analisi costo del venduto | Costo del venduto (COGS) in base alla persona giuridica, COGS per trimestre dell'anno in corso e dell'anno precedente, COGS rispetto alle vendite per persona giuridica, COGS totale e COGS in base alle percentuali di vendita                                                                                                                                                                                   |
| Analisi capitale circolante    | Capitale circolante in base alla persona giuridica, capitale circolante per trimestre, cespiti correnti, passività correnti e capitale circolante totale                                                                                                                                                                                                                   |
| Analisi cespiti e debiti     | Ritorno sui cespiti e sui debiti rispetto ai cespiti totali in base alla persona giuridica e al trimestre corrente, cespiti e passività                                                                                                                                                                                     |
| Analisi margine di profitto      | Margine di profitto effettivo e stimato in base alla persona giuridica e per trimestre, percentuale del margine di profitto e margine di profitto                                                                                                                                                                                                                       |
| Analisi reddito netto         | Reddito netto e previsto in base alla persona giuridica, reddito netto nell'anno in corso e in quello precedente e percentuale di spese rispetto al reddito netto                                                                                                                                                                                                                       |
| Analisi redditi           | Redditi effettivi e previsti prima di interessi e imposte (EBIT) in base alla persona giuridica, importo EBIT nell'anno in corso e in quello precedente, percentuale di spese rispetto ai ricavi e spese effettive e previste rispetto ai ricavi                                                                                                                                                          |
| Analisi ricavi            | Ricavi totali, ricavi totali effettivi e previsti in base alla persona giuridica, ricavi totali nell'anno in corso e in quello precedente, scostamento dal budget in base alla persona giuridica e ricavi totali nel periodo in corso e in quello precedente                                                                                                                                                 |
| Analisi spese            | Spese totali, spese totali effettive rispetto al budget in base alla persona giuridica, spese totali effettive e previste per trimestre, spese totali per categoria di conto e indice di spese operative                                                                                                                                                                 |
| Analisi ricavo fatturato     | Contabilità clienti totali, Contabilità clienti totali in base alla persona giuridica, Contabilità clienti totali per trimestre e i saldi per la contabilità clienti su ** nota: ** Report non includono saldi iniziali per i conti CoGe della contabilità clienti. Indicano il totale delle nuove transazioni registrate nella contabilità clienti. |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati che vengono immessi il dashboard e i report inclusi nel contenuto delle prestazioni finanziarie sono imballano Dynamics 365 per i dati delle operazioni. Le seguenti entità sono state utilizzate come base del collo di contenuto: ** Entità di dati aggregate **

-   ** GeneralLedgerActivities ** questa entità raggruppa i saldi contabili per la categoria di conti.
-   ** BudgetActivities ** questa entità raggruppa i saldi budget per la categoria di conti.

**Data entities**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Contabilità generali
-   ChartofAccounts

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Le misure calcolate vengono utilizzate per calcolare gli indicatori di prestazione chiave (KPIs) e i report utilizzati nel collo di contenuto. Per impostazione predefinita, il pacchetto di contenuti include dati per gli ultimi tre anni e un anno successivo. Per includere i calcoli aggiuntive in report e dashboard, è possibile modificare la [cartella di lavoro di Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Questa cartella di lavoro è il modello dati predefinito utilizzato per creare il pacchetto di contenuti. Al termine delle modifiche, è possibile creare un pacchetto di contenuti per l'organizzazione e un dashboard che contengono le informazioni aggiunte.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)



