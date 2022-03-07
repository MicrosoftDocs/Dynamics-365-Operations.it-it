---
title: Soluzione PowerBI.com per prestazioni finanziarie
description: Questo argomento descrive la soluzione PowerBI.com per le prestazioni finanziarie.
author: kweekley
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ca8338473b2efd91b6570e140ee1def3fa93df14dcf57273f601efb7f548d08
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767805"
---
# <a name="financial-performance-powerbicom-solution"></a>Soluzione PowerBI.com per prestazioni finanziarie

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Questa soluzione PowerBI.com è stata deprecata come documentato in Funzionalità [rimosse o deprecate per Finance and Operations](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Questo argomento descrive la soluzione PowerBI.com per **Prestazioni finanziarie**. Descrive il dashboard e i report che vengono inclusi e fornisce informazioni sul modello di dati e sulle entità utilizzati per creare la soluzione.

## <a name="main-account-setup"></a>Impostazione del conto principale
Poiché le organizzazioni desiderano che le passività e gli importi dei ricavi appaiano come importi positivi nei report, l'impostazione dei conti principali è importante. Affinché questi conti principali vengano visualizzati come importi positivi, il tipo di conto principale deve essere impostato su **Passività** o **Ricavi**. Quando si utilizzano questi tipi di conto, la dichiarazione nei report tramite Power BI invertirà i segni e gli importi risulteranno positivi.

## <a name="dashboard-and-reports-that-are-included-in-the-powerbicom-solution"></a>Dashboard e report inclusi nella soluzione PowerBI.com
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
| Analisi di cassa               | Importo di cassa in base alla persona giuridica e al trimestre, importo di cassa totale e per conto<blockquote>[!NOTE] L'importo di cassa per trimestre non include i saldi iniziali nel totale per il primo trimestre. Mostra il totale delle nuove transazioni registrate in ciascun trimestre.</blockquote> |
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
| Analisi ricavo fatturato     | Contabilità clienti totale, contabilità clienti totale in base alla persona giuridica, contabilità clienti totale per trimestre e saldi dei conti della contabilità clienti<blockquote>[!NOTE] Le informazioni non includono i saldi iniziali per i conti CoGe della contabilità clienti. Indicano il totale delle nuove transazioni registrate nella contabilità clienti.</blockquote> |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Le entità seguenti sono state utilizzate come base della soluzione PowerBI.com per **Prestazioni finanziarie**:

**Entità di dati aggregate**

- **GeneralLedgerActivities**: questa entità aggrega i saldi di contabilità generale per categoria di conti.
- **BudgetActivities**: questa entità aggrega i saldi di budget per categoria di conti.

**Entità di dati**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Contabilità generali
- ChartofAccounts

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Le misure calcolate vengono utilizzate per calcolare gli indicatori di prestazione chiave (KPI) e i report utilizzati nel contenuto. Per impostazione predefinita, il contenuto include dati per gli ultimi tre anni e un anno successivo. Per includere i calcoli aggiuntive in report e dashboard, è possibile modificare la [cartella di lavoro di Microsoft Excel](/dynamics/s-e/). Questa cartella di lavoro è il modello dati predefinito utilizzato per creare il contenuto.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]