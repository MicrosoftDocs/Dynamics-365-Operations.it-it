---
title: Elenchi di controllo di manutenzione
description: In questo argomento vengono descritti gli elenchi di controllo di manutenzione in Gestione cespiti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 135887e4ca8dfc6cae9aa73b316815ed3a7041a9
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347094"
---
# <a name="maintenance-checklists"></a>Elenchi di controllo di manutenzione

[!include [banner](../../includes/banner.md)]



Gli elenchi di controllo di manutenzione sono impostati nei tipi di processo di manutenzione. La compilazione degli elenchi di controllo di manutenzione fa parte del processo di completamento di un ordine di lavoro. Vedere [Categorie di tipi di processo di manutenzione e tipi di processo di manutenzione, varianti di tipi di processo di manutenzione, settori di processi di manutenzione ed elenchi di controllo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) per ulteriori informazioni su come impostare elenchi di controllo di manutenzione in tipi di processo di manutenzione nella pagina **Valori predefiniti tipo di processo di manutenzione**.

Quando si utilizzano elenchi di controllo di manutenzione in un ordine di lavoro, è possibile compilare gli elenchi di controllo di manutenzione predefiniti associati ai tipi di processo di manutenzione. È inoltre possibile aggiungere più elenchi di controllo di manutenzione.


## <a name="fill-in-a-maintenance-checklist"></a>Compilare un elenco di controllo di manutenzione

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro, quindi nel riquadro azioni, nella scheda **Ordine di lavoro**, nel gruppo **Righe**, selezionare **Elenco di controllo di manutenzione**.

3. In **Elenco di controllo processo di manutenzione di ordine di lavoro** sono visualizzati gli elenchi di controllo per tutti i processi di ordine di lavoro. Se i processi di ordine di lavoro hanno tipi di processo di manutenzione differenti, gli elenchi di controllo di manutenzione possono essere diversi in ogni processo di ordine di lavoro. Selezionare un processo di ordine di lavoro da utilizzare con l'elenco di controllo di manutenzione correlato. I dettagli della riga di elenco di controllo di manutenzione selezionato sono visualizzati nella Scheda dettaglio **Dettagli riga**.

4. Completare tutte le righe di elenco di controllo di manutenzione, una alla volta, nell'ordine in cui sono visualizzate. Per completare una riga di elenco di controllo di manutenzione, riempire i campi nella Scheda dettaglio **Dettagli riga**. Le informazioni necessarie per completare una riga possono variare, a seconda del tipo di riga. Ad esempio, in una riga di tipo **Testo**, si aggiunge una nota che spiega il risultato del controllo. In una riga di tipo **Misura**, si aggiunge il controvalore letto sull'attrezzatura nonché una nota, secondo le necessità. Una riga di elenco di controllo di manutenzione di tipo **Intestazione** viene utilizzata come intestazione per raggruppare le righe di elenco di controllo di manutenzione esposte di seguito. Non è necessario compilare un'intestazione. Come per tutti gli altri tipi di righe dell'elenco di controllo della manutenzione, è possibile aggiungere una nota a una riga di tipo **Intestazione**.

5. Se a una riga di elenco di controllo di manutenzione sono associate delle istruzioni, la casella di controllo **Istruzioni** è selezionata. Leggere le istruzioni per la riga di elenco di controllo di manutenzione selezionata nel campo **Istruzioni** della Scheda dettaglio **Dettagli riga**.

6. Dopo aver completato una riga di elenco di controllo di manutenzione, selezionare la casella di controllo **Verificata** nella riga per contrassegnarla come completata. Per eliminare una riga di elenco di controllo di manutenzione perché non pertinente per il processo di ordine di lavoro, selezionare la casella di controllo **N/D** nella riga. Se la casella di controllo **Obbligatorio** è selezionata in una riga dell'elenco di controllo di manutenzione, è necessario selezionare la casella di controllo **Contrassegnata** o **N/D**.

>[!NOTE]
>È possibile aggiornare le registrazioni dell'elenco di controllo di manutenzione solo se lo stato del ciclo di vita dell'ordine di lavoro è [Attivo](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Aggiungere una riga di elenco di controllo di manutenzione

Gli elenchi di controllo di manutenzione vengono creati dalla definizione nel tipo di processo di manutenzione predefinito e trasferiti a un processo di ordine di lavoro. Se necessario, è possibile aggiungere righe di elenco di controllo di manutenzione a un processo di ordine di lavoro. Le righe dell'elenco di controllo di manutenzione aggiunte manualmente acquisiscono il riferimento **Manuale**.

1. Nella pagina **Elenco di controllo processo di manutenzione di ordine di lavoro** selezionare il processo di ordine di lavoro per il quale si desidera aggiungere un elenco di controllo di manutenzione.

2. Nella Scheda dettaglio **Righe elenco di controllo di manutenzione**, selezionare una riga di elenco di controllo di manutenzione. Quindi, inserire una nuova riga dopo la riga selezionata, premere il tasto **freccia GIÙ**. Il numero successivo nella sequenza viene immesso automaticamente nel campo **Numero riga**. Per inserire una nuova riga prima della riga selezionata, selezionare **Aggiungi riga**. 

3. Nel campo **Nome** immettere un nome per la riga di elenco di controllo di manutenzione.

4. Nel campo **Tipo** selezionare un tipo per la riga di elenco di controllo di manutenzione. Per ogni tipo di elenco di controllo di manutenzione, i campi associati sono visualizzati nella Scheda dettaglio **Dettagli riga**.
    - **Testo** - Utilizzare questo tipo per aggiungere una riga dell'elenco di controllo di manutenzione con un testo che descriva l'operazione da eseguire. Ad esempio, è possibile utilizzare questo tipo se si desidera che un lavoratore controlli o verifichi qualcosa, senza attendere un risultato specifico (misurabile). Dopo aver selezionato il tipo, nella scheda dettaglio **Dettagli righe**, nel campo **Istruzioni**, immettere il testo che descrive le operazioni da eseguire.
    - **Intestazione** - Una riga di elenco di controllo di manutenzione di questo tipo viene utilizzata come intestazione per raggruppare le righe di elenco di controllo di manutenzione esposte di seguito. Questo tipo è utile se sono presenti varie righe di elenco di controllo di manutenzione che possono essere suddivise in specifiche aree. Dopo aver selezionato questo tipo, immettere un nome descrittivo nel campo **Nome**.
    - **Modello** - Questo tipo non è applicabile quando si aggiunge manualmente una riga di elenco di controllo di manutenzione in un processo di ordine di lavoro.  
    - **Variabile** - Utilizzare questo tipo per definire un possibile risultato in un intervallo in una riga di elenco di controllo di manutenzione. Per informazioni sull'impostazione delle variabili degli elenchi di controllo di manutenzione, vedere [Categorie di tipi di processi di manutenzione e tipi di processi di manutenzione, varianti di tipo di processi di manutenzione, commerci di processi di manutenzione e ed elenchi di controllo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Dopo aver selezionato questo tipo, immettere un nome descrittivo per la variabile nel campo **Nome**. Nella scheda dettaglio **Dettagli riga**, nel campo **Variabile**, selezionare la variabile. Nel campo **Istruzioni**, immettere una descrizione dell'operazione da eseguire.
    - **Misura** - Utilizzare questo tipo per registrare una misura specifica nella riga dell'elenco di controllo di manutenzione. Dopo aver selezionato questo tipo, immettere un nome per la misura nel campo **Nome**. Nella scheda dettaglio **Dettagli riga**, nei campi **Unità** e **Contatore**, selezionare i valori appropriati. Nel campo **Istruzioni**, immettere una descrizione dell'operazione da eseguire.

5. Una volta aggiunte manualmente tutte le righe dell'elenco di controllo di manutenzione, completare le righe come descritto nella sezione **Compilare un elenco di controllo di manutenzione** precedente.

>[!NOTE]
>Nella pagina **Elenco di controllo processo di manutenzione di ordine di lavoro**, non è possibile eliminare righe di elenco di controllo di manutenzione il cui riferimento è **Tipo di processo**. È possibile eliminare solo le righe di elenco di controllo di manutenzione create manualmente il cui riferimento è **Manuale**.

Nella figura seguente viene illustrato un esempio di elenco di controllo di manutenzione.

![Figura 1.](media/14-work-orders.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]