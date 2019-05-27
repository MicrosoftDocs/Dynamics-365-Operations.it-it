---
title: Non è possibile creare un ambiente nell'interfaccia di amministrazione di PowerApps
description: In questo argomento viene descritto come procedere se l'amministratore non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft PowerApps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 97d44dc034cb8097fc0ecf9ac4e485425f097102
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518327"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a><span data-ttu-id="79f28-103">Non è possibile creare un ambiente nell'interfaccia di amministrazione di PowerApps</span><span class="sxs-lookup"><span data-stu-id="79f28-103">Can't create an environment in the PowerApps Admin center</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="79f28-104">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="79f28-104">**Issue**</span></span>

- <span data-ttu-id="79f28-105">L'amministratore di ambiente/tenant non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="79f28-105">The tenant/environment admin can't create an environment in the Microsoft PowerApps Admin center.</span></span>
- <span data-ttu-id="79f28-106">Una licenza che concede agli utenti il diritto di eseguire l'operazione di creazione dell'ambiente non è stata assegnata direttamente all'utente che esegue quell'operazione.</span><span class="sxs-lookup"><span data-stu-id="79f28-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="79f28-107">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="79f28-107">**Solution**</span></span>

<span data-ttu-id="79f28-108">Verificare che l'amministratore del tenant abbia assegnato una licenza PowerApps P2 valida direttamente all'utente che esegue l'operazione di creazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="79f28-108">Make sure that the tenant admin has assigned a valid PowerApps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="79f28-109">Di seguito sono riportati i piani del servizio Microsoft Dynamics che forniscono quel diritto.</span><span class="sxs-lookup"><span data-stu-id="79f28-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="79f28-110">Unità di stockkeeping (SKU) globale di un prodotto</span><span class="sxs-lookup"><span data-stu-id="79f28-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="79f28-111">Piano del servizio PowerApps P2</span><span class="sxs-lookup"><span data-stu-id="79f28-111">PowerApps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="79f28-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="79f28-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="79f28-113">PowerApps per Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="79f28-113">PowerApps for Dynamics 365</span></span> |
| <span data-ttu-id="79f28-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="79f28-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="79f28-115">PowerApps per Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="79f28-115">PowerApps for Dynamics 365</span></span> |

<span data-ttu-id="79f28-116">Da notare che oltre alle unità di stockkeeping di PowerApps Piano 2, anche varie unità di stockkeeping di Microsoft Office forniscono quel diritto.</span><span class="sxs-lookup"><span data-stu-id="79f28-116">Note that various Microsoft Office SKUs also provide the right, together with standalone PowerApps Plan 2 SKUs.</span></span> <span data-ttu-id="79f28-117">L'aspetto importante è che una di queste unità di stockkeeping deve essere presente.</span><span class="sxs-lookup"><span data-stu-id="79f28-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="79f28-118">Accedere a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="79f28-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="79f28-119">Creare gli ambienti seguendo le istruzioni in [Eseguire il provisioning di Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="79f28-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
