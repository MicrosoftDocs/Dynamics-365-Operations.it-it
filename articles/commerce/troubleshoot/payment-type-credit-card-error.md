---
title: Errore "Il tipo di pagamento deve essere una carta di credito" nella pagina dell'ordine cliente
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando viene visualizzato un messaggio di errore nella pagina dell'ordine cliente dopo la sincronizzazione di un ordine.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5be19949e9d1dbc43fdd3e6def119effa50a34d0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018412"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>Errore "Il tipo di pagamento deve essere una carta di credito" nella pagina dell'ordine cliente

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando viene visualizzato un messaggio di errore nella pagina dell'ordine cliente dopo la sincronizzazione di un ordine.

## <a name="description"></a>Descrizione

Quando si apre la pagina dell'ordine cliente dopo aver sincronizzato un ordine, viene visualizzato il seguente messaggio di errore: "Il tipo di pagamento deve essere una carta di credito poiché è stato specificato il numero di carta di credito".

![Errore "Il tipo di pagamento deve essere una carta di credito"](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Impostare il tipo di pagamento in Commerce Headquarters

1. Andare a **Contabilità clienti \> Impostazione pagamenti \> Condizioni di pagamento**.
1. Nella barra di navigazione a sinistra, selezionare i termini di pagamento.
1. Nel campo **Tipo di pagamento**, assicurarsi che **Carta di credito** sia selezionato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Registrazione di vendite e pagamenti online](../tasks/posting-online-sales-payments.md)
