---
title: Visualizzare e gestire le modifiche agli indirizzi
description: Questo argomento spiega come visualizzare e gestire le modifiche agli indirizzi in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bd7180c8f53687d561c429456387e0fe999dd508
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070177"
---
# <a name="view-and-manage-address-changes"></a>Visualizzare e gestire le modifiche agli indirizzi


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento spiega come visualizzare e gestire le modifiche degli indirizzi nella pagina **Modifica dettagli personali** (che puoi aprire dall'area di lavoro **Self-service dipendenti**) o nella pagina dei dettagli del **Lavoratore** in Dynamics 365 Human Resources.

Molte organizzazioni desiderano che i dipendenti gestiscano i propri dati personali attraverso un'esperienza self-service. È possibile consentire agli utenti di aggiornare il proprio indirizzo nell'area di lavoro **Dipendente self-service**. È quindi possibile monitorare queste modifiche nell'area di lavoro **Gestione personale**. Per utilizzare questa funzione, è necessario specificare il numero di giorni in cui si desidera visualizzare le modifiche nella pagina **Parametri Human Resources**.

## <a name="configure-address-change-parameters"></a>Configurare i parametri di modifica dell'indirizzo

Per configurare il numero di giorni in cui si desidera che le modifiche dell'indirizzo appaiano nell'area di lavoro **Gestione personale**, seguire questi passaggi:

1. Nel riquadro di navigazione, selezionare **Gestione personale**.
2. Selezionare **Collegamenti**.
3. Selezionare **Parametri di Human Resources**.
4. Nel campo **Numero di giorni** in **Modifica indirizzo**, immettere il numero di giorni in cui si desidera che le modifiche dell'indirizzo appaiano nell'area di lavoro **Gestione personale**.
5. Chiudere la pagina.

## <a name="create-or-change-an-employee-address"></a>Creare o modificare l'indirizzo di un dipendente

I dipendenti possono aggiornare il proprio indirizzo nell'area di lavoro **Dipendente self-service**. Per creare o modificare un indirizzo procedere come segue:

1. Selezionare il riquadro **Dipendente self-service** nella pagina **Home**.
2. Selezionare **Modifica dettagli personali**.
3. Per aggiungere un indirizzo selezionare **Aggiungi**. Per aggiornare un indirizzo esistente, selezionare l'indirizzo dall'elenco, quindi selezionare **Modifica**.
4. Immettere il **nome o la descrizione**.
5. Selezionare la casella a discesa **Scopo**, quindi il tipo di indirizzo.
6. Immettere il **Paese**.
7. Immettere il **Codice postale**.
8. Immettere la **Via**.
9. Immettere la **Città**, lo **Stato** e il **Paese**. In genere, questi campi vengono impostati automaticamente in base al campo **Codice postale**.
10. Facoltativamente, selezionare il campo **Primario** per indicare un indirizzo principale. È possibile contrassegnare un solo indirizzo come principale. Se un altro indirizzo è già contrassegnato come indirizzo principale, sarà necessario confermare che si desidera utilizzare questo indirizzo come principale.
11. Facoltativamente, selezionare il campo **Privato** per indicare che l'indirizzo è privato. Solo gli utenti con autorizzazione esplicita a visualizzare le informazioni sull'indirizzo privato possono visualizzare questo indirizzo.
12. Selezionare **OK**.

## <a name="create-or-change-a-worker-address"></a>Creare o modificare un indirizzo lavoratore

È possibile aggiornare un indirizzo nell'area di lavoro **Gestione personale**. Per creare o modificare un indirizzo procedere come segue:

1. Nell'area di lavoro **Gestione personale**, selezionare **Collegamenti**, quindi selezionare **Lavoratori**.
2. Selezionare il lavoratore, quindi **Indirizzi**.
3. Per aggiungere un indirizzo selezionare **Aggiungi**. Per aggiornare un indirizzo esistente, selezionare l'indirizzo dall'elenco, quindi selezionare **Modifica**.
4. Immettere il **nome o la descrizione**.
5. Selezionare la casella a discesa **Scopo**, quindi il tipo di indirizzo.
6. Immettere il **Paese**.
7. Immettere il **Codice postale**.
8. Immettere la **Via**.
9. Immettere la **Città**, lo **Stato** e il **Paese**. In genere, questi campi vengono impostati automaticamente in base al campo **Codice postale**.
10. Facoltativamente, selezionare il campo **Primario** per indicare un indirizzo principale. È possibile contrassegnare un solo indirizzo come principale. Se un altro indirizzo è già contrassegnato come indirizzo principale, sarà necessario confermare che si desidera utilizzare questo indirizzo come principale.
11. Facoltativamente, selezionare il campo **Privato** per indicare che l'indirizzo è privato. Solo gli utenti con autorizzazione esplicita a visualizzare le informazioni sull'indirizzo privato possono visualizzare questo indirizzo.
12. Selezionare **OK**.
 
## <a name="create-a-future-change-for-an-address"></a>Creare una modifica futura per un indirizzo

In alcuni casi, potresti voler aggiornare un indirizzo per modificarlo in futuro. Ad esempio, questo sarebbe utile se un dipendente si trasferisse il 15 del mese successivo.

1. Aprire la pagina **Gestisci indirizzi** selezionando **Altre opzioni > Avanzate** da qualsiasi griglia di indirizzi.
2. Selezionare **Nuovo** per creare un nuovo indirizzo.
3. Immettere i dettagli dell'indirizzo.
4. Selezionare la scheda **Generale**.
5. Nel campo **Data effettiva** selezionare la data di entrata in vigore del nuovo indirizzo.
6. Nel campo **Data di scadenza** selezionare facoltativamente la data in cui l'indirizzo non sarà più valido.
7. Chiudere le pagine.

## <a name="view-and-monitor-address-changes"></a>Visualizzare e monitorare le modifiche agli indirizzi

Il personale delle risorse umane può visualizzare e monitorare le modifiche agli indirizzi dall'area di lavoro **Gestione personale**. Per visualizzare le modifiche degli indirizzi, selezionare il riquadro **Gestione personale** nella pagina **Home**. Le modifiche degli indirizzi vengono visualizzate su un riquadro nell'angolo in alto a destra. Il numero sopra **Modifiche indirizzi** mostra quante modifiche agli indirizzi si sono verificate nel numero di giorni specificato nella pagina **Parametri di Human Resources**. 

Quando si seleziona il riquadro **Modifiche agli indirizzi**, una nuova pagina mostra i dettagli di eventuali modifiche agli indirizzi. Se lo si desidera, è possibile selezionare **Includi future modifiche agli indirizzi** nell'angolo in alto a destra per visualizzare le modifiche agli indirizzi con una data futura.

> [!NOTE]
> Se si desidera ricevere un avviso o un'e-mail su queste modifiche agli indirizzi, è possibile creare una nuova regola di avviso nella scheda **Opzioni** del riquadro azioni. Per ulteriori informazioni sulle regole di avviso, vedere [Creare regole di avviso](../fin-ops-core/fin-ops/get-started/create-alerts.md).
>
> Se si desidera configurare un flusso di lavoro per le modifiche agli indirizzi, è possibile selezionare l'opzione **Invia esternamente** nella regola di avviso, quindi utilizzare Power Automate per attivare l'evento aziendale e configurare un flusso di lavoro. Per ulteriori informazioni, vedere [Avvisi come eventi aziendali](../fin-ops-core/fin-ops/get-started/create-alerts.md#alerts-as-business-events).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
