---
title: Human Resources non appare nelle app Microsoft Dynamics 365
description: Questo articolo descrive come procedere se l'app Microsoft Dynamics 365 Human Resources non è visualizzata tra le app di Microsoft Dynamics 365.
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
ms.openlocfilehash: cbf47b4673e1c97965bba7728e5669b7639c4d56
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419176"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="d17b6-103">Human Resources non appare nelle app Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d17b6-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="d17b6-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="d17b6-104">**Issue**</span></span>

<span data-ttu-id="d17b6-105">Il cliente non vede Dynamics 365 Human Resources tra le app di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d17b6-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="d17b6-106">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="d17b6-106">**Resolution**</span></span>

<span data-ttu-id="d17b6-107">L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="d17b6-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="d17b6-108">L'utente amministratore che dispone di una licenza di Power Apps Piano 2 deve aprire il [Portale di amministrazione di Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="d17b6-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="d17b6-109">Selezionare **Ambienti** e scegliere l'ambiente corretto per Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d17b6-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="d17b6-110">Nella scheda **Ruoli ambiente** della scheda **Sicurezza**, selezionare **Creatore dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="d17b6-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Scheda Ruoli ambiente](media/environment-roles.png)

4. <span data-ttu-id="d17b6-112">Nella scheda **Utenti**, aggiungere l'utente o l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d17b6-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Scheda Utenti](media/environment-maker.png)

5. <span data-ttu-id="d17b6-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d17b6-114">Select **Save**.</span></span>

6. <span data-ttu-id="d17b6-115">L'utente deve ora accedere a [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="d17b6-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="d17b6-116">Selezionare **Sincronizza** per aggiornare le app dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d17b6-116">Select **Sync** to update the user apps.</span></span>

    ![Pulsante Sincronizza](media/get-more.png)

    <span data-ttu-id="d17b6-118">Dopo che la sincronizzazione viene completata, l'app Human Resources verrà visualizzata nella home page.</span><span class="sxs-lookup"><span data-stu-id="d17b6-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
