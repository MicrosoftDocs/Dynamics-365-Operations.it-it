---
title: Articoli di reso in più fatture e ordini cliente
description: In questo argomento viene descritta la funzionalità che consente di eseguire resi in più fatture e ordini cliente in Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
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
ms.openlocfilehash: 25a1081e5f903076e23089c41dda7437f8a70124
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017991"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="2eda3-103">Articoli di reso in più fatture e ordini cliente</span><span class="sxs-lookup"><span data-stu-id="2eda3-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="2eda3-104">I resi possono essere effettuati in più fatture e ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="2eda3-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="2eda3-105">Configurare Retail per supportare i resi in più fatture e ordini cliente</span><span class="sxs-lookup"><span data-stu-id="2eda3-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="2eda3-106">Andare a **Parametri di vendita al dettaglio \> Ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="2eda3-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="2eda3-107">Attivare il parametro **Consenti resi per più ordini**.</span><span class="sxs-lookup"><span data-stu-id="2eda3-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="2eda3-108">Elaborare i resi</span><span class="sxs-lookup"><span data-stu-id="2eda3-108">Process returns</span></span>

<span data-ttu-id="2eda3-109">Dopo che il parametro è attivato e le modifiche vengono sincronizzate nei punti vendita, il cassiere nel punto vendita può selezionare più ordini cliente relativi a un cliente per il reso.</span><span class="sxs-lookup"><span data-stu-id="2eda3-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="2eda3-110">Quando gli ordini sono selezionati, verrà visualizzato un elenco di tutti i prodotti restituibili in tutte le fatture per gli ordini.</span><span class="sxs-lookup"><span data-stu-id="2eda3-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="2eda3-111">A questo punto il cassiere può selezionare i prodotti da restituire.</span><span class="sxs-lookup"><span data-stu-id="2eda3-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="2eda3-112">Un unico ordine di reso verrà creato per tutti i prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="2eda3-112">A single return order will be created for all the selected products.</span></span>
