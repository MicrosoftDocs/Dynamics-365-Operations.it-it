---
title: Visualizzare, gestire e approvare gli ordini pianificati
description: Questo articolo fornisce informazioni su come visualizzare, gestire e approvare gli ordini pianificati.
author: t-benebo
ms.date: 04/07/2021
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
ms.author: benebotg
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: a4c3b6c2dd149d3fedf1dc3dc418541961ad1a73
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740960"
---
# <a name="view-manage-and-approve-planned-orders"></a>Visualizzare, gestire e approvare gli ordini pianificati

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce informazioni su come visualizzare, gestire e approvare gli ordini pianificati.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>Visualizzare e gestire gli ordini pianificati

È possibile visualizzare e gestire gli ordini pianificati in qualsiasi pagina elenco di ordini pianificati. Vai in una delle seguenti posizioni, a seconda del tipo di ordini pianificati con cui desideri lavorare:

- Pianificazione generale \> Aree di lavoro \> Pianificazione generale
- Pianificazione generale \> Pianificazione generale \> Ordini pianificati
- Controllo produzione \> Ordini di produzione \> Tutti gli ordini pianificati
- Approvvigionamento \> Ordini fornitore \> Tutti gli ordini pianificati.
- Gestione articoli \> Ordini in entrata \> Trasferimenti pianificati
- Gestione articoli \> Ordini in uscita \> Trasferimenti pianificati

## <a name="view-and-edit-the-status-of-planned-orders"></a>Visualizzare e modificare lo stato degli ordini pianificati

Puoi usare il campo **Stato** di ogni ordine pianificato per monitorare i tuoi progressi o modificare il modo in cui verrà elaborato un ordine pianificato. Sono disponibili i seguenti valori di **Stato**:

- **Inevaso** - Agli ordini pianificati generati mediante la pianificazione generale viene assegnato questo stato. Gli ordini pianificati con questo stato verranno eliminati durante la successiva esecuzione della pianificazione.
- **Completato** - Questo stato indica che l'ordine pianificato è stato completato. A un ordine pianificato che si sceglie di non stabilizzare è possibile cambiare manualmente lo stato in *Completato*. Notare che gli stati *Inevaso* e *Completato* sono trattati allo stesso modo dal sistema.
- **Approvato** - Questo stato indica che l'ordine pianificato è approvato per la stabilizzazione. Se si desidera stabilizzare un ordine pianificato, è possibile modificarne lo stato in *Approvato*. Se si desidera mantenere le modifiche apportate a un ordine pianificato o se si prevede di stabilizzare un ordine pianificato, modificarne lo stato in *Approvato*. Ordini pianificati con stato *Approvato* sono considerati come fornitura fissa e prevista dalla pianificazione generale. Pertanto, non vengono modificati o eliminati durante le successive esecuzioni della pianificazione generale. Per ottenere questo comportamento, la logica di pianificazione copia gli ordini pianificati con stato *Approvato* dalla vecchia versione del piano alla nuova versione del piano durante la pianificazione generale. Nota che gli ordini pianificati con stato *Approvato* sono considerati fornitura solo all'interno del piano generale specifico.

Per modificare lo stato di un singolo ordine pianificato, [aprire qualsiasi pagina elenco degli ordini pianificati](#view-planned-orders), aprire l'ordine e quindi seguire uno di questi passaggi:

- Nella Scheda dettaglio **Generale**, modificare il valore del campo **Stato**.
- Nel riquadro Azioni, nella scheda **Ordine pianificato**, nel gruppo **Processo** selezionare **Cambia stato**.
- Per contrassegnare l'ordine come approvato, nel riquadro Azioni, selezionare **Approva**.

Per modificare lo stato di più ordini pianificati contemporaneamente, [aprire qualsiasi pagina elenco degli ordini pianificati](#view-planned-orders), selezionare la casella di controllo per ogni ordine che desideri modificare, quindi seguire uno di questi passaggi:

- Nel riquadro Azioni, nella scheda **Ordine pianificato**, nel gruppo **Processo** selezionare **Cambia stato**.
- Per contrassegnare gli ordini come approvati, nel riquadro Azioni, selezionare **Approva**.

## <a name="approve-planned-orders"></a>Approva ordini pianificati

L'approvazione degli ordini pianificati è un passaggio facoltativo nel processo per creare un ordine stabilizzato da un ordine pianificato.

La figura seguente mostra come utilizzare il valore **Stato** assegnato a ciascun ordine pianificato per implementare un flusso di lavoro di approvazione. Per implementare un processo di approvazione, modificare manualmente il valore **Stato** per ogni ordine pianificato come descritto nella sezione precedente.

![Flusso dell'ordine pianificato.](media/approved-planned-orders-1.png)

> [!TIP]
> Si consiglia di approvare gli ordini pianificati modificati. In caso contrario, le modifiche verranno ignorate e sovrascritte dalla successiva esecuzione della pianificazione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Stabilizza ordini pianificati](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
