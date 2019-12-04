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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 4cf402e2811aaf92ddfa78eaf6d8887d88d93cbc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770992"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="61925-103">Siti e magazzini integrati</span><span class="sxs-lookup"><span data-stu-id="61925-103">Integrated sites and warehouses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61925-104">In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="61925-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="61925-105">I siti e magazzini operativi sono concetti comuni in un'applicazione di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="61925-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="61925-106">Questi vengono utilizzati per modellare la catena di approvvigionamento della società.</span><span class="sxs-lookup"><span data-stu-id="61925-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="61925-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="61925-107">Templates</span></span>

<span data-ttu-id="61925-108">Grazie all'integrazione con Common Data Service, tali concetti e tutte le informazioni correlate sono disponibili in Common Data Service utilizzando le entità di dati di siti e magazzini nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="61925-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="61925-109">App Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="61925-109">Finance and Operations apps</span></span> | <span data-ttu-id="61925-110">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="61925-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="61925-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61925-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="61925-112">Siti</span><span class="sxs-lookup"><span data-stu-id="61925-112">Sites</span></span> | <span data-ttu-id="61925-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="61925-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="61925-114">Magazzini</span><span class="sxs-lookup"><span data-stu-id="61925-114">Warehouses</span></span> | <span data-ttu-id="61925-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="61925-115">msdyn_warehouses</span></span> | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

