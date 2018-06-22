---
title: Sincronizzare i contratti di progetto in Project Service Automation direttamente con i contratti di progetto di Finance and Operations
description: "Questo argomento descrive il modello e le attività sottostanti che vengono utilizzati per sincronizzare i contratti di progetto e i progetti direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
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
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 8d8e3268ae8c612bad87c3c6416f223219149ee6
ms.contentlocale: it-it
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-contracts-and-projects-from-project-service-automation-directly-to-project-contracts-and-projects-in-finance-and-operations"></a>Sincronizzare i contratti di progetto e i progetti in Project Service Automation direttamente con i contratti e i progetti in Finance and Operations

Questo argomento descrive il modello e le attività sottostanti che vengono utilizzati per sincronizzare i contratti di progetto e i progetti direttamente da Microsoft Dynamics 365 for Project Service Automation con Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE] 
> Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, è necessario installare KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flusso di dati per Project Service Automation verso Finance and Operations

> [!NOTE]
> Prima di poter utilizzare la soluzione di integrazione Project Service Automation in Finance and Operations, è consigliabile acquisire familiarità con la funzionalità Integrazione dati di Dynamics 365.

La soluzione di integrazione di Project Service Automation in Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. Il modello di integrazione disponibile con la funzionalità Integrazione dati abilita il flusso di dati su progetti, contratti di progetto, righe di contratto di progetto e punti cardine delle righe di contratto di progetto da Project Service Automation a Finance and Operations.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i contratti di progetto e i progetti da Project Service Automation a Finance and Operations:

- **Nome del modello in Integrazione dati:** Progetti e contratti (da PSA a Fin and Ops)
- **Nome delle attività del progetto:**

  - Contratti di progetto da PSA a Fin and Ops
  - Progetto da PSA a Fin and Ops
  - Righe di contratto di progetto da PSA a Fin and Ops
  - Punti cardine righe di contratto di progetto da PSA a Fin and Ops

Prima di eseguire la sincronizzazione di contratti di progetto e di progetti, è necessario sincronizzare gli account.

## <a name="entity-set"></a>Insieme di entità

| Project Service Automation       | Finance and Operations                                 |
|----------------------------------|--------------------------------------------------------|
| Ordini                           | Entità di integrazione per contratto di progetto                |
| Progetti                         | Entità di integrazione per progetto                         |
| Righe ordine                      | Entità di integrazione per riga di contratto del progetto          |
| Punti cardine righe di contratto del progetto | Entità di integrazione per il punto cardine della riga di contratto del progetto |

## <a name="entity-flow"></a>Flusso di entità

I contratti di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con Finance and Operations come contratti di progetto. Come parte del modello di integrazione, è possibile impostare l'origine dell'integrazione in Finance and Operations per il contratto di progetto.

I progetti di tempistica e materiali e a prezzo fisso vengono gestiti in Project Service Automation e vengono sincronizzati con Finance and Operations come progetti. Come parte dell'integrazione del modello, è possibile impostare l'origine dell'integrazione in Finance and Operations per il contratto di progetto.

Le righe di contratto di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance and Operations come regole di fatturazione dei contratti di progetto. La sincronizzazione aggiornerà il tipo di progetto per il progetto o il gruppo di progetti con riga di contratto se il metodo di fatturazione è diverso da quello del tipo di progetto predefinito.

I punti cardine delle righe di contratto di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con Finance and Operations come punti cardine delle regole di fatturazione dei contratti di progetto.

## <a name="project-service-automation-to-finance-and-operations-integration-solution"></a>Soluzione di integrazione di Project Service Automation con Finance and Operations

Il campo **ID contratto di progetto** è disponibile nella pagina **Contratti di progetto**. Questo campo è diventato una chiave naturale e univoca per supportare l'integrazione.

Quando un nuovo contratto di progetto viene creato, se un valore di **ID contratto di progetto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica. Il valore consiste di **ORD**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **ORD-01022-Z4M9Q0**.

Il campo **Numero progetto** è disponibile nella pagina **Progetti**. Questo campo è diventato una chiave naturale e univoca per supportare l'integrazione.

Quando un nuovo progetto viene creato, se un valore per **Numero progetto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica. Il valore consiste di **PRJ**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **PRJ-01049-CCNID0**.

Quando viene applicata la soluzione di integrazione di Project Service Automation con Finance and Operations<TO DO: link in the top level document link where we will be adding the instructions for applying the PSA solution>, uno script di aggiornamento imposta il campo **ID contratto di progetto** per i contratti di progetto esistenti e il campo **Numero progetto** per i progetti esistenti in Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

- Prima di eseguire la sincronizzazione di contratti di progetto e di progetti, è necessario sincronizzare gli account.
- Nel set di connessioni, aggiungere il mapping di un campo chiave di integrazione per **msdyn\_organizationalunits** a **msdyn\_name \[Name\]**. È innanzitutto necessario aggiungere un progetto al set di connessioni. Per ulteriori informazioni sulle chiavi di integrazione, vedere Integrazione dati di Dynamics 365.
- Nel set di connessioni, aggiungere il mapping di un campo chiave di integrazione per **msdyn\_projects** a **msdynce\_projectnumber \[Project Number\]**. È innanzitutto necessario aggiungere un progetto al set di connessioni. Per ulteriori informazioni sulle chiavi di integrazione, vedere Integrazione dati di Dynamics 365.
- L'elemento **SourceDataID** per i contratti di progetti e i progetti può essere aggiornato su un valore diverso o essere rimosso dal mapping. Il valore del modello predefinito è **Project Service Automation**.
- Il mapping di **PaymentTerms** deve essere aggiornato in modo che rifletta i termini di pagamento validi in Finance and Operations. È inoltre possibile rimuovere il mapping dall'attività di progetto. La mappa dei valori predefiniti include i valori predefiniti per i dati dimostrativi. Nella seguente tabella sono riportati i valori in Project Service Automation.

    | Valore | descrizione   |
    |-------|---------------|
    | 1     | Net 30        |
    | 2     | 2%10, Net 30 |
    | 3     | Net 45        |
    | 4     | Net 60        |

## <a name="power-query"></a>Power Query
È necessario utilizzare Microsoft Power Query per filtrare i dati se si verificano le condizioni seguenti:

- Si dispone di ordini cliente in Microsoft Dynamics 365 for Sales.
- Si dispone di più unità organizzative in Project Service Automation e queste unità verranno mappate a più persone giuridiche in Finance and Operations.

Se è necessario utilizzare Power Query, seguire queste indicazioni:

- Il modello di contratti di progetto (da PSA a Fin and Ops) presenta un filtro predefinito che include solo ordini cliente del tipo **Elemento di lavoro (msdyn\_ordertype = 192350001)**. Questo filtro assicura che non vengano creati contratti di progetto per gli ordini cliente in Finance and Operations. Se si crea un modello personale, è necessario aggiungere questo filtro.
- È necessario creare un filtro di Power Query che includa solo le organizzazioni del contratto che devono essere sincronizzate con la persona giuridica del set di connessioni di integrazione. Ad esempio, i contratti di progetto di cui si dispone con l'unità organizzativa del contratto di Contoso US devono essere sincronizzati con la persona giuridica USSI, ma i contratti di progetto di cui si dispone con l'unità organizzativa di contratto di Contoso Global devono essere sincronizzati con la persona giuridica USMF. Se non si aggiunge questo filtro al mapping delle attività, tutti i contratti di progetto verranno sincronizzati con la persona giuridica che è definita per il set di connessioni, indipendentemente dall'unità organizzativa del contratto.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

> [!NOTE] 
> I campi **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** e **AddressZipCode** non vengono inclusi nel mapping predefinito per i contratti di progetto. È possibile aggiungere i mapping se è necessario che questi dati siano sincronizzati per i contratti di progetto.
> I campi **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber** e **ProjectType** non vengono inclusi nel mapping predefinito per i progetti. È possibile aggiungere i mapping se è necessario che questi dati siano sincronizzati per i progetti.

Nelle figure seguenti vengono mostrati esempi dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Mapping del modello](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Mapping del modello](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Mapping del modello](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

