---
title: Incorporare app di PowerApps in Core HR
description: In questo argomento viene descritto come risolvere il problema in cui la voce di menu PowerApps non è più visualizzata nel modulo Amministrazione sistema.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "305029"
---
# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="9d0ca-103">Incorporare app di PowerApps in Core HR</span><span class="sxs-lookup"><span data-stu-id="9d0ca-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9d0ca-104">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="9d0ca-104">**Issue**</span></span>

<span data-ttu-id="9d0ca-105">La voce di menu **PowerApps** non è più visualizzata nel modulo **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="9d0ca-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="9d0ca-106">**Cause**</span></span>

<span data-ttu-id="9d0ca-107">Il design dell'interfaccia utente è stato modificato e Microsoft PowerApps è ora incluso nel modello di personalizzazione standard.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="9d0ca-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="9d0ca-108">**Resolution**</span></span>

<span data-ttu-id="9d0ca-109">Il modo in cui le app di PowerApps sono incorporate è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="9d0ca-110">Le app di PowerApps ora vengono aggiunte tramite il modello di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="9d0ca-111">È possibile aggiungere app di PowerApps a quasi tutte le pagine in Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 for Talent.</span></span>

<span data-ttu-id="9d0ca-112">Per informazioni su come incorporare app di PowerApp in Talent, consultare [Incorporare le app di PowerApps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="9d0ca-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="9d0ca-113">Qualsiasi cliente PowerApps che ha incorporato app prima della modifica deve eseguire l'aggiornamento al nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="9d0ca-114">Il pulsante **PowerApps** è disponibile nell'angolo superiore destro di quasi ogni pagina in Talent.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="9d0ca-115">È possibile utilizzare questo pulsante per inserire un app di PowerApps.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="9d0ca-116">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-116">Here is an example.</span></span>

1. <span data-ttu-id="9d0ca-117">Accedere a **Gestione dipendente \> Collegamenti \> Lavoratori \> Dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="9d0ca-118">Selezionare il pulsante **PowerApps** e quindi selezionare **Inserisci una PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Pulsante PowerApps](media/png.png)

3. <span data-ttu-id="9d0ca-120">Completare i campi nella finestra di dialogo **Inserisci una PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Finestra di dialogo Inserisci una PowerApp](media/insert-powerapp.png)

<span data-ttu-id="9d0ca-122">In alternativa, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="9d0ca-123">Nella scheda **Opzioni** del riquadro azioni della pagina, nel gruppo **Personalizza**, selezionare **Personalizza modulo**.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Gruppo Personalizza nella scheda Opzioni](media/options.png)

    <span data-ttu-id="9d0ca-125">Viene visualizzata la barra degli strumenti di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="9d0ca-126">Nella barra degli strumenti, selezionare **Inserisci \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="9d0ca-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Inserire un app di PowerApps utilizzando la barra degli strumenti di personalizzazione](media/powerapp-bar.png)
