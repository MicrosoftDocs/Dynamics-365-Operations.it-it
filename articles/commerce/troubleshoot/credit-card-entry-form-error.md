---
title: La pagina di immissione della carta di credito visualizza un errore al momento del pagamento
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la sezione Metodo di pagamento non viene caricata e viene visualizzato un messaggio di errore.
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
ms.openlocfilehash: 25f0dde83efff7c1d9a2a456270f5d48047f44ba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269757"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>La pagina di immissione della carta di credito visualizza un errore al momento del pagamento

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la sezione **Metodo di pagamento** non viene caricata e viene visualizzato un messaggio di errore.

## <a name="description"></a>Descrizione

Quando si apre la pagina di pagamento di un punto vendita online, la sezione **Metodo di pagamento** non viene caricata e viene visualizzato il seguente messaggio di errore: "Si è verificato un errore. Riprova più tardi."

![Errore nel modulo di pagamento.](media/payment-module-error.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Attendere che la cache di Commerce Scale Unit scada

Le impostazioni del servizio di pagamento nella pagina di pagamento del punto vendita online vengono memorizzate nella cache in Commerce Scale Unit e la loro visualizzazione sul sito di e-commerce può richiedere fino a 15 minuti. Queste impostazioni del servizio di pagamento includono modifiche all'ID account esercente, chiave API cloud e varie impostazioni di configurazione relative al metodo di pagamento.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un canale online](../channel-setup-online.md)
