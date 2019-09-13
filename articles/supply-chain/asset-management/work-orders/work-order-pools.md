---
title: Pool di ordini di lavoro
description: In questo argomento viene descritto come utilizzare pool di ordini di lavoro in Gestione cespiti.
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
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875736"
---
# <a name="work-order-pools"></a>Pool di ordini di lavoro


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


È possibile utilizzare pool di ordini di lavoro per raggruppare ordini di lavoro che hanno qualcosa in comune. Ad esempio, è possibile creare pool di ordini di lavoro per

- squadra di lavoro, ad esempio, Squadra di manutenzione A, Squadra di manutenzione B  

- competenze professionali, ad esempio, elettricisti o idraulici  

- ubicazioni fisiche  

- pianificazioni temporali ad esempio, settimane o altri periodi  


Se necessario, un ordine di lavoro può essere inserito in molti pool di ordini di lavoro.


## <a name="create-work-order-pool"></a>Creare pool di ordini di lavoro

In **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**, è possibile ottenere una panoramica dei pool di ordini di lavoro e creare nuovi pool.

1. Fare clic su **Gestione cespiti** > **Comune** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**.

2. Fare clic su **Nuovo**.

3. Immettere un ID di pool di ordine di lavoro nel campo **Pool** e un nome nel campo **Nome**.

4. Impostare l'interruttore **Attivo** su "Sì" per indicare che il pool di ordini di lavoro è attivo.

5. Impostare l'interruttore **Elimina relazioni di ordini di lavoro** su "Sì" se gli ordini di lavoro devono essere rimossi automaticamente dal pool di ordini di lavoro.

6. Nel campo **Elimina stato del ciclo di vita**, selezionare lo stato del ciclo di vita di ordine di lavoro. Ad esempio, lo stato del ciclo di vita di ordine di lavoro per il completamento di un ordine di lavoro può essere impostato per eliminare automaticamente le relazioni con pool di ordini di lavoro.

7. È possibile iniziare a aggiungere ordini di lavoro al pool di ordini di lavoro utilizzato immediatamente. Nella Scheda dettaglio **Ordini di lavoro** fare clic su **Aggiungi riga**.

8. Selezionare un ordine di lavoro nel campo **Ordine di lavoro**. I campi correlati vengono aggiornati automaticamente.

9. Ripetere i passaggi da 7 a 8 per aggiungere più ordini di lavoro.

10. Nel campo **Ordinamento**, è possibile indicare se gli ordini di lavoro devono essere eseguiti in un determinato ordine. Inserire i numeri 1, 2, 3 e così via per indicare una sequenza specifica per gli ordini di lavoro selezionati.

11. Fare clic sul pulsante **Ordini di lavoro** per visualizzare un elenco di tutti gli ordini di lavoro inclusi nel pool di ordini di lavoro.

12. Fare clic sul pulsante **Carico di capacità** per aprire **Carico di capacità** in modo da calcolare e visualizzare il carico di capacità per il programma di manutenzione, gli ordini di lavoro non programmati e gli ordini di lavoro programmati.

13. Fare clic sul pulsante **Previsione articolo** per aprire **Previsione articolo** in modo da calcolare e visualizzare le previsioni per articoli (pezzi di ricambio e altri articoli necessari) correlate al programma di manutenzione, agli ordini di lavoro non programmati e agli ordini di lavoro programmati.

14. Fare clic sul pulsante **Richiesta di acquisto ordine di lavoro** per aprire l'elenco **Richiesta di acquisto ordine di lavoro** allo scopo di visualizzare un elenco delle richieste di acquisto correlate agli ordini di lavoro nel pool di ordini di lavoro.

15. Fare clic sul pulsante **Acquisto ordine di lavoro** per aprire l'elenco **Acquisto ordine di lavoro** per visualizzare un elenco di ordini di lavoro correlati agli ordini di lavoro nel pool di ordini di lavoro.

>[!NOTE]
>Quando un pool di ordini di lavoro non è più appropriato per la pianificazione del lavoro, impostare la casella di controllo **Attivo** di quel pool su "No" nella visualizzazione elenco **Pool di ordini di lavoro**.

Selezionare la casella di controllo **Elimina relazioni di ordini di lavoro** se si desidera eliminare tutte le righe di ordine di lavoro, ad esempio per creare un pool vuoto utilizzabile successivamente per altri ordini di lavoro. Deselezionare la casella di controllo **Elimina relazioni di ordini di lavoro** se si desidera utilizzare il pool di ordini di lavoro per creare nuove relazioni di ordine di lavoro in seguito.


![Figura 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a>Aggiungere un ordine di lavoro a un pool di ordini di lavoro

Come descritto nella sezione precedente, è possibile aggiungere ordini di lavoro a un pool di ordini di lavoro quando si crea il pool. È inoltre possibile aggiungere un ordine di lavoro a un pool di ordini di lavoro dall'elenco **Tutti gli ordini di lavoro**.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro nell'elenco e fare clic su **Pool di ordini di lavoro**.

3. Selezionare "Aggiungi" nel campo **Aggiungi/rimuovi**.

4. Selezionare il pool di ordini di lavoro nel campo **Pool**.

5. Fare clic su **OK**.

6. Dopo aver aggiunto un ordine di lavoro a un pool di ordini di lavoro, se si desidera inserire un ordine di lavoro in una sequenza specifica nel pool: aprire una delle pagine elenco dei pool di ordini di lavoro, selezionare il pool e fare clic su **Modifica** e modificare l'ordinamento degli ordini di lavoro inclusi nel pool nel modulo **Pool di ordini di lavoro** > Scheda dettaglio **Ordini di lavoro** > campo **Ordinamento**.

Se si intende rimuovere l'ordine di lavoro selezionato da un pool di ordini di lavoro, selezionare "Rimuovi" nel passaggio 3.

