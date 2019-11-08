---
title: Pool di ordini di lavoro
description: In questo argomento viene descritto come utilizzare pool di ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 161244cb4451ddc7b13b579fd02e828a61adeea4
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626364"
---
# <a name="work-order-pools"></a>Pool di ordini di lavoro

[!include [banner](../../includes/banner.md)]


È possibile utilizzare pool di ordini di lavoro per raggruppare ordini di lavoro che hanno qualcosa in comune. Di seguito sono riportati alcuni esempi di elementi per i quali è possibile creare i pool di ordini di lavoro:

- Squadra di lavoro, ad esempio, Squadra di manutenzione A o Squadra di manutenzione B  

- Competenze professionali, ad esempio, elettricisti o idraulici  

- Ubicazioni fisiche  

- Pianificazioni temporali ad esempio, settimane o altri periodi  

Se necessario, è possibile inserire un ordine di lavoro in più pool di ordini di lavoro.


## <a name="create-a-work-order-pool"></a>Creare un pool di ordini di lavoro

Nella pagina elenco **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**, è possibile ottenere una panoramica dei pool di ordini di lavoro e creare nuovi pool.

1. Selezionare **Gestione cespiti** > **Comune** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**.

2. Selezionare **Nuovo**.

3. Nel campo **Pool** immettere un ID per il pool di ordini di lavoro.

4. Nel campo **Nome** immettere un nome.

5. Impostare l'opzione **Attivo** su **Sì** per indicare che il pool di ordini di lavoro è attivo.

6. Impostare l'opzione **Elimina relazioni di ordini di lavoro** su **Sì** se gli ordini di lavoro devono essere rimossi automaticamente dal pool di ordini di lavoro.

7. Nel campo **Elimina stato del ciclo di vita**, selezionare lo stato del ciclo di vita di ordine di lavoro. Ad esempio, lo stato del ciclo di vita di ordine di lavoro per il completamento di un ordine di lavoro può essere impostato per eliminare automaticamente le relazioni con pool di ordini di lavoro.

    È possibile iniziare a aggiungere ordini di lavoro al pool di ordini di lavoro utilizzato immediatamente.

8. Nella Scheda dettaglio **Ordini di lavoro** selezionare **Aggiungi riga**.

9. Selezionare un ordine di lavoro nel campo **Ordine di lavoro**. I campi correlati vengono aggiornati automaticamente.

10. Ripetere i passaggi da 8 a 9 per aggiungere ulteriori ordini di lavoro.

11. Se gli ordini di lavoro aggiunti devono essere eseguiti in un ordine specifico, nel campo **Ordinamento** immettere i numeri **1**, **2**, **3** e così via per specificare l'ordine.

12. Per visualizzare un elenco di tutti gli ordini di lavoro inclusi nel pool di ordini di lavoro, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Visualizza pool di ordini di lavoro correlato**, selezionare **Ordini di lavoro** per aprire la pagina elenco **Tutti gli ordini di lavoro**.

13. Per calcolare e visualizzare il carico di capacità per la programmazione della manutenzione, gli ordini di lavoro non programmati e gli ordini di lavoro programmati, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Visualizza pool di ordini di lavoro correlato**, scegliere **Carico capacità** per aprire la finestra di dialogo **Calcola carico di capacità**.

14. Per calcolare e visualizzare le previsioni per gli articoli (parti di ricambio e altri articoli richiesti) correlati alla programmazione della manutenzione, agli ordini di lavoro non programmati e agli ordini di lavoro programmati, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Visualizza pool di ordini di lavoro correlato**, scegliere **Previsione articolo** per aprire la finestra di dialogo **Calcolare previsioni articolo**.

15. Per visualizzare un elenco di richieste di acquisto correlate agli ordini di lavoro nel pool di ordini di lavoro, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Approvvigionamento**, selezionare **Richiesta di acquisto ordine di lavoro** per aprire la pagina elenco **Richiesta di acquisto ordine di lavoro**.

16. Per visualizzare un elenco di ordini fornitore correlati agli ordini di lavoro nel pool di ordini di lavoro, nel riquadro azioni, nella scheda **Pool di ordini di lavoro**, nel gruppo **Approvvigionamento**, selezionare **Acquisto ordine di lavoro** per aprire la pagina elenco **Acquisto ordine di lavoro**.

>[!NOTE]
>Quando un pool di ordini di lavoro non è più appropriato per la pianificazione del lavoro, impostare l'opzione **Attivo** di quel pool su **No** nella pagina **Pool di ordini di lavoro**.

Per eliminare tutte le righe degli ordini di lavoro, impostare l'opzione **Elimina relazioni di ordini di lavoro** su **Sì**. Questa opzione è utile se, ad esempio, si desidera creare un pool vuoto da utilizzare in seguito per altri ordini di lavoro. Quando si è pronti per utilizzare il pool di ordini di lavoro per creare nuove relazioni di ordini di lavoro in un secondo momento, ricordare di impostare l'opzione **Elimina relazioni di ordini di lavoro** su **No**.

Nell'illustrazione seguente è illustrato un esempio della pagina elenco **Pool di ordini di lavoro**.

![Figura 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a>Aggiungere un ordine di lavoro a un pool di ordini di lavoro

Come descritto nella sezione precedente, è possibile aggiungere ordini di lavoro a un pool di ordini di lavoro quando si crea il pool. È inoltre possibile aggiungere ordini di lavoro a un pool di ordini di lavoro nella pagina elenco **Ordini di lavoro attivi** o **Tutti gli ordini di lavoro**.

1. Selezionare l'ordine di lavoro, quindi nel riquadro azioni, nella scheda **Ordine di lavoro**, nel gruppo **Gestisci**, selezionare **Pool di ordini di lavoro**.

2. Selezionare l'ordine di lavoro nell'elenco e fare clic su **Pool di ordini di lavoro**.

3. Nella finestra di dialogo **Gestisci pool di ordini di lavoro**, nel campo **Aggiungi/Rimuovi**, selezionare **Aggiungi**.

4. Selezionare il pool di ordini di lavoro nel campo **Pool**.

5. Selezionare **OK**.

6. Per inserire l'ordine di lavoro aggiunto in un ordine specifico del pool di ordini di lavoro, nella pagina elenco **Pool di ordini di lavoro attivi** o **Tutti i pool di ordini di lavoro**, selezionare il pool e **Modifica**. Quindi, nella pagina **Pool di ordini di lavoro**, nella Scheda dettaglio **Ordini di lavoro**, utilizzare il campo **Ordinamento** per modificare l'ordinamento degli ordini di lavoro inclusi nel pool.

Per rimuovere un ordine di lavoro da un pool di ordini di lavoro, ripetere questi passaggi, ma selezionare **Rimuovi** nel passaggio 3.

