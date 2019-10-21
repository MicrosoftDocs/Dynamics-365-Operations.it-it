---
title: Sincronizzare i contratti di progetto e progetti direttamente da Project Service Automation a Finance and Operations
description: Questo argomento descrive il modello e le attività sottostanti che vengono utilizzati per sincronizzare i contratti di progetto e i progetti direttamente da Microsoft Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 09/09/2019
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
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 76c62f3a503ff2a8c93143390fc91ef81fbf7d0f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250463"
---
# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizzare i contratti di progetto e progetti direttamente da Project Service Automation a Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive il modello e le attività sottostanti che vengono utilizzati per sincronizzare i contratti di progetto e i progetti direttamente da Dynamics 365 Project Service Automation a Dynamics 365 Finance.

> [!NOTE] 
> Se si utilizza Enterprise Edition 7.3.0, è necessario installare KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flusso di dati per Project Service Automation verso Finance

> [!NOTE]
> Prima di poter utilizzare la soluzione di integrazione Project Service Automation in Finance, è consigliabile acquisire familiarità con la funzionalità Integrazione dati di Dynamics 365.

La soluzione di integrazione di Project Service Automation a Finance utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. Il modello di integrazione disponibile con la funzionalità Integrazione dati abilita il flusso di dati su progetti, contratti di progetto, righe di contratto di progetto e punti cardine delle righe di contratto di progetto da Project Service Automation a Finance.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

I seguenti modelli e le attività sottostanti vengono utilizzati per sincronizzare i contratti di progetto e i progetti da Project Service Automation a Finance:

### <a name="integrating-with-dynamics-365-project-service-automation-v2x"></a>Integrazione con Dynamics 365 Project Service Automation v2.x
- **Nome del modello in Integrazione dati:** Progetti e contratti (da PSA a Fin and Ops)
- **Nome delle attività del progetto:**

    - Contratti di progetto da PSA a Fin and Ops
    - Progetto da PSA a Fin and Ops
    - Righe di contratto di progetto da PSA a Fin and Ops
    - Punti cardine righe di contratto di progetto da PSA a Fin and Ops
  
### <a name="integrating-with-dynamics-365-project-service-automation-v3x"></a>Integrazione con Dynamics 365 Project Service Automation v3.x
È disponibile una modifica dello schema in Project Service Automation che influisce sul modello cardine della riga del contratto di progetto e l'uso della versione v2 del modello è necessario per integrare Project Service Automation v3.x con Dynamics 365.

- **Nome del modello in Integrazione dati:** Progetti e contratti (da PSA 3.x a Fin and Ops) - v2
- **Nome delle attività del progetto:**

    - Contratti di progetto da PSA a Fin and Ops
    - Progetto da PSA a Fin and Ops
    - Righe di contratto di progetto da PSA a Fin and Ops
    - Punti cardine righe di contratto di progetto da PSA a Fin and Ops

Prima di eseguire la sincronizzazione di contratti di progetto e di progetti, è necessario sincronizzare gli account.

## <a name="entity-set"></a>Insieme di entità

| Project Service Automation       | Dati finanziari                                                |
|----------------------------------|--------------------------------------------------------|
| Ordini                           | Entità di integrazione per contratto di progetto                |
| Progetti                         | Entità di integrazione per progetto                         |
| Righe ordine                      | Entità di integrazione per riga di contratto del progetto           |
| Punti cardine righe di contratto del progetto | Entità di integrazione per il punto cardine della riga di contratto del progetto |

## <a name="entity-flow"></a>Flusso di entità

I contratti di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con Finance come contratti di progetto. Come parte del modello di integrazione, è possibile impostare l'origine dell'integrazione in Finance per il contratto di progetto.

I progetti di tempistica e materiali e a prezzo fisso vengono gestiti in Project Service Automation e vengono sincronizzati con Finance come progetti. Come parte del modello di integrazione, è possibile impostare l'origine dell'integrazione in Finance per il progetto.

Le righe di contratto di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance come regole di fatturazione dei contratti di progetto. Se il metodo di fatturazione differisce dal tipo di progetto predefinito, la sincronizzazione aggiorna il tipo di progetto per il progetto o il gruppo di progetti con riga di contratto.

I punti cardine delle righe di contratto di progetto vengono gestiti in Project Service Automation e vengono sincronizzati con Finance come punti cardine delle regole di fatturazione dei contratti di progetto.

## <a name="project-service-automation-to-finance-integration-solution"></a>Soluzione di integrazione di Project Service Automation con Finance

Il campo **ID contratto di progetto** è disponibile nella pagina **Contratti di progetto**. Questo campo è diventato una chiave naturale e univoca per supportare l'integrazione.

Quando un nuovo contratto di progetto viene creato, se un valore di **ID contratto di progetto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica. Il valore consiste di **ORD**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **ORD-01022-Z4M9Q0**.

Il campo **Numero progetto** è disponibile nella pagina **Progetti**. Questo campo è diventato una chiave naturale e univoca per supportare l'integrazione.

Quando un nuovo progetto viene creato, se un valore per **Numero progetto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica. Il valore consiste di **PRJ**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **PRJ-01049-CCNID0**.

Quando viene applicata la soluzione di integrazione di Project Service Automation con Finance, uno script di aggiornamento imposta il campo **ID contratto di progetto** per i contratti di progetto esistenti e il campo **Numero progetto** per i progetti esistenti in Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

- Prima di eseguire la sincronizzazione di contratti di progetto e di progetti, è necessario sincronizzare gli account.
- Nel set di connessioni, aggiungere il mapping di un campo chiave di integrazione per **msdyn\_organizationalunits** a **msdyn\_name \[Name\]**. Potrebbe essere innanzitutto necessario aggiungere un progetto al set di connessioni. Per ulteriori informazioni, vedere [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- Nel set di connessioni, aggiungere il mapping di un campo chiave di integrazione per **msdyn\_projects** a **msdynce\_projectnumber \[Project Number\]**. Potrebbe essere innanzitutto necessario aggiungere un progetto al set di connessioni. Per ulteriori informazioni, vedere [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- L'elemento **SourceDataID** per i contratti di progetti e i progetti può essere aggiornato su un valore diverso o essere rimosso dal mapping. Il valore del modello predefinito è **Project Service Automation**.
- Il mapping di **PaymentTerms** deve essere aggiornato in modo che rifletta i termini di pagamento validi in Finance. È inoltre possibile rimuovere il mapping dall'attività di progetto. La mappa dei valori predefiniti include i valori predefiniti per i dati dimostrativi. Nella seguente tabella sono riportati i valori in Project Service Automation.

    | Valore | descrizione   |
    |-------|---------------|
    | 1     | Net 30        |
    | 2     | 2% 10, Net 30 |
    | 3     | Net 45        |
    | 4     | Net 60        |

## <a name="power-query"></a>Power Query

È necessario utilizzare Microsoft Power Query per Excel per filtrare i dati se si verificano le condizioni seguenti:

- Si dispone di ordini cliente in Dynamics 365 Sales.
- Si dispone di più unità organizzative in Project Service Automation e queste unità verranno mappate a più persone giuridiche in Finance.

Se è necessario utilizzare Power Query, seguire queste indicazioni:

- Il modello di progetti e contratti (da PSA a Fin and Ops) presenta un filtro predefinito che include solo ordini cliente del tipo **Elemento di lavoro (msdyn\_ordertype = 192350001)**. Questo filtro assicura che non vengano creati contratti di progetto per gli ordini cliente in Finance. Se si crea un modello personale, è necessario aggiungere questo filtro.
- È necessario creare un filtro di Power Query che includa solo le organizzazioni del contratto che devono essere sincronizzate con la persona giuridica del set di connessioni di integrazione. Ad esempio, i contratti di progetto di cui si dispone con l'unità organizzativa del contratto di Contoso US devono essere sincronizzati con la persona giuridica USSI, ma i contratti di progetto di cui si dispone con l'unità organizzativa di contratto di Contoso Global devono essere sincronizzati con la persona giuridica USMF. Se non si aggiunge questo filtro al mapping delle attività, tutti i contratti di progetto verranno sincronizzati con la persona giuridica che è definita per il set di connessioni, indipendentemente dall'unità organizzativa del contratto.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

> [!NOTE] 
> I campi **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** e **AddressZipCode** non vengono inclusi nel mapping predefinito per i contratti di progetto. È possibile aggiungere i mapping se è necessario che questi dati siano sincronizzati per i contratti di progetto.
>
> I campi **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber** e **ProjectType** non vengono inclusi nel mapping predefinito per i progetti. È possibile aggiungere i mapping se è necessario che questi dati siano sincronizzati per i progetti.

Nelle figure seguenti vengono mostrati esempi dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.

[![Mapping del modello](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Mapping del modello](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Mapping del modello](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Mapping del modello](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

#### <a name="project-contract-line-milestone-mapping-in-the-projects-and-contracts-psa-3x-to-dynamics---v2-template"></a>Mapping cardine della riga di contratto del progetto nel modello Progetti e contratti (da PSA 3.x a Dynamics) - v2:

[![Mapping del modello](./media/ProjectContractLineMilestoneMapping_v2.jpg)](./media/ProjectContractLineMilestoneMapping_v2.jpg)
