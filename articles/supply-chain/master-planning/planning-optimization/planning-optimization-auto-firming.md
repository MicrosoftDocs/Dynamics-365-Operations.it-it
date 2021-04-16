---
title: Stabilizzazione automatica con Ottimizzazione pianificazione
description: In questo argomento viene illustrato come utilizzare la stabilizzazione automatica con l'ottimizzazione di pianificazione.
author: ChristianRytt
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 3542e343de29c9fd9d19ed99cab4b4eebacd2899
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813005"
---
# <a name="autofirming-with-planning-optimization"></a>Stabilizzazione automatica con Ottimizzazione pianificazione

[!include [banner](../../includes/banner.md)]

La stabilizzazione automatica consente di stabilizzare ovvero rilasciare gli ordini pianificati nel processo di pianificazione generale. Quando gli ordini pianificati vengono stabilizzati, vengono trasformati negli ordini fornitore, di trasferimento o di produzione effettivi. Quando l'ottimizzazione di progettazione viene utilizzata, gli ordini pianificati vengono stabilizzati durante l'esecuzione di una pianificazione generale quando la data dell'ordine ovvero la data di inizio rientra nell'intervallo temporale specificato per la stabilizzazione.

> [!NOTE]
> La stabilizzazione automatica di un ordine fornitore pianificato può avvenire solo se l'articolo è associato a un fornitore.
> 
> Gli ordini derivati consolidati (ordini fornitore in conto lavoro) mostreranno lo stato di *In revisione* quando è abilitato il rilevamento delle modifiche al caso.

## <a name="turn-on-autofirming"></a>Attivare la stabilizzazione automatica

Per attivare la stabilizzazione automatica, effettuare le seguenti operazioni.

1. Nell'area di lavoro **Gestione funzionalità**, scheda **Nuovo**, selezionare **Stabilizzazione automatica per l'ottimizzazione di pianificazione** nell'elenco. Se la funzionalità non è presente nella scheda **Nuovo**, considerare le schede **Tutto** e **Non abilitato**.
1. Selezionare **Abilita ora**. In alternativa, selezionare **Programmazione** e quindi selezionare l'ora in cui si desidera che la funzionalità sia abilitata.

## <a name="set-up-the-firming-time-fence"></a>Impostare l'intervallo temporale della stabilizzazione

L'intervallo temporale di stabilizzazione viene calcolato in avanti a partire dalla data di esecuzione della pianificazione generale. È definito dal numero di giorni immessi. È possibile controllare l'intervallo temporale nei seguenti modi:

- Per definire l'intervallo temporale predefinito per la stabilizzazione di un gruppo di copertura, andare a **Pianificazione generale** \> **Impostazione** \> **Copertura** \> **Gruppi di copertura** e selezionare un gruppo di copertura. Quindi, nella Scheda dettaglio **Altro**, nel campo **Intervallo temporale di stabilizzazione automatica (giorni)**, immettere il numero di giorni.
- Per sovrascrivere l'intervallo temporale per la stabilizzazione definito per il gruppo di copertura per un articolo specifico, vai a **Gestione informazioni sul prodotto** \> **Prodotti rilasciati**, quindi nel riquadro azioni **Piano** seleziona **Copertura articoli**. Nella scheda **Generale**, selezionare **Ignora intervalli temporali** e nel campo **Intervallo temporale di stabilizzazione automatico (giorni)**, immettere il numero di giorni.
- Per sovrascrivere l'intervallo temporale per la stabilizzazione definito per il gruppo di copertura e la copertura articoli per un piano generale specifico, andare a **Pianificazione generale** \> **Impostazione** \> **Piani generali** e selezionare un piano generale. Quindi, nella Scheda dettaglio **Intervallo temporale in giorni**, impostare **Stabilizzazione** su **Sì** e immettere il numero di giorni.

Se la stabilizzazione automatica è attivata per l'esecuzione di una pianificazione generale che utilizza l'ottimizzazione di pianificazione, il processo di stabilizzazione automatica viene eseguito in base all'impostazione di stabilizzazione automatica. Se la stabilizzazione automatica non è attivata o se la pianificazione viene avviata dalla pagina **Fabbisogno netto**, il processo di stabilizzazione automatica verrà ignorato.

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a>Ottimizzazione di pianificazione rispetto al motore di pianificazione integrato di Supply Chain Management

Sia l'ottimizzazione di pianificazione che il motore di pianificazione integrato in Microsoft Dynamics 365 Supply Chain Management possono essere utilizzati per stabilizzare automaticamente gli ordini pianificati. Tuttavia, esistono delle differenze importanti. Ad esempio, mentre l'ottimizzazione di pianificazione utilizza la data dell'ordine (ovvero la data di inizio) per determinare quali ordini pianificati devono essere consolidati, il motore di pianificazione integrato di Supply Chain Management utilizza la data del fabbisogno (ovvero la data di fine). Di seguito è riportato un riepilogo delle differenze.

**Ottimizzazione pianificazione**

- La stabilizzazione automatica si basa sulla data dell'ordine (data di inizio).
- Poiché la data dell'ordine (data di inizio) attiva la stabilizzazione, non è necessario considerare i lead time come parte dell'intervallo temporale per la stabilizzazione.
- Se si desidera stabilizzare tutti gli ordini che devono iniziare nella settimana corrente, l'intervallo temporale per la stabilizzazione deve essere di una settimana.

**Motore di pianificazione integrato di Supply Chain Management**

- La stabilizzazione automatica si basa sulla data del fabbisogno (data di fine).
- Per garantire che gli ordini vengano stabilizzati in tempo utile, l'intervallo temporale per la stabilizzazione deve essere più lungo del lead time.
- Se si desidera stabilizzare tutti gli ordini che devono iniziare nella settimana corrente, l'intervallo temporale per la stabilizzazione deve essere il lead time più una settimana.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
