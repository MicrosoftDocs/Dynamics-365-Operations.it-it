---
title: Sincronizzare su richiesta con il motore di determinazione del prezzo di Supply Chain Management
description: Questo argomento descrive come utilizzare il motore di determinazione del prezzo in Microsoft Dynamics 365 Supply Chain Management da Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: e2067e83d3f0c98e986873b8eaf1b817de912c0f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570142"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a><span data-ttu-id="5a3f1-103">Sincronizzare su richiesta con il motore di determinazione del prezzo di Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="5a3f1-103">Sync on-demand with the Supply Chain Management pricing engine</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="5a3f1-104">Microsoft Dynamics 365 Supply Chain Management include un motore di determinazione del prezzo che gestisce accordi commerciali, listini prezzi, programmi di fidelizzazione dei clienti, promozioni e sconti.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="5a3f1-105">Il motore di determinazione del prezzo utilizza regole complesse per determinare il prezzo migliore per un determinato preventivo od ordine.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="5a3f1-106">Quando si utilizza la doppia scrittura, si usa il prezzo statico o il motore di determinazione dei prezzi da Dynamics 365 Supply Chain Management nelle pagine Offerta e Ordine in Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="5a3f1-107">Utilizzare il motore di determinazione dei prezzi da Supply Chain Management in Sales</span><span class="sxs-lookup"><span data-stu-id="5a3f1-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="5a3f1-108">In Sales, andare a **Vendite \> Ordini**.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="5a3f1-109">Selezionare **Nuovo** per creare un nuovo ordine o selezionare un ordine esistente nell'elenco **Ordini personali**.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="5a3f1-110">Aggiungere una nuova riga ordine.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-110">Add a new order line.</span></span>
4. <span data-ttu-id="5a3f1-111">Se stai creando un nuovo ordine, selezionare **Prezzo ordine** nel riquadro Azione.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="5a3f1-112">Se stai aggiornando un ordine esistente, selezionare **Ricalcola** nel riquadro Azione.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="5a3f1-113">Le colonne riportate di seguito vengono automaticamente popolate:</span><span class="sxs-lookup"><span data-stu-id="5a3f1-113">The following columns are automatically filled in:</span></span>

    + <span data-ttu-id="5a3f1-114">Dettagli importo</span><span class="sxs-lookup"><span data-stu-id="5a3f1-114">Detail Amount</span></span>
    + <span data-ttu-id="5a3f1-115">% sconto</span><span class="sxs-lookup"><span data-stu-id="5a3f1-115">Discount %</span></span>
    + <span data-ttu-id="5a3f1-116">Sconto</span><span class="sxs-lookup"><span data-stu-id="5a3f1-116">Discount</span></span>
    + <span data-ttu-id="5a3f1-117">Importo pre-trasporto</span><span class="sxs-lookup"><span data-stu-id="5a3f1-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="5a3f1-118">Importo trasporto</span><span class="sxs-lookup"><span data-stu-id="5a3f1-118">Freight Amount</span></span>
    + <span data-ttu-id="5a3f1-119">Totale imposta</span><span class="sxs-lookup"><span data-stu-id="5a3f1-119">Total Tax</span></span>
    + <span data-ttu-id="5a3f1-120">Importo totale</span><span class="sxs-lookup"><span data-stu-id="5a3f1-120">Total Amount</span></span>
    
5. <span data-ttu-id="5a3f1-121">Per assicurarsi che il sistema consideri gli accordi per i contratti di vendita per calcolare il prezzo:</span><span class="sxs-lookup"><span data-stu-id="5a3f1-121">To ensure that the system considers trade and sales agreements to calculate the price:</span></span>
    1. <span data-ttu-id="5a3f1-122">Accedere all'ambiente Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-122">Navigate to your Supply Chain Management environment.</span></span>
    2. <span data-ttu-id="5a3f1-123">Spostarsi su **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-123">Navigate to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    3. <span data-ttu-id="5a3f1-124">Selezionare la scheda **Prezzi** nella barra di spostamento laterale.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-124">Select the **Prices** tab in the side navigation bar.</span></span>
    4. <span data-ttu-id="5a3f1-125">Sotto la scheda dettaglio **Valutazione dell'accordo commerciale**, deselezionare l'opzione **Immissione manuale**.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-125">Under the **Trade agreement evaluation** fastab, uncheck the **Manual entry** option.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="5a3f1-126">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="5a3f1-126">How it works</span></span>

<span data-ttu-id="5a3f1-127">Quando si seleziona **Prezzo ordine** in Sales, la funzione **Totali** nella scheda **Ordine di vendita \> Visualizza** in Supply Chain Management viene chiamata per l'ordine di vendita associato.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-127">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="5a3f1-128">I valori nel totale dell'ordine in Sales vengono utilizzati per compilare le colonne corrispondenti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-128">The values in the order total in Sales are used to fill in the corresponding columns in Supply Chain Management.</span></span>

<span data-ttu-id="5a3f1-129">Quando il totale dell'ordine cliente viene calcolato in Supply Chain Management, il calcolo valuta gli accordi commerciali e gli accordi di vendita esistenti per il cliente e i prodotti elencati nell'ordine di vendita.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-129">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="5a3f1-130">Questa informazione viene utilizzata per calcolare i totali.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-130">This information is used to calculate the totals.</span></span> <span data-ttu-id="5a3f1-131">Quando **Prezzo ordine** è selezionato, Sales riflette automaticamente tutte le impostazioni applicate in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-131">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="5a3f1-132">Limiti</span><span class="sxs-lookup"><span data-stu-id="5a3f1-132">Limitations</span></span>

<span data-ttu-id="5a3f1-133">Quando le colonne in Sales sono compilate, si applicano le seguenti limitazioni:</span><span class="sxs-lookup"><span data-stu-id="5a3f1-133">When the columns in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="5a3f1-134">L'impostazione degli addebiti e delle allocazioni degli addebiti in Supply Chain Management non viene replicata in Sales.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-134">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="5a3f1-135">Il prezzo non considera i prezzi al dettaglio speciali specificati nella colonna **Canale al dettaglio** della pagina della riga ordine cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-135">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** column on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="5a3f1-136">Gli sconti definiti nella sezione **Gestione indennità commerciali** di Supply Chain Management non sono considerati.</span><span class="sxs-lookup"><span data-stu-id="5a3f1-136">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]