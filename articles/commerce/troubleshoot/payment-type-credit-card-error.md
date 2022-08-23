---
title: Errore "Il tipo di pagamento deve essere una carta di credito" nella pagina dell'ordine cliente
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando viene visualizzato un messaggio di errore nella pagina dell'ordine cliente dopo la sincronizzazione di un ordine.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 71c5cbaf574866c74e222f4d67132004327db8fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285634"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>Errore "Il tipo di pagamento deve essere una carta di credito" nella pagina dell'ordine cliente

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando viene visualizzato un messaggio di errore nella pagina dell'ordine cliente dopo la sincronizzazione di un ordine.

## <a name="description"></a>Descrizione

Quando si apre la pagina dell'ordine cliente dopo aver sincronizzato un ordine, viene visualizzato il seguente messaggio di errore: "Il tipo di pagamento deve essere una carta di credito poiché è stato specificato il numero di carta di credito".

![Errore "Il tipo di pagamento deve essere una carta di credito".](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Impostare il tipo di pagamento in Commerce Headquarters

1. Andare a **Contabilità clienti \> Impostazione pagamenti \> Condizioni di pagamento**.
1. Nella barra di navigazione a sinistra, selezionare i termini di pagamento.
1. Nel campo **Tipo di pagamento**, assicurarsi che **Carta di credito** sia selezionato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Registrazione di vendite e pagamenti online](../tasks/posting-online-sales-payments.md)
