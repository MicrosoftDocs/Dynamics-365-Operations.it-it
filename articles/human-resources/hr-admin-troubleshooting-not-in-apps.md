---
title: Human Resources non appare nelle app Microsoft Dynamics 365
description: Questo articolo descrive come procedere se l'app Microsoft Dynamics 365 Human Resources non è visualizzata tra le app di Microsoft Dynamics 365.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: d78199cf0e76ffd0676a26961a8e646938dc7333
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113157"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="df8b8-103">Human Resources non appare nelle app Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="df8b8-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="df8b8-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="df8b8-104">**Issue**</span></span>

<span data-ttu-id="df8b8-105">Il cliente non vede Dynamics 365 Human Resources tra le app di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df8b8-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="df8b8-106">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="df8b8-106">**Resolution**</span></span>

<span data-ttu-id="df8b8-107">L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="df8b8-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="df8b8-108">L'utente amministratore che dispone di una licenza di Power Apps Piano 2 deve aprire il [Portale di amministrazione di Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="df8b8-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="df8b8-109">Selezionare **Ambienti** e scegliere l'ambiente corretto per Human Resources.</span><span class="sxs-lookup"><span data-stu-id="df8b8-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="df8b8-110">Nella scheda **Ruoli ambiente** della scheda **Sicurezza**, selezionare **Creatore dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="df8b8-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Scheda Ruoli ambiente](media/environment-roles.png)

4. <span data-ttu-id="df8b8-112">Nella scheda **Utenti**, aggiungere l'utente o l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df8b8-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Scheda Utenti](media/environment-maker.png)

5. <span data-ttu-id="df8b8-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="df8b8-114">Select **Save**.</span></span>

6. <span data-ttu-id="df8b8-115">L'utente deve ora accedere a [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="df8b8-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="df8b8-116">Selezionare **Sincronizza** per aggiornare le app dell'utente.</span><span class="sxs-lookup"><span data-stu-id="df8b8-116">Select **Sync** to update the user apps.</span></span>

    ![Pulsante Sincronizza](media/get-more.png)

    <span data-ttu-id="df8b8-118">Dopo che la sincronizzazione viene completata, l'app Human Resources verrà visualizzata nella home page.</span><span class="sxs-lookup"><span data-stu-id="df8b8-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
