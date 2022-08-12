---
title: Previsioni di manutenzione
description: In questo articolo vengono descritte le previsioni di manutenzione in Gestione cespiti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4e3da8ab9a739c8455d2c1d2720f94f91a42927d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111602"
---
# <a name="maintenance-forecasts"></a>Previsioni di manutenzione

[!include [banner](../../includes/banner.md)]



Quando si crea un ordine di lavoro, si creano processi di ordine di lavoro con i relativi cespiti e tipi di processo di manutenzione. Quando si seleziona un tipo di processo di manutenzione contenente previsioni di manutenzione, queste vengono copiate automaticamente nell'ordine di lavoro.

È possibile aggiungere righe di previsione a un ordine di lavoro o cancellarle da un ordine di lavoro. L'impostazione dello stato del ciclo di vita dell'ordine di lavoro, il tipo di progetto correlato e le regole della fase correlate al tipo di progetto determinano se è possibile aggiungere o modificare le righe di previsione. Per ulteriori informazioni sugli stati del ciclo di vita di ordine di lavoro e sulle fasi di progetto correlate, vedere [Previsioni, ordini di lavoro e progetti](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

1. Seleziona **Gestione cespiti** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro nell'elenco, quindi nel riquadro azioni > nella scheda **Ordine di lavoro** > nel gruppo **Progetto**, selezionare **Previsione**. Nella pagina **Previsione di manutenzione ordine di lavoro** vengono visualizzate le righe di previsione del tipo di processo di manutenzione selezionato nel processo di ordine di lavoro.


## <a name="add-an-hours-forecast-to-a-work-order"></a>Aggiungere una previsione di ore a un ordine di lavoro

1. Nella pagina **Previsioni di manutenzione dell'ordine di lavoro**, selezionare il processo ordine di lavoro a cui aggiungere una previsione.

2. Nella Scheda dettaglio **Ore** selezionare **Aggiungi** per creare una nuova riga.

3. Selezionare una categoria nel campo **Categoria**.

4. Immettere il numero di ore previste nel campo **Ore**.

5. Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.


## <a name="add-an-items-forecast-to-a-work-order"></a>Aggiungere una previsione di articoli a un ordine di lavoro

Sono disponibili tre modi per aggiungere articoli a una previsione di manutenzione di ordine di lavoro. È possibile righe per articoli (pezzi di ricambio) che non sono inclusi nell'elenco dei pezzi di ricambio o nel DBA cespiti, selezionare i pezzi di ricambio dall'elenco dei pezzi di ricambio approvato e selezionare articoli nel DBA cespiti.

- Nella pagina **Previsioni di manutenzione dell'ordine di lavoro**, selezionare il processo ordine di lavoro a cui aggiungere una previsione.

- Nella scheda dettaglio **Articoli**, aggiungere gli articoli alla previsione di manutenzione utilizzando il metodo appropriato.

Per creare una riga per un pezzo di ricambio non incluso nell'elenco dei pezzi di ricambio o nel DBA cespiti, effettuare i seguenti passaggi:

1. Selezionare **Aggiungi**.
2. Nel campo **Numero articolo**, selezionare l'articolo.
3. Nel campo **Quantità di vendita** immettere la quantità.
4. Nel campo **Unità** selezionare l'unità di misura per la quantità.
5. Nei campi **Prezzo di costo** e **Valuta** immettere i valori appropriati.
6. Nel campo **Proprietà riga**, selezionare una proprietà riga.
7. Per modificare l'elenco delle dimensioni visualizzate nelle righe degli articoli, selezionare **Inventario** > **Visualizza dimensioni**, selezionare le dimensioni e impostare l'opzione **Salva impostazione** su **Sì**.

Per aggiungere un pezzo di ricambio da un elenco di pezzi di ricambio approvato, effettuare le operazioni seguenti:

1. Selezionare **Aggiungi pezzi di ricambio**.
2. Selezionare il pezzo di ricambio e modificare le informazioni secondo le necessità.
3. Selezionare **OK**.

Per aggiungere un articolo dal DBA cespiti, effettuare le seguenti operazioni:

1. Selezionare **Aggiungi articoli DBA**.
2. Selezionare l'articolo e modificare le informazioni secondo le necessità.
3. Selezionare **OK**.

Per ottenere una panoramica di dove l'articolo viene utilizzato nella riga selezionata in relazione ai cespiti, ai valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro, selezionare **Utilizzo dell'articolo**. Per ulteriori informazioni su questa panoramica, vedere [Utilizzo dell'articolo](../controlling-and-reporting/item-where-used.md).


## <a name="add-an-expense-forecast-to-a-work-order"></a>Aggiungere una previsione di spesa a un ordine di lavoro

1. Nella pagina **Previsioni di manutenzione dell'ordine di lavoro**, selezionare il processo ordine di lavoro a cui aggiungere una previsione.

2. Nella Scheda dettaglio **Spesa** selezionare **Aggiungi** per creare una riga.

3. Selezionare una categoria nel campo **Categoria**.

4. Nel campo **Quantità** immettere la quantità.

5. Nei campi **Prezzo di costo**, **Valuta di vendita** e **Prezzo di vendita**, immettere i valori appropriati.

6. Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.

>[!NOTE]
>La Scheda dettaglio **Totali previsione di manutenzione** mostra una panoramica del numero di righe create per il processo di ordine di lavoro selezionato e per l'ordine di lavoro in ogni scheda dettaglio. Mostra inoltre il totale delle ore lavorative previste per l'ordine di lavoro e il processo di ordine di lavoro.

Nell'illustrazione seguente è illustrato un esempio della pagina **Previsioni di manutenzione dell'ordine di lavoro**.

![Figura 1.](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Aggiornamento automatico delle previsioni dell'ordine di lavoro

Se i costi delle ore, i costi degli articoli e le spese vengono aggiornati in altri moduli, le previsioni sugli ordini di lavoro in Gestione cespiti possono essere aggiornate automaticamente per riflettere tali modifiche. Questa funzionalità garantisce l'utilizzo degli ultimi prezzi di costo nelle previsioni dell'ordine di lavoro. È inoltre possibile apportare aggiornamenti simili per le [previsioni del tipo di processo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Selezionare **Gestione cespiti** > **Periodico** > **Previsione** > **Aggiorna previsione ordine di lavoro**.

2. Nella finestra di dialogo **Aggiorna previsione ordine di lavoro**, nella scheda dettaglio **Record da includere**, è possibile aggiungere selezioni relative a specifici ordini di lavoro o processi di ordine di lavoro secondo le necessità. Fare clic su **Filtro** per effettuare la selezione delle opzioni rilevanti.

3. Nella Scheda dettaglio **Esecuzione in background**, è possibile impostare l'aggiornamento automatico come processo batch, come necessario.

4. Selezionare **OK** per avviare l'aggiornamento delle previsioni.


Nella figura seguente è illustrato un esempio della finestra di dialogo **Aggiorna previsione ordine di lavoro**.

![Figura 2.](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
