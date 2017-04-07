---
title: Home page di impostazione budget
description: "In questo argomento viene fornita una panoramica dei componenti del budget di funzionalità, degli strumenti del budget e della dichiarazione di capacità in Microsoft Dynamics 365 per le operazioni."
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
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: f7b4efc06b8e64c05da026850b41cb5b68c33ec3
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-home-page"></a>Home page di impostazione budget

In questo argomento viene fornita una panoramica dei componenti del budget di funzionalità, degli strumenti del budget e della dichiarazione di capacità in Microsoft Dynamics 365 per le operazioni.

<a name="components-of-budgeting-functionality"></a>Componenti della funzionalità Impostazione budget
-------------------------------------

Il ciclo di pianificazione delle risorse per una società è costituito in genere dalla programmazione, dall'impostazione del budget e dalla previsione delle attività.
[componenti del budget delle funzionalità![(]. /media/budgeting-functionality-components.jpg)](. /media/budgeting-functionality-components.jpg) I processi sia per la pianificazione strategica lungo termine della pianificazione del budget annuale sono supportati tramite un documento piano di budget. I documenti dei piani di budget sono strettamente integrati con Microsoft Excel. Gli utenti possono configurare gli scenari monetari e quantitativi illimitati e anche definire una gerarchia organizzativa di impostazione del budget per supportare i metodi di impostazione budget dall'alto verso il basso e dal basso verso l'alto. Dopo che un budget è definito e approvato in Microsoft Dynamics 365 for Operations, il piano di budget viene convertito in una voce del registro di budget. Le voci del registro di budget forniscono gli strumenti per gestire il budget e per tenere traccia degli importi attraverso codici di budget. Le voci del registro di budget consentono di esaminare i budget originali, eseguono i trasferimenti e riportano gli importi del budget dell'anno precedente. In base al budget stabilito, una società può abilitare il controllo del budget. Il livello di controllo dipende dalla cultura e dal livello di sviluppo dell'organizzazione. Le organizzazioni con un livello basso di sviluppo potrebbero lasciare il budget "com'è" ed essere più reattive che dinamiche se un budget non soddisfa le aspettative. Altre organizzazioni possono abilitare i criteri di controllo del budget che impediscono agli utenti di acquistare se i fondi di budget non sono disponibili. Infine, organizzazioni potrebbero essere mature per stabilire una lingua organizzativa in cui i dipendenti istruiti sugli obiettivi dell'organizzazione e tenere traccia degli obiettivi ai criteri vengono considerati come "Riunione online anziché un viaggio". Dynamics 365 per le operazioni include una struttura di controllo del budget che consente la gestione della società seleziona il controllo definitivo (che impedisca le registrazioni che supererebbero il budget) o controllo preliminare (in cui gli utenti sono che può comunque supereranno i fondi budget disponibili ma possono decidere se per quelli di continuare). Infine, è possibile utilizzare previsioni continue. Una previsioni continue è un confronto tra rettificare il budget e i numeri effettivi e viene utilizzata per definire il modo in cui opera la società rispetto al budget. Una previsione ricorrente viene inoltre utilizzata per identificare le tendenze. In Microsoft Dynamics 365 for Operations le previsioni ricorrenti sono supportate, tramite un documento di piano di budget, come attività iniziali di pianificazione. Possono essere eseguite parallelamente alla pianificazione del ciclo di budget imminente.

-   [Pianificazione del budget di base: panoramica e configurazione](basic-budgeting-overview-configuration.md)
-   [Controllo del budget: panoramica e configurazione](budget-control-overview-configuration.md)
-   [Pianificazione del budget: panoramica e configurazione](budget-planning-overview-configuration.md)
-   [Previsione della posizione](position-forecasting.md)
-   [] Documenti di motivazione di pianificazione del budget (budget-planning-justification-docs.md)
-   [Modelli di Microsoft Excel per la pianificazione] budget (budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Strumenti di budget in Dynamics 365 for Operations
[strumenti del![(]. /media/budgeting-tools.jpg)](. /media/budgeting-tools.jpg) 

La pianificazione aggiuntiva e le funzionalità di impostazione del budget sono disponibili in Dynamics 365 for Operations e sono integrate nei budget della contabilità generale.

-   **Budget della forza lavoro** - L'impostazione del budget della forza lavoro include la pianificazione dettagliata dei componenti di costo del budget per le posizioni, i gruppi di retribuzione e così via.
-   **Budget cespiti** - In base alle informazioni sui cespiti, è possibile calcolare l'ammortamento pianificato e registrare altre transazioni pianificate correlate ai cespiti.
-   **Budget di progetto** - Nel modulo Progetti è possibile creare le previsioni di progetto dettagliate. Le previsioni di progetto comprenderanno i dettagli relativi a ore, spese, commissioni e articoli pianificati.
-   ** Previsione della domanda ** - sui dati dello storico delle transazioni, è possibile valutare la domanda futura di magazzino e creare previsioni della domanda.

Per informazioni su come introdurre i dati di pianificazione da altri moduli nel piano del budget, vedere [Integrazione della pianificazione del budget con altri moduli](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Interfaccia utente e funzionalità di creazione di report
In Microsoft Dynamics 365 for Operations gli utenti possono creare piani di budget direttamente nel client Microsoft Dynamics 365 for Operations (mediante una pagina configurabile del documento di piano di budget) o in Excel. Excel fornisce più funzionalità aggiuntive. Ad esempio, è possibile utilizzare i dati esterni come origine per un piano di budget, eseguire calcoli personalizzati e utilizzare le tabelle pivot e i grafici Microsoft. La maggior parte delle variabili nel processo di pianificazione del budget può essere configurata. Ad esempio, è possibile definire gli utenti che impostano il budget, che cosa viene sottoposto a budget e a che cosa assomiglia il processo. Sebbene sia possibile utilizzare Excel per la pianificazione del budget, Dynamics 365 for Operations è considerato l'unica fonte attendibile e consente di impedire problemi di controllo del budget. I processi periodici possono essere utilizzati per introdurre i dati iniziali per l'impostazione del budget nel piano di budget. Per la dichiarazione Dynamics 365 for Operations offre un set di pagine standard di indagine che consentono di visualizzare e analizzare i dati di impostazione del budget. I dati del piano di budget sono accessibili tramite lo Strumento di creazione report di gestione e scenari del piano di budget distinti possono essere visualizzati come colonne nel report Strumento di creazione report di gestione.





