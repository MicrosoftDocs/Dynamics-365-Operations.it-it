---
title: Panoramica dei contratti di assistenza
description: Nel contratto di servizio, il cliente accetta un tempo minimo di risposta basato sulla data in cui la società di servizi registra l'uscita e quando il problema viene risolto.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01cdfe519e55ca2a9aa17f4ac181ee675b2793cf
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431235"
---
# <a name="service-level-agreements-overview"></a>Panoramica dei contratti di assistenza       

[!include [banner](../includes/banner.md)]


Un contratto di servizio (SLA) è un contratto tra una società di servizi e un cliente di servizio. Nel contratto di servizio, il cliente accetta un tempo minimo di risposta basato sulla data in cui la società di servizi registra l'uscita e quando il problema viene risolto.

Un accordo di questo tipo offre un livello di servizio fornito ai clienti in modo standardizzato e risulta utile perché consente alla società di determinare con precisione la data entro la quale deve essere completato un lavoro.

Per offrire ai clienti diversi livelli di servizio, è possibile creare più accordi.

## <a name="create-a-service-level-agreement"></a>Creare un accordo sui livelli di servizio

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Contratti di assistenza** \> **Accordi sui livelli di servizio**.

2.  Nel campo **Accordo sui livelli di servizio** selezionare un accordo sui livelli di servizio da associare al nuovo contratto di assistenza.

3.  Immettere il tempo che si desidera consentire per il completamento delle chiamate di assistenza collegate al contratto di servizio. Selezionare un calendario se si desidera basare il contratto di assistenza su un calendario specifico.

## <a name="apply-a-service-level-agreement"></a>Applicare un accordo sui livelli di servizio

L'accordo sui livelli di servizi viene applicato direttamente a un contratto di assistenza.

Gli ordini di assistenza creati manualmente e collegati a un contratto di assistenza associato a un accordo sui livelli di servizio vengono valutati in base all'accordo.

Gli ordini di assistenza creati automaticamente non vengono collegati a un accordo sui livelli di servizio.

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>Applicare l'accordo sui livelli di servizio al contratto di assistenza

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**. Selezionare il contratto di assistenza in cui si desidera applicare il contratto di assistenza e fare clic su **Modifica** nel **riquadro azioni**.

2.  Nel campo **Accordo sui livelli di servizio**, selezionare il contratto di servizio da assegnare.

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>Applicare l'accordo sui livelli di servizio al gruppo dei contratti di assistenza

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Contratti di assistenza** \> **Gruppi contratti di assistenza**.

2.  Nel campo **Accordo sui livelli di servizio**, selezionare il contratto di servizio da assegnare.

## <a name="track-time-on-a-service-order-against-an-sla"></a>Tenere traccia del tempo in un ordine di assistenza in base a un accordo sui livelli di servizio

Quando si crea un nuovo ordine di assistenza per un contratto di assistenza a cui è assegnato il contratto di assistenza, l'intervallo di tempo per la consegna di servizio inizia e il sistema inizia a tenere traccia del tempo di consegna. Inoltre, è possibile impostare le seguenti opzioni:

  - È possibile iniziare e interrompere la registrazione del tempo nell'ordine di assistenza per registrare il tempo complessivo impiegato per eseguire gli ordini di assistenza.

  - È possibile monitorare la conformità con l'intervallo di tempo impostato nell'accordo sui livelli di servizio.

  - È possibile definire i codici motivo che dovranno essere impostati se l'intervallo di tempo specificato nell'accordo sui livelli di servizio viene superato.

## <a name="see-also"></a>Vedere anche

[Visualizzare la conformità ai contratti di servizio](view-compliance-with-service-level-agreements.md)

  


