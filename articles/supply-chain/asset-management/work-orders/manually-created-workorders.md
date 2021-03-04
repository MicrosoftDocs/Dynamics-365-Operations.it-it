---
title: Ordini di lavoro creati manualmente
description: In questo argomento viene descritto come creare manualmente ordini di lavoro in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4a4b148d9ac5d032d2caa5fcea0398a5a3726f0e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430965"
---
# <a name="manually-created-work-orders"></a>Ordini di lavoro creati manualmente

[!include [banner](../../includes/banner.md)]


È possibile creare ordini di lavoro manualmente in due modi:

- Nella pagina **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi** 
- Nella pagina **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali** 

## <a name="create-work-order"></a>Crea ordine di lavoro

1. Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare **Nuovo**.

3. Nella finestra di dialogo **Crea ordine di lavoro**, selezionare un tipo di ordine di lavoro nel campo **Tipo di ordine di lavoro**.

4. Se necessario, selezionare una **descrizione**.

5. Selezionare il cespite nel campo **Cespite**.

>[!NOTE]
>Quando si seleziona un cespite, tre schede potrebbero essere disponibili nel menu a discesa **Cespite**: 

- **Cespiti attivi** - Questa scheda include un elenco di tutti i cespiti con stato del ciclo di vita del cespite "Attivo". 
- **Visualizzazione cespiti** - Questa scheda mostra una visualizzazione ad albero delle unità funzionali e dei cespiti installati nelle unità.
- **Cespiti personali** - Questa scheda include i cespiti correlati alle unità funzionali che possono essere allocate al lavoratore che esegue l'accesso a sistema. Per informazioni sull'impostazione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md). Se le unità funzionali non sono impostate per un lavoratore in [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md), la scheda **Cespiti personali** non è disponibile. 

6. Selezionare il tipo di processo di manutenzione per l'ordine di lavoro nel campo **Tipo di processo di manutenzione**.

7. Se necessario, selezionare **Variante tipi di processo di manutenzione** e **Settore**.

8. Se necessario, è possibile modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio**.

9. Selezionare le **date di inizio** e **di fine previste** nei campi correlati.

10. Fare clic su **OK** per creare l'ordine di lavoro.

11. Nella pagina elenco **Tutti gli ordini di lavoro**, è possibile modificare l'ordine di lavoro secondo le necessità.

Notare i punti seguenti:

- Nella visualizzazione dettagli della pagina elenco **Tutti gli ordini di lavoro**, è possibile aggiungere vari cespiti a un ordine di lavoro aggiungendo righe nella Scheda dettaglio **Processi di manutenzione ordine di lavoro**. In un cespite, è possibile selezionare solo i tipi di processo di manutenzione definiti nel tipo di cespite selezionato per il cespite.  

- Se si modifica un livello di servizio cespiti o una criticità cespiti dopo che è stato già utilizzato il cespite in un ordine di lavoro, il livello di servizio o la criticità nell'ordine di lavoro non viene aggiornato di conseguenza. Per ulteriori informazioni sui livelli di servizio e le criticità, vedere [Livello del servizio cespiti](../setup-for-objects/object-priorities.md) e [Tipi di criticità dei cespiti](../setup-for-objects/object-criticalities.md).

- La criticità in un ordine di lavoro viene ricalcolata ogni volta in cui un processo ordine di lavoro viene aggiunto o eliminato dall'ordine di lavoro.

- Nella visualizzazione dettagli **Tutti gli ordini di lavoro** > scheda **Intestazione** > Scheda dettaglio **Programma**, è possibile selezionare un gruppo di addetti alla manutenzione responsabile o un addetto alla manutenzione responsabile nei campi **Gruppo responsabile** o **Responsabile**. Queste impostazioni possono essere modificate quando l'ordine di lavoro è attivo. Ad esempio, possono essere modificate quando cambia lo stato del ciclo di vita dell'ordine di lavoro. La selezione automatica effettuata durante la creazione di ordini di lavoro è basata sull'impostazione nella pagina **Addetti alla manutenzione responsabili**. Se si aggiungono o rimuovono i processi di ordine di lavoro dopo aver creato un ordine di lavoro e se i campi **Gruppo responsabile** e **Responsabile** sono vuoti quando si aggiorna un ordine di lavoro, Gestione cespiti cerca una possibile corrispondenza nella pagina di impostazione per un addetto alla manutenzione responsabile o un gruppo di addetti alla manutenzione responsabile. Il campo **Gruppo responsabile** o **Responsabile** è già impostato quando si aggiorna l'ordine di lavoro e non viene apportata alcuna modifica. Per ulteriori informazioni sugli addetti alla manutenzione responsabile e sui gruppi di addetti alla manutenzione responsabile, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).

- Nella pagina [Stato della manutenzione](../controlling-and-reporting/maintenance-status.md), è possibile eseguire un calcolo per ottenere una panoramica del carico di lavoro relativo agli ordini di lavoro ricevuti e completati.  

- Nella visualizzazione dettagli della pagina **Tutti gli ordini di lavoro**, nella Scheda dettaglio **Dettagli riga**, è possibile utilizzare i campi **Longitudine** e **Latitudine** per aggiungere le coordinate geografiche per il cespite selezionato nel processo ordine di lavoro.  


## <a name="create-related-work-order"></a>Crea ordine di lavoro correlato

È possibile creare un ordine di lavoro basato su un ordine di lavoro esistente. Questa funzionalità è utile ad esempio se si desidera utilizzare ordini di lavoro principali e secondari. Un nuovo ordine di lavoro è basato su un processo di ordine di lavoro di un ordine di lavoro esistente.

1. Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro di cui creare un ordine di lavoro correlato.

3. Nella scheda **Ordine di lavoro** del riquadro azioni, nel gruppo **Nuovo**, selezionare **Ordine di lavoro correlato**.

4. Nella finestra di dialogo **Creare ordine di lavoro correlato**, selezionare il processo di ordine di lavoro per il quale si desidera creare un ordine di lavoro correlato nel campo **Processo ordine di lavoro**.

5. Selezionare il tipo di processo di manutenzione nel campo **Tipo di processo di manutenzione**.

6. Selezionare la variante e il settore associato al tipo di processo di manutenzione nei campi **Variante tipi di processo di manutenzione** e **Settore**.

7. Se l'ordine di lavoro è il primo ordine di lavoro correlato creato per l'ordine di lavoro selezionato, effettuare le seguenti operazioni:
    1. Selezionare l'opzione **Nuovo ordine di lavoro**.
    2. Nel campo **Tipo di ordine di lavoro** selezionare un tipo di ordine di lavoro.
    3. Nel campo **Descrizione** immettere una descrizione.
    4. Modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio** secondo le necessità.
    5. Nei campi **Data di inizio prevista** e **Data di fine prevista**, selezionare le date di inizio e fine previste.
    6. Selezionare **OK**. Il nuovo ordine di lavoro correlato è visualizzato nella pagina elenco **Tutti gli ordini di lavoro**.  

8. Se l'ordine di lavoro per cui si sta creando questo ordine di lavoro correlato ha già ordini di lavoro correlati, attenersi alla seguente procedura per aggiungere un nuovo processo di ordine di lavoro a un ordine di lavoro correlato esistente:
    1. Selezionare l'opzione **Aggiungi a ordine di lavoro correlato**.
    2. Nel campo **Ordine di lavoro** selezionare l'ordine di lavoro correlato a cui si desidera aggiungere un nuovo processo di ordine di lavoro.
    3. Modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio** secondo le necessità.
    4. Nei campi **Data di inizio prevista** e **Data di fine prevista**, modificare le date di inizio e fine previste secondo le necessità.
    5. Selezionare **OK**. Il processo di ordine di lavoro viene aggiunto all'ordine di lavoro correlato esistente.

Nella figura seguente è illustrato un esempio della finestra di dialogo **Crea ordine di lavoro correlato**.

![Figura 1](media/03-work-orders.png)

>[!NOTE]
>Se è stata impostata una maschera di ordine di lavoro correlato in **Parametri di gestione cespiti** > scheda **Ordini di lavoro** > campo **Maschera ordini di lavoro correlati**, gli ID di ordine di lavoro saranno creati in base all'impostazione della maschera. Se non è stata impostata una maschera di ordine di lavoro correlato, per gli ordini di lavoro correlati viene utilizzato l'ID di ordine di lavoro disponibile successivo.

## <a name="copy-a-work-order"></a>Copiare un ordine di lavoro

È possibile creare rapidamente un nuovo ordine di lavoro da un ordine di lavoro esistente. Questo modo di utilizzare gli ordini di lavoro differisce dalla creazione di ordini di lavoro basati sui [piani di manutenzione](../preventive-and-reactive-maintenance/maintenance-plans.md). È utile se, ad esempio, un ordine di lavoro contiene numerosi processi di ordine di lavoro con vari processi da completare in diversi cespiti a intervalli regolari.

1. Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro da cui copiare il contenuto.

3. Nella scheda **Ordine di lavoro** del riquadro azioni > gruppo **Nuovo**, selezionare **Copia ordine di lavoro**.

4. Viene visualizzata l'impostazione dell'ordine di lavoro selezionato. È possibile modificare alcuni campi secondo le necessità.

5. Selezionare **OK** per creare il nuovo ordine di lavoro.

6. Nella pagina elenco **Tutti gli ordini di lavoro**, è possibile modificare l'ordine di lavoro secondo le necessità.

>[!NOTE]
>Quando si crea il nuovo ordine di lavoro, alcune informazioni vengono copiate direttamente dall'ordine di lavoro esistente. Le informazioni su previsioni, strumenti, liste di controllo di manutenzione, unità funzionale, indirizzi e pianificazione non vengono copiate. Vengono invece inizializzate dall'impostazione corrente in Gestione risorse. Pertanto, se tali informazioni sono state modificate tra il momento in cui è stato creato il primo ordine di lavoro e il momento in cui è stata effettuata una copia dell'ordine di lavoro, le modifiche sono incluse nel nuovo ordine di lavoro. Esempi di questa operazione sono le modifiche alle previsioni e gli aggiornamenti agli elenchi di controllo di manutenzione.

Nella figura seguente è illustrato un esempio della finestra di dialogo **Copia ordine di lavoro**.

![Figura 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a>Creare un ordine di lavoro basato su una richiesta di intervento di manutenzione

1. Selezionare **Gestione cespiti** > **Comune** > **Richieste di intervento di manutenzione** > **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.

2. Selezionare la richiesta di intervento di manutenzione per la quale creare un ordine di lavoro e fare clic su **Modifica**.

3. Nella scheda **Richiesta di intervento di manutenzione** del riquadro azioni > gruppo **Nuovo**, selezionare **Ordine di lavoro**.

4. Nella finestra di dialogo **Ordine di lavoro**, impostare i campi. Se un tipo di processo di manutenzione è stato selezionato nella richiesta di intervento di manutenzione, è possibile selezionare un tipo di processo di manutenzione diverso quando si crea l'ordine di lavoro secondo le necessità.

5. Selezionare **OK**. Il messaggio informa che l'ordine di lavoro è stato creato.

6. Per visualizzare gli ordini di lavoro collegati a una richiesta di intervento di manutenzione, nella pagine elenco **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**, selezionare la richiesta di intervento di manutenzione. Nella scheda **Richiesta di intervento di manutenzione** del riquadro azioni, nel gruppo **Visualizza**, selezionare **Ordini di lavoro**.


Nella figura seguente è illustrato un esempio della finestra di dialogo **Creare ordine di lavoro**.

![Figura 3](media/05-work-orders.png)


>[!NOTE]
>Per creare automaticamente gli ordini di lavoro è possibile pianificare i processi del piano di manutenzione o impostare la creazione automatica dei [piani di manutenzione](../preventive-and-reactive-maintenance/maintenance-plans.md) o [cicli di manutenzione](../preventive-and-reactive-maintenance/maintenance-rounds.md) per un cespite. Gli ordini di lavoro creati dalle richieste di intervento di manutenzione nella pagina elenco **Tutti i programmi di manutenzione** hanno i tipi di processo di manutenzione selezionati nelle richieste di intervento di manutenzione.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]