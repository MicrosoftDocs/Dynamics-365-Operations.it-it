---
title: Sincronizzare le informazioni sui clienti interaziendali
description: In questo articolo viene descritta la sincronizzazione delle informazioni sui clienti per gli ordini interaziendali
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
ms.openlocfilehash: a3a67c9bcf93f88375d2d4d78d87175200626d50
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897518"
---
# <a name="synchronize-intercompany-customer-information"></a>Sincronizzare le informazioni sui clienti interaziendali

[!include [banner](../../includes/banner.md)]

Le informazioni sul cliente vengono sincronizzate se è abilitato il campo **Informazioni cliente** quando si crea l'ordine cliente o quando si apportano modifiche al cliente, al riferimento fornitore o al numero della richiesta di approvvigionamento cliente.

Il valore specificato nei campi di sincronizzazione può essere sempre modificato. Tuttavia, per determinare se il valore deve essere copiato negli altri ordini interaziendali, è necessario selezionare questo parametro. Se nell'ordine cliente interaziendale è stato abilitato il campo **Informazioni cliente**, un'eventuale modifica a tale ordine verrà sincronizzata con l'ordine fornitore interaziendale. Se il campo **Informazioni cliente** è stato abilitato anche nell'ordine fornitore interaziendale, verrà sincronizzato anche con l'ordine cliente originario.

> [!NOTE]
> Se il campo **Informazioni cliente** è stato abilitato sia nell'ordine fornitore interaziendale sia nell'ordine cliente interaziendale, gli aggiornamenti effettuati da una persona di una determinata società verranno sostituiti dagli aggiornamenti effettuati sullo stesso ordine da un'altra persona di una diversa società.

Come procedura consigliata abilitare il campo **Informazioni cliente** nell'ordine fornitore interaziendale, in modo da consentire la sincronizzazione tra l'ordine cliente originario e l'ordine fornitore interaziendale e tra quest'ultimo e l'ordine cliente interaziendale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
