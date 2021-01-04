---
title: Approvvigionamento
description: In questo argomento viene descritto l'approvvigionamento in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderPurchaseListPagePreviewPane, EntAssetWorkOrderPurchaseListPage, EntAssetWorkOrderPurchaseLineAmountInfoPart, EntAssetWorkOrderPurchReqListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 552b1b211460ae86af06e183af91c062a3ee569a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431344"
---
# <a name="procurement"></a>Approvvigionamento

[!include [banner](../../includes/banner.md)]

In Gestione cespiti, è possibile ottenere una panoramica delle richieste di acquisto e degli ordini fornitore associati agli ordini di lavoro. È inoltre possibile creare un ordine fornitore o una richiesta di acquisto da un ordine di lavoro.

La pagina elenco **Richiesta di acquisto ordine di lavoro** (**Gestione cespiti** > **Comune** > **Approvvigionamento** > **Richiesta di acquisto ordine di lavoro**) contiene le richieste di acquisto correlate agli ordini di lavoro. Quando si seleziona un processo di ordine di lavoro in questa pagina, è possibile utilizzare i pulsanti del gruppo **Mostra** della scheda del riquadro azioni **Richiesta di acquisto ordine di lavoro** per eseguire le varie operazioni:

- Per aprire la richiesta di acquisto correlata, selezionare **Richiesta di acquisto**. 
- Per aprire l'ordine di lavoro correlato, selezionare **Ordine di lavoro**.
- Per ottenere una panoramica di dove l'articolo viene utilizzato nella riga selezionata in relazione ai cespiti, ai valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro, selezionare **Utilizzo dell'articolo**. Per ulteriori informazioni su questa panoramica, vedere [Utilizzo dell'articolo](../controlling-and-reporting/item-where-used.md).

Nell'illustrazione seguente è illustrato un esempio della pagina elenco **Richiesta di acquisto ordine di lavoro**.

![Figura 1](media/08-work-orders.png)


La pagina elenco **Acquisto ordine di lavoro** (**Gestione cespiti** > **Comune** > **Approvvigionamento** > **Acquisto ordine di lavoro**) contiene l'elenco degli ordini fornitore correlati agli ordini di lavoro. Quando si seleziona un processo di ordine di lavoro in questa pagina, è possibile utilizzare i pulsanti del gruppo **Mostra** della scheda del riquadro azioni **Acquisto ordine di lavoro** per eseguire le varie operazioni:

- Per aprire l'ordine fornitore correlato, selezionare **Ordine fornitore**. 
- Per aprire l'ordine di lavoro correlato, selezionare **Ordine di lavoro**.
- Per ottenere una panoramica di dove l'articolo viene utilizzato nella riga selezionata in relazione ai cespiti, ai valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro, selezionare **Utilizzo dell'articolo**. Per ulteriori informazioni su questa panoramica, vedere [Utilizzo dell'articolo](../controlling-and-reporting/item-where-used.md).

Nell'illustrazione seguente è illustrato un esempio della pagina elenco **Acquisto ordine di lavoro**.

![Figura 2](media/09-work-orders.png)


Nella pagina elenco **Acquisto ordine di lavoro** e nella pagina elenco **Richiesta di acquisto ordine di lavoro**, un simbolo correlato al controllo della data di consegna viene visualizzato a destra di ciascuna riga. Se il simbolo è un punto esclamativo in un cerchio rosso, la consegna dell'ordine fornitore correlato o della richiesta di acquisto può essere ritardata.

Per un ordine fornitore, la data correlata alla riga ordine fornitore viene utilizzata per calcolare un ritardo possibile. Per visualizzare la data, nella pagina **Ordine fornitore**, selezionare la riga ordine fornitore. La data viene visualizzata nel campo **Data di consegna confermata** della scheda **Impostazione** della scheda dettaglio **Dettagli riga**. Se il campo **Data di consegna confermata** non è impostato, la data nel campo **Data di consegna** della scheda dettaglio **Intestazione ordine fornitore** viene utilizzata per il calcolo. Una di quelle date viene confrontata alla data disponibile nell'ordine di lavoro o nel processo ordine di lavoro nell'ordine seguente:

1. Data di inizio effettiva nell'ordine di lavoro  

2. Data di inizio programmata nel processo di ordine di lavoro associato 

3. Data di inizio programmata nell'ordine di lavoro 

4. Data di inizio prevista nell'ordine di lavoro 

Per una richiesta di acquisto, viene utilizzata la data nel campo **Data richiesta** della scheda dettaglio **Intestazione richiesta di acquisto** della pagina **Richieste di acquisto** per calcolare il possibile ritardo. Tale data nel campo viene confrontata con la data disponibile nell'ordine di lavoro o nel processo ordine di lavoro nello stesso ordine utilizzato per un ordine fornitore.


## <a name="create-a-purchase-order-from-a-work-order"></a>Creare un ordine fornitore da un ordine cliente

Nella pagina elenco **Tutti gli ordini di lavoro**, è possibile selezionare un processo di ordine di lavoro e creare un ordine fornitore o una richiesta di acquisto correlata. In questo modo si garantisce la presenza delle relazioni di progetto tra l'ordine fornitore o la richiesta di acquisto e l'ordine di lavoro.

1. Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro per creare un ordine fornitore, quindi selezionare **Modifica**.

3. Nella Scheda dettaglio **Processi di manutenzione ordine di lavoro**, selezionare il processo di ordine di lavoro per il quale si desidera creare l'ordine fornitore.

4. Selezionare **Attività articolo** > **Ordine fornitore da processo di ordine di lavoro**.

5. Nella pagina elenco **Ordini fornitore progetto**, fare clic su **Nuovo**.

6. Crea l'ordine fornitore.

>[!NOTE]
>Per creare una richiesta di acquisto correlata, seguire la stessa procedura. Tuttavia, selezionare **Attività articolo** > **Richiesta di acquisto da processo di ordine di lavoro** al passaggio 4.


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relazione progetti tra ordine di lavoro e ordine fornitore o richiesta di acquisto

Una riga di ordine fornitore o di richiesta di acquisto è associata a un processo di ordine di lavoro tramite il progetto di ordine di lavoro e il numero di attività di progetto correlato. Quando si crea un ordine fornitore o una richiesta di acquisto da un processo di ordine di lavoro, il numero di attività di progetto correlato è obbligatorio. Se tutti i processi ordine di lavoro presenti nell'ordine di lavoro correlato hanno lo stesso tipo di processo di manutenzione, il numero di attività di progetto viene automaticamente immesso nell'ordine fornitore o nella richiesta di acquisto. Se i processi ordine di lavoro hanno tipi di processo di manutenzione diversi, è necessario immettere manualmente il numero di attività di progetto nell'ordine fornitore o nella richiesta di acquisto.

Per visualizzare o inserire il numero di attività correlato a una riga ordine fornitore, nella pagina elenco **Acquisto ordine di lavoro**, selezionare il record dell'ordine fornitore e nella colonna **Ordine fornitore** selezionare il collegamento dell'ordine fornitore. Il campo **Numero attività** è disponibile nella scheda **Progetto** della scheda dettaglio **Dettagli riga**.

Nella figura seguente è illustrato un esempio della pagina **Ordine fornitore** con lo stato attivo su **Numero attività**.

![Figura 3](media/10-work-orders.png)

Analogamente, per visualizzare o inserire il numero di attività correlato a una richiesta di ordine fornitore, nella pagina elenco **Richiesta di acquisto ordine di lavoro**, selezionare il record della richiesta di acquisto e nella colonna **Richiesta di acquisto** selezionare il collegamento della richiesta di acquisto. Il campo **Numero attività** è disponibile nella scheda **Progetto** della scheda dettaglio **Dettagli riga**.

