---
title: Sincronizzare i numeri effettivi di Project Service Automation direttamente con il giornale di registrazione di integrazione progetto per la registrazione in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i numeri effettivi del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: it-it
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Sincronizzare i numeri effettivi di Project Service Automation direttamente con il giornale di registrazione di integrazione progetto per la registrazione in Finance and Operations

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i numeri effettivi del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.

Il modello sincronizza le transazioni da Project Service Automation in una tabella di staging in Finance and Operations. Al termine della sincronizzazione, è necessario importare dalla tabella di staging nel giornale di registrazione di integrazione.

> [!NOTE]
> L'integrazione de numeri effettivi di progetto è disponibile in Dynamics 365 for Finance and Operations versione 8.01.

> [!NOTE]
> Se si immettono importi IVA su transazioni di spesa o temporali in Project Service Automation, è necessario installare l'aggiornamento 7 di Project Service Automation. Se questo aggiornamento non è installato, i numeri effettivi IVA non vengono collegati ai numeri effettivi di tempo o di spesa associati e non vengono sincronizzati con Finance and Operations. Per ulteriori informazioni, contattare il supporto.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flusso di dati per Project Service Automation verso Finance and Operations

La soluzione di integrazione di Project Service Automation in Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consente il flusso di dati relativi ai numeri effettivi del progetto da Project Service Automation a Finance and Operations.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)


## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i numeri effettivi di progetto da Project Service Automation a Finance and Operations:

-  **Nome del modello in Integrazione dati:** valori effettivi di progetto (da PSA a Fin and Ops)

-  **Nome delle attività del progetto:** 
    - Effettivi 
    - TransactionConnections

## <a name="entity-set"></a>Insieme di entità

| Project Service Automation      | Finance and Operations                                      |
|---------------------------------|-------------------------------------------------------------|
| Effettivi                         | Entità di integrazione per effettivi di progetto                      |
| Connessioni delle transazioni         | Entità di integrazione per relazioni tra transazioni del progetto    |

## <a name="entity-flow"></a>Flusso di entità

I valori effettivi di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con Finance and Operations nel giornale di registrazione di integrazione progetto. La contabilità verrà applicato in base alle dimensioni finanziarie predefinite e all'impostazione della registrazione.

## <a name="preconditions"></a>Condizioni preliminari

Prima di eseguire la sincronizzazione dei valori effettivi, è necessario configurare i parametri di integrazione di Project Service Automation e sincronizzare progetti, attività di progetto e categorie di transazioni di spesa del progetto.

## <a name="power-query"></a>Power Query

È necessario utilizzare Microsoft Power Query nel modello dei valori effettivi di progetto per:
- Trasformare il **tipo di transazione** di Project Service Automation nel **tipo di transazione** di Finance and Operations. Nel modello di valori effettivi di progetto (da PSA a Fin and Ops) questa trasformazione è già definita.
- Trasformare il **tipo di fatturazione** di Project Service Automation nel **tipo di fatturazione** corretto in Finance and Operations. Nel modello di valori effettivi di progetto (da PSA a Fin and Ops) questa trasformazione è già definita. Il tipo di fatturazione viene quindi mappato alla **proprietà di riga** in base alla configurazione presente nel modulo dei parametri di integrazione di Dynamics 365 per Project Service Automation.
- Filtrare **Unità organizzative delle risorse** specifiche che devono essere sincronizzate con questo modello.
- Se i **valori effettivi di spesa interaziendale o di tempo interaziendale** verranno sincronizzati in Finance and Operations, è necessario trasformare l'**unità organizzativa contratto** nella **persona giuridica** corretta in Finance and Operations. Il modello di valori effettivi di progetto (da PSA a Fin and Ops) dispone di una colonna condizionale definita in base a dati dimostrativi. È necessario aggiornare la colonna di condizione inserita più di recente per la persona giuridica corretta. In caso contrario potrebbe verificarsi un errore di integrazione o potrebbero essere generate transazioni di valori effettivi errate importate in Finance and Operations.
- Se i **valori effettivi di tempo interaziendale o di spesa interaziendale** non vengono sincronizzati con Finance and Operations, è necessario eliminare dal modello la colonna dell'ultima condizione immessa. In caso contrario potrebbe verificarsi un errore di integrazione o potrebbero essere generate transazioni di valori effettivi errate importate in Finance and Operations.

### <a name="contract-organizational-unit"></a>Unità organizzativa contratto
Per aggiornare la colonna di condizione inserita nel modello, fare clic sulla freccia **Mappa** per aprire il mapping. Selezionare per aprire Query avanzata e Filtro avanzato.
- Se si utilizza il modello predefinito dei valori effettivi di Microsoft Project (da PSA a Fin and Ops), selezionare l'ultima **Condizione inserita** nella sezione **Passaggi applicati**. Nella voce **Funzione** sostituire **USSI** con il nome della **Persona giuridica** da utilizzare con l'integrazione. Aggiungere condizioni supplementari in base alle esigenze alla voce **Funzione** e aggiornare la condizione **else** da **USMF** alla **Persona giuridica** corretta.
- Se si crea un nuovo modello, è necessario aggiungere questa colonna per supportare tempo e spese interaziendali. Selezionare **Aggiungi colonna condizionale** e assegnare un nome alla colonna, ad esempio LegalEntity. Inserire la condizione per la colonna dove se msdyn_contractorganizationalunitid.msdyn_name è <organizational unit>, allora <enter the Legal entity>; altrimenti null.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mapping del modello](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table"></a>Importa da tabella di gestione temporanea

Il processo periodico Importa da tabella di gestione temporanea deve essere eseguito dopo la sincronizzazione di valori effetti da Project Service Automation a Finance and Operations. Questo processo importerà le transazioni di progetto dalla tabella di gestione temporanea nel giornale di registrazione integrazione di Project Service Automation, dove la contabilità viene applicata e le transazioni importate possono essere registrate. È consigliabile eseguire questo processo nella modalità batch e facoltativamente può essere impostato in modo da essere eseguito come batch ricorrente.

## <a name="update-actuals"></a>Aggiornare i valori effettivi

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le imposte e il numero di giustificativo per le transazioni di progetto registrate da Finance and Operations in Project Service Automation:

-  **Nome del modello in Integrazione dati:** aggiornamento dei valori effettivi di progetto (da Fin and Ops a PSA)
-  **Nome delle attività del progetto:** 
     - Effettivi 
     - TransactionConnections

## <a name="entity-set"></a>Insieme di entità

| Finance and Operations                                         | Project Service Automation        |
|----------------------------------------------------------------|-----------------------------------|
| Entità di integrazione per effettivi di progetto                         | Effettivi                           |
| Entità di integrazione per relazioni tra transazioni del progetto       | Connessioni delle transazioni           |

## <a name="entity-flow"></a>Flusso di entità

I valori effettivi di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con Finance and Operations nel giornale di registrazione di integrazione progetto. Dopo la registrazione in Finance and Operations, i valori effettivi vengono aggiornati in Project Service Automation con il numero di giustificativo da Finance and Operations. Se vengono aggiunte imposte in Finance and Operations, verranno creati nuovi valori effettivi di imposta in Project Service Automation.

## <a name="power-query"></a>Power Query

È necessario utilizzare Microsoft Power Query nel modello di aggiornamento dei valori effettivi di progetto per:
- Trasformare il **tipo di transazione** di Finance and Operations nel **tipo di transazione** corretto in Project Service Automation. Nel modello di aggiornamento dei valori effettivi di progetto (da Fin and Ops a PSA) questa trasformazione è già definita.
- Trasformare il **tipo di fatturazione** di Finance and Operations nel **tipo di fatturazione** corretto in Project Service Automation. Nel modello di aggiornamento dei valori effettivi di progetto (da Fin and Ops a PSA) questa trasformazione è già definita.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti vengono mostrati esempi dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Finance and Operations a Project Service Automation.

[![Mapping del modello](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mapping del modello](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)




