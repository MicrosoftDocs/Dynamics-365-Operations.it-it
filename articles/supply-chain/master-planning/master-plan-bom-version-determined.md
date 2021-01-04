---
title: Determinare la versione DBA
description: Durante un'esplosione della domanda, se per un articolo è impostato il tipo di ordine predefinito Produzione, il motore di pianificazione identifica una versione DBA valida in base al sito,
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 766c857cca603f84bb7fcef2c7eea3bc76620c19
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431387"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="10ad3-103">Determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="10ad3-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="10ad3-104">Durante un'esplosione della domanda, se per un articolo è impostato il tipo di ordine predefinito Produzione, il motore di pianificazione identifica una versione DBA valida in base al sito,</span><span class="sxs-lookup"><span data-stu-id="10ad3-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="10ad3-105">La dimensione sito è sempre nota ed è indicata nella transazione della domanda.</span><span class="sxs-lookup"><span data-stu-id="10ad3-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="10ad3-106">Di seguito è illustrato il processo in base al quale viene determinata la versione DBA da utilizzare:</span><span class="sxs-lookup"><span data-stu-id="10ad3-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="10ad3-107">Se nel sito della domanda è definita una versione DBA per l'articolo, verrà utilizzata la DBA specifica del sito.</span><span class="sxs-lookup"><span data-stu-id="10ad3-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="10ad3-108">Se invece per l'articolo non è definita una versione DBA specifica del sito, verrà utilizzata una DBA generale,</span><span class="sxs-lookup"><span data-stu-id="10ad3-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="10ad3-109">ovvero una DBA valida per più siti.</span><span class="sxs-lookup"><span data-stu-id="10ad3-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="10ad3-110">Se presente, verrà utilizzata la DBA generale.</span><span class="sxs-lookup"><span data-stu-id="10ad3-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="10ad3-111">Se non è presente una versione DBA da utilizzare, l'esplosione della domanda verrà interrotta in questo punto.</span><span class="sxs-lookup"><span data-stu-id="10ad3-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="10ad3-112">Una versione DBA valida, generale o specifica di un sito, deve soddisfare i criteri relativi alla data e alla quantità.</span><span class="sxs-lookup"><span data-stu-id="10ad3-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>





