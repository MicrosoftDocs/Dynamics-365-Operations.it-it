---
title: Sincronizzare i numeri effettivi direttamente da Project Service Automation al giornale di registrazione di integrazione progetto per la registrazione in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i numeri effettivi del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 0a965e8de596decf39a15977e6df8a6aa9dd35b0
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="synchronize-project-actuals-directly-from-project-service-automation-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Sincronizzare i numeri effettivi direttamente da Project Service Automation al giornale di registrazione di integrazione progetto per la registrazione in Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i numeri effettivi del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Microsoft Dynamics 365 for Finance and Operations.

Il modello sincronizza le transazioni da Project Service Automation in una tabella di gestione temporanea in Finance and Operations. Al termine della sincronizzazione, **è necessario** importare i dati dalla tabella di gestione temporanea nel giornale di registrazione di integrazione.

> [!NOTE]
> - L'integrazione dei numeri effettivi di progetto è disponibile in Microsoft Dynamics 365 for Finance and Operations versione 8.0.1 o successive.
> - Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità. Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.
> - Se si utilizza Finance and Operations 7.3.0 e si eseguono transazioni di tipo commissione da Project Service Automation, è necessario installare KB 4345320 per includere tali commissioni nella fattura di progetto.
> - Se si immettono importi IVA su transazioni di spesa o temporali in Project Service Automation, è necessario installare Project Service Automation Update 7. Se questo aggiornamento non è installato, i numeri effettivi IVA non verranno collegati ai numeri effettivi temporali o di spesa associati e non verranno sincronizzati con Finance and Operations. Per ulteriori informazioni, contattare il supporto.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flusso di dati per Project Service Automation verso Finance and Operations

La soluzione di integrazione di Project Service Automation in Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consente il flusso di dati relativi ai numeri effettivi del progetto da Project Service Automation a Finance and Operations.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)

## <a name="project-actuals-from-project-service-automation"></a>Valori effettivi del progetto da Project Service Automation

### <a name="template-and-tasks"></a>Modello e attività

Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i numeri effettivi di progetto da Project Service Automation a Finance and Operations:

- **Nome del modello in Integrazione dati:** valori effettivi di progetto (da PSA a Fin and Ops)
- **Nome delle attività del progetto:**

    - Effettivi
    - TransactionConnections

### <a name="entity-set"></a>Insieme di entità

| Project Service Automation | Finance and Operations                                   |
|----------------------------|----------------------------------------------------------|
| Effettivi                    | Entità di integrazione per effettivi di progetto                   |
| Connessioni delle transazioni    | Entità di integrazione per relazioni tra transazioni del progetto |

### <a name="entity-flow"></a>Flusso di entità

I valori effettivi di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con il giornale di registrazione di integrazione progetto in Finance and Operations. La contabilità verrà applicata in base alle dimensioni finanziarie predefinite e all'impostazione della registrazione.

### <a name="prerequisites"></a>Prerequisiti

Prima di eseguire la sincronizzazione dei valori effettivi, è necessario configurare i parametri di integrazione di Project Service Automation e sincronizzare progetti, attività di progetto e categorie di transazioni di spesa del progetto.

### <a name="power-query"></a>Power Query

Nel modello dei valori effettivi del progetto, è necessario utilizzare Microsoft Power Query per Excel per completare queste attività:

- Trasformare il tipo di transazione di Project Service Automation nel tipo di transazione di Finance and Operations. Questa trasformazione è già definita nel modello di valori effettivi di progetto (da PSA a Fin and Ops).
- Trasformare il tipo di fatturazione di Project Service Automation nel tipo di fatturazione corretto in Finance and Operations. Questa trasformazione è già definita nel modello di valori effettivi di progetto (da PSA a Fin and Ops). Il tipo di fatturazione viene quindi mappato alla proprietà di riga in base alla configurazione nella pagina **Parametri di integrazione di Project Service Automation**.
- Filtrare le unità organizzative delle risorse specifiche che devono essere sincronizzate con questo modello.
- Se i valori effettivi di spesa interaziendale o di tempo interaziendale verranno sincronizzati in Finance and Operations, è necessario trasformare l'unità organizzativa contratto nella persona giuridica corretta in Finance and Operations. Il modello di valori effettivi di progetto (da PSA a Fin and Ops) dispone di una colonna condizionale definita in base a dati dimostrativi. È necessario aggiornare la colonna condizionale inserita più di recente con la persona giuridica corretta. In caso contrario potrebbe verificarsi un errore di integrazione o potrebbero essere generate transazioni di valori effettivi errate importate in Finance and Operations.
- Se i valori effettivi di tempo interaziendale o di spesa interaziendale non vengono sincronizzati con Finance and Operations, è necessario eliminare dal modello la colonna condizionale inserita per ultima. In caso contrario potrebbe verificarsi un errore di integrazione o potrebbero essere generate transazioni di valori effettivi errate importate in Finance and Operations.

#### <a name="contract-organizational-unit"></a>Unità organizzativa contratto
Per aggiornare la colonna condizionale inserita nel modello, fare clic sulla freccia **Mappa** per aprire il mapping. Selezionare il collegamento **Query avanzata e Filtro avanzato** per aprire Power Query.

- Se si utilizza il modello predefinito dei valori effettivi di progetto (da PSA a Fin and Ops), in Power Query selezionare l'ultima **Condizione inserita** nella sezione **Passaggi applicati**. Nella voce **Funzione** sostituire **USSI** con il nome della persona giuridica da utilizzare con l'integrazione. Aggiungere condizioni supplementari alla voce **Funzione** in base alle esigenze e aggiornare la condizione **else** da **USMF** alla Persona giuridica corretta.
- Se si crea un nuovo modello, è necessario aggiungere la colonna per supportare tempo e spese interaziendali. Selezionare **Aggiungi colonna condizionale** e assegnare un nome alla colonna, ad esempio **LegalEntity**. Immettere una condizione per la colonna, in cui se **msdyn\_contractorganizationalunitid.msdyn\_nome** è \<unità organizzativa\>, allora \<inserire persona giuridica\>; altrimenti null.

### <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene mostrato un esempio del mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mapping del modello](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table-after-integration-from-project-service-automation"></a>Importare dalla tabella di gestione temporanea dopo l'integrazione da Project Service Automation

Il processo periodico di importazione dalla tabella di gestione temporanea deve essere eseguito dopo la sincronizzazione di valori effetti da Project Service Automation a Finance and Operations. Questo processo importerà le transazioni di progetto dalla tabella di gestione temporanea nel giornale di registrazione integrazione di Project Service Automation, dove la contabilità viene applicata e le transazioni importate possono essere registrate. È consigliabile eseguire questo processo nella modalità batch e facoltativamente può essere impostato in modo da essere eseguito come batch ricorrente.

## <a name="update-actuals-from-finance-and-operations"></a>Aggiornare i valori effettivi da Finance and Operations

### <a name="template-and-tasks"></a>Modello e attività

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le imposte e il numero di giustificativo per le transazioni di progetto registrate da Finance and Operations in Project Service Automation:

- **Nome del modello in Integrazione dati:** aggiornamento dei valori effettivi di progetto (da Fin and Ops a PSA)
- **Nome delle attività del progetto:**

    - Effettivi 
    - TransactionConnections

### <a name="entity-set"></a>Insieme di entità

| Finance and Operations                                   | Project Service Automation |
|----------------------------------------------------------|----------------------------|
| Entità di integrazione per effettivi di progetto                   | Effettivi                    |
| Entità di integrazione per relazioni tra transazioni del progetto | Connessioni delle transazioni    |

### <a name="entity-flow"></a>Flusso di entità

I valori effettivi di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con il giornale di registrazione di integrazione progetto in Finance and Operations. Dopo la registrazione in Finance and Operations, i valori effettivi vengono aggiornati in Project Service Automation con il numero di giustificativo da Finance and Operations. Se vengono aggiunte imposte in Finance and Operations, verranno creati nuovi valori effettivi di imposta in Project Service Automation.

### <a name="power-query"></a>Power Query

Nel modello di aggiornamento dei valori effettivi del progetto, è necessario utilizzare Power Query per completare queste attività:

- Trasformare il tipo di transazione di Finance and Operations nel tipo di transazione di Project Service Automation. Questa trasformazione è già definita nel modello di aggiornamento dei valori effettivi di progetto (da Fin Ops a PSA).
- Trasformare il tipo di fatturazione di Finance and Operations nel tipo di fatturazione corretto in Project Service Automation. Questa trasformazione è già definita nel modello di aggiornamento dei valori effettivi di progetto (da Fin Ops a PSA).

### <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti vengono mostrati esempi dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Finance and Operations a Project Service Automation.

[![Mapping del modello](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mapping del modello](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)

