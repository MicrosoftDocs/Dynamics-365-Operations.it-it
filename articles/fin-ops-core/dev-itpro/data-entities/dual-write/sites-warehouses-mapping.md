---
title: Siti e magazzini integrati
description: In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Dataverse.
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
ms.openlocfilehash: d192343d78f9248e4d1232d6aee1a1f800383805
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679322"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="cc83b-103">Siti e magazzini integrati</span><span class="sxs-lookup"><span data-stu-id="cc83b-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="cc83b-104">In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc83b-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="cc83b-105">I siti e magazzini operativi sono concetti comuni in un'applicazione di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cc83b-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="cc83b-106">Questi vengono utilizzati per modellare la catena di approvvigionamento della società.</span><span class="sxs-lookup"><span data-stu-id="cc83b-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="cc83b-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="cc83b-107">Templates</span></span>

<span data-ttu-id="cc83b-108">Grazie all'integrazione con Dataverse, tali concetti e tutte le informazioni correlate sono disponibili in Dataverse utilizzando le tabelle di dati di siti e magazzini nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cc83b-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="cc83b-109">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cc83b-109">Finance and Operations apps</span></span> | <span data-ttu-id="cc83b-110">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="cc83b-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="cc83b-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="cc83b-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="cc83b-112">Siti</span><span class="sxs-lookup"><span data-stu-id="cc83b-112">Sites</span></span> | <span data-ttu-id="cc83b-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="cc83b-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="cc83b-114">Magazzini</span><span class="sxs-lookup"><span data-stu-id="cc83b-114">Warehouses</span></span> | <span data-ttu-id="cc83b-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="cc83b-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

