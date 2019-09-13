---
title: Approvvigionamento
description: In questo argomento viene descritto l'approvvigionamento in Gestione cespiti.
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
ms.openlocfilehash: 1678dbe2432e4be46aebb40a12e73dfd695c3e77
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875733"
---
# <a name="procurement"></a>Approvvigionamento


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

In Gestione cespiti, è possibile ottenere una panoramica delle richieste di acquisto e degli ordini fornitore associati agli ordini di lavoro. È inoltre possibile creare un ordine fornitore o una richiesta di acquisto da un ordine di lavoro.

L'elenco **Richiesta di acquisto ordine di lavoro** (**Gestione cespiti** > **Comune** > **Approvvigionamento** > **Richiesta di acquisto ordine di lavoro**) contiene le richieste di acquisto correlate agli ordini di lavoro.

- Selezionare un processo di ordine di lavoro nell'elenco **Richiesta di acquisto ordine di lavoro** e fare clic sul pulsante **Richiesta di acquisto** per aprire la richiesta di acquisto correlata.  
- Selezionare un processo di ordine di lavoro nell'elenco **Richiesta di acquisto ordine di lavoro** e fare clic sul pulsante **Ordine di lavoro** per aprire l'ordine di lavoro correlato.  
- Selezionare un processo di ordine di lavoro nell'elenco **Richiesta di acquisto ordine di lavoro** e fare clic sul pulsante **Utilizzo dell'articolo** se si desidera ottenere una panoramica dell'utilizzo dell'articolo nella riga selezionata in Gestione cespiti in relazione a cespiti, valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro. 

![Figura 1](media/08-work-orders.png)


L'elenco **Acquisto ordine di lavoro** (**Gestione cespiti aziendali** > **Comune** > **Approvvigionamento** > **Acquisto ordine di lavoro**) contiene gli ordini fornitore correlati agli ordini di lavoro.

- Selezionare un processo di ordine di lavoro nell'elenco **Acquisto ordine di lavoro** e fare clic sul pulsante **Ordine fornitore** per aprire l'ordine fornitore correlato.  
- Selezionare un processo di ordine di lavoro nell'elenco **Acquisto ordine di lavoro** e fare clic sul pulsante **Ordine di lavoro** per aprire l'ordine di lavoro correlato.  
- Selezionare un processo di ordine di lavoro nell'elenco **Richiesta di acquisto ordine di lavoro** e fare clic sul pulsante **Utilizzo dell'articolo** se si desidera ottenere una panoramica dell'utilizzo dell'articolo nella riga selezionata in Gestione cespiti in relazione a cespiti, valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro. 

![Figura 2](media/09-work-orders.png)


Negli elenchi esposti sopra, a destra di ciascuna riga è visualizzata un'icona relativa al controllo della data di consegna. Se l'icona visualizza un punto esclamativo in un cerchio rosso, significa che la consegna per la richiesta di acquisto o l'ordine fornitore correlato può essere ritardata.

In una richiesta di acquisto, la data utilizzata per calcolare il possibile ritardo si trova nel modulo **Richieste di acquisto** > Scheda dettaglio **Richiesta di acquisto** > campo **Data richiesta**. Tale data viene confrontata alla data disponibile nell'ordine di lavoro o nel processo ordine di lavoro come avviene per la data dell'ordine fornitore.

In un ordine fornitore, la data utilizzata per calcolare il ritardo possibile è la data relativa alla riga dell'ordine fornitore, visualizzata nel modulo **Ordine fornitore** > selezionare la riga dell'ordine fornitore > Scheda dettaglio **Dettagli riga** > scheda **Impostazione** > campo **Data di consegna confermata**. Se quel campo non è specificato, viene utilizzata la data nel campo **Data di consegna** della Scheda dettaglio **Intestazione ordine fornitore**. Una di quelle date viene confrontata alla data disponibile nell'ordine di lavoro o nel processo ordine di lavoro nell'ordine seguente:

- Data di inizio effettiva nell'ordine di lavoro oppure  

- Data di inizio programmata nel processo di ordine di lavoro associato oppure  

- Data di inizio programmata nell'ordine di lavoro oppure  

- Data di inizio prevista nell'ordine di lavoro  


## <a name="create-purchase-order-from-a-work-order"></a>Creare un ordine fornitore da un ordine cliente

In **Tutti gli ordini di lavoro**, si seleziona un processo di ordine di lavoro e si crea un ordine fornitore o una richiesta di acquisto correlato. Ciò garantisce le relazioni di progetto tra l'ordine fornitore o la richiesta di acquisto e l'ordine di lavoro.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Nell'elenco **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**, selezionare l'ordine di lavoro per il quale si desidera creare un ordine fornitore e fare clic su **Modifica**.

3. Nel modulo **Ordine di lavoro** > Scheda dettaglio **Processi di manutenzione ordine di lavoro**, selezionare il processo di ordine di lavoro per il quale si desidera creare l'ordine fornitore.

4. Fare clic su **Attività articolo** > **Ordine fornitore da processo di ordine di lavoro**.

5. Nella pagina elenco **Ordini fornitore progetto**, fare clic su **Nuovo**.

6. Crea l'ordine fornitore.

>[!NOTE]
>La creazione di una richiesta di acquisto è quasi identica alla creazione di un ordine fornitore. L'unica differenza è che nella procedura esposta sopra, si fa clic su **Attività articolo** > **Richiesta di acquisto da processo di ordine di lavoro** nel passaggio 2.

## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relazione progetti tra ordine di lavoro e ordine fornitore o richiesta di acquisto

Una riga di ordine fornitore o di richiesta di acquisto è associata a un processo di ordine di lavoro tramite il progetto di ordine di lavoro e il numero di attività di progetto correlato. Quando si crea un ordine fornitore o una richiesta di acquisto da un processo di ordine di lavoro, il numero di attività di progetto correlato è obbligatorio. Il numero di attività di progetto viene automaticamente immesso in un ordine fornitore o una richiesta di acquisto se l'ordine di lavoro correlato contiene processi di ordine di lavoro che utilizzano tutti lo stesso tipo di processo di manutenzione. Se i processi di ordine di lavoro contengono tipi di processo di manutenzione differenti, il numero di attività di progetto deve essere immesso manualmente.

Per visualizzare o immettere il numero di attività relativo a una riga di ordine fornitore, aprire **Acquisto ordine di lavoro** > selezionare il record di ordine fornitore > fare clic sull'ordine fornitore nella colonna **Ordine fornitore** > Scheda dettaglio **Dettagli riga** > scheda **Progetto** > campo **Numero di attività**.


![Figura 3](media/10-work-orders.png)


Analogamente, per visualizzare o immettere il numero di attività relativo a una riga di richiesta di acquisto di ordine fornitore, aprire **Acquisto ordine di lavoro** > selezionare il record di richiesta di acquisto > fare clic sulla richiesta di acquisto nella colonna **Richiesta di acquisto** > Scheda dettaglio **Dettagli riga** > scheda **Progetto** > campo **Numero di attività**.

