---
title: Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Microsoft Dynamics 365 Finance e Dynamics 365 Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 7b0b3721c3b0755218c834d2bf77ec976be3bdcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770314"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Dynamics 365 Finance e Dynamics 365 Project Service Automation.

> [!NOTE]
> - L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili nella versione 8.0.
> - L'integrazione dei numeri effettivi è disponibile nella versione 8.0.1 o successive.
> - Se si utilizza Enterprise Edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità. Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.

## <a name="data-flow-for-project-service-automation-and-finance"></a>Flusso di dati per Project Service Automation e Finance

La soluzione di integrazione di Project Service Automation e Finance utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consentono il flusso di dati relativi alle categorie di transazioni di spesa di progetto tra Finance e Project Service Automation.

Se le categorie di spesa di progetto vengono gestite in Finance, il flusso di integrazione avviene prima di tutto da Finance a Project Service Automation. Gli ID integrazione delle categorie di spesa di progetto vengono quindi aggiornati attraverso la sincronizzazione da Project Service Automation a Finance.

Se le categorie di spesa di progetto vengono gestite in Project Service Automation, il flusso di integrazione avviene prima di tutto da Project Service Automation a Finance. Le categorie di progetto devono essere già configurate in Finance prima della sincronizzazione da Project Service Automation. Occorre quindi sincronizzare di nuovo da Finance a Project Service Automation e poi da Project Service Automation a Finance. In questo modo, si garantisce che le categorie siano collegate e che non vengano creati duplicati.

> [!NOTE]
> In genere, le categorie di spesa di progetto vengono gestite in Finance. Se tuttavia non vengono gestite o se le categorie di spesa sono già state create in Project Service Automation, è necessario prima di tutto eseguire la sincronizzazione utilizzando il modello delle categorie di transazione di spesa di progetto (da PSA a Fin and Ops). Successivamente si può sincronizzare utilizzando il modello di categorie di transazione di spesa di progetto (da Fin and Ops a PSA). Si consiglia quindi eseguire ancora una volta la sincronizzazione da Project Service Automation a Finance.
>
> Se si esegue la sincronizzazione prima da Project Service Automation, è necessario soddisfare i seguenti requisiti in Finance prima di avviare la sincronizzazione:
>
> - La categoria condivisa corrispondente alla categoria di progetto che è impostata in Project Service Automation deve essere presente e deve essere attivata per **Progetto** e per **Spese**.
> - Per ciascuna persona giuridica di Finance che deve essere integrata, devono essere presenti le seguenti categorie di progetto:
>
>     - **Categoria progetto** esiste. 
>     - **Usa in Gestione spese** è attivata.
>     - **Attivo nei giornali di registrazione** è attivata.
>     - **Tipo di transazione** è impostato su **Spesa**.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a>Sincronizzazione delle categorie di spesa del progetto da Finance a Project Service Automation

### <a name="template-and-task"></a>Modello e attività

Per accedere al modello disponibile, nell'interfaccia di amministrazione di Microsoft Power Apps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie delle spese da Finance a Project Service Automation:

- **Nome del modello in Integrazione dati:** Categorie di transazione di spesa di progetto (da Fin and Ops a PSA)
- **Nome dell'attività del progetto:** Sincronizzare le categorie a PSA

### <a name="entity-set"></a>Insieme di entità

| Dati finanziari                           | Project Service Automation |
|-----------------------------------|----------------------------|
| Entità di integrazione per categorie | Categorie di transazioni     |

### <a name="entity-flow"></a>Flusso di entità

Le categorie di spesa di progetto vengono gestite in Finance e vengono sincronizzate con Project Service Automation come categorie di transazioni.

### <a name="power-query"></a>Power Query

Quando si sincronizza in Project Service Automation, è necessario utilizzare Microsoft Power Query per Excel per impostare il tipo di fatturazione sulla categoria di transazione. Il modello delle categorie di transazione di spesa di progetto (da Fin and Ops a PSA) include una colonna predefinita e un mapping predefiniti. Se si crea un modello personale, è necessario aggiungere una colonna condizionale in Power Query. Eseguire i passaggi indicati di seguito.

1. Fare clic sulla freccia per aprire il mapping dell'attività categorie di spesa di progetto nel modello di categorie di transazione di spesa di progetto (da Fin and Ops a PSA).
2. Fare clic sul collegamento **Query avanzata e Filtro avanzato** per aprire Power Query.
2. Selezionare **Aggiungi colonna condizionale**.
3. Immettere un nome per la nuova colonna, ad esempio **BillingType**.
4. Immettere la seguente condizione: **if CATEGORYID not equal to null then 19235001, Otherwise null**.
5. Fare clic su **OK** sulla colonna.
6. Assicurarsi di mappare la nuova colonna nella pagina di mapping.

Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Finance a Project Service Automation.

[![Mapping del modello](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a>Sincronizzazione delle categorie di spesa del progetto da Project Service Automation a Finance

### <a name="template-and-task"></a>Modello e attività

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie delle spese da Project Service Automation a Finance:

- **Nome del modello in Integrazione dati:** categorie di transazione di spesa di progetto (da PSA a Fin and Ops)
- **Nome dell'attività del progetto:** Sincronizzare le categorie in Fin Ops

### <a name="entity-set"></a>Insieme di entità

| Project Service Automation | Dati finanziari                           |
|----------------------------|-----------------------------------|
| Categorie di transazioni     | Entità di integrazione per categorie |

### <a name="entity-flow"></a>Flusso di entità

Le categorie di spesa di progetto vengono gestite in Finance e vengono sincronizzate con Project Service Automation come categorie di transazioni. La nuova sincronizzazione con Finance aggiorna la categoria di progetto di Finance con l'ID integrazione da Project Service Automation.

### <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.

> [!NOTE]
> Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.

[![Mapping del modello](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)
