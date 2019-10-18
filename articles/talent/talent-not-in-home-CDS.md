---
title: Talent non appare tra le app Microsoft Dynamics 365 (Common Data Service 1.0)
description: Questo argomento descrive come procedere se Microsoft Dynamics 365 Talent non è visualizzato tra le app di Microsoft Dynamics 365.
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
ms.openlocfilehash: 956af80a8ab2f454d9f523d3c74dda754ef0f793
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009378"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a><span data-ttu-id="9bf19-103">Talent non appare tra le app Microsoft Dynamics 365 (Common Data Service 1.0)</span><span class="sxs-lookup"><span data-stu-id="9bf19-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (Common Data Service 1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9bf19-104">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="9bf19-104">**Issue**</span></span>

<span data-ttu-id="9bf19-105">Microsoft Dynamics 365 Talent non è visualizzato tra le app di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9bf19-105">The customer doesn't see the Microsoft Dynamics 365 Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="9bf19-106">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="9bf19-106">**Resolution**</span></span>

<span data-ttu-id="9bf19-107">L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="9bf19-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="9bf19-108">L'utente amministratore che dispone di una licenza di PowerApps Piano 2 deve aprire il [Portale di amministrazione di PowerApps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="9bf19-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="9bf19-109">Selezionare **Ambienti** e scegliere l'ambiente corretto per Talent.</span><span class="sxs-lookup"><span data-stu-id="9bf19-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="9bf19-110">Nella scheda **Ruoli ambiente** della scheda **Sicurezza**, selezionare **Creatore dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="9bf19-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Scheda Ruoli ambiente](media/environment-roles.png)

4. <span data-ttu-id="9bf19-112">Nella scheda **Utenti**, aggiungere l'utente o l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9bf19-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Scheda Utenti](media/environment-maker.png)

5. <span data-ttu-id="9bf19-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9bf19-114">Select **Save**.</span></span>
6. <span data-ttu-id="9bf19-115">L'utente deve ora accedere a [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="9bf19-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="9bf19-116">Selezionare **Sincronizza** per aggiornare le app dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9bf19-116">Select **Sync** to update the user apps.</span></span>

    ![Pulsante Sincronizza](media/get-more.png)

    <span data-ttu-id="9bf19-118">Dopo che la sincronizzazione viene completata, Talent verrà visualizzato nella home page.</span><span class="sxs-lookup"><span data-stu-id="9bf19-118">After synchronization is completed, Talent will appear on the home page.</span></span>
