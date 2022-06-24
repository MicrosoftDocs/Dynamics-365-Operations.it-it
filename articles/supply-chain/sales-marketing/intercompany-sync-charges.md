---
title: Sincronizzare gli addebiti interaziendali
description: In questo articolo viene descritta la sincronizzazione degli addebiti interaziendali
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
ms.openlocfilehash: e7b3de3d7da7be6c1c8b5c3842862e7bccd78277
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857288"
---
# <a name="synchronize-intercompany-charges"></a>Sincronizzare gli addebiti interaziendali

[!include [banner](../../includes/banner.md)]

Gli addebiti vengono sincronizzati solo tra l'ordine cliente e l'ordine fornitore interaziendali e la sincronizzazione viene sempre eseguita.

Se nell'ordine fornitore interaziendale o nell'ordine cliente interaziendale è selezionato il campo **Consenti modifica prezzi**, è possibile aggiungere manualmente addebiti a tale ordine. In caso contrario, la modifica non sarà consentita.

Se nell'ordine cliente interaziendale non è selezionato il campo **Consenti modifica prezzi**, non è possibile aggiungere manualmente un addebito a tale ordine.

Se nell'ordine fornitore interaziendale non è selezionato il campo **Consenti modifica prezzi**, non è possibile aggiungere un addebito a tale ordine.

Se nell'ordine fornitore e nell'ordine cliente interaziendali è attivato il campo **Consenti modifica prezzi**, è possibile aggiungere manualmente addebiti a entrambi gli ordini. Potrebbe accadere tuttavia che molti addebiti vengano aggiunti in modo non corretto.

Per evitare questi tipi di conflitti, è consigliabile consentire l'aggiunta di addebiti all'ordine cliente interaziendale o all'ordine fornitore interaziendale, ma non a entrambi.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
