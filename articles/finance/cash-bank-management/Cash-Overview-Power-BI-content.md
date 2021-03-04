---
title: Contenuto di Power BI della panoramica situazione di cassa
description: Questo argomento descrive il contenuto Panoramica situazione di cassa di Power BI. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto.
author: saraschi2
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6ad99f00438b0f9ccbf84e504219e39aa49f2bc1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444822"
---
# <a name="cash-overview-power-bi-content"></a>Contenuto di Power BI della panoramica situazione di cassa

[!include [banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Panoramica situazione di cassa** di Microsoft Power BI. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto **Panoramica situazione di cassa** di Power BI è stato creato per i responsabili della cassa dell'organizzazione. Il contenuto **Panoramica situazione di cassa** di Power BI fornisce la visibilità del flusso di cassa. Fornisce inoltre le previsioni che consentono di prendere decisioni migliori e quindi migliorare la stabilità del flusso di cassa. È possibile analizzare il flusso di cassa per persona giuridica, valuta e conto bancario per ottenere una migliore comprensione delle eccedenze e delle carenze.

## <a name="setup-needed-to-view-power-bi-content"></a>Impostazione necessaria per visualizzare il contenuto di Power BI

La seguente impostazione deve essere completata per visualizzare i dati nelle rappresentazioni **Panoramica situazione di cassa** e **Gestione banche** di Power BI.

1. Andare a **Amministrazione sistema > Impostazioni > Parametri di sistema** per impostare **Valuta di sistema** e **Tipo di tasso di cambio del sistema**.
2. Vai a **Contabilità generale> Calendari > Calendari fiscali** per convalidare le date del calendario fiscale assegnate al periodo di tempo attivo.
3. Passare a **Contabilità generale > Impostazioni > Contabilità generale** per impostare **Valuta di contabilizzazione** e **Tipo di tasso di cambio**.
4. Definire i tassi di cambio tra le valute della transazioni e la valuta di contabilizzazione, la valuta di contabilizzazione e la valuta di sistema, la valuta di contabilizzazione e le valute delle banche. A tale scopo, andare a **Contabilità generale > Valute > Tassi di cambio valutario**.
5. Configurare ed eseguire Previsione di cassa. Per ulteriori informazioni su come impostare Previsione di cassa, vedere [Previsione di cassa](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting). 
6. Passare a **Amministrazione sistema > Impostazioni > Archivio entità** per aggiornare la misura di aggregazione **LedgerCovLiquidityMeasurement**.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

I report dal contenuto Power BI **Panoramica situazione di cassa** vengono visualizzati nelle aree di lavoro **Panoramica situazione di cassa** e **Gestione banche**.

Per visualizzare i report delle previsioni di cassa con dati, è necessario prima eseguire il processo di calcolo delle previsioni utilizzando la funzione **Calcola previsioni di cassa** nell'area Gestione banche e di cassa. Deve essere completato per ogni società inclusa nella previsione.  Nella pagina **Archivio entità** è necessario quindi aggiornare la misura di aggregazione LedgerCovLiquidityMeasurement.  

A tale scopo, è possibile aggiungere i dati dimostrativi delle previsioni di cassa utilizzando la pagina **Genera dati** dal modulo Dati dimostrativi.  Questo script inserirà i dati nelle tabelle delle previsioni di cassa per popolare rapidamente le informazioni necessarie per i report.  Questo modulo è disponibile solo se si dispone del modello della serie di dati dimostrativi distribuito nell'ambiente. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Panoramica situazione di cassa**.

| Report                                | Contenuto |
|---------------------------------------|----------|
| Panoramica situazione di cassa - tutte le società         | <ul><li>Entrate e uscite nella valuta di sistema</li><li>Saldi previsti in valuta</li><li>Saldo bancario totale nella valuta di sistema</li><li>Saldo per persona giuridica</li><li>Saldo effettivo odierno rispetto al saldo previsto nella valuta del conto bancario</li></ul> |
| Panoramica situazione di cassa - società corrente       | <ul><li>Entrate e uscite nella valuta di contabilizzazione</li><li>Saldi previsti in valuta</li><li>Saldo bancario totale nella valuta di contabilizzazione</li><li>Saldo effettivo odierno rispetto al saldo previsto nella valuta del conto bancario</li></ul> |
| Previsione di cassa - tutte le società    | <ul><li>Entrate e uscite nella valuta di sistema</li><li>Riepilogo previsione giornaliero</li><li>Dettagli previsione</li></ul> |
| Previsione di cassa - società in valuta | <ul><li>Entrate e uscite nella valuta di contabilizzazione</li><li>Riepilogo previsione giornaliero</li><li>Dettagli previsione</li></ul> |
| Previsione in valuta                     | <ul><li>Saldi previsti in valuta</li><li>Riepilogo valuta giornaliero</li><li>Dettagli previsione</li></ul> |
| Saldi banca                         | <ul><li>Saldo bancario totale nella valuta di sistema</li><li>Saldo per persona giuridica</li><li>Saldo effettivo odierno rispetto al saldo previsto nella valuta del conto bancario</li><li>Saldo per conto bancario</li><li>Saldo per valuta</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

Nella tabella seguente vengono illustrate le entità su cui si basa il contenuto di Power BI **Panoramica situazione di cassa**.

| Entità                                                                          | Contenuto |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Società in base a cui filtrare i report |
| LedgerCovLiquidityMeasurement\_Date                                             | Date in base a cui filtrare i report |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Estratto conto effettivo rispetto all'ultimo estratto conto previsto |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Dettagli transazione previsione |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Riepilogo di entrate di cassa, uscite e saldo utilizzando la valuta di contabilizzazione di ciascuna società |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Riepilogo di entrate di cassa, uscite e saldo utilizzando la valuta di sistema per tutte le società |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Riepilogo dell'importo della transazione e del saldo netti delle valute utilizzando la valuta della transazione |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]