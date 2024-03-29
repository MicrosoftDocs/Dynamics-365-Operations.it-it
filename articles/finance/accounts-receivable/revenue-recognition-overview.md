---
title: Panoramica del riconoscimento ricavi (contiene video)
description: In questo articolo vengono fornite informazioni sulla funzionalità di riconoscimento dei ricavi. Questa funzionalità fornisce un framework flessibile che consente di definire regole specifiche della società per riconoscere sia il prezzo che la programmazione dei ricavi per ordini con più elementi.
author: bking
ms.date: 03/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 5bf07356b5613f438034f8dabac7db197e69a6c8
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644032"
---
# <a name="revenue-recognition-overview"></a>Panoramica del riconoscimento ricavi

[!include [banner](../includes/banner.md)]

>[!NOTE]
>Questa funzionalità verrà deprecata a ottobre 2023, i nuovi utenti dovranno usare la fatturazione abbonamento.

Le società di settori che vendono più elementi, ad esempio prodotti, servizi, sottoscrizioni e così via, devono essere in grado di separare gli ordini con più elementi in modo che sia possibile riconoscere i ricavi in base a un set di linee guida specifiche della società e del settore.

Il riconoscimento dei ricavi, inclusa la funzionalità aggregazione, non è supportato per l'utilizzo nei canali di Commerce (e-commerce, POS, servizio clienti). Gli articoli configurati con il riconoscimento dei ricavi non devono essere aggiunti agli ordini o alle transazioni creati nei canali di Commerce.

In generale, il processo di riconoscimento ricavi può essere utilizzato in genere per eseguire queste attività:

* Allocare i ricavi per garantire che il prezzo dei ricavi venga riconosciuto correttamente in base al valore dei componenti presenti negli ordini con più elementi.
* Differire i ricavi in base a una programmazione che rappresenta l'intervallo di tempo contrattuale e le percentuali per riconoscere i ricavi nel tempo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

Il video su [come usare il riconoscimento ricavi in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (mostrato in precedenza) è incluso nella [playlist delle app per la finanza e le operazioni](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.

La funzionalità di riconoscimento ricavi fornisce un framework flessibile che consente di definire regole specifiche della società per riconoscere sia il prezzo che la programmazione dei ricavi.

I prodotti rilasciati vengono utilizzati per supportare il riconoscimento ricavi sui documenti degli ordini cliente. I prodotti rilasciati contengono le impostazioni necessarie per determinare il prezzo e la programmazione dei ricavi. L'ordine cliente può derivare da un progetto di tempistica e materiali.

Le società possono utilizzare la funzionalità di programmazione dei ricavi senza utilizzare quella relativa ai prezzi. Di conseguenza, il prezzo nelle righe dell'ordine cliente verrà utilizzato come ricavo o come ricavo differito. Se nella riga ordine cliente è presente una programmazione ricavi, il prezzo in tale riga verrà differito. Se nella riga ordine cliente non è presente alcuna programmazione ricavi, il prezzo in tale riga verrà registrato in un conto ricavi al momento della fatturazione.

Il prezzo dei ricavi viene calcolato quando l'ordine cliente viene confermato o quando viene registrata la fattura. Per visualizzare in anteprima il prezzo dei ricavi prima della registrazione della fattura, è necessario confermare l'ordine cliente.

Quando l'ordine cliente viene confermato, se in una riga dell'ordine cliente è presente una programmazione dei ricavi, viene creata anche una programmazione dei ricavi prevista. Quando l'ordine cliente viene fatturato, la programmazione dei ricavi prevista viene eliminata e sostituita con la programmazione del riconoscimento ricavi effettiva.

I dettagli della programmazione per il riconoscimento dei ricavi vengono mantenuti per ogni riga ordine cliente. Di conseguenza, il responsabile del riconoscimento ricavi può visualizzare i dettagli e rilasciare le righe sui ricavi quando l'obbligo contrattuale è stato soddisfatto. Al termine di ogni periodo, il responsabile del riconoscimento ricavi può creare un giornale di registrazione ricavi per rilasciare tutte le righe di programmazione in scadenza prima o in corrispondenza di una data definita. Tale giornale non viene registrato immediatamente. Di conseguenza, il responsabile del riconoscimento ricavi può verificare che gli importi corretti vengano rilasciati dai ricavi differiti a quelli effettivi.

Se una modifica del contratto determina l'aggiunta di una nuova riga ordine cliente all'ordine cliente esistente oppure a uno nuovo, è possibile eseguire un processo di riassegnazione per correggere il prezzo dei ricavi in tutte le righe dell'ordine cliente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

