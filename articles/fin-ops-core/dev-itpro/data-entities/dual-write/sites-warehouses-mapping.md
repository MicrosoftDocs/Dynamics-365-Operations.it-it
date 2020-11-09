---
title: Siti e magazzini integrati
description: In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: d5c2030160f6025c9de63b2c29215364f5f87e6f
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997626"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="c581f-103">Siti e magazzini integrati</span><span class="sxs-lookup"><span data-stu-id="c581f-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="c581f-104">In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c581f-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="c581f-105">I siti e magazzini operativi sono concetti comuni in un'applicazione di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c581f-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="c581f-106">Questi vengono utilizzati per modellare la catena di approvvigionamento della società.</span><span class="sxs-lookup"><span data-stu-id="c581f-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="c581f-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="c581f-107">Templates</span></span>

<span data-ttu-id="c581f-108">Grazie all'integrazione con Common Data Service, tali concetti e tutte le informazioni correlate sono disponibili in Common Data Service utilizzando le entità di dati di siti e magazzini nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c581f-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="c581f-109">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c581f-109">Finance and Operations apps</span></span> | <span data-ttu-id="c581f-110">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c581f-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="c581f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c581f-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="c581f-112">Siti</span><span class="sxs-lookup"><span data-stu-id="c581f-112">Sites</span></span> | <span data-ttu-id="c581f-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="c581f-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="c581f-114">Magazzini</span><span class="sxs-lookup"><span data-stu-id="c581f-114">Warehouses</span></span> | <span data-ttu-id="c581f-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="c581f-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

