---
title: Funzionalità rimosse o deprecate in Dynamics 365 Commerce
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335278"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="43823-103">Funzionalità rimosse o deprecate in Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="43823-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43823-104">In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="43823-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="43823-105">Una funzionalità *rimossa* non è più disponibile nel prodotto.</span><span class="sxs-lookup"><span data-stu-id="43823-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="43823-106">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="43823-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="43823-107">Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="43823-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="43823-108">Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="43823-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="43823-109">È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="43823-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="43823-110">Funzionalità rimosse o deprecate nella versione Commerce 10.0.10</span><span class="sxs-lookup"><span data-stu-id="43823-110">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="43823-111">Operazione POS 803 - Fare clic su Prelievo e ricevimento</span><span class="sxs-lookup"><span data-stu-id="43823-111">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="43823-112">**Motivo del deprecamento/rimozione**</span><span class="sxs-lookup"><span data-stu-id="43823-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="43823-113">Le operazioni di prelievo e ricevimento sono deprecate a causa della ridefinizione di nuove operazioni.</span><span class="sxs-lookup"><span data-stu-id="43823-113">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="43823-114">**Sostituita da un'altra funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="43823-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="43823-115">Sì.</span><span class="sxs-lookup"><span data-stu-id="43823-115">Yes.</span></span> <span data-ttu-id="43823-116">È sostituita da due nuove operazioni POS: operazione in entrata (804) e operazione in uscita (805).</span><span class="sxs-lookup"><span data-stu-id="43823-116">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="43823-117">**Aree del prodotto interessate**</span><span class="sxs-lookup"><span data-stu-id="43823-117">**Product areas affected**</span></span>         | <span data-ttu-id="43823-118">Applicazione POS (Point of sale)</span><span class="sxs-lookup"><span data-stu-id="43823-118">Point of sale (POS) application</span></span> |
| <span data-ttu-id="43823-119">**Opzione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="43823-119">**Deployment option**</span></span>              | <span data-ttu-id="43823-120">Tutti</span><span class="sxs-lookup"><span data-stu-id="43823-120">All</span></span> |
| <span data-ttu-id="43823-121">**Stato**</span><span class="sxs-lookup"><span data-stu-id="43823-121">**Status**</span></span>                         | <span data-ttu-id="43823-122">Deprecata: dalla versione 10.0.10 l'operazione di prelievo e ricevimento non riceverà più alcun nuovo aggiornamento delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="43823-122">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="43823-123">Solo le correzioni di bug critici verranno eseguite per questa operazione nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="43823-123">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="43823-124">Tutti i clienti sono incoraggiati a passare alle nuove [operazioni in entrata](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) e [operazioni in uscita](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), che continueranno a far parte della nostra roadmap di prodotti a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="43823-124">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="43823-125">Funzionalità rimosse o deprecate nella versione Commerce 10.0.7</span><span class="sxs-lookup"><span data-stu-id="43823-125">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="43823-126">API Commerce GetProductAvailabilities e GetAvailableInventoryNearby</span><span class="sxs-lookup"><span data-stu-id="43823-126">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="43823-127">**Motivo del deprecamento/rimozione**</span><span class="sxs-lookup"><span data-stu-id="43823-127">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="43823-128">Nuove API ottimizzate sono state create per sostituire le API GetProductAvailabilities e GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="43823-128">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="43823-129">**Sostituita da un'altra funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="43823-129">**Replaced by another feature?**</span></span>   | <span data-ttu-id="43823-130">Sì: sostituzione tramite le API GetEstimatedAvailabilty e GetEstimatedProductWarehouseAvailability.</span><span class="sxs-lookup"><span data-stu-id="43823-130">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="43823-131">**Aree del prodotto interessate**</span><span class="sxs-lookup"><span data-stu-id="43823-131">**Product areas affected**</span></span>         | <span data-ttu-id="43823-132">SDK dell'applicazione e-Commerce</span><span class="sxs-lookup"><span data-stu-id="43823-132">e-Commerce application SDK</span></span> |
| <span data-ttu-id="43823-133">**Opzione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="43823-133">**Deployment option**</span></span>              | <span data-ttu-id="43823-134">Tutti</span><span class="sxs-lookup"><span data-stu-id="43823-134">All</span></span> |
| <span data-ttu-id="43823-135">**Stato**</span><span class="sxs-lookup"><span data-stu-id="43823-135">**Status**</span></span>                         | <span data-ttu-id="43823-136">Obsoleta: dalla versione 10.0.7 non verranno più eseguiti gli investimenti tecnici messi in atto per GetProductAvailabilities e GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="43823-136">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="43823-137">Le organizzazioni che utilizzano queste API nelle loro distribuzioni e-Commerce devono passare alle nuove API GetEstimatedAvailability e GetEstimatedProductWarehouseAvailability e abilitare la [funzionalità di calcolo della disponibilità del prodotto ottimizzata](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="43823-137">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="43823-138">Annunci precedenti sulle funzionalità rimosse o deprecate</span><span class="sxs-lookup"><span data-stu-id="43823-138">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="43823-139">Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="43823-139">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
