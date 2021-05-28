---
title: La pagina di immissione della carta di credito visualizza un errore al momento del pagamento
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la sezione Metodo di pagamento non viene caricata e viene visualizzato un messaggio di errore.
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
ms.openlocfilehash: ea9105481e6c5812565f0d3604906c905bcb5443
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018508"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>La pagina di immissione della carta di credito visualizza un errore al momento del pagamento

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la sezione **Metodo di pagamento** non viene caricata e viene visualizzato un messaggio di errore.

## <a name="description"></a>Descrizione

Quando si apre la pagina di pagamento di un punto vendita online, la sezione **Metodo di pagamento** non viene caricata e viene visualizzato il seguente messaggio di errore: "Si è verificato un errore. Riprova più tardi."

![Errore nel modulo di pagamento](media/payment-module-error.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Attendere che la cache di Commerce Scale Unit scada

Le impostazioni del servizio di pagamento nella pagina di pagamento del punto vendita online vengono memorizzate nella cache in Commerce Scale Unit e la loro visualizzazione sul sito di e-commerce può richiedere fino a 15 minuti. Queste impostazioni del servizio di pagamento includono modifiche all'ID account esercente, chiave API cloud e varie impostazioni di configurazione relative al metodo di pagamento.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un canale online](../channel-setup-online.md)
