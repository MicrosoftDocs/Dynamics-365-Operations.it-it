---
title: Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps
description: In questo articolo viene descritto come procedere se l'amministratore non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 68e6dbcbbc9811211570e968047f5faa8a2c8bd0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419175"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="c75d2-103">Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps</span><span class="sxs-lookup"><span data-stu-id="c75d2-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="c75d2-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c75d2-104">**Issue**</span></span>

- <span data-ttu-id="c75d2-105">L'amministratore di ambiente/tenant non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c75d2-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="c75d2-106">Una licenza che concede agli utenti il diritto di eseguire l'operazione di creazione dell'ambiente non è stata assegnata direttamente all'utente che esegue quell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c75d2-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="c75d2-107">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="c75d2-107">**Solution**</span></span>

<span data-ttu-id="c75d2-108">Verificare che l'amministratore del tenant abbia assegnato una licenza Power Apps P2 valida direttamente all'utente che esegue l'operazione di creazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c75d2-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="c75d2-109">Di seguito sono riportati i piani del servizio Microsoft Dynamics che forniscono quel diritto.</span><span class="sxs-lookup"><span data-stu-id="c75d2-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="c75d2-110">Unità di stockkeeping (SKU) globale di un prodotto</span><span class="sxs-lookup"><span data-stu-id="c75d2-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="c75d2-111">Piano di servizio Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="c75d2-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="c75d2-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="c75d2-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="c75d2-113">Power Apps per Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c75d2-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="c75d2-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c75d2-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="c75d2-115">Power Apps per Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c75d2-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="c75d2-116">Da notare che oltre alle unità di stockkeeping di Power Apps Piano 2, anche varie unità di stockkeeping di Microsoft Office forniscono quel diritto.</span><span class="sxs-lookup"><span data-stu-id="c75d2-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="c75d2-117">L'aspetto importante è che una di queste unità di stockkeeping deve essere presente.</span><span class="sxs-lookup"><span data-stu-id="c75d2-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="c75d2-118">Accedere a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="c75d2-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="c75d2-119">Creare gli ambienti seguendo le istruzioni in [Eseguire il provisioning di Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="c75d2-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
