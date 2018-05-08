---
title: Impedire sconti per prodotti al dettaglio
description: Esistono vari motivi per cui i rivenditori intendono non applicare sconti ad alcuni prodotti durante una promozione o la vendita al POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 70139c124486e3e6a01c1c08e71f140dcf1864c0
ms.openlocfilehash: e0d3a16da6a673f9ce6a025a7d4bde9ffb1a9e9b
ms.contentlocale: it-it
ms.lasthandoff: 10/24/2017

---

# <a name="prevent-discounts-for-retail-products"></a>Impedire sconti per prodotti al dettaglio

[!include [banner](includes/banner.md)]

Esistono vari motivi per cui i rivenditori intendono non applicare sconti ad alcuni prodotti durante una promozione o la vendita al POS.

Le opzioni seguenti, disponibili nella scheda **Vendita al dettaglio** dei prodotti rilasciati, consentono di configurare il prodotto per impedire l'applicazione di tutti gli sconti o di quelli manuali. Le impostazioni possono anche essere specificate a livello di categoria nella gerarchia di categorie di vendite al dettaglio.

**Impedisci tutti gli sconti**: selezionare questa opzione per impedire l'applicazione di tutti i tipi di sconti al prodotto. Sono inclusi gli sconti gamma articoli, quantità e di soglia, nonché gli sconti riga manuali e transazione applicati durante una vendita da un utente POS.

**Impedisci sconti manuali**: selezionare questa opzione per impedire gli sconti riga manuali o transazione applicati durante una vendita da un utente POS. Ai prodotti con questa opzione selezionata è sempre possibile applicare le promozioni, ad esempio sconti gamma articoli, quantità e di soglia.

**Nota**: queste impostazioni non limitano l'operazione di sostituzione dei prezzi in quanto questa definisce il prezzo base e non è considerata come sconto.  

[![campo Impedisci sconti](./media/prevent discounts.png)](./media/prevent discounts.png)

