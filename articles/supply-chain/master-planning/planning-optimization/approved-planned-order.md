---
title: Approva ordini pianificati
description: Questo argomento descrive l'approvazione degli ordini pianificati supportati in Ottimizzazione pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 8745a461986c1f16f2b3f9fd23011701d104a30c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264020"
---
# <a name="approve-planned-orders"></a>Approva ordini pianificati

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce informazioni su come aggiornare lo stato degli ordini pianificati in Ottimizzazione pianificazione.

L'approvazione degli ordini pianificati è un passaggio facoltativo, nel percorso per creare un ordine stabilizzato da un ordine pianificato. Si consiglia di approvare gli ordini pianificati modificati, altrimenti le modifiche verranno ignorate e sovrascritte dalla successiva esecuzione della pianificazione.

![Flusso dell'ordine pianificato](media/approved-planned-orders-1.png)

Il campo **Stato** aiuta a tracciare l'avanzamento utilizzando i seguenti valori:

- **Inevaso:** Agli ordini pianificati generati mediante la pianificazione generale viene assegnato uno stato di *Inevaso*. Gli ordini pianificati con questo stato verranno eliminati durante la successiva esecuzione della pianificazione.
- **Completato:** se si decide di non stabilizzare un ordine pianificato, è possibile modificare lo stato in *Completato* per indicare che la valutazione di questo ordine pianificato è stata completata. Notare che gli stati *Inevaso* e *Completato* sono trattati allo stesso modo dal sistema.
- **Approvato:** se si desidera mantenere le modifiche o si prevede di confermare un ordine pianificato, modificare lo stato in *Approvato*. Gli ordini pianificati con stato *Approvato* vengono considerati come fornitura fissa e prevista dalla pianificazione generale, non vengono modificati né eliminati durante le esecuzioni di pianificazione generale successive. Per raggiungere questo obiettivo, la logica di pianificazione copia gli ordini pianificati con stato *Approvato* dalla vecchia versione del piano alla nuova versione del piano durante la pianificazione generale. Notare che gli ordini pianificati *approvati* sono considerati fornitura solo all'interno del piano generale specifico.

È possibile gestire gli ordini pianificati nell'area di lavoro **Pianificazione generale**, nell'elenco **Ordine pianificato** o negli elenchi **Ordini di produzione pianificati**, **Ordini fornitore pianificati** e **Trasferimento pianificato**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]