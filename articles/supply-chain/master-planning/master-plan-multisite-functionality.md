---
title: Panoramica della pianificazione generale e delle funzionalità multisito
description: Nella pianificazione generale devono essere prese in considerazione le impostazioni delle dimensioni inventariali relative al sito e al magazzino.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da8db87f44c974b3fee8e249e318669ca8e9f2b8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220826"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="f9fda-103">Panoramica della pianificazione generale e delle funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="f9fda-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9fda-104">Nella pianificazione generale devono essere prese in considerazione le impostazioni delle dimensioni inventariali relative al sito e al magazzino.</span><span class="sxs-lookup"><span data-stu-id="f9fda-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="f9fda-105">La dimensione sito è obbligatoria ed è possibile impostare la dimensione magazzino come obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="f9fda-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="f9fda-106">Quando una dimensione è obbligatoria, è necessario immettere un valore di dimensione in tutte le operazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="f9fda-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="f9fda-107">Pertanto, durante la pianificazione principale, il sito e il magazzino per la domanda iniziale sono noti.</span><span class="sxs-lookup"><span data-stu-id="f9fda-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="f9fda-108">La dimensione sito è inoltre una dimensione coerente. Di conseguenza, durante l'esplosione della domanda a livello inferiore, il valore del sito rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="f9fda-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="f9fda-109">Quando invece il magazzino non è impostato come obbligatorio, potrebbe non essere ricavabile dalla domanda iniziale.</span><span class="sxs-lookup"><span data-stu-id="f9fda-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="f9fda-110">Il motore di pianificazione dovrà determinare il magazzino da utilizzare in base alle impostazioni definite per l'articolo, i singoli magazzini e i dettagli della riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="f9fda-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="f9fda-111">Negli argomenti riportati di seguito viene descritta la logica in base alla quale il motore di pianificazione determina il magazzino da utilizzare a seconda delle impostazioni definite.</span><span class="sxs-lookup"><span data-stu-id="f9fda-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="f9fda-112">Pianificazione generale a livello di sito e magazzino, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f9fda-112">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f9fda-113">Pianificazione generale per copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f9fda-113">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f9fda-114">Pianificazione generale a livello di sito e magazzino, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f9fda-114">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f9fda-115">Pianificazione generale per copertura a livello di sito, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f9fda-115">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f9fda-116">Determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="f9fda-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]