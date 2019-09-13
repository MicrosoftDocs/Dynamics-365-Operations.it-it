---
title: Ordini di lavoro creati manualmente
description: In questo argomento viene descritto come creare manualmente ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875734"
---
# <a name="manually-created-work-orders"></a>Ordini di lavoro creati manualmente

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


È possibile creare ordini di lavoro manualmente in due modi:

- In **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**  
- In **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**.  

## <a name="create-work-order"></a>Crea ordine di lavoro

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Fare clic sul pulsante **Nuovo**.

3. Nel menu a discesa **Crea ordine di lavoro**, selezionare un tipo di ordine di lavoro.

4. Se necessario, selezionare una descrizione.

5. Selezionare il cespite per l'ordine di lavoro nonché un tipo di processo di manutenzione.

>[!NOTE]
>Quando si seleziona un cespite, è possibile che siano disponibili tre schede: la scheda **Cespiti personali** include i cespiti correlati alle unità funzionali a cui il lavoratore connesso al sistema può essere assegnato (impostazione in [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md)). Se non sono impostate unità funzionali per un lavoratore in [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md), la scheda **Cespiti personali** non sarà visibile. La scheda **Cespiti attivi** include un elenco di tutti i cespiti con stato del ciclo di vita del cespite "Attivo". La scheda **Visualizzazione cespiti** mostra una visualizzazione struttura delle unità funzionali e dei cespiti installati nelle unità.

6. Se necessario, selezionare **Variante tipi di processo di manutenzione** e **Settore**.

7. Se necessario, è possibile modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio**.

8. Selezionare le date di inizio e di fine previste nei campi correlati.

9. Fare clic su **OK** per creare un nuovo ordine di lavoro.

10. Modificare l'ordine di lavoro in **Tutti gli ordini di lavoro**, se necessario.

- In **Tutti gli ordini di lavoro**, è possibile aggiungere vari cespiti a un ordine di lavoro nella visualizzazione dettagli aggiungendo righe nella Scheda dettaglio **Processi di manutenzione ordine di lavoro**. In un cespite, è possibile selezionare solo i tipi di processo di manutenzione definiti nel tipo di cespite selezionato per il cespite.  
- Se si è modificato un livello di servizio cespiti o una criticità cespiti dopo l'utilizzo in un ordine di lavoro (fare riferimento a [Livelli di servizio cespiti](../setup-for-objects/object-priorities.md) e [Criticità cespiti](../setup-for-objects/object-criticalities.md)), il livello di servizio o la criticità nell'ordine di lavoro non verrà aggiornato di conseguenza.
- La criticità in un ordine di lavoro viene ricalcolata ogni volta che una riga di ordine di lavoro viene aggiunta o eliminatq nell'ordine di lavoro.
- Nella visualizzazione dettagli **Tutti gli ordini di lavoro** > visualizzazione **Intestazione** > Scheda dettaglio **Programma**, è possibile selezionare un gruppo di addetti alla manutenzione responsabile o un addetto alla manutenzione responsabile nei campi **Gruppo responsabile** o **Responsabile**. Queste impostazioni possono essere modificate purché l'ordine di lavoro sia attivo, ad esempio, quando lo stato del ciclo di vita di ordine di lavoro cambia. La selezione automatica effettuata durante la creazione di ordini di lavoro è basata sull'impostazione in **Addetti alla manutenzione responsabili**. Se si aggiungono o rimuovono i processi di ordine di lavoro dopo aver creato un ordine di lavoro e i campi **Gruppo responsabile** e **Responsabile** sono vuoti quando si aggiorna un ordine di lavoro, Gestione cespiti cerca una possibile corrispondenza nel modulo di impostazione per un addetto alla manutenzione o un gruppo di addetti alla manutenzione responsabile. Il campo **Gruppo responsabile** o **Responsabile** è già popolato quando si aggiorna l'ordine di lavoro e non viene apportata alcuna modifica. 

- In **Stato della manutenzione**, è possibile eseguire un calcolo per ottenere una panoramica del carico di lavoro relativo agli ordini di lavoro ricevuti e completati.  

- Nella Scheda dettaglio **Dettagli riga**, utilizzare i campi **Longitudine** e **Latitudine** per aggiungere le coordinate geografiche per il cespite nel processo di ordine di lavoro.  

## <a name="create-related-work-order"></a>Crea ordine di lavoro correlato

È possibile creare un ordine di lavoro associato a un ordine di lavoro esistente se, ad esempio, si intende utilizzare ordini di lavoro principali e secondari. Un nuovo ordine di lavoro è basato su un processo di ordine di lavoro di un ordine di lavoro esistente.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro per il quale si desidera creare un ordine di lavoro correlato.

3. Fare clic su **Ordine di lavoro correlato**.

4. Nella finestra di dialogo a discesa **Creare ordine di lavoro correlato**, selezionare il processo di ordine di lavoro per il quale si desidera creare un ordine di lavoro correlato nel campo **Processo ordine di lavoro**.

5. Selezionare un tipo di processo di manutenzione nel campo **Tipo di processo di manutenzione** e, se necessario, un settore e una variante di tipi di processo di manutenzione associati nei campi **Settore** e **Variante tipi di processo di manutenzione**.

6. Se si tratta del primo ordine di lavoro correlato creato, fare clic sul pulsante radio **Nuovo ordine di lavoro**.

7. Selezionare un **Tipo di ordine di lavoro** e una **Descrizione** nei relativi campi.

8. Se necessario, modificare il livello di servizio di ordine di lavoro nel campo **Livello servizio**.

9. Immettere le date di inizio e di fine previste nei campi correlati.

10. Fare clic su **OK**. Il nuovo ordine di lavoro correlato è visualizzato nell'elenco **Tutti gli ordini di lavoro**.

11. Se si crea un ordine di lavoro correlato in un ordine di lavoro che presenta già degli ordini di lavoro correlati, è possibile aggiungere il processo di ordine di lavoro a un ordine di lavoro già correlato. Questa operazione può essere effettuata facendo clic sul pulsante di opzione **Aggiungi a ordine di lavoro correlato** nel passaggio 6. Selezionare quindi l'ordine di lavoro correlato a cui si desidera aggiungere un nuovo processo di ordine di lavoro. Modificare i campi **Livello servizio**, **Data di inizio prevista** e **Data di fine prevista** come necessario e fare clic su **OK**. Il processo di ordine di lavoro viene aggiunto all'ordine di lavoro correlato esistente.


![Figura 1](media/03-work-orders.png)

**Nota:** se è stata impostata una maschera di ordine di lavoro correlato in **Parametri di gestione cespiti** >  collegamento **Ordini di lavoro** > campo **Maschera ordini di lavoro correlati**, gli ID di ordine di lavoro saranno creati in conformità con l'impostazione della maschera. Se non è stata impostata una maschera di ordine di lavoro correlato, per gli ordini di lavoro correlati verrà utilizzato l'ID di ordine di lavoro disponibile successivo.

## <a name="copy-work-order"></a>Copia ordine di lavoro

È possibile creare rapidamente un nuovo ordine di lavoro da un ordine di lavoro esistente. Questo metodo è differente dalla creazione di ordini di lavoro in base a piani di manutenzione. È utile se, ad esempio, si ha un ordine di lavoro contenente numerosi processi di ordine di lavoro con vari processi in cespiti differenti che devono essere completati a intervalli regolari.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro da cui copiare il contenuto.

3. Fare clic su **Copia ordine di lavoro**. Viene visualizzata l'impostazione dell'ordine di lavoro selezionato. Se necessario, è possibile modificare alcuni campi.

4. Fare clic su **OK** per creare il nuovo ordine di lavoro.

5. Modificare l'ordine di lavoro in **Tutti gli ordini di lavoro**, se necessario.

>[!NOTE]
>Quando si crea il nuovo ordine di lavoro, alcune informazioni vengono copiate direttamente dall'ordine di lavoro esistente. Le informazioni relative a previsioni, strumenti, elenchi di controllo di manutenzione, unità funzionale, indirizzi e programmazione non vengono copiate, ma inizializzate dall'impostazione corrente in Gestione cespiti. Ciò significa che se le modifiche sono state eseguite in quei dati dalla creazione del primo ordine di lavoro fino alla creazione di una copia dell'ordine di lavoro, sono incluse nel nuovo ordine di lavoro creato. Esempi di questa operazione sono le modifiche nelle previsioni o negli elenchi di controllo di manutenzione aggiornati.


![Figura 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a>Creare un ordine di lavoro basato su una richiesta di intervento di manutenzione

1. Fare clic su **Gestione cespiti** > **Comune** > **Richieste di intervento di manutenzione** > **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.

2. Selezionare la richiesta di intervento di manutenzione per la quale si desidera creare un ordine di lavoro e fare clic su **Modifica**.

3. In **Tutte le richieste**, fare clic su **Ordine di lavoro**.

4. Popolare i campi in **Ordine di lavoro**. Se un tipo di processo di manutenzione è stato selezionato nella richiesta di intervento di manutenzione, è possibile selezionare un altro tipo di processo di manutenzione, se necessario, quando si crea l'ordine di lavoro.

5. Fare clic su **OK**. Viene visualizzato un messaggio che informa della creazione dell'ordine di lavoro.

6. Se si desidera visualizzare gli ordini di lavoro collegati a una richiesta di intervento di manutenzione, selezionare la richiesta di intervento di manutenzione negli elenchi **Tutte le richiesta di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** e fare clic sui pulsanti **Ordini di lavoro**.


![Figura 3](media/05-work-orders.png)


>[!NOTE]
>Gli ordini di lavoro possono anche essere generati automaticamente programmando processi di piano di manutenzione o impostando "Crea automaticamente" per i piani di manutenzione o i cicli di manutenzione di un cespite. Gli ordini di lavoro creati dalle richieste di intervento di manutenzione in **Programma di manutenzione** vengono creati con i tipi di processo di manutenzione selezionati nelle richieste di intervento di manutenzione.

