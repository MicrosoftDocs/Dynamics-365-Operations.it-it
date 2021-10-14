---
title: Richieste articoli degli ordini di assistenza
description: In questo argomento vengono descritte le richieste articoli degli ordini di assistenza
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae211cb24e3ed0e9e54643448ee378a20658ad89
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573203"
---
# <a name="service-order-item-requirements"></a>Richieste articoli degli ordini di assistenza

[!include [banner](../includes/banner.md)]

È possibile creare un ordine di assistenza per tenere traccia dei e gestire i servizi forniti ai clienti. Se è necessario prenotare articoli specifici per un ordine di assistenza, è possibile creare le richieste articolo di magazzino. Una richiesta articolo può essere immediatamente utilizzata dal magazzino oppure può avviare un ordine di produzione per l'articolo.

Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione.

Le richieste articoli per gli ordini di assistenza vengono elaborati nel corso di un progetto. Per creare una richiesta articolo in un ordine di assistenza, è necessario che l'ordine di assistenza sia collegato a un progetto.

Una richiesta articolo creata per un ordine di assistenza è immediatamente visibile da **Gestione progetti** nell'ordine di assistenza specifico o mediante il modulo **Ordine cliente**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Visualizzare una richiesta articolo da un ordine di assistenza

1. Selezionare **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.
1. Selezionare **Spedisci**, quindi **Richiesta articolo** per aprire il modulo **Richieste articoli**.
1. Selezionare la scheda **Progetto** e selezionare il campo **Ordine di assistenza** per visualizzare gli ordini di assistenza della richiesta articolo.

## <a name="delete-service-orders-with-item-requirements"></a>Eliminare ordini di assistenza con richieste articoli

Se si crea una richiesta articolo per un ordine di assistenza, non è possibile eliminare l'ordine di assistenza. È necessario eliminare la richiesta articolo prima di poter eliminare l'ordine di assistenza.

1. Selezionare **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.
1. Selezionare **Spedisci**, quindi **Richiesta articolo** per aprire il modulo **Richieste articoli**. In questo modulo verrà visualizzato l'elenco di tutte le richieste articoli create nell'ordine di assistenza.
1. Selezionare la richiesta articolo da eliminare, quindi selezionare **Elimina**.

oppure

1. Selezionare **Gestione progetti e contabilità** \> **Comune** \> **Progetti** \> **Tutti i progetti**.
1. Aprire il progetto che include l'ordine di assistenza in cui è stata creata una richiesta articolo.
1. Nel modulo **Progetti**, nel riquadro destro, selezionare **Richieste articoli**. Verrà aperto il modulo **Richieste articoli** con l'elenco delle richieste articolo associate al progetto selezionato.
1. Selezionare la richiesta articolo da eliminare, quindi selezionare **Elimina**.

## <a name="see-also"></a>Vedere anche

[Richieste articoli (modulo)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]