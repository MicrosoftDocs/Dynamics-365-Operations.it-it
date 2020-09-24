---
title: Articoli di reso per più fatture e ordini cliente
description: In questo argomento viene descritta la funzionalità che consente di eseguire resi per più fatture e ordini cliente in Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: e95f06ffaaf2d250b02a8458faa2d9e0b5ef5631
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760252"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="9b78d-103">Articoli di reso per più fatture e ordini cliente</span><span class="sxs-lookup"><span data-stu-id="9b78d-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="9b78d-104">Questo articolo descrive due funzionalità che ottimizzano i resi degli ordini cliente su più fatture.</span><span class="sxs-lookup"><span data-stu-id="9b78d-104">This article describes two features that optimize customer order returns over multiple invoices.</span></span> 

## <a name="enable-refunds-over-multiple-captures"></a><span data-ttu-id="9b78d-105">Abilita rimborsi per più acquisizioni</span><span class="sxs-lookup"><span data-stu-id="9b78d-105">Enable refunds over multiple captures</span></span>

<span data-ttu-id="9b78d-106">Questa funzione consente più rimborsi collegati sullo stesso ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9b78d-106">This feature enables multiple linked refunds against the same customer order.</span></span> 

1. <span data-ttu-id="9b78d-107">Accedere all'area di lavoro **Gestione funzionalità** e cercare **Abilita rimborsi su più acquisizioni**.</span><span class="sxs-lookup"><span data-stu-id="9b78d-107">Go to the **Feature management** workspace and search for **Enable refunds over multiple captures**.</span></span>
2. <span data-ttu-id="9b78d-108">Selezionare **Abilita rimborsi su più ordini** e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="9b78d-108">Select **Enable refunds over multiple orders** and then click **Enable**.</span></span> 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a><span data-ttu-id="9b78d-109">Abilita il calcolo delle imposte corretto per i resi con quantità parziale</span><span class="sxs-lookup"><span data-stu-id="9b78d-109">Enable proper tax calculation for returns with partial quantity</span></span>

<span data-ttu-id="9b78d-110">Questa funzione garantisce che quando un ordine viene restituito utilizzando più fatture, le imposte saranno pari all'importo delle imposte addebitato in origine.</span><span class="sxs-lookup"><span data-stu-id="9b78d-110">This feature ensures that when an order is returned using multiple invoices, the taxes will ultimately be equal to the tax amount originally charged.</span></span> 

1. <span data-ttu-id="9b78d-111">Accedere all'area di lavoro **Gestione funzionalità** e cercare **Abilita il calcolo delle imposte corretto per i resi con quantità parziale**.</span><span class="sxs-lookup"><span data-stu-id="9b78d-111">Go to the **Feature management** workspace and search for **Enable proper tax calculation for returns with partial quantity**.</span></span>
2. <span data-ttu-id="9b78d-112">Selezionare **Abilita il calcolo delle imposte corretto per i resi con quantità parziale** e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="9b78d-112">Select **Enable proper tax calculation for returns with partial quantity** and then click **Enable**.</span></span> 


## <a name="process-returns"></a><span data-ttu-id="9b78d-113">Elaborare i resi</span><span class="sxs-lookup"><span data-stu-id="9b78d-113">Process returns</span></span>

<span data-ttu-id="9b78d-114">Dopo che queste funzionalità sono attivate e le modifiche vengono sincronizzate nei punti vendita, il cassiere nel punto vendita può selezionare più ordini cliente relativi a un cliente per il reso.</span><span class="sxs-lookup"><span data-stu-id="9b78d-114">After these features are turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="9b78d-115">Quando gli ordini sono selezionati, verrà visualizzato un elenco di tutti i prodotti restituibili in tutte le fatture per gli ordini.</span><span class="sxs-lookup"><span data-stu-id="9b78d-115">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="9b78d-116">A questo punto il cassiere può selezionare i prodotti da restituire.</span><span class="sxs-lookup"><span data-stu-id="9b78d-116">The cashier can then select the products to return.</span></span> <span data-ttu-id="9b78d-117">Un unico ordine di reso verrà creato per tutti i prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="9b78d-117">A single return order will be created for all the selected products.</span></span>

<span data-ttu-id="9b78d-118">Se l'ordine viene reso integralmente, l'importo delle imposte restituite al cliente sarà pari all'importo delle imposte addebitare in origine.</span><span class="sxs-lookup"><span data-stu-id="9b78d-118">If the order is fully returned, the amount of taxes returned to the customer will be equal to the amount of tax originally charged.</span></span>

