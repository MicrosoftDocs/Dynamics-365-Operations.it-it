---
title: Gli articoli non disponibili possono essere acquistati
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i clienti possono aggiungere articoli non disponibili al carrello e procedere al pagamento.
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
ms.openlocfilehash: 4fa7769044c45faffd9ff61b3de8e6217a5e0354
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018460"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Gli articoli non disponibili possono essere acquistati

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i clienti possono aggiungere articoli non disponibili al carrello e procedere al pagamento.

## <a name="description"></a>Descrizione

Gli utenti possono aggiungere un articolo al carrello, anche se non ci sono scorte disponibili nel punto vendita, e procedere alla pagina di pagamento.

## <a name="resolution"></a>Risoluzione

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a>Abilitare la proprietà Mostra errori scorte esaurite in Creazione di siti di Commerce

Per abilitare la proprietà **Mostra errori scorte esaurite** in Creazione di siti di Commerce, procedere come segue.

1. Selezionare il sito sul quale si sta lavorando.
1. Nel pannello di navigazione a sinistra, selezionare **Pagine**.
1. Selezionare **CartPage** per aprire questa pagina.
1. Selezionare lo slot **Carrello 1**, selezionare **Modifica** quindi nel riquadro delle proprietà, selezionare la casella di controllo **Mostra errori scorte esaurite**.
1. Salva e pubblica la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

[Applicare le impostazioni delle scorte](../inventory-settings.md)

[Calcolare la disponibilità scorte per i canali di vendita al dettaglio](../calculated-inventory-retail-channels.md)

[Configurare buffer scorte e livelli scorte](../inventory-buffers-levels.md)
