---
title: Articoli di reso per più fatture e ordini cliente
description: In questo argomento viene descritta la funzionalità che consente di eseguire resi per più fatture e ordini cliente in Dynamics 365 Commerce.
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
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004460"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="49d8b-103">Articoli di reso per più fatture e ordini cliente</span><span class="sxs-lookup"><span data-stu-id="49d8b-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="49d8b-104">I resi possono essere effettuati per più fatture e ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="49d8b-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="49d8b-105">Configurare Commerce per supportare i resi per più fatture e ordini cliente</span><span class="sxs-lookup"><span data-stu-id="49d8b-105">Configure Commerce to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="49d8b-106">Andare a **Parametri di commercio \> Ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="49d8b-106">Go to **Commerce parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="49d8b-107">Attivare il parametro **Consenti resi per più ordini**.</span><span class="sxs-lookup"><span data-stu-id="49d8b-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="49d8b-108">Elaborare i resi</span><span class="sxs-lookup"><span data-stu-id="49d8b-108">Process returns</span></span>

<span data-ttu-id="49d8b-109">Dopo che il parametro è attivato e le modifiche vengono sincronizzate nei punti vendita, il cassiere nel punto vendita può selezionare più ordini cliente relativi a un cliente per il reso.</span><span class="sxs-lookup"><span data-stu-id="49d8b-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="49d8b-110">Quando gli ordini sono selezionati, verrà visualizzato un elenco di tutti i prodotti restituibili in tutte le fatture per gli ordini.</span><span class="sxs-lookup"><span data-stu-id="49d8b-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="49d8b-111">A questo punto il cassiere può selezionare i prodotti da restituire.</span><span class="sxs-lookup"><span data-stu-id="49d8b-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="49d8b-112">Un unico ordine di reso verrà creato per tutti i prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="49d8b-112">A single return order will be created for all the selected products.</span></span>
