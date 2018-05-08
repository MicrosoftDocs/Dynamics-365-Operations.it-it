---
title: Contenuto di Power BI Panoramica situazione di cassa
description: "Questo argomento descrive il contenuto Panoramica situazione di cassa di Power BI. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto."
author: saraschi2
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 5d02a009ca988f91a212e467d4f9784248bbae76
ms.contentlocale: it-it
ms.lasthandoff: 12/19/2017

---

# <a name="cash-overview-power-bi-content"></a>Contenuto di Power BI Panoramica situazione di cassa

[!include [banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Panoramica situazione di cassa** di Microsoft Power BI. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto **Panoramica situazione di cassa** di Power BI è stato creato per i responsabili della cassa dell'organizzazione. Il contenuto **Panoramica situazione di cassa** di Power BI fornisce la visibilità del flusso di cassa. Fornisce inoltre le previsioni che consentono di prendere decisioni migliori e quindi migliorare la stabilità del flusso di cassa. È possibile analizzare il flusso di cassa per persona giuridica, valuta e conto bancario per ottenere una migliore comprensione delle eccedenze e delle carenze.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

I report dal contenuto Power BI **Panoramica situazione di cassa** vengono visualizzati nelle aree di lavoro **Panoramica situazione di cassa** e **Gestione banche**.

Per visualizzare i report delle previsioni di cassa con dati, è necessario prima eseguire il processo di calcolo delle previsioni utilizzando la funzione **Calcola previsioni di cassa** nell'area Gestione banche e di cassa.  Deve essere completato per ogni società inclusa nella previsione.  Nella pagina **Archivio entità** è necessario quindi aggiornare la misura di aggregazione LedgerCovLiquidityMeasurement.  

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



