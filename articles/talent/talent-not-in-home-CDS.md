---
title: "Talent non è visualizzato come app di Microsoft Dynamics 365 (CDS1.0)"
description: "Questo argomento descrive come procedere se Microsoft Dynamics 365 for Talent non è visualizzato tra le app di Microsoft Dynamics 365."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: it-it
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a><span data-ttu-id="83ae7-103">Talent non è visualizzato come app di Microsoft Dynamics 365 (CDS1.0)</span><span class="sxs-lookup"><span data-stu-id="83ae7-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (CDS1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="83ae7-104">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="83ae7-104">**Issue**</span></span>

<span data-ttu-id="83ae7-105">Microsoft Dynamics 365 for Talent non è visualizzato tra le app di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="83ae7-105">The customer doesn't see the Microsoft Dynamics 365 for Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="83ae7-106">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="83ae7-106">**Resolution**</span></span>

<span data-ttu-id="83ae7-107">L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="83ae7-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="83ae7-108">L'utente amministratore che dispone di una licenza di PowerApps Piano 2 deve aprire il [Portale di amministrazione di PowerApps)](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="83ae7-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="83ae7-109">Selezionare **Ambienti** e scegliere l'ambiente corretto per Talent.</span><span class="sxs-lookup"><span data-stu-id="83ae7-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="83ae7-110">Nella scheda **Ruoli ambiente** della scheda **Sicurezza**, selezionare **Creatore dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="83ae7-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Scheda Ruoli ambiente](media/environment-roles.png)

4. <span data-ttu-id="83ae7-112">Nella scheda **Utenti**, aggiungere l'utente o l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="83ae7-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Scheda Utenti](media/environment-maker.png)

5. <span data-ttu-id="83ae7-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="83ae7-114">Select **Save**.</span></span>
6. <span data-ttu-id="83ae7-115">L'utente deve ora accedere a [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="83ae7-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="83ae7-116">Selezionare **Sincronizza** per aggiornare le app dell'utente.</span><span class="sxs-lookup"><span data-stu-id="83ae7-116">Select **Sync** to update the user apps.</span></span>

    ![Pulsante Sincronizza](media/get-more.png)

    <span data-ttu-id="83ae7-118">Dopo che la sincronizzazione viene completata, Talent verrà visualizzato nella home page.</span><span class="sxs-lookup"><span data-stu-id="83ae7-118">After synchronization is completed, Talent will appear on the home page.</span></span>

