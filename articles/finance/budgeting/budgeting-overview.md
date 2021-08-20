---
title: Home page di impostazione del budget
description: In questo argomento viene fornita una panoramica dei componenti della funzionalità e degli strumenti di impostazione del budget e delle funzionalità di creazione di report in Microsoft Dynamics 365 Finance.
author: panolte
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "106043"
- intro-internal
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4cd874cc7e95d09f5109f7ee4cf480158bce845bf9dbcbab1293f2982dbfabe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750438"
---
# <a name="budgeting-home-page"></a>Home page di impostazione del budget

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dei componenti della funzionalità e degli strumenti di impostazione budget e delle funzionalità di creazione di report. 

## <a name="components-of-budgeting-functionality"></a>Componenti della funzionalità di impostazione del budget

Il ciclo di pianificazione delle risorse per un'azienda consiste generalmente nelle attività di pianificazione, impostazione del budget e previsione.

[![Componenti della funzionalità di impostazione del budget.](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

I processi per la pianificazione strategica a lungo termine e per la pianificazione del budget annuale sono supportati tramite un documento di piano di budget. I documenti del piano di budget sono strettamente integrati con Microsoft Excel. Gli utenti possono configurare scenari quantitativi e monetari illimitati e possono definire anche una gerarchia organizzativa di impostazione del budget per supportare i metodi di impostazione del budget dall'alto verso il basso e dal basso verso l'alto. Dopo aver definito e approvato un budget nell'applicazione, è possibile convertire il piano di budget in una voce del registro di budget. Le voci del registro di budget forniscono gli strumenti per la gestione del budget e per il tracciamento degli importi tramite i codici budget. Le voci del registro di budget consentono di rivedere i budget originali, eseguire trasferimenti e riportare gli importi di budget dall'anno precedente. Sulla base del budget determinato, una società può abilitare il controllo del budget. Il livello del controllo dipende dalle impostazioni cultura e dal livello di maturità dell'organizzazione. Le organizzazioni con un basso livello di maturità potrebbero lasciare il budget "così come è" e potrebbero essere più reattive che proattive se un budget non soddisfa le aspettative. Altre organizzazioni potrebbero abilitare i criteri di controllo del budget che impediscono agli utenti di acquistare se i fondi di budget non sono disponibili.

Infine, le organizzazioni con un alto livello di maturità potrebbero definire una cultura aziendale in cui i dipendenti vengono istruiti sugli obiettivi organizzativi e seguono tali obiettivi attraverso criteri quali "Considerare una riunione online anziché un viaggio". L'applicazione include un framework di controllo del budget che consente alla gestione aziendale di selezionare un controllo di tipo rigido (che impedisce le registrazioni superiori al budget) o flessibile (dove gli utenti vengono avvertiti del fatto che supereranno i fondi di budget disponibili ma possono decidere autonomamente come procedere). Infine, è possibile utilizzare le previsioni di rolling. Una previsione rolling è un confronto regolare del budget rispetto ai valori effettivi e viene utilizzata per valutare come la società utilizza il budget. Una previsione rolling viene utilizzata anche per identificare le tendenze. In Finance and Operations, le previsioni rolling sono supportate, tramite un documento del piano di budget, come attività di pianificazione iniziale. Le previsioni di rolling possono essere eseguite in parallelo con la pianificazione del successivo ciclo di budget.

-   [Panoramica dell'impostazione budget](basic-budgeting-overview-configuration.md)
-   [Panoramica del controllo del budget](budget-control-overview-configuration.md)
-   [Panoramica della pianificazione del budget](budget-planning-overview-configuration.md)
-   [Previsione delle posizioni](position-forecasting.md)
-   [Documenti di motivazione per pianificazione del budget](budget-planning-justification-docs.md)
-   [Modelli di pianificazione del budget per Excel](budget-planning-excel-templates.md)

## <a name="budgeting-tools"></a>Strumenti di impostazione del budget
[![Strumenti di impostazione del budget.](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Sono disponibili ulteriori funzionalità di pianificazione e impostazione del budget integrate nei budget di contabilità generale.

-   **Budget della forza lavoro**: l'impostazione del budget della forza lavoro include la pianificazione dettagliata dei componenti del costo di budget per posizioni, gruppi di retribuzione e così via.
-   **Budget di cespiti**: sulla base delle informazioni dei cespiti, è possibile calcolare l'ammortamento pianificato e registrare altre transazioni pianificate relative ai cespiti.
-   **Budget di progetto**: nel modulo del progetto è possibile creare previsioni dettagliate per il progetto. Le previsioni dei progetti includono i dettagli sulle ore, sulle spese, sulle commissioni e sugli articoli pianificati.
-   **Previsione della domanda**: sulla base dei dati storici delle transazioni, è possibile stimare la domanda di articoli futura e creare previsioni della domanda.

Per informazioni su come utilizzare i dati di pianificazione di altri moduli nei piani di budget, vedere [Integrazione della pianificazione del budget con altri moduli](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Interfaccia utente e funzionalità di creazione di report
Gli utenti possono creare i piani di budget direttamente nel client (utilizzando una pagina del documento del piano di budget configurabile) o tramite Excel. In Excel sono fornite diverse funzionalità aggiuntive. Ad esempio, è possibile utilizzare dati esterni come origine di un piano di budget, eseguire calcoli personalizzati e utilizzare la tabella pivot e i grafici di Microsoft. È possibile configurare la maggior parte delle variabili del processo di pianificazione del budget. 

Ad esempio, è possibile definire chi si occupa dell'impostazione del budget, cosa è incluso nel budget e l'aspetto del processo. Sebbene sia possibile utilizzare Excel per la pianificazione del budget, l'applicazione rappresenta una singola soluzione attendibile che consente di evitare problemi di controllo del budget. È possibile utilizzare processi periodici per passare i dati iniziali dell'impostazione del budget nel piano di budget. Per la creazione di report, l'applicazione offre un set di pagine di richieste informazioni standard che consentono di visualizzare e analizzare i dati dell'impostazione del budget. È possibile accedere ai dati del piano di budget tramite [Financial Reporting](../general-ledger/financial-reporting-getting-started.md) e gli scenari dei piani di budget separati possono essere visualizzati come colonne del report finanziario.








[!INCLUDE[footer-include](../../includes/footer-banner.md)]
