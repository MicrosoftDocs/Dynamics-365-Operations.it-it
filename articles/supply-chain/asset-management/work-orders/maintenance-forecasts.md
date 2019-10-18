---
title: Previsioni di manutenzione
description: In questo argomento vengono descritte le previsioni di manutenzione in Gestione cespiti.
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
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024501"
---
# <a name="maintenance-forecasts"></a>Previsioni di manutenzione

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Quando si crea un ordine di lavoro, si creano processi di ordine di lavoro con i relativi cespiti e tipi di processo di manutenzione. Quando si seleziona un tipo di processo di manutenzione contenente previsioni di manutenzione, queste vengono copiate automaticamente nell'ordine di lavoro.

Esiste la possibilità di aggiungere o eliminare righe di previsione, ma ciò dipende dall'impostazione dello stato del ciclo di vita di ordine di lavoro, dal tipo di progetto correlato e dalla regole di fase associate. 

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro nell'elenco e fare clic su **Previsione**. In **Previsione di manutenzione ordine di lavoro**, vengono visualizzate le righe di previsione del tipo di processo di manutenzione selezionato nel processo di ordine di lavoro.


## <a name="add-hours-forecast-to-a-work-order"></a>Aggiungere la previsione di ore a un ordine di lavoro

1. Selezionare il processo di ordine di lavoro a cui si desidera aggiungere una previsione.

2. Nella Scheda dettaglio **Ore** fare clic su **Aggiungi** per creare una nuova riga.

3. Selezionare una categoria nel campo **Categoria**.

4. Immettere il numero di ore previste nel campo **Ore**.

5. Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.


## <a name="add-items-forecast-to-a-work-order"></a>Aggiungere la previsione di articoli a un ordine di lavoro

Sono disponibili tre modi per aggiungere articoli a una previsione di manutenzione di ordine di lavoro: creando righe per articoli (pezzi di ricambio) non inclusi nell'elenco dei pezzi di ricambio o nel DBA cespiti, selezionando i pezzi di ricambio dall'elenco dei pezzi di ricambio approvato e selezionando articoli nel DBA cespiti.

1. Selezionare il processo di ordine di lavoro a cui si desidera aggiungere una previsione.

2. Selezionare la Scheda dettaglio **Articoli**.

3. Fare clic su **Aggiungi** per creare una nuova riga per un pezzo di ricambio non incluso nell'elenco dei pezzi di ricambio o nel DBA cespiti.

4. Nel campo **Numero articolo**, selezionare l'articolo.

5. Inserire la quantità nel campo **Quantità di vendita** e selezionare un'unità di quantità nel campo **Unità**.

6. Immettere la valuta e il prezzo di costo nei campi pertinenti e selezionare una **proprietà riga**.

7. Se si desidera modificare l'elenco delle dimensioni visualizzate nelle righe degli articoli, fare clic su **Inventario** > **Visualizza dimensioni**, selezionare le dimensioni e impostare l'interruttore **Salva impostazione** su "Sì".

8. Se si desidera aggiungere un pezzo di ricambio approvato alla previsione di manutenzione, fare clic su **Aggiungi pezzi di ricambio**, selezionare il pezzo di ricambio, modificare le informazioni correlate se necessario e fare clic su **OK**.

9. Se si desidera aggiungere articoli del DBA cespiti alla previsione, fare clic su **Aggiungi articoli DBA**, selezionare l'articolo, modificare le informazioni correlate se necessario e fare clic su **OK**.

10. Per ottenere una panoramica sull'utilizzo dell'articolo nella riga selezionata in Gestione cespiti in relazione a cespiti, valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro, fare clic su **Utilizzo dell'articolo**. 



## <a name="add-expense-forecast-to-a-work-order"></a>Aggiungere la previsione in spese a un ordine di lavoro

1. In questo argomento viene descritto come aggiungere una previsione di spesa a un ordine di lavoro. Nella parte sinistra del modulo, selezionare il processo di ordine di lavoro a cui si desidera aggiungere una previsione.

2. Selezionare la Scheda dettaglio **Spese**.

3. Per creare una nuova riga, fare clic su **Aggiungi**.

4. Selezionare una categoria nel campo **Categoria**.

5. Nel campo **Quantità** immettere la quantità.

6. Immettere il prezzo di costo, la valuta di vendita e il prezzo di vendita nei campi pertinenti.

7. Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.

>[!NOTE]
>Nella Scheda dettaglio **Totali previsione di manutenzione**, è possibile visualizzare una panoramica del numero di righe create in ogni scheda per il processo di ordine di lavoro selezionato e per l'ordine di lavoro. Inoltre, è possibile visualizzare una somma delle ore lavorative previste per l'ordine di lavoro e il processo di ordine di lavoro.

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Aggiornamento automatico delle previsioni dell'ordine di lavoro

In Gestione cespiti, è possibile aggiornare automaticamente qualsiasi modifica nelle previsioni degli ordini di lavoro relative ai costi delle ore, ai costi degli articoli e alle spese, che sono state aggiornate in altri moduli. Ciò garantisce l'utilizzo degli ultimi prezzi di costo nelle previsioni dell'ordine di lavoro. È inoltre possibile effettuare aggiornamenti simili per le [previsioni del tipo di processo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Fare clic su **Gestione cespiti** > **Periodico** > **Previsione** > **Aggiorna previsione ordine di lavoro**.

2. Nella finestra di dialogo a discesa **Aggiorna previsione ordine di lavoro**, è possibile aggiungere selezioni relative a specifici ordini di lavoro o processi di ordine di lavoro se necessario. Fare clic su **Filtro** per eseguire tali selezioni.

3. Se necessario, è possibile impostare l'aggiornamento automatico come processo batch nella Scheda dettaglio **Esecuzione in background**.

4. Fare clic su **OK** per avviare l'aggiornamento delle previsioni.


![Figura 2](media/07-work-orders.png)

