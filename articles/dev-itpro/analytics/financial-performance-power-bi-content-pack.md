---
title: Contenuto Power BI per prestazioni finanziarie
description: Questo argomento descrive il contenuto Prestazioni finanziarie di Power BI.
author: kweekley
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 88bbc54721f5da94dd811ef155e8d3bcf8c2b53c
ms.openlocfilehash: d062937d8d1cb7d8e4f4cc055eb4514fa56b4eab
ms.contentlocale: it-it
ms.lasthandoff: 05/09/2018

---

# <a name="financial-performance-power-bi-content"></a>Contenuto Power BI per prestazioni finanziarie

[!include [banner](../includes/banner.md)]

> [!Note]
> Questo pacchetto di contenuti è stato deprecato come documentato in [Pacchetti di contenuti Power BI disponibili in AppSource](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Questo argomento descrive il contenuto **Prestazioni finanziarie** di Microsoft Power BI. Descrive il dashboard e i report che vengono inclusi e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="main-account-setup"></a>Impostazione del conto principale
Poiché le organizzazioni desiderano che le passività e gli importi dei ricavi appaiano come importi positivi nei report, l'impostazione dei conti principali è importante. Affinché questi conti principali vengano visualizzati come importi positivi, il tipo di conto principale deve essere impostato su **Passività** o **Ricavi**. Quando si utilizzano questi tipi di conto, la dichiarazione nei report tramite Power BI invertirà i segni e gli importi risulteranno positivi.

## <a name="dashboard-and-reports-that-are-included-in-the-power-bi-content"></a>Dashboard e report inclusi nel contenuto di Power BI
Il dashboard contiene riquadri di riepilogo di dati basati sui report sottostanti. Ogni riquadro contiene informazioni riepilogative per l'anno corrente per tutte le società in un'organizzazione. Di seguito sono riportati alcuni riquadri:

- In contanti
- Ricavi totali anno in corso
- Spese totali anno in corso
- Reddito netto anno in corso
- Indice rapido
- Spese totali per l'anno in corso per la categoria di conti
- Indice corrente
- Rapporto debiti/totale attività
- Ricavi effettivi rispetto ai ricavi previsti
- Ricavo fatturato anno in corso
- Indice spese operative anno in corso
- Margine di profitto anno in corso
- Spese effettive rispetto alle spese previste - tutte le società

Ogni riquadro è supportato da un report. Questi report contengono i grafici e le tabelle che forniscono ulteriori informazioni. Nella seguente tabella vengono illustrati i report.

| Report                      | Informazioni contenute nel report |
|-----------------------------|--------------------------------------|
| Analisi di cassa               | Importo di cassa in base alla persona giuridica e al trimestre, importo di cassa totale e per conto<br><br>**Nota:** l'importo di cassa per trimestre non include i saldi iniziali nel totale per il primo trimestre. Mostra il totale delle nuove transazioni registrate in ciascun trimestre.|
| Analisi indice corrente      | Indice corrente in base alla persona giuridica e per trimestre e saldi per cespiti e passività correnti |
| Analisi indice rapido        | Indice rapido in base alla persona giuridica, indice rapido per trimestre e saldi per importo di cassa, contabilità clienti e passività correnti |
| Analisi costo del venduto | Costo del venduto (COGS) in base alla persona giuridica, COGS per trimestre dell'anno in corso e dell'anno precedente, COGS rispetto alle vendite per persona giuridica, COGS totale e COGS in base alle percentuali di vendita |
| Analisi capitale circolante    | Capitale circolante in base alla persona giuridica, capitale circolante per trimestre, cespiti correnti, passività correnti e capitale circolante totale |
| Analisi cespiti e debiti     | Ritorno sui cespiti e sui debiti rispetto ai cespiti totali in base alla persona giuridica e al trimestre corrente, cespiti e passività |
| Analisi margine di profitto      | Margine di profitto effettivo e stimato in base alla persona giuridica e per trimestre, percentuale del margine di profitto e margine di profitto |
| Analisi reddito netto         | Reddito netto e previsto in base alla persona giuridica, reddito netto nell'anno in corso e in quello precedente e percentuale di spese rispetto al reddito netto |
| Analisi redditi           | Redditi effettivi e previsti prima di interessi e imposte (EBIT) in base alla persona giuridica, importo EBIT nell'anno in corso e in quello precedente, percentuale di spese rispetto ai ricavi e spese effettive e previste rispetto ai ricavi |
| Analisi ricavi            | Ricavi totali, ricavi totali effettivi e previsti in base alla persona giuridica, ricavi totali nell'anno in corso e in quello precedente, scostamento dal budget in base alla persona giuridica e ricavi totali nel periodo in corso e in quello precedente |
| Analisi spese            | Spese totali, spese totali effettive rispetto al budget in base alla persona giuridica, spese totali effettive e previste per trimestre, spese totali per categoria di conto e indice di spese operative |
| Analisi ricavo fatturato     | Contabilità clienti totale, contabilità clienti totale in base alla persona giuridica, contabilità clienti totale per trimestre e saldi dei conti della contabilità clienti<br><br>**Nota:** le informazioni non includono i saldi iniziali per i conti CoGe della contabilità clienti. Indicano il totale delle nuove transazioni registrate nella contabilità clienti. |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Le entità seguenti sono state utilizzate come base del contenuto di Power BI **Prestazioni finanziarie**

**Entità di dati aggregate**

- **GeneralLedgerActivities**: questa entità aggrega i saldi di contabilità generale per categoria di conti.
- **BudgetActivities**: questa entità aggrega i saldi di budget per categoria di conti.

**Entità di dati**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Contabilità generali
- ChartofAccounts

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Le misure calcolate vengono utilizzate per calcolare gli indicatori di prestazione chiave (KPI) e i report utilizzati nel contenuto. Per impostazione predefinita, il contenuto include dati per gli ultimi tre anni e un anno successivo. Per includere i calcoli aggiuntive in report e dashboard, è possibile modificare la [cartella di lavoro di Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Questa cartella di lavoro è il modello dati predefinito utilizzato per creare il contenuto. 

