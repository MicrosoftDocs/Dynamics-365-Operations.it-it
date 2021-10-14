---
title: Sincronizzare prezzi e sconti interaziendali
description: In questo argomento viene descritta la sincronizzazione di prezzi e sconti per ordini cliente e ordini fornitore interaziendali
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a9467e8d06a44cfaab9e3c8ea3944675c3eb8fb5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548345"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>Sincronizzare prezzi e sconti interaziendali

[!include [banner](../../includes/banner.md)]

Sconti e prezzi vengono sempre sincronizzati tra l'ordine cliente interaziendale e l'ordine fornitore interaziendale. È inoltre possibile sincronizzare il prezzo e gli sconti con e dall'ordine cliente originario, in modo che in tutti gli ordini siano presenti gli stessi prezzi e sconti. È possibile farlo dalla pagina **Interaziendale** a cui si accede dalla scheda **Generale** sulla pagina elenco **Tutti i clienti**, da **Vendite e marketing** o da **Approvvigionamento**.

Il campo **Prezzo e sconto** viene sincronizzato con la riga dell'ordine cliente interaziendale. In questo modo, selezionando i campi **Consenti modifica prezzi** e **Consenti modifica sconti** sarà possibile apportare una modifica tra l'ordine cliente interaziendale e l'ordine fornitore interaziendale. Una modifica al prezzo unitario, all'unità di prezzo o alle spese di vendita nell'ordine cliente interaziendale determinerà il prezzo nella riga dell'ordine fornitore interaziendale.

Se i campi **Consenti modifica prezzi** e **Consenti modifica sconti** sono abilitati nell'ordine cliente interaziendale o nell'ordine fornitore interaziendale, sarà possibile modificare manualmente il prezzo o lo sconto nell'uno o nell'altro ordine. In caso contrario, la modifica non sarà consentita.

Se i campi **Consenti modifica prezzi** e **Consenti modifica sconti** sono abilitati nell'ordine cliente interaziendale, non è possibile modificare manualmente il prezzo (o addebiti) o lo sconto in un ordine cliente interaziendale.

Se i campi **Consenti modifica prezzi** e **Consenti modifica sconti** sono abilitati nell'ordine fornitore interaziendale, non è possibile modificare manualmente il prezzo (o addebiti) o lo sconto in un ordine fornitore interaziendale.

Se i campi **Consenti modifica prezzi** e **Consenti modifica sconti** sono abilitati nell'ordine cliente interaziendale e nell'ordine fornitore interaziendale, sarà possibile modificare manualmente entrambi gli ordini. È possibile tuttavia che si verifichi una situazione in cui gli aggiornamenti apportati da una persona vengano sostituiti da quelli apportati da un'altra persona in un'altra società nello stesso ordine.

> [!NOTE]
> Se il campo **Prezzo e sconto** è stato abilitato sia nell'ordine fornitore interaziendale sia nell'ordine cliente interaziendale, non si avrà il controllo dei prezzi.

Per evitare questi tipi di conflitti, la procedura consigliata consiste nel consentire la modifica di prezzi e sconti nell'ordine cliente interaziendale o nell'ordine fornitore interaziendale. Ciò si ottiene abilitando i campi **Consenti modifica prezzi** e **Consenti modifica sconti** in uno di questi ordini.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
