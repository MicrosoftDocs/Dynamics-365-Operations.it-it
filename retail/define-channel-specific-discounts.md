---
title: Definire gli sconti specifici del canale
description: "I rivenditori fissano spesso sconti diversi in canali diversi. In questo argomento vengono esaminati i concetti che è necessario conoscere per creare uno sconto per un canale specifico."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: b2f59db59ea49925c3bb5e1d75beee95191220d0
ms.lasthandoff: 03/31/2017


---

# <a name="define-channel-specific-discounts"></a>Definire gli sconti specifici del canale

I rivenditori fissano spesso sconti diversi in canali diversi. In questo argomento vengono esaminati i concetti che è necessario conoscere per creare uno sconto per un canale specifico. 

<a name="channel-specific-discounts"></a>Sconti specifici del canale
--------------------------

I rivenditori spesso offrono gli sconti diversi di canali diversi. Si tratta può essere effettuata per eliminare le condizioni di mercato locali o per la gestione dei rivenditori concorrenti.

La vendita al dettaglio e il commercio in Microsoft Dynamics 365 per le operazioni utilizzati i gruppi di prezzi per definire gli sconti Manica- specifici. I gruppi di prezzi possono essere assegnati a una o più delle entità seguenti: canali, cataloghi, affiliazioni e programmi fedeltà. In questo articolo vengono illustrati i canali, ma gli stessi concetti si applicano per gli sconti di catalogo, gli sconti di affiliazioni e gli sconti fedeltà.

## <a name="price-groups"></a>Gruppi prezzi
alignnone" width= " 640 "di align= " a " id= del titolo\[con\_256084 "\][gruppi di prezzi![(]. /media/price-groups-1024x608.png)](. Il gruppo di prezzi /media/price-groups.png) dei collegamenti da\[a /caption\]

Nel diagramma di cui sopra illustrata la relazione tra le entità che possono essere in una transazione (canale, catalogo, report, clienti, Carta fedeltà) e nei vari tipi di sconti che è possibile configurare. Tutte le transazioni si verificano in un canale, il canale viene garantito per essere presente una transazione. Le entità rimanenti sono facoltative. In ogni pagina anagrafica è presente un collegamento a una pagina correlata dei gruppi di prezzi in cui è possibile visualizzare e aggiungere i gruppi di prezzi in base alle necessità. Un gruppo di prezzi viene utilizzato per collegare quattro diversi tipi di entità agli sconti, le rettifiche di prezzo e agli accordi commerciali. È consigliabile a progettare una strategia per la nominerete i gruppi di prezzi tenerli organizzati. Opzione disponibile sarà di utilizzare una lettera o un prefisso o un suffisso di distinguere i diversi tipi. Ad esempio, 1 xxxxx per gruppi di prezzi del canale e 2 xxxxx per gruppi di prezzi del catalogo. Sono disponibili quattro pagine di richiesta che si concentrano in ciascuna delle entità al dettaglio che possono essere associate.

-   **Gruppi di prezzi canale di vendita al dettaglio **- In questa pagina viene visualizzato un elenco dei canali e degli sconti collegati e per ogni gruppo prezzi.
-   **Gruppi prezzi catalogo **- In questa pagina viene visualizzato un elenco dei cataloghi e degli sconti collegati e per ogni gruppo prezzi.
-   **Gruppi di prezzi programma fedeltà **- In questa pagina viene visualizzato un elenco dei programma fedeltà e degli sconti collegati e per ogni gruppo prezzi.
-   **Gruppi di prezzi rapporti **- In questa pagina viene visualizzato un elenco dei rapporti e degli sconti collegati e per ogni gruppo prezzi.

## <a name="example-channel-discount-set-up"></a>Impostazione di esempio di sconto di canale
Nel seguente esempio sono illustrate le attività in questione nell'impostazione dello sconto di canale.

1.  Per questo esempio, si ha un canale **Houston** e si crea un nuovo sconto denominato **Di nuovo a scuola.**
2.  Poiché la strategia di sconto e dei prezzi comprende la possibilità degli sconti di canale, creare sempre un gruppo di prezzi specifico del canale quando si crea un canale.
3.  Si ha il gruppo di prezzi **Houston-PG** ed è assegnato al canale **Houston**.
4.  Dopo aver creato il nuovo sconto **Di nuovo a scuola**, è necessario fare clic su **Gruppi prezzi** nella parte superiore della pagina **Sconto**. Si apre la pagina **Gruppi di prezzo scontati**. Dopodiché, fare clic su **Nuovo** e selezionare il gruppo di prezzi **Houston-PG**.
5.  Ora è possibile attivare lo sconto e spingerlo nel canale.

 

<a name="see-also"></a>Vedere anche
--------

[Price adjustments and discounts](price-adjustments-discounts.md)


