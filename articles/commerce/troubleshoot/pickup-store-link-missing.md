---
title: L'opzione Ritira non appare nella pagina del carrello o nelle pagine dei dettagli del prodotto
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'opzione per il ritiro presso il punto vendita non viene visualizzata nella pagina del carrello o nelle pagine dei dettagli del prodotto.
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
ms.openlocfilehash: f692d73bf1755422e9bfc8314c1156e043ccf761
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020810"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="21925-103">L'opzione "Ritira" non appare nella pagina del carrello o in quelle dei dettagli del prodotto</span><span class="sxs-lookup"><span data-stu-id="21925-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="21925-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'opzione per il ritiro presso il punto vendita non viene visualizzata nella pagina del carrello o nelle pagine dei dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="21925-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="21925-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21925-105">Description</span></span>

<span data-ttu-id="21925-106">Il pulsante **Ritira** non appare nella pagina del carrello o nelle pagine dei dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="21925-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="21925-107">La figura seguente mostra un esempio di una pagina che include il pulsante **Ritira**.</span><span class="sxs-lookup"><span data-stu-id="21925-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Pulsante Ritira](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="21925-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="21925-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="21925-110">Abilitare l'estensione BOPIS in Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="21925-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="21925-111">Per abilitare l'estensione "acquisto online, ritiro in negozio" (BOPIS) in Creazione di siti di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="21925-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="21925-112">Selezionare il sito.</span><span class="sxs-lookup"><span data-stu-id="21925-112">Select your site.</span></span>
1. <span data-ttu-id="21925-113">Selezionare **Impostazioni sito**, quindi selezionare **Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="21925-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="21925-114">Assicurarsi che l'opzione **Disabilita BOPIS** sia deselezionata.</span><span class="sxs-lookup"><span data-stu-id="21925-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="21925-115">Configurare le modalità di consegna in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="21925-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="21925-116">Per configurare modalità di consegna in Commerce Headquarters, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="21925-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="21925-117">Selezionare **Approvvigionamento \> Impostazione \> Modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="21925-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="21925-118">Assicurarsi che una modalità di consegna **Ritiro del cliente** sia stata creata e che alla stessa siano assegnati prodotti e indirizzi.</span><span class="sxs-lookup"><span data-stu-id="21925-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="21925-119">Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri**.</span><span class="sxs-lookup"><span data-stu-id="21925-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="21925-120">Nel riquadro di spostamento sinistro, selezionare **Ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="21925-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="21925-121">Assicurarsi che l'opzione **Modalità di consegna ritiro** sia configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="21925-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="21925-122">Configurare i pagamenti di ordini cliente</span><span class="sxs-lookup"><span data-stu-id="21925-122">Configure customer orders payments</span></span>

<span data-ttu-id="21925-123">Per configurare i pagamenti di ordini cliente in Commerce Headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="21925-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="21925-124">Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri**.</span><span class="sxs-lookup"><span data-stu-id="21925-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="21925-125">Nel riquadro di spostamento sinistro, selezionare **Ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="21925-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="21925-126">Nella Scheda dettaglio **Pagamenti**, assicurarsi che i campi **Termini di pagamento** e **Metodo di pagamento** siano impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="21925-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21925-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="21925-127">Additional resources</span></span>

[<span data-ttu-id="21925-128">Configurare l'estensione BOPIS</span><span class="sxs-lookup"><span data-stu-id="21925-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="21925-129">Abilitare più modalità di consegna ritiro per gli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="21925-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="21925-130">Pagamenti ordini Commerce multicanale</span><span class="sxs-lookup"><span data-stu-id="21925-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="21925-131">Memorizzare il modulo di selezione</span><span class="sxs-lookup"><span data-stu-id="21925-131">Store selector module</span></span>](../store-selector.md)
