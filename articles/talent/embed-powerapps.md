---
title: Incorporare app di PowerApps in Dynamics 365 - Core HR
description: In questo argomento viene descritto come risolvere il problema in cui la voce di menu PowerApps non è più visualizzata nel modulo Amministrazione sistema.
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
ms.openlocfilehash: 4fbc24c5ceb73389b84b125eb942ac31757928aa
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008432"
---
# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="744de-103">Incorporare app di PowerApps in Core HR</span><span class="sxs-lookup"><span data-stu-id="744de-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="744de-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="744de-104">**Issue**</span></span>

<span data-ttu-id="744de-105">La voce di menu **PowerApps** non è più visualizzata nel modulo **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="744de-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="744de-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="744de-106">**Cause**</span></span>

<span data-ttu-id="744de-107">Il design dell'interfaccia utente è stato modificato e Microsoft PowerApps è ora incluso nel modello di personalizzazione standard.</span><span class="sxs-lookup"><span data-stu-id="744de-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="744de-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="744de-108">**Resolution**</span></span>

<span data-ttu-id="744de-109">Il modo in cui le app di PowerApps sono incorporate è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="744de-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="744de-110">Le app di PowerApps ora vengono aggiunte tramite il modello di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="744de-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="744de-111">È possibile aggiungere app di PowerApps a quasi tutte le pagine in Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="744de-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="744de-112">Per informazioni su come incorporare app di PowerApps in Talent, consultare [Incorporare le app di PowerApps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="744de-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="744de-113">Qualsiasi cliente PowerApps che ha incorporato app prima della modifica deve eseguire l'aggiornamento al nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="744de-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="744de-114">Il pulsante **PowerApps** è disponibile nell'angolo superiore destro di quasi ogni pagina in Talent.</span><span class="sxs-lookup"><span data-stu-id="744de-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="744de-115">È possibile utilizzare questo pulsante per inserire un app di PowerApps.</span><span class="sxs-lookup"><span data-stu-id="744de-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="744de-116">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="744de-116">Here is an example.</span></span>

1. <span data-ttu-id="744de-117">Accedere a **Gestione dipendente \> Collegamenti \> Lavoratori \> Dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="744de-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="744de-118">Selezionare il pulsante **PowerApps** e quindi selezionare **Inserisci una PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="744de-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Pulsante PowerApps](media/png.png)

3. <span data-ttu-id="744de-120">Completare i campi nella finestra di dialogo **Inserisci una PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="744de-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Finestra di dialogo Inserisci una PowerApp](media/insert-powerapp.png)

<span data-ttu-id="744de-122">In alternativa, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="744de-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="744de-123">Nella scheda **Opzioni** del riquadro azioni della pagina, nel gruppo **Personalizza**, selezionare **Personalizza modulo**.</span><span class="sxs-lookup"><span data-stu-id="744de-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Gruppo Personalizza nella scheda Opzioni](media/options.png)

    <span data-ttu-id="744de-125">Viene visualizzata la barra degli strumenti di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="744de-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="744de-126">Nella barra degli strumenti, selezionare **Inserisci \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="744de-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Inserire un app di PowerApps utilizzando la barra degli strumenti di personalizzazione](media/powerapp-bar.png)
