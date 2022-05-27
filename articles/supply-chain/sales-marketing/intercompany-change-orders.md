---
title: Modificare gli ordini interaziendali
description: Questo argomento spiega la modifica della funzionalità degli ordini interaziendali
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
ms.openlocfilehash: 10efc397c64833785f286983987fd05854a69c0f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672908"
---
# <a name="change-intercompany-orders"></a>Modificare gli ordini interaziendali

[!include [banner](../../includes/banner.md)]

Se si modifica un ordine cliente o un ordine fornitore interaziendale, tale modifica verrà applicata anche al corrispondente ordine cliente o fornitore nella società corrispondente.

## <a name="adding-new-lines"></a>Aggiunta di nuove righe

È possibile aggiungere nuove righe a un ordine cliente e un ordine fornitore interaziendali se l'ordine cliente originario fa parte della catena di ordini interaziendali. È inoltre possibile aggiungere nuove righe se l'ordine cliente originario non prevede una consegna diretta. Se invece l'ordine cliente originario prevede una consegna diretta, sarà possibile aggiungere nuove righe ordine all'ordine cliente e all'ordine fornitore interaziendali solo se nella Scheda dettaglio **Impostazioni interaziendali** dell'ordine cliente originario è selezionato il campo **Consenti creazione indiretta**.

## <a name="changing-prices-and-discounts"></a>Modifica di prezzi e sconti

È possibile modificare i prezzi e gli sconti se le caselle di controllo **Consenti modifica prezzi** e **Consenti modifica sconto** sono selezionate nella pagina **Interaziendale**.

Se si modifica il prezzo unitario di una delle righe esistenti nell'ordine cliente interaziendale, verrà modificato anche il prezzo unitario nell'ordine fornitore interaziendale.

Se si modifica uno dei campi relativi agli sconti nella riga dell'ordine cliente interaziendale, verranno aggiornati automaticamente i campi relativi agli sconti pertinenti nell'ordine fornitore interaziendale.

## <a name="changing-and-adding-new-charges"></a>Modifica e aggiunta di nuovi addebiti

È possibile modificare gli addebiti se le caselle di controllo **Consenti modifica prezzi** e **Consenti modifica sconto** sono selezionate nella pagina **Interaziendale**.

Se si aggiunge un nuovo addebito all'intestazione dell'ordine cliente interaziendale e alla riga dell'ordine cliente interaziendale, entrambi gli addebiti verranno copiati nell'ordine fornitore interaziendale. Di conseguenza, l'ordine cliente interaziendale e l'ordine fornitore interaziendale avranno lo stesso importo totale. Gli addebiti non vengono mai copiati nell'ordine cliente originario.

## <a name="copying-a-fee"></a>Copia di corrispettivi

Per copiare corrispettivi nell'ordine cliente originario, è necessario crearli come una nuova riga di vendita con un articolo di tipo **Servizio**.

## <a name="changing-quantities-and-deleting-intercompany-purchases-and-sales-order-lines"></a>Modifica delle quantità ed eliminazione di righe dell'ordine cliente e dell'ordine fornitore interaziendale

È possibile modificare la quantità o eliminare una riga dell'ordine cliente o dell'ordine fornitore interaziendale solo se la riga è stata creata direttamente dal modulo **Ordine cliente** o **Ordine fornitore**. In questo modo, l'ordine cliente o fornitore interaziendale oppure le righe ordine diventeranno l'origine.

## <a name="origins-of-orders-and-order-lines"></a>Origini di ordini e righe ordine

Agli ordini e alle righe ordine interaziendali può essere assegnata una delle seguenti origini:

- **Derivata**: l'ordine è stato creato automaticamente da una catena di ordini interaziendali.
- **Origine**: l'ordine è stato creato manualmente da un utente.

L'origine viene indicata nel campo **Origine** dell'intestazione degli ordini cliente e degli ordini fornitore interaziendali. Questo campo è disponibile nella Scheda dettaglio **Impostazioni interaziendali** dell'ordine cliente e nella Scheda dettaglio **Impostazione** dell'ordine fornitore.

Le origini **Derivata** e **Origine** sono applicabili solo agli ordini interaziendali. Il campo **Origine** è vuoto per tutti gli altri ordini cliente e fornitore e per tutte le altre righe ordine. Questo campo è vuoto anche nell'ordine cliente originario.

## <a name="example-derived-origin"></a>Esempio: origine derivata

Viene creato un ordine cliente originario per un cliente esterno. In questo ordine cliente è presente una sola riga ordine. Tramite questo ordine cliente originario viene creato un ordine fornitore interaziendale contenente una riga ordine, da cui viene creato un ordine cliente interaziendale contenente una riga ordine. L'intestazione dell'ordine fornitore interaziendale e la riga ordine vengono creati automaticamente dall'ordine cliente originario.

Il valore del campo **Origine** nella Scheda dettaglio **Impostazione** dell'ordine fornitore interaziendale e nella Scheda dettaglio **Impostazioni interaziendali** delle intestazioni dell'ordine cliente interaziendale è **Derivata**. Anche il valore del campo **Origine** nella scheda **Dettagli riga** delle righe ordine cliente e ordine fornitore è **Derivata**.

Se una riga ordine ha un'origine **Derivata**, non sarà possibile eliminarla direttamente. La riga ordine potrà essere eliminata solo dall'origine che ha creato tale riga. Anche la quantità ordinata può essere modificata solo dall'origine che ha creato la riga ordine.

Se un ordine cliente originario e una riga ordine cliente originario fanno parte della catena di ordini interaziendali, sarà possibile modificare le quantità ordinate ed eliminare righe nell'ordine cliente originario.

## <a name="example-source-origin"></a>Esempio: origine

Per un fornitore interaziendale viene creato un ordine fornitore. L'origine di questo ordine e della relativa riga ordine sarà per entrambi **Origine**. L'ordine fornitore interaziendale avrà pertanto funzione di controllo e l'ordine cliente interaziendale creato automaticamente nella società fornitore avrà come origine **Derivata**.

Inoltre, le quantità prenotate di una riga ordine creata nell'ordine fornitore interaziendale non possono essere modificate nell'ordine cliente interaziendale. La riga ordine può essere eliminata solo dall'ordine fornitore interaziendale. Se all'ordine cliente interaziendale viene aggiunta una nuova riga, l'origine della riga ordine cliente interaziendale sarà quindi **Origine**.

Se un ordine cliente originario fa parte della catena di ordini interaziendali, è sempre possibile controllare gli ordini interaziendali e le relative righe dall'ordine cliente originario.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
