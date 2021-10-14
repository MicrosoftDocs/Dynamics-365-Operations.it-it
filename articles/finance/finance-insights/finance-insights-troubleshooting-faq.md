---
title: Risoluzione dei problemi di configurazione di Finance Insights
description: Questo argomento elenca i problemi che possono verificarsi quando si utilizzano le funzionalità di Finance Insights. Spiega anche come risolvere questi problemi.
author: panolte
ms.date: 08/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 7ff42ffc334147c1a4c6b6349c86580df7f1955b
ms.sourcegitcommit: 47a3ad71210c7ac84d0c25e913c440b5ba205282
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7512892"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Risoluzione dei problemi di configurazione di Finance Insights

[!include [banner](../includes/banner.md)]

Questo argomento elenca i problemi che possono verificarsi quando si utilizzano le funzionalità di Finance Insights. Spiega anche come risolvere questi problemi.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Sintomo: perché non riesco a mappare la colonna di destinazione del modello di integrazione dei dati Informazioni dettagliate pagamenti cliente?

### <a name="resolution"></a>Risoluzione

È possibile che si stia utilizzando un modello per una versione precedente. Prima del rilascio della versione 10.0.17, i clienti dell'anteprima configuravano il modello di integrazione dei dati (DI) **Risultati delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops)** utilizzando l'entità **Risultato della previsione di pagamento (anteprima)**. Dopo un aggiornamento alla versione 10.0.17 e successive, è necessario utilizzare il modello DI **Risultato delle analisi di pagamenti cliente (da CDS a Fin and Ops 10.0.17 e versioni successive)** per completare il mapping. Potrebbe non essere possibile mappare la colonna di destinazione del modello DI finché l'elenco delle entità di gestione dei dati non viene aggiornato e l'entità **Risultato della previsione di pagamento** non appare in esso. Per aggiornare l'elenco delle entità e mostrare il risultato della previsione di pagamento, è necessario completare i passaggi in Microsoft Dynamics 365 Finance e Dataverse (precedentemente denominato portale di amministrazione Common Data Service \[CDS\]).

### <a name="in-finance"></a>In Finance

In Finance, dopo l'aggiornamento, eseguire i passaggi indicati di seguito.

1. Passare all'**Amministrazione sistema \> Aree di lavoro \> Gestione dati**.
2. Nell'area di lavoro **Gestione dati**, selezionare il riquadro **Parametri del framework**.
3. Nella pagina **Parametri framework di importazione/esportazione dei dati**, selezionare **Impostazioni entità**, quindi **Aggiorna elenco entità**.
4. Chiudere la pagina **Parametri framework di importazione/esportazione dei dati**.
5. Nell'area di lavoro **Gestione dati** selezionare la scheda **Entità di dati**.
6. Cercare "Risultato della previsione di pagamento". Verificare che l'entità **Risultato della previsione di pagamento** non sia la versione di anteprima. Il nome della versione di anteprima termina con "(anteprima)". Se è visibile solo la versione di anteprima dell'entità, contattare il supporto tecnico Microsoft.

### <a name="in-dataverse"></a>In Dataverse

Seguire questi passaggi nell'[interfaccia di amministrazione Power Platform](https://admin.powerplatform.microsoft.com/environments) per aggiornare i progetti di integrazione dei dati.

1. Se si sta utilizzando una versione di anteprima di Finance Insights, rimuovere il progetto DI associato al modello **Risultati delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops)**.
2. Seguire i passaggi in [Creare un progetto di integrazione dei dati](create-data-integrate-project.md). Utilizzare il modello **Risultato delle analisi di pagamenti cliente (da CDS a Fin and Ops 10.0.17 e versioni successive)**.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Sintomo: perché la scheda Previsione di cassa nell'area di lavoro Previsione di cassa non mostra alcun dato?

### <a name="resolution"></a>Risoluzione

La funzione di previsione di cassa in Gestione cassa e banche e la funzione Previsioni di cassa in Finance Insights devono essere configurate e abilitate per mostrare correttamente i dati nell'area di lavoro **Previsione di cassa**.

Innanzitutto, configurare e abilitare i conti liquidità e la previsione di cassa. Per ulteriori informazioni, vedi [Previsione di cassa](../cash-bank-management/cash-flow-forecasting.md). Se questa configurazione è stata completata ma non sono visibili i risultati previsti, vedere [Risolvere i problemi di configurazione della previsione del flusso di cassa](../cash-bank-management/cash-flow-forecasting-tsg.md) per maggiori informazioni.

Quindi, confermare che la funzione Previsioni di cassa in Finance Insights (**Gestione cassa e banca \> Impostazioni \> Finance Insights \> Previsioni di cassa**) sia stata abilitato e che il training del modello di intelligenza artificiale sia stato completato. Se il training non è stato completato, selezionare **Esegui previsione ora** per avviare il processo di training del modello.
