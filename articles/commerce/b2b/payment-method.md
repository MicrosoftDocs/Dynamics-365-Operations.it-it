---
title: Configurare il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B
description: Questo argomento descrive come configurare il metodo di pagamento del conto cliente per i siti di e-commerce business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 82dfd6ac7e97d838ef442fd6ded4a4f165fc795b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211203"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a><span data-ttu-id="92719-103">Configurare il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="92719-103">Configure the customer account payment method for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="92719-104">Questo argomento descrive come configurare il metodo di pagamento del conto cliente per i siti di e-commerce business-to-business (B2B).</span><span class="sxs-lookup"><span data-stu-id="92719-104">This topic describes how to configure the customer account payment method for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="92719-105">I rivenditori possono accettare diversi tipi di pagamento per i prodotti venduti e i servizi forniti in un canale di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="92719-105">Retailers can accept various types of payment in exchange for the products and services that they sell in an e-commerce channel.</span></span> <span data-ttu-id="92719-106">Ogni tipo di pagamento accettato da un rivenditore deve essere configurato in Microsoft Dynamics 365 Commerce quando si imposta il sistema.</span><span class="sxs-lookup"><span data-stu-id="92719-106">Each payment type that a retailer accepts must be configured in Microsoft Dynamics 365 Commerce when the system is set up.</span></span> <span data-ttu-id="92719-107">Il metodo di pagamento del conto cliente (o "in acconto") deve essere supportato sui siti di e-commerce B2B.</span><span class="sxs-lookup"><span data-stu-id="92719-107">The customer account (or "on account") payment method must be supported on B2B e-commerce sites.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="92719-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="92719-108">Prerequisites</span></span>

1. <span data-ttu-id="92719-109">Aggiungi il metodo di pagamento del conto cliente in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="92719-109">Add the customer account payment method in Commerce headquarters.</span></span>
2. <span data-ttu-id="92719-110">Associa il metodo di pagamento del conto cliente al canale di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="92719-110">Associate the customer account payment method with the e-commerce channel.</span></span>
3. <span data-ttu-id="92719-111">Assicurati che **Consenti in acconto** sia abilitato per il cliente in **Retail e Commerce \> Clienti \> Tutti i clienti \> Impostazioni predefinite pagamento** in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="92719-111">Make sure that **Allow on account** is enabled for the customer at **Retail and Commerce \> Customers \> All customers \> Payment defaults** in Commerce headquarters.</span></span> <span data-ttu-id="92719-112">Assicurati anche che i parametri **Limite di credito** siano impostati in modo appropriato per il cliente in **Retail e Commerce \> Clienti \> Tutti i clienti \> Credito e riscossioni** in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="92719-112">Also make sure that **Credit limit** parameters are set appropriately for the customer at **Retail and Commerce \> Customers \> All customers \> Credit and Collections** in Commerce headquarters.</span></span> 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a><span data-ttu-id="92719-113">Abilitare il metodo di pagamento del conto cliente in Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="92719-113">Enable the customer account payment method in Commerce site builder</span></span> 

<span data-ttu-id="92719-114">Per abilitare il metodo di pagamento del conto cliente in Creazione di siti di Commerce, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="92719-114">To enable the customer account payment method in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="92719-115">Vai a **Impostazioni sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="92719-115">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="92719-116">Imposta la proprietà **Abilita pagamenti conto cliente** su **Abilitato per clienti B2B**.</span><span class="sxs-lookup"><span data-stu-id="92719-116">Set the **Enable customer account payments** property to **Enabled for B2B customers**.</span></span> 
1. <span data-ttu-id="92719-117">Selezionare **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="92719-117">Select **Save and Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="92719-118">Le nuove impostazioni del sito avranno effetto solo dopo l'aggiornamento del file app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="92719-118">The new site settings take effect only after the app.settings.json file is updated.</span></span> <span data-ttu-id="92719-119">Per ulteriori informazioni, vedi [SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md).</span><span class="sxs-lookup"><span data-stu-id="92719-119">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md).</span></span>

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a><span data-ttu-id="92719-120">Abilitare il metodo di pagamento del conto cliente nella pagina di pagamento del sito di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="92719-120">Enable the customer account payment method on the checkout page for the B2B e-commerce site</span></span>

<span data-ttu-id="92719-121">Per abilitare il metodo di pagamento del conto cliente nella pagina di pagamento del sito di e-commerce B2B, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="92719-121">To enable the customer account payment method on the checkout page for the B2B e-commerce site, follow these steps.</span></span>

1. <span data-ttu-id="92719-122">In Creazione di siti di Commerce, trova e modifica la pagina di pagamento o il frammento che contiene il modulo di pagamento per il sito di e-commerce B2B.</span><span class="sxs-lookup"><span data-stu-id="92719-122">In Commerce site builder, find and edit the checkout page or fragment that contains the checkout module for the B2B e-commerce site.</span></span>
1. <span data-ttu-id="92719-123">Nello slot **Contenitore sezione checkout**, seleziona **Aggiungi modulo**, quindi aggiungi un modulo **Pagamento conto cliente**.</span><span class="sxs-lookup"><span data-stu-id="92719-123">In the **Checkout section container** slot, select **Add Module**, and then add a **Customer account payment** module.</span></span>
1. <span data-ttu-id="92719-124">Posiziona il modulo **Pagamento conto cliente** selezionando i puntini di sospensione (**...**), quindi selezionando **Sposta su** o **Sposta giù** come necessario.</span><span class="sxs-lookup"><span data-stu-id="92719-124">Position the **Customer account payment** module by selecting the ellipsis (**...**), and then selecting **Move Up** or **Move Down** as required.</span></span>
1. <span data-ttu-id="92719-125">Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="92719-125">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a><span data-ttu-id="92719-126">Verificare che il metodo di pagamento del conto cliente sia stato abilitato e pubblicato</span><span class="sxs-lookup"><span data-stu-id="92719-126">Confirm that the customer account payment method has been enabled and published</span></span>

<span data-ttu-id="92719-127">Per verificare che il metodo di pagamento del conto cliente sia stato abilitato e pubblicato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="92719-127">To confirm that the customer account payment method has been enabled, follow these steps.</span></span>

1. <span data-ttu-id="92719-128">Accedi al sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="92719-128">Sign in to the e-commerce site.</span></span>
1. <span data-ttu-id="92719-129">Aggiungi un prodotto al carrello.</span><span class="sxs-lookup"><span data-stu-id="92719-129">Add a product to the cart.</span></span>
1. <span data-ttu-id="92719-130">Vai alla pagina di pagamento.</span><span class="sxs-lookup"><span data-stu-id="92719-130">Go to the checkout page.</span></span> <span data-ttu-id="92719-131">Dovresti vedere il nuovo metodo di pagamento **Conto cliente**.</span><span class="sxs-lookup"><span data-stu-id="92719-131">You should see the new **Customer Account** payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92719-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="92719-132">Additional resources</span></span>

[<span data-ttu-id="92719-133">Impostare un sito di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="92719-133">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="92719-134">Creare gerarchie di modellazione per le organizzazioni B2B</span><span class="sxs-lookup"><span data-stu-id="92719-134">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="92719-135">Gestisci gli utenti dei partner commerciali sui siti di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="92719-135">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="92719-136">Impostare limiti di quantità di prodotti per i siti di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="92719-136">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)

[<span data-ttu-id="92719-137">SDK e aggiornamenti libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="92719-137">SDK and Module library updates</span></span>](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]