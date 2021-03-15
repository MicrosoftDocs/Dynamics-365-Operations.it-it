---
title: Contenuto Power BI Effettivi rispetto al budget
description: Questo argomento descrive il contenuto Power BI Effettivi rispetto al budget. Spiega come accedere ai report e fornisce informazioni sul modello di dati.
author: panolte
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 908b96af5b3d67f265953648edd6aa7ec31556a4
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093850"
---
# <a name="actual-vs-budget-power-bi-content"></a>Contenuto Power BI Effettivi rispetto al budget

[!include [banner](../includes/banner.md)]

Questo argomento descrive il contenuto Power BI **Effettivi rispetto al budget**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Effettivi rispetto al budget** è stato creato per i singoli responsabili per il monitoraggio delle prestazioni degli effettivi rispetto al budget nella loro organizzazione. Il contenuto di Power BI **Effettivi rispetto al budget** fornisce visibilità negli scostamenti di budget. È possibile analizzare il budget per l'anno corrente in base a categoria di conti, codice budget, conto principale, descrizioni del conto principale o periodo fiscale per ottenere una migliore comprensione della causa di tutti gli scostamenti.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
I report dal contenuto di Power BI **Effettivi rispetto al budget** vengono visualizzati nelle aree di lavoro **Budget contabili e previsioni** e **Responsabile finanziario**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI
Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Effettivi rispetto al budget**.

| Report                      | Metriche                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| Spese - Effettivi rispetto al budget | <ul><li>Spese totali anno in corso</li><li>Spese totali budget anno in corso</li></ul>  |
| Ricavi - Effettivi rispetto al budget  | <ul><li>Ricavi totali anno in corso</li><li>Ricavi totali budget anno in corso</li><ul>     |
| Gestione spese                     | <ul><li>Spese totali anno in corso</li><li>Obiettivo per le spese in base al budget</li><ul> |
| Ricavi                     | <ul><li>Ricavi totali anno in corso</li><li>Obiettivo per ricavi in base al budget</li><ul>   |
| Reddito netto                  | <ul><li>Reddito netto anno in corso</li><li>Obiettivo per reddito netto in base al budget</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

| Entità                    | Contenuto                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| Attività di contabilità generale | Importo transazione per contabilità generale                                       |
| Attività di budget         | Importi di transazione per il registro di budget                                      |
| Conti principali             | Conti principali per filtrare i report per                                               |
| Calendari fiscali          | Calendari fiscali per filtrare i report per                                            |
| Contabilità generali                   | Contabilità generale utilizzabile per filtrare il report nella contabilità generale corrente              |
| Codici budget              | Codici budget per filtrare i report per                                                |
| Persone giuridiche            | Persone giuridiche utilizzabili per filtrare il report nella persona giuridica corrente |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]