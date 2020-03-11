---
title: Opzioni per impedire sconti sui prodotti al dettaglio
description: Esistono vari motivi per cui i rivenditori intendono non applicare sconti ad alcuni prodotti durante una promozione o la vendita al POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 6a683ffce487dc4388711ad160c2e8dc55a690dd
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057466"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a><span data-ttu-id="a7c14-103">Opzioni per impedire sconti sui prodotti al dettaglio</span><span class="sxs-lookup"><span data-stu-id="a7c14-103">Options for preventing discounts for retail products</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a7c14-104">Esistono vari motivi per cui i rivenditori intendono non applicare sconti ad alcuni prodotti durante una promozione o la vendita al POS.</span><span class="sxs-lookup"><span data-stu-id="a7c14-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="a7c14-105">Le opzioni seguenti, disponibili nella scheda **Commerce** dei prodotti rilasciati, consentono di configurare il prodotto per impedire l'applicazione di tutti gli sconti o di quelli manuali.</span><span class="sxs-lookup"><span data-stu-id="a7c14-105">The following options, which can be found on the **Commerce** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="a7c14-106">Le impostazioni possono anche essere specificate a livello di categoria nella gerarchia di categorie.</span><span class="sxs-lookup"><span data-stu-id="a7c14-106">The settings can also be specified at the category level from the category hierarchy.</span></span>

- <span data-ttu-id="a7c14-107">**Impedisci tutti gli sconti**: selezionare questa opzione per impedire l'applicazione di tutti i tipi di sconti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="a7c14-107">**Prevent all discounts** – Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="a7c14-108">Sono inclusi gli sconti gamma articoli, quantità e di soglia, nonché gli sconti riga manuali e transazione applicati durante una vendita da un utente POS.</span><span class="sxs-lookup"><span data-stu-id="a7c14-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>
- <span data-ttu-id="a7c14-109">**Impedisci sconti manuali**: selezionare questa opzione per impedire gli sconti riga manuali o transazione applicati durante una vendita da un utente POS.</span><span class="sxs-lookup"><span data-stu-id="a7c14-109">**Prevent manual discounts** – Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="a7c14-110">Ai prodotti con questa opzione selezionata è sempre possibile applicare le promozioni, ad esempio sconti gamma articoli, quantità e di soglia.</span><span class="sxs-lookup"><span data-stu-id="a7c14-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

> [!NOTE]
> <span data-ttu-id="a7c14-111">Queste impostazioni non limitano l'operazione di sostituzione dei prezzi in quanto questa definisce il prezzo base e non è considerata come sconto.</span><span class="sxs-lookup"><span data-stu-id="a7c14-111">These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>

<span data-ttu-id="a7c14-112">[![Campo Impedisci sconti](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span><span class="sxs-lookup"><span data-stu-id="a7c14-112">[![Prevent discounts field](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span></span>