---
title: Pianificazione generale e funzionalità multisito
description: Nella pianificazione generale devono essere prese in considerazione le impostazioni delle dimensioni inventariali relative al sito e al magazzino.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10981e0fe201566c83fd28c792000865bc533cd3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573093"
---
# <a name="master-planning-and-multisite-functionality"></a><span data-ttu-id="e116f-103">Pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="e116f-103">Master planning and multisite functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e116f-104">Nella pianificazione generale devono essere prese in considerazione le impostazioni delle dimensioni inventariali relative al sito e al magazzino.</span><span class="sxs-lookup"><span data-stu-id="e116f-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="e116f-105">La dimensione sito è obbligatoria ed è possibile impostare la dimensione magazzino come obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="e116f-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="e116f-106">Quando una dimensione è obbligatoria, è necessario immettere un valore di dimensione in tutte le operazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="e116f-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="e116f-107">Pertanto, durante la pianificazione principale, il sito e il magazzino per la domanda iniziale sono noti.</span><span class="sxs-lookup"><span data-stu-id="e116f-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="e116f-108">La dimensione sito è inoltre una dimensione coerente. Di conseguenza, durante l'esplosione della domanda a livello inferiore, il valore del sito rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="e116f-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="e116f-109">Quando invece il magazzino non è impostato come obbligatorio, potrebbe non essere ricavabile dalla domanda iniziale.</span><span class="sxs-lookup"><span data-stu-id="e116f-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="e116f-110">Il motore di pianificazione dovrà determinare il magazzino da utilizzare in base alle impostazioni definite per l'articolo, i singoli magazzini e i dettagli della riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="e116f-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="e116f-111">Negli argomenti riportati di seguito viene descritta la logica in base alla quale il motore di pianificazione determina il magazzino da utilizzare a seconda delle impostazioni definite.</span><span class="sxs-lookup"><span data-stu-id="e116f-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="e116f-112">Pianificazione generale: copertura a livello di sito magazzino, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="e116f-112">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="e116f-113">Pianificazione generale: copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="e116f-113">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="e116f-114">Pianificazione generale: copertura a livello di sito magazzino, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="e116f-114">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="e116f-115">Pianificazione generale: copertura a livello di sito, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="e116f-115">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="e116f-116">Pianificazione generale - Come determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="e116f-116">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



