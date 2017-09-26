---
title: Impedire sconti per prodotti al dettaglio
description: Esistono vari motivi per cui i rivenditori intendono non applicare sconti ad alcuni prodotti durante una promozione o la vendita al POS.
author: jeffbl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: c124ecf104bdb3de786c9dd98c2b07a4c9c04041
ms.openlocfilehash: 0debfe984a83295dde145fe4b8c2deb836345cd6
ms.contentlocale: it-it
ms.lasthandoff: 07/31/2017

---

# <a name="prevent-discounts-for-retail-products"></a>Impedire sconti per prodotti al dettaglio

[!include[banner](includes/banner.md)]

Esistono vari motivi per cui i rivenditori intendono non applicare sconti ad alcuni prodotti durante una promozione o la vendita al POS.

Le opzioni seguenti, disponibili nella scheda **Vendita al dettaglio** dei prodotti rilasciati, consentono di configurare il prodotto per impedire l'applicazione di tutti gli sconti o di quelli manuali. Le impostazioni possono anche essere specificate a livello di categoria nella gerarchia di categorie di vendite al dettaglio.

**Impedisci tutti gli sconti**: selezionare questa opzione per impedire l'applicazione di tutti i tipi di sconti al prodotto. Sono inclusi gli sconti gamma articoli, quantità e di soglia, nonché gli sconti riga manuali e transazione applicati durante una vendita da un utente POS.

**Impedisci sconti manuali**: selezionare questa opzione per impedire gli sconti riga manuali o transazione applicati durante una vendita da un utente POS. Ai prodotti con questa opzione selezionata è sempre possibile applicare le promozioni, ad esempio sconti gamma articoli, quantità e di soglia.

**Nota**: queste impostazioni non limitano l'operazione di sostituzione dei prezzi in quanto questa definisce il prezzo base e non è considerata come sconto.  

![campo Impedisci sconti](/media/prevent-discounts.png)

