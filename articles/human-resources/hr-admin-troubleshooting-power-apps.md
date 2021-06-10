---
title: Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps
description: In questo articolo viene descritto come procedere se l'amministratore non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73c8910900ba6486a8e60a547b07ea0c82a6cb10
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053349"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="3dbba-103">Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps</span><span class="sxs-lookup"><span data-stu-id="3dbba-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3dbba-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3dbba-104">**Issue**</span></span>

- <span data-ttu-id="3dbba-105">L'amministratore di ambiente/tenant non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="3dbba-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="3dbba-106">L'utente non dispone di una licenza che dia il diritto di creare ambienti.</span><span class="sxs-lookup"><span data-stu-id="3dbba-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="3dbba-107">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="3dbba-107">**Solution**</span></span>

<span data-ttu-id="3dbba-108">Assicurati che l'amministratore del tenant abbia assegnato una licenza Power Apps P2 per l'utente che crea l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="3dbba-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="3dbba-109">I seguenti piani di servizio Microsoft Dynamics forniscono le autorizzazioni per creare ambienti:</span><span class="sxs-lookup"><span data-stu-id="3dbba-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="3dbba-110">Unità di stockkeeping (SKU) globale di un prodotto</span><span class="sxs-lookup"><span data-stu-id="3dbba-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="3dbba-111">Piano di servizio Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="3dbba-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="3dbba-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="3dbba-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="3dbba-113">Power Apps per Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3dbba-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="3dbba-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3dbba-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="3dbba-115">Power Apps per Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3dbba-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="3dbba-116">Da notare che oltre alle unità di stockkeeping di Power Apps Piano 2, anche varie unità di stockkeeping di Microsoft Office forniscono quel diritto.</span><span class="sxs-lookup"><span data-stu-id="3dbba-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="3dbba-117">L'aspetto importante è che una di queste unità di stockkeeping deve essere presente.</span><span class="sxs-lookup"><span data-stu-id="3dbba-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="3dbba-118">Accedere a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="3dbba-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="3dbba-119">Creare gli ambienti seguendo le istruzioni in [Eseguire il provisioning di Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="3dbba-119">Create the environments by following the instructions in [Provision Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]