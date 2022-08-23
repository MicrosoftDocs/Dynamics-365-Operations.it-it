---
title: Definire gli sconti specifici del canale
description: I rivenditori fissano spesso sconti diversi in canali diversi. In questo articolo vengono esaminati i concetti che è necessario conoscere per creare uno sconto per un canale specifico.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.industry: Retail
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
ms.openlocfilehash: f426503a6897a73010b77082f4277b65545bfcc3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273556"
---
# <a name="define-channel-specific-discounts"></a>Definire gli sconti specifici del canale

[!include [banner](includes/banner.md)]

In questo articolo vengono esaminati i concetti che è necessario conoscere per creare uno sconto per un canale specifico.

## <a name="channel-specific-discounts"></a>Sconti specifici del canale

I rivenditori offrono spesso sconti diversi in canali diversi. Questa strategia può servire per andare incontro alle condizioni di mercato locali o per gestire i rivenditori concorrenti.

Commerce utilizza i gruppi di prezzi per definire gli sconti specifici del canale. I gruppi di prezzi possono essere assegnati a una o più delle entità seguenti: canali, cataloghi, affiliazioni e programmi fedeltà. In questo articolo vengono illustrati i canali, ma gli stessi concetti si applicano per gli sconti di catalogo, gli sconti di affiliazioni e gli sconti fedeltà.

## <a name="price-groups"></a>Gruppi di prezzi

[![Gruppi prezzi.](./media/price-groups-1024x608.png)](./media/price-groups.png)

Il diagramma precedente illustra la relazione tra le entità che possono essere presenti in una transazione (canale, catalogo, affiliazione, cliente, carta fedeltà) e i vari tipi di sconto che possono essere configurati. Tutte le transazioni si verificano in un canale, pertanto il canale è sicuramente presente in una transazione. Le entità rimanenti sono facoltative. In ogni pagina anagrafica è presente un collegamento a una pagina correlata dei gruppi di prezzi in cui è possibile visualizzare e aggiungere i gruppi di prezzi in base alle necessità. Un gruppo di prezzi viene utilizzato per collegare quattro diversi tipi di entità agli sconti, le rettifiche prezzo e gli accordi commerciali. È consigliabile progettare una strategia sui nomi da assegnare ai gruppi di prezzi per tenerli organizzati. Un'opzione consiste nell'utilizzare un prefisso o un suffisso numerico o letterale per distinguere i diversi tipi. Ad esempio, 1-xxxxx per gruppi di prezzi del canale e 2-xxxxx per gruppi di prezzi del catalogo. Sono disponibili quattro pagine di richiesta che si concentrano in ciascuna delle entità di commercio che possono essere associate.

- **Gruppi di prezzi canale di commercio**- In questa pagina viene visualizzato un elenco dei canali e degli sconti collegati e per ogni gruppo prezzi.
- **Gruppi prezzi catalogo** – In questa pagina viene visualizzato un elenco dei cataloghi e degli sconti collegati e per ogni gruppo prezzi.
- **Gruppi di prezzi programma fedeltà** – In questa pagina viene visualizzato un elenco dei programma fedeltà e degli sconti collegati e per ogni gruppo prezzi.
- **Gruppi di prezzi rapporti** – In questa pagina viene visualizzato un elenco dei rapporti e degli sconti collegati e per ogni gruppo prezzi.

## <a name="example-channel-discount-set-up"></a>Impostazione di esempio di sconto di canale

Nel seguente esempio sono illustrate le attività in questione nell'impostazione dello sconto di canale.

1. Per questo esempio, si ha un canale **Houston** e si crea un nuovo sconto denominato **Di nuovo a scuola**.
2. Poiché la strategia di sconto e dei prezzi comprende la possibilità degli sconti di canale, creare sempre un gruppo di prezzi specifico del canale quando si crea un canale.
3. Si ha il gruppo di prezzi **Houston-PG** ed è assegnato al canale **Houston**.
4. Dopo aver creato il nuovo sconto **Di nuovo a scuola**, è necessario fare clic su **Gruppi prezzi** nella parte superiore della pagina **Sconto**. Si apre la pagina **Gruppi di prezzo scontati**. Dopodiché, fare clic su **Nuovo** e selezionare il gruppo di prezzi **Houston-PG**.
5. Ora è possibile attivare lo sconto e spingerlo nel canale.

## <a name="additional-resources"></a>Risorse aggiuntive

[Rettifiche prezzi e sconti](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
