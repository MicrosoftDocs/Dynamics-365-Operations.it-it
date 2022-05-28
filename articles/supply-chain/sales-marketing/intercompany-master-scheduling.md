---
title: Programmazione generale interaziendale
description: Questo argomento spiega la programmazione generale interaziendale
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 02d1a3675cfe30f2e72237f69509398122d17f05
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671872"
---
# <a name="intercompany-master-scheduling"></a>Programmazione generale interaziendale

[!include [banner](../../includes/banner.md)]

La programmazione generale interaziendale è il modo di calcolare i fabbisogni e di generare ordini interaziendali pianificati tra più società interne. La programmazione generale interaziendale viene eseguita per il numero di iterazioni specificato. Per consentire l'esecuzione della programmazione generale interaziendale in Microsoft Dynamics 365 Supply Chain Management, è necessario impostarla in ciascuna società interaziendale. Ciò comporta diverse iterazioni nelle quali viene creato automaticamente un ordine fornitore interaziendale in Microsoft Dynamics 365 Supply Chain Management e conseguentemente un ordine cliente interaziendale che, a sua volta, determina nuove domande.

Il piano generale interaziendale e l'ordine di programmazione interaziendale vengono impostati nei parametri di **Pianificazione generale** in ciascuna società interaziendale.

Per propagare la domanda attraverso la catena interaziendale, è necessario impostare i parametri per assicurare che gli ordini fornitore pianificati vengano stabilizzati automaticamente, ovvero non possano essere modificati in termini di tempo e quantità. Impostare l'**Intervallo temporale di stabilizzazione** sul gruppo Copertura o l'**Intervallo temporale di stabilizzazione** nel piano generale. Se non viene impostato un valore in **Intervallo temporale di stabilizzazione**, non verrà creato automaticamente alcun ordine fornitore interaziendale. Solo la prima esecuzione della programmazione generale genera ordini pianificati. Tuttavia, poiché non viene creato alcun ordine fornitore interaziendale, non viene creato alcun ordine cliente interaziendale e, di conseguenza, non vengono creati più ordini fornitore interaziendali e così via.

Quando si avvia la programmazione generale interaziendale in Microsoft Dynamics 365 Supply Chain Management, ne viene eseguita automaticamente una prima iterazione in ciascuna società interaziendale, quindi una seconda iterazione in ciascuna società interaziendale e così via, finché non viene raggiunto il numero di iterazioni specificato. È possibile impostare un massimo di 30 iterazioni, tuttavia, maggiore è il numero di iterazioni specificato, più si prolungherà l'esecuzione della programmazione.

È possibile avviare la programmazione generale interaziendale da qualsiasi società interaziendale, in quanto la programmazione generale nelle società è controllata dalla sequenza di programmazione interaziendale, ovvero l'ordine in cui viene assegnata automaticamente la priorità alle programmazioni generali in ciascuna società interaziendale. Poiché la sequenza di programmazione interaziendale determina l'ordine di esecuzione della programmazione generale nelle società, è ininfluente la società dalla quale viene avviata la programmazione. In ciascuna iterazione la programmazione generale interaziendale nella società corrente viene eseguita per ultima.

> [!NOTE]
> La procedura consigliata consiste nel consentire l'avvio della programmazione generale interaziendale da una società di Microsoft Dynamics 365 Supply Chain Management.

Nella pagina **Programmazione generale interaziendale** è possibile avviare una sequenza di programmazione generale nell'ambito della quale venga eseguita, la prima volta, una programmazione generale in base al principio di aggiornare il calcolo del fabbisogno selezionato per la prima iterazione per tutte le società interaziendali. Per le ulteriori iterazioni verrà utilizzato il principio secondario selezionato per l'iterazione successiva e questo principio verrà applicato finché non si raggiunge il numero di iterazioni specificato.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
