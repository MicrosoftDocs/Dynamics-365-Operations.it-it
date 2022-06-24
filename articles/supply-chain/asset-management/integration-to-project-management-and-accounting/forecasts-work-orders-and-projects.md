---
title: Previsioni, ordini di lavoro e progetti
description: In questo articolo vengono illustrate le previsioni e l'integrazione di ordini di lavoro con il modulo Gestione progetti e contabilità in Gestione cespiti.
author: johanhoffmann
ms.date: 08/29/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 80f0380d50a0c050242846c0c3e70bc1a0bd6bf5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880453"
---
# <a name="forecasts-work-orders-and-projects"></a>Previsioni, ordini di lavoro e progetti

[!include [banner](../../includes/banner.md)]

 

In Gestione cespiti, l'integrazione con il modulo **Gestione progetti e contabilità** consente di ottimizzare il controllo dei costi di modo che gli utenti possano tenere traccia dei costi nelle previsioni del tipo di processo di manutenzione e nei processi di ordine di lavoro.

Per tenere traccia delle previsioni del tipo di processo di ordine di lavoro, è necessario eseguire due impostazioni:

1. Selezionare un progetto in **Gestione cespiti** > **Impostazione** > **Parametri di gestione cespiti** e quindi nella scheda **Cespiti** della Scheda dettaglio **Progetto**, nel campo **Progetto previsione di manutenzione**, selezionare un progetto.

2. Quando si crea una riga predefinita del tipo di processo di manutenzione, un numero di attività viene creato automaticamente per la riga nella pagina **Valori predefiniti tipo di processo di manutenzione** (**Gestione cespiti** > **Impostazione** > **Processi** > **Valori predefiniti tipo di processo di manutenzione**).

Le previsioni del tipo di processo di ordine di lavoro sono utili per due motivi: 

- È possibile tenere traccia dei costi nelle previsioni del tipo di processo di manutenzione nel modulo **Gestione progetti e contabilità**. 
- Le previsioni sono trasferite automaticamente a un progetto di processo di ordine di lavoro quando si seleziona un tipo di processo di manutenzione in un processo di ordine di lavoro.

Per tenere traccia dei costi nei processi di ordine di lavoro, è innanzitutto necessario impostare i progetti di ordine di lavoro. Per ulteriori informazioni, vedere [Impostazione del progetto di ordine di lavoro](../setup-for-work-orders/work-order-project-setup.md).

## <a name="work-order-job-projects"></a>Progetti di processo di ordine di lavoro

Quando si crea un processo di ordine di lavoro in un ordine di lavoro, il progetto di ordine di lavoro viene determinato dall'impostazione del progetto principale per gli ordini di lavoro nella pagina **Impostazione del progetto di ordine di lavoro** (**Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto**).

I progetti di processo di ordine di lavoro sono creati utilizzando una combinazione delle seguenti informazioni relative agli ordini di lavoro:

- Il tipo di ordine di lavoro selezionato nell'ordine di lavoro 
- L'unità funzionale correlata al cespite nel processo di ordine di lavoro
- Il tipo di cespite correlato al cespite nel processo di ordine di lavoro  
- La data e l'ora di inizio e di fine previste impostate nell'ordine di lavoro  

Alcune di queste informazioni potrebbero non essere presenti in un ordine di lavoro. Di conseguenza, la ricerca di un progetto di ordine di lavoro principale viene eseguita utilizzando la combinazione disponibile di dati e selezionando l'ID progetto che corrisponde ai dati dell'ordine di lavoro.

Ad esempio, nell'illustrazione seguente, a causa dell'impostazione del tipo di cespite **Motore camion**, ogni processo di ordine di lavoro creato con il tipo di cespite **Motore camion** sarà un sottoprogetto del progetto 000186.

![Figura 1.](media/01-integration-to-pma.png)

Lo scopo dell'ID progetto nel processo di ordine di lavoro e del numero di attività correlato è di tenere traccia dei costi relativi al processo di ordine di lavoro e al cespite selezionato nello stesso nel modulo **Gestione progetti e contabilità**. Per visualizzare l'ID progetto e il numero di attività, selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** e quindi selezionare l'ordine di lavoro. Nella Scheda dettaglio **Dettagli riga**, il campo **ID progetto** mostra l'ID progetto e il campo **Numero attività** visualizza il numero di attività. Per ulteriori informazioni sul controllo dei costi in Gestione cespiti, vedere [Controllo dei costi e delle date](../controlling-and-reporting/cost-and-date-control.md).

Nella figura seguente è illustrata una panoramica grafica dei progetti di ordine di lavoro e delle attività di progetto correlate.

![Figura 2.](media/02-integration-to-pma.png)

Quando un nuovo processo di ordine di lavoro viene creato in un ordine di lavoro, un progetto di ordine di lavoro viene automaticamente creato per il processo. Le dimensioni finanziarie per il cespite correlato al processo di ordine di lavoro vengono trasferite automaticamente al progetto di ordine di lavoro.

L'attività di progetto creata per un processo di ordine di lavoro ha informazioni correlate associate. Queste informazioni sono relative al tipo di processo di manutenzione, alla variante di tipi di processo di manutenzione e al settore. Sono utili se, ad esempio, si crea un ordine fornitore da un ordine di lavoro (vedere [Approvvigionamento](../work-orders/procurement.md)), oppure se si utilizza il modulo **Gestione progetti e contabilità** per la registrazione ore.

Se il cespite è stato installato in un'unità funzionale ma viene successivamente installato in un'unità funzionale differente, le dimensioni finanziarie correlate alla nuova unità funzionale sono automaticamente aggiornate nel cespite. Quindi, quando si crea una processo di ordine di lavoro per il cespite, il progetto di ordine di lavoro per il processo di ordine di lavoro acquisisce automaticamente le dimensioni finanziarie che sono ora correlate al cespite. Di conseguenza, quando si utilizzano unità funzionali, è sempre possibile tenere traccia dei costi nelle unità funzionali in cui un cespite è stato installato in ogni dato momento. L'aggiornamento automatico delle dimensioni finanziarie consente di garantire la completa tracciabilità dei costi per il controllo dei progetti e il reporting.

## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Progetti di ordine di lavoro, stati del ciclo di vita di ordine di lavoro, fasi di progetto e tipi di progetto

Per assicurare l'utilizzo corretto degli stati del ciclo di vita di ordine di lavoro e le relative fasi di progetto negli ordini di lavoro, considerare le dipendenze in relazione al modulo **Gestione progetti e contabilità** :

- Nel modulo **Gestione progetti e contabilità**, le fasi di progetto vengono impostate nei tipi di progetto nella pagina **Parametri Gestione progetti e contabilità**.  
- Nella pagina **Parametri Gestione progetti e contabilità**, utilizzare le caselle di controllo per selezionare le fasi di progetto pertinenti per tutti i tipi di progetto che si utilizzeranno. Nelle illustrazioni seguenti, cinque fasi (**Creato**, **Stimato**, **Programmato**, **In corso** e **Finito**) sono state selezionate per i tipi di progetto **Tempistica e materiali** e **Interno**. Queste cinque fasi sono pertinenti ai processi di manutenzione interna e ai processi di manutenzione di assistenza.
- Nel modulo **Gestione cespiti**, i tipi di progetto sono definiti dai gruppi di progetti definiti nella pagina **Impostazione del progetto dell'ordine di lavoro** > scheda **Gruppo di progetti** (**Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto**).  
- I gruppi di progetti definiti nella pagina **Impostazione del progetto di ordine di lavoro** sono utilizzati quando si creano ordini di lavoro. Quando un ordine di lavoro viene creato, un progetto di ordine di lavoro viene automaticamente creato per l'ordine di lavoro.  
- Ogni stato del ciclo di vita di ordine di lavoro deve avere una fase di progetto correlata.  
- La fase di progetto correlata a uno stato del ciclo di vita di ordine di lavoro deve essere definita come fase attiva per il gruppo di progetti definito nel progetto di ordine di lavoro. Il progetto di ordine di lavoro viene creato automaticamente in un ordine di lavoro.
- Quando si crea un nuovo ordine di lavoro, l'allocazione automatica di un progetto di ordine di lavoro è basata sull'impostazione nella pagina **Impostazione del progetto di ordine di lavoro**.  

Le illustrazioni seguenti mostrano le associazioni tra gruppi di progetti di ordine di lavoro, tipi di progetto correlati, fasi di progetto e stati del ciclo di vita di ordine di lavoro.

![Figura 3.](media/03-integration-to-pma.png)

![Figura 4.](media/04-integration-to-pma.png)

![Figura 5.](media/05-integration-to-pma.png)

Per ulteriori informazioni su come impostare i progetti di ordine di lavoro, vedere [Impostazione del progetto di ordine di lavoro](../setup-for-work-orders/work-order-project-setup.md). Per ulteriori informazioni su come creare stati del ciclo di vita di ordine di lavoro, vedere [Stati del ciclo di vita ordine di lavoro](../setup-for-work-orders/work-order-lifecycle-states.md).

Nella figura seguente è illustrata una panoramica grafica dei vari progetti creati nel modulo **Gestione cespiti** per consentire l'integrazione con il modulo **Gestione progetti e contabilità**. Sono inoltre visualizzati i processi di lavoro a cui i progetti sono correlati.

![Figura 6.](media/06-integration-to-pma.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]