---
title: Elenchi di controllo di manutenzione
description: In questo argomento vengono descritti gli elenchi di controllo di manutenzione in Gestione cespiti.
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
ms.openlocfilehash: 325ff1fa0811d6aac5189cc69f21483fce6b3e8f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875741"
---
# <a name="maintenance-checklists"></a>Elenchi di controllo di manutenzione


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Gli elenchi di controllo di manutenzione sono impostati nei tipi di processo di manutenzione e utilizzati quando si elabora un ordine di lavoro. La compilazione degli elenchi di controllo di manutenzione fa parte del completamento di un ordine di lavoro. Vedere la sezione [Categorie di tipi di processo di manutenzione e tipi di processo di manutenzione, varianti di tipi di processo di manutenzione, settori di processi di manutenzione ed elenchi di controllo di manutenzione:](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) per ulteriori informazioni su come impostare elenchi di controllo di manutenzione in tipi di processo di manutenzione nel modulo **Valori predefiniti tipo di processo di manutenzione**.

Quando si utilizzano elenchi di controllo di manutenzione in un ordine di lavoro, è possibile compilare gli elenchi di controllo di manutenzione predefiniti associati ai tipi di processo di manutenzione. È inoltre possibile aggiungere ulteriori elenchi di controllo di manutenzione.

## <a name="fill-out-a-maintenance-checklist"></a>Compilare un elenco di controllo di manutenzione

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro e fare clic su **Elenco di controllo di manutenzione**.

3. In **Elenco di controllo processo di manutenzione di ordine di lavoro** sono visualizzati gli elenchi di controllo di manutenzione per tutti i processi di ordine di lavoro. Se i processi di ordine di lavoro hanno tipi di processo di manutenzione differenti, gli elenchi di controllo di manutenzione possono essere diversi in ogni processo di ordine di lavoro. Selezionare un processo di ordine di lavoro da utilizzare con l'elenco di controllo di manutenzione correlato. I dettagli di una riga di elenco di controllo di manutenzione selezionato sono visualizzati nella Scheda dettaglio **Dettagli riga**.

4. Completare tutte le righe di elenco di controllo di manutenzione, una alla volta, nell'ordine sequenziale in cui sono visualizzate. Una riga di elenco di controllo di manutenzione di tipo "Intestazione" viene utilizzata come intestazione per raggruppare le righe di elenco di controllo di manutenzione esposte di seguito. Non è necessario completare un'intestazione, ma come per tutti i tipi di riga di elenco di controllo di manutenzione, è possibile aggiungere una **Nota** all'intestazione.

5. Se a una riga di elenco di controllo di manutenzione sono associate delle istruzioni, la casella di controllo **Istruzioni** è selezionata. Leggere le istruzioni per la riga di elenco di controllo di manutenzione selezionata nella Scheda dettaglio **Dettagli riga** > sezione **Istruzioni**.

6. Le informazioni necessarie per completare una riga di elenco di controllo di manutenzione, possono variare a seconda del tipo di elenco di controllo di manutenzione associato. Per completare una riga di elenco di controllo di manutenzione, riempire i campi nella Scheda dettaglio **Dettagli riga**. Ad esempio, in una riga di tipo "Testo", si aggiunge una **Nota** che spiega il risultato di quella riga di elenco di controllo. In una riga di tipo "Misura", si aggiunge il **Controvalore** letto sull'attrezzatura nonché una **Nota**, se necessaria.

- Dopo aver completato una riga di elenco di controllo di manutenzione, selezionare la casella di controllo **Verificata** nella riga per contrassegnarla come completata. Se si desidera eliminare una riga di elenco di controllo di manutenzione perché non pertinente per il processo di ordine di lavoro, selezionare la casella di controllo **N/A** nella riga. Se una riga di elenco di controllo di manutenzione è **Obbligatoria**, è necessario contrassegnarla come "Verificata"o "N/A".  
- È possibile aggiornare le registrazioni dell'elenco di controllo di manutenzione solo se lo stato del ciclo di vita dell'ordine di lavoro è [Attivo](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Aggiungere una riga di elenco di controllo di manutenzione

Gli elenchi di controllo di manutenzione vengono creati dalla definizione nel tipo di processo di manutenzione predefinito e trasferiti a un processo di ordine di lavoro. Se necessario, è possibile aggiungere righe di elenco di controllo di manutenzione a un processo di ordine di lavoro. Le righe di elenco di controllo di manutenzione aggiunte manualmente acquisiscono il riferimento "Manuale".

1. In **Elenco di controllo processo di manutenzione di ordine di lavoro** selezionare il processo di ordine di lavoro per il quale si desidera aggiungere un elenco di controllo di manutenzione.

2. Nella Scheda dettaglio **Righe elenco di controllo di manutenzione**, selezionare una riga di elenco di controllo di manutenzione e premere il pulsante freccia giù sulla tastiera se si desidera inserire una nuova riga dopo la riga di elenco di controllo di manutenzione selezionata. Il numero successivo nella sequenza viene inserito automaticamente nel campo **Numero riga**. È anche possibile selezionare una riga di elenco di controllo di manutenzione e fare clic sul pulsante **Aggiungi riga** se si desidera inserire una nuova riga sopra quella dell'elenco di controllo di manutenzione selezionata.

3. Nel campo **Nome** immettere un nome per la riga di elenco di controllo di manutenzione.

4. Nel campo **Tipo** selezionare un tipo per la riga di elenco di controllo di manutenzione. Per ogni tipo di elenco di controllo di manutenzione, i campi associati sono visualizzati nella Scheda dettaglio **Dettagli riga**.  
  a. "Testo" è utilizzato per aggiungere una riga di elenco di controllo di manutenzione con una descrizione di testo che indica cosa fare. Questo tipo di elenco di controllo di manutenzione può essere utilizzato se un lavoratore deve verificare o ispezionare qualcosa senza aspettarsi uno specifico risultato (misurabile). Immettere una descrizione di cosa fare nella sezione **Istruzioni** della Scheda dettaglio **Dettagli riga**. b. "Intestazione" viene utilizzato come intestazione per raggruppare le righe di elenco di controllo di manutenzione visualizzate sotto l'intestazione. Ciò è utile se sono presenti varie righe di elenco di controllo di manutenzione che possono essere suddivise in specifiche aree. Nel campo **Nome** immettere un nome descrittivo.  
  c. "Modello" non è applicabile quando si aggiunge manualmente una riga di elenco di controllo di manutenzione in un processo di ordine di lavoro.  
  d. "Variabile" viene utilizzato per definire un possibile risultato in un intervallo in una riga di elenco di controllo di manutenzione. L'impostazione delle variabili degli elenchi di controllo di manutenzione è descritta in [Categorie di tipi di processo di manutenzione e tipi di processo di manutenzione, varianti di tipi di processo di manutenzione, settori di processi di manutenzione ed elenchi di controllo di manutenzione:](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Nel campo **Nome** immettere un nome per descrivere la variabile. Selezionare la variabile nel campo **Variabile**. Immettere una descrizione di cosa fare nella sezione **Istruzioni** della Scheda dettaglio **Dettagli riga**.  
  e. "Misura" viene utilizzato per registrare una specifica misura. Nel campo **Nome** immettere un nome per la misura. Nella Scheda dettaglio **Dettagli riga**, selezionare **Contatore** e **Unità**. Immettere una descrizione di cosa fare nella sezione **Istruzioni**.  

5. Al termine dell'aggiunta manuale di righe di elenco di controllo di manutenzione, completare le righe come descritto nella sezione precedente.

>[!NOTE]
>In **Elenco di controllo processo di manutenzione di ordine di lavoro**, non è possibile eliminare righe di elenco di controllo di manutenzione il cui riferimento è "Tipo di processo". È possibile eliminare solo le righe di elenco di controllo di manutenzione il cui riferimento, creato manualmente dall'utente o da altri lavoratori. è "Manuale".


![Figura 1](media/14-work-orders.png)

