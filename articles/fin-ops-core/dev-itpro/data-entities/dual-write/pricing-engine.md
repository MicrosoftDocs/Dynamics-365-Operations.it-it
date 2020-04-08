---
title: Sincronizzare con il motore di determinazione del prezzo Dynamics 365 Supply Chain Management su richiesta
description: Questo argomento descrive come utilizzare il motore di determinazione del prezzo in Microsoft Dynamics 365 Supply Chain Management da Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: ef4465144155130087b078f9f96911df38b62c41
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173179"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a><span data-ttu-id="e4a9c-103">Sincronizzare con il motore di determinazione del prezzo Dynamics 365 Supply Chain Management su richiesta</span><span class="sxs-lookup"><span data-stu-id="e4a9c-103">Sync with the Dynamics 365 Supply Chain Management pricing engine on demand</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="e4a9c-104">Microsoft Dynamics 365 Supply Chain Management include un motore di determinazione del prezzo che gestisce accordi commerciali, listini prezzi, programmi di fidelizzazione dei clienti, promozioni e sconti.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="e4a9c-105">Il motore di determinazione del prezzo utilizza regole complesse per determinare il prezzo migliore per un determinato preventivo od ordine.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="e4a9c-106">Quando si utilizza la doppia scrittura, si usa il prezzo statico o il motore di determinazione dei prezzi da Dynamics 365 Supply Chain Management nelle pagine Offerta e Ordine in Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="e4a9c-107">Utilizzare il motore di determinazione dei prezzi da Supply Chain Management in Sales</span><span class="sxs-lookup"><span data-stu-id="e4a9c-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="e4a9c-108">In Sales, andare a **Vendite \> Ordini**.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="e4a9c-109">Selezionare **Nuovo** per creare un nuovo ordine o selezionare un ordine esistente nell'elenco **Ordini personali**.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="e4a9c-110">Aggiungere una nuova riga ordine.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-110">Add a new order line.</span></span>
4. <span data-ttu-id="e4a9c-111">Se stai creando un nuovo ordine, selezionare **Prezzo ordine** nel riquadro Azione.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="e4a9c-112">Se stai aggiornando un ordine esistente, selezionare **Ricalcola** nel riquadro Azione.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="e4a9c-113">I campi riportati di seguito vengono automaticamente popolati:</span><span class="sxs-lookup"><span data-stu-id="e4a9c-113">The following fields are automatically filled in:</span></span>

    + <span data-ttu-id="e4a9c-114">Dettagli importo</span><span class="sxs-lookup"><span data-stu-id="e4a9c-114">Detail Amount</span></span>
    + <span data-ttu-id="e4a9c-115">% sconto</span><span class="sxs-lookup"><span data-stu-id="e4a9c-115">Discount %</span></span>
    + <span data-ttu-id="e4a9c-116">Sconto</span><span class="sxs-lookup"><span data-stu-id="e4a9c-116">Discount</span></span>
    + <span data-ttu-id="e4a9c-117">Importo pre-trasporto</span><span class="sxs-lookup"><span data-stu-id="e4a9c-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="e4a9c-118">Importo trasporto</span><span class="sxs-lookup"><span data-stu-id="e4a9c-118">Freight Amount</span></span>
    + <span data-ttu-id="e4a9c-119">Totale imposta</span><span class="sxs-lookup"><span data-stu-id="e4a9c-119">Total Tax</span></span>
    + <span data-ttu-id="e4a9c-120">Importo totale</span><span class="sxs-lookup"><span data-stu-id="e4a9c-120">Total Amount</span></span>

## <a name="how-it-works"></a><span data-ttu-id="e4a9c-121">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="e4a9c-121">How it works</span></span>

<span data-ttu-id="e4a9c-122">Quando si seleziona **Prezzo ordine** in Sales, la funzione **Totali** nella scheda **Ordine di vendita \> Visualizza** in Supply Chain Management viene chiamata per l'ordine di vendita associato.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-122">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="e4a9c-123">I valori nel totale dell'ordine in Sales vengono utilizzati per compilare i campi corrispondenti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-123">The values in the order total in Sales are used to fill in the corresponding fields in Supply Chain Management.</span></span>

<span data-ttu-id="e4a9c-124">Quando il totale dell'ordine cliente viene calcolato in Supply Chain Management, il calcolo valuta gli accordi commerciali e gli accordi di vendita esistenti per il cliente e i prodotti elencati nell'ordine di vendita.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-124">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="e4a9c-125">Questa informazione viene utilizzata per calcolare i totali.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-125">This information is used to calculate the totals.</span></span> <span data-ttu-id="e4a9c-126">Quando **Prezzo ordine** è selezionato, Sales riflette automaticamente tutte le impostazioni applicate in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-126">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="e4a9c-127">Limiti</span><span class="sxs-lookup"><span data-stu-id="e4a9c-127">Limitations</span></span>

<span data-ttu-id="e4a9c-128">Quando i campi in Sales sono compilati, si applicano le seguenti limitazioni:</span><span class="sxs-lookup"><span data-stu-id="e4a9c-128">When the fields in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="e4a9c-129">L'impostazione degli addebiti e delle allocazioni degli addebiti in Supply Chain Management non viene replicata in Sales.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-129">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="e4a9c-130">Il prezzo non considera i prezzi al dettaglio speciali specificati nel campo **Canale al dettaglio** della pagina della riga ordine cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-130">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** field on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="e4a9c-131">Gli sconti definiti nella sezione **Gestione indennità commerciali** di Supply Chain Management non sono considerati.</span><span class="sxs-lookup"><span data-stu-id="e4a9c-131">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>
