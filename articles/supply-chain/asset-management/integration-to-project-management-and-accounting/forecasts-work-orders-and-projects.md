---
title: Previsioni, ordini di lavoro e progetti
description: In questo argomento vengono illustrate le previsioni e l'integrazione di ordini di lavoro con il modulo Gestione progetti e contabilità in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886818"
---
# <a name="forecasts-work-orders-and-projects"></a>Previsioni, ordini di lavoro e progetti

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

In Gestione cespiti, l'integrazione al modulo **Gestione progetti e contabilità** viene eseguita per ottimizzare il controllo dei costi, consentendo gli utenti di tenere traccia dei costi nelle previsioni del tipo di processo di manutenzione e nei processi di ordine di lavoro.

Per tenere traccia delle previsioni del tipo di processo di ordine di lavoro, è necessario eseguire due impostazioni:

1. Selezionare un progetto in **Gestione cespiti** > **Impostazione** > **Parametri di gestione cespiti** >  collegamento **Cespiti** > Scheda dettaglio **Progetto** > campo **Progetto previsione di manutenzione**.

2. In **Valori predefiniti tipo di processo di manutenzione**, quando si crea una riga predefinita del tipo di processo di manutenzione, un numero di attività viene creato automaticamente per la riga (**Gestione cespiti** > **Impostazione** > **Processi** > **Valori predefiniti tipo di processo di manutenzione**).

Le previsioni del tipo di processo di ordine di lavoro sono utili per due motivi: è possibile tenere traccia dei costi nelle previsioni del tipo di processo di manutenzione nel modulo **Gestione progetti e contabilità**. Inoltre, le previsioni verranno trasferite automaticamente a un progetto di processo di ordine di lavoro quando si seleziona un tipo di processo di manutenzione in un processo di ordine di lavoro.

Per tenere traccia dei costi nei processi di ordine di lavoro, è innanzitutto necessario impostare i progetti di ordine di lavoro. Fare riferimento alla sezione [Impostazione del progetto di ordine di lavoro](../setup-for-work-orders/work-order-project-setup.md) per una descrizione della procedura.

## <a name="work-order-job-projects"></a>Progetti di processo di ordine di lavoro

Quando si crea un processo di ordine di lavoro in un ordine di lavoro, il progetto di ordine di lavoro viene determinato dall'impostazione del progetto principale per gli ordini di lavoro in **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto**.

I progetti di processo di ordine di lavoro sono creati utilizzando una combinazione delle seguenti informazioni relative agli ordini di lavoro:

- Il tipo di ordine di lavoro selezionato nell'ordine di lavoro 
- L'unità funzionale correlata al cespite nel processo di ordine di lavoro
- Il tipo di cespite correlato al cespite nel processo di ordine di lavoro  
- La data e l'ora di inizio e quelle di fine previste impostate nell'ordine di lavoro  

È possibile che non tutte le informazioni menzionate precedentemente siano presenti in un ordine di lavoro. Di conseguenza, la ricerca di un progetto di ordine di lavoro principale viene eseguita utilizzando la combinazione disponibile di dati e selezionando l'ID progetto che corrisponde ai dati dell'ordine di lavoro.

Esempio: nella figura seguente, l'impostazione del tipo di cespite "Camion" indica che ogni processo di ordine di lavoro creato con il tipo di cespite sarà un progetto secondario dell'ID progetto "000186 ".

![Figura 1](media/01-integration-to-pma.png)

La funzione dell'ID progetto nel processo di ordine di lavoro e il numero di attività correlato (**Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** > selezionare l'ordine di lavoro nell'elenco > nella Scheda dettaglio **Dettagli riga** > campo **ID progetto** e campo **Numero di attività**) è di tenere traccia dei costi relativi al processo di ordine di lavoro e del cespite selezionato nel processo di ordine di lavoro nel modulo **Gestione progetti e contabilità**. 

Nella figura seguente, è visualizzata una panoramica grafica dei progetti di ordine di lavoro e delle attività di progetto correlate.

![Figura 2](media/02-integration-to-pma.png)

Quando un nuovo processo di ordine di lavoro viene creato in un ordine di lavoro, un progetto di ordine di lavoro viene automaticamente creato per il processo. Le dimensioni finanziarie per il cespite correlato al processo di ordine di lavoro vengono trasferite automaticamente al progetto di ordine di lavoro. L'attività di progetto creata per un processo di ordine di lavoro presenta informazioni correlate associate al processo in relazione al tipo di processo di manutenzione, alla variante di tipi di processo di manutenzione e al settore. Tali dati sono utili se, ad esempio, si crea un ordine fornitore da un ordine di lavoro (vedere [Approvvigionamento](../work-orders/procurement.md)), ovvero se si utilizza il modulo **Gestione progetti e contabilità** per la registrazione ore.  

Se il cespite è stato installato in un'unità funzionale e tale cespite viene successivamente installato in un'altra unità funzionale, le dimensioni finanziarie correlate alla nuova unità funzionale viene aggiornata automaticamente nel cespite. Successivamente, quando si crea una processo di ordine di lavoro per il cespite, il progetto di ordine di lavoro per il processo di ordine di lavoro acquisisce le dimensioni finanziarie che sono ora correlate al cespite. Ciò significa che quando si utilizzano le unità funzionali, è sempre possibile tenere traccia dei costi nelle unità funzionali in cui un cespite è stato installato in ogni dato momento. L'aggiornamento automatico delle dimensioni finanziarie garantisce la completa tracciabilità dei costi per il controllo dei progetto e il reporting.  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Progetti di ordine di lavoro, stati del ciclo di vita di ordine di lavoro, fasi di progetto e tipi di progetto

Per assicurare l'utilizzo corretto degli stati del ciclo di vita di ordine di lavoro e le relative fasi di progetto negli ordini di lavoro, considerare le dipendenze in relazione al modulo **Gestione progetti e contabilità** :

- Nel modulo **Gestione progetti e contabilità**, le fasi di progetto vengono impostate nei tipi di progetto in **Parametri Gestione progetti e contabilità**.  
- In **Parametri Gestione progetti e contabilità**, ricordare di selezionare le caselle di controllo pertinenti delle fasi di progetto pertinenti per tutti i tipi di progetto che si desidera utilizzare. Nella figura seguente, cinque fasi **Creato** - **Stimato** - **Programmato** - **In corso** - **Finito** sono state selezionate per i tipi di progetto "Tempistica e materiali" e "Interno". Quelle cinque fasi sono pertinenti per i processi di manutenzione interna e i processi di manutenzione di assistenza.  
- In **Gestione cespiti**, i tipi di progetto vengono definiti per gruppi di progetti impostati nel modulo **Impostazione del progetto di ordine di lavoro** > collegamento **Gruppo di progetti**.  
- I gruppi di progetti impostati in **Impostazione del progetto di ordine di lavoro** sono utilizzati quando si creano ordini di lavoro. Quando un ordine di lavoro viene creato, un progetto di ordine di lavoro viene automaticamente creato per l'ordine di lavoro.  
- Ogni stato del ciclo di vita di ordine di lavoro deve avere una fase di progetto correlata.  
- La fase di progetto correlata a uno stato del ciclo di vita di ordine di lavoro deve essere definita come fase attiva per il gruppo di progetti definito nel progetto di ordine di lavoro. Il progetto di ordine di lavoro viene creato automaticamente in un ordine di lavoro.  
- Quando si crea un nuovo ordine di lavoro, l'allocazione automatica di un progetto di ordine di lavoro è basata sull'impostazione in **Impostazione del progetto di ordine di lavoro** (**Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto**).  

Le associazioni tra gruppi di progetti di ordine di lavoro, tipi di progetto correlati, fasi di progetto e stati del ciclo di vita di ordine di lavoro sono visualizzate nelle figure seguenti.  

![Figura 3](media/03-integration-to-pma.png)

![Figura 4](media/04-integration-to-pma.png)

![Figura 5](media/05-integration-to-pma.png)

Fare riferimento a [Impostazione del progetto di ordine di lavoro](../setup-for-work-orders/work-order-project-setup.md) per informazioni su come impostare progetti di ordine di lavoro e a [Stati del ciclo di vita ordine di lavoro](../setup-for-work-orders/work-order-lifecycle-states.md) per informazioni su come creare stati del ciclo di vita di ordine di lavoro.

Nella figura seguente è illustrata una panoramica grafica dei vari progetti creati nel modulo **Gestione cespiti** per consentire l'integrazione con il modulo **Gestione progetti e contabilità** nonché dei processi di lavoro a cui i progetti sono correlati.

![Figura 6](media/06-integration-to-pma.png)

