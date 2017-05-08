---
title: Home page di impostazione budget
description: "In questo argomento viene fornita una panoramica dei componenti della funzionalità e degli strumenti di impostazione budget e delle funzionalità di creazione di report in Microsoft Dynamics 365 for Operations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: index-page
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: dd17842365e357ecb5cb6034ed8878fcd60be5fc
ms.openlocfilehash: aacce0449c9490c4ab66cacb9945ed64fa40de34
ms.contentlocale: it-it
ms.lasthandoff: 04/26/2017


---

# <a name="budgeting-home-page"></a>Home page di impostazione budget

[!include[banner](../includes/banner.md)]


In questo argomento viene fornita una panoramica dei componenti della funzionalità e degli strumenti di impostazione budget e delle funzionalità di creazione di report in Microsoft Dynamics 365 for Operations. 

<a name="components-of-budgeting-functionality"></a>Componenti della funzionalità di impostazione del budget
-------------------------------------

Il ciclo di pianificazione delle risorse per un'azienda consiste di norma nelle attività di pianificazione, impostazione del budget e previsione.
[![Componenti della funzionalità di impostazione del budget](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg) I processi di pianificazione strategica a lungo termine e pianificazione del bilancio annuale sono supportati da un documento del piano di budget. I documenti del piano di budget sono strettamente integrati con Microsoft Excel. Gli utenti possono configurare scenari quantitativi e monetari illimitati e possono definire anche una gerarchia organizzativa di impostazione del budget per supportare i metodi di impostazione del budget dall'alto in basso e dal basso verso l'alto. Dopo aver definito e approvato un budget in Microsoft Dynamics 365 for Operations, è possibile convertire il piano di budget in una voce del registro di budget. Le voci del registro di budget forniscono gli strumenti per la gestione del budget e per tracciare gli importi tramite i codici budget. Le voci del registro di budget consentono di rivedere i budget originali, eseguire trasferimenti e riportare gli importi di budget dall'anno precedente. Sulla base del budget determinato, una società può abilitare il controllo del budget. Il livello del controllo dipende dalle impostazioni cultura e dal livello di maturità dell'organizzazione. Le organizzazioni con un basso livello di maturità potrebbero lasciare il budget "così come è" e potrebbero essere più reattive che proattive se un budget non soddisfa le aspettative. Altre organizzazioni potrebbero abilitare i criteri di controllo del budget che impediscono agli utenti di acquistare se i fondi di budget non sono disponibili. Infine, le organizzazioni con un alto livello di maturità potrebbero definire le impostazioni cultura dell'organizzazione in cui i dipendenti vengono istruiti sugli obiettivi organizzativi e seguono tali obiettivi attraverso i criteri quali "Considerare la riunione online anziché un viaggio". Dynamics 365 for Operations include un framework di controllo di budget che consente alla gestione aziendale di selezionare un rigido controllo (che impedisce le registrazioni che superino il budget) o un controllo soft (dove gli utenti vengono avvertiti che supereranno i fondi di budget disponibili ma possono decidere autonomamente come procedere). Infine, è possibile utilizzare le previsioni di rolling. Una previsione di rolling è un confronto regolare del budget rispetto agli effettivi e viene utilizzato per definire come la società utilizza il budget. La previsione di rolling viene utilizzata anche per identificare le tendenze. In Microsoft Dynamics 365 for Operations, le previsioni di rolling sono supportate tramite un documento del piano di budget, come attività di pianificazione iniziale. Le previsioni di rolling possono essere eseguite in parallelo con la pianificazione del successivo ciclo di budget.

-   [Impostazione del budget di base: panoramica e configurazione](basic-budgeting-overview-configuration.md)
-   [Controllo del budget: panoramica e configurazione](budget-control-overview-configuration.md)
-   [Impostazione del budget: panoramica e configurazione](budget-planning-overview-configuration.md)
-   [Previsione delle posizioni](position-forecasting.md)
-   [Documenti di motivazione per pianificazione del budget](budget-planning-justification-docs.md)
-   [Modelli di Microsoft Excel per la pianificazione del budget](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Strumenti di impostazione del budget in Dynamics 365 for Operations
[![Strumenti di impostazione del budget](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

In Dynamics 365 for Operations sono disponibili ulteriori funzionalità di pianificazione e impostazione del budget che sono integrate nei budget contabili.

-   **Budget della forza lavoro**: l'impostazione del budget della forza lavoro include la pianificazione dettagliata dei componenti del costo di budget per posizioni, gruppi di compensazione e così via.
-   **Budget di cespiti**: sulla base delle informazioni dei cespiti, è possibile calcolare l'ammortamento pianificato e registrare altre transazioni pianificate relative ai cespiti.
-   **Budget di progetto**: nel modulo del progetto è possibile creare previsioni dettagliate per il progetto. Le previsioni dei progetti includono i dettagli sulle ore, sulle spese, sulle commissioni e sugli articoli pianificati.
-   **Previsione della domanda**: Sulla base dei dati storici delle transazioni, è possibile stimare la domanda di articoli futura e creare previsioni della domanda.

Per informazioni su come utilizzare i dati di pianificazione di altri moduli nei piani di budget, vedere [Integrazione della pianificazione del budget con altri moduli](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Interfaccia utente e funzionalità di creazione di report
In Dynamics 365 for Operations, gli utenti possono creare i piani di budget direttamente nel client Dynamics 365 for Operations (utilizzando una pagina del documento di piano di budget configurabile) o tramite Excel. In Excel sono fornite diverse funzionalità aggiuntive. Ad esempio, è possibile utilizzare dati esterni come origine di un piano di budget, eseguire calcoli personalizzati e utilizzare la tabella pivot e i grafici di Microsoft. È possibile configurare la maggior parte delle variabili del processo di pianificazione del budget. Ad esempio, è possibile definire chi esegue l'impostazione del budget, cosa è incluso nel budget e l'aspetto del processo. Sebbene sia possibile utilizzare Excel per la pianificazione del budget, Dynamics 365 for Operations è considerata l'unica soluzione attendibile che consente di evitare problemi di controllo del budget. I processi periodici possono essere utilizzati per passare i dati iniziali dell'impostazione del budget nel piano di budget. Per la dichiarazione, Dynamics 365 for Operations offre un set di pagine di indagine standard che consentono di visualizzare e analizzare i dati dell'impostazione del budget. È possibile accedere ai dati del piano di budget tramite Management Reporter e gli scenari dei piani di budget separati possono essere visualizzati come colonne del report di Management Reporter.







