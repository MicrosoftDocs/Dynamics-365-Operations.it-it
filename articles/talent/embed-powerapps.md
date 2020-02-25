---
title: Incorporare app Power Apps in Dynamics 365 Human Resources
description: In questo argomento viene descritto come risolvere il problema in cui la voce di menu Microsoft Power Apps non è più visualizzata nel modulo Amministrazione sistema.
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
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017875"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a><span data-ttu-id="fce13-103">Incorporare app Power Apps in Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="fce13-103">Embed Power Apps apps in Dynamics 365 Human Resources</span></span>

<span data-ttu-id="fce13-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="fce13-104">**Issue**</span></span>

<span data-ttu-id="fce13-105">La voce di menu **Power Apps** non è più visualizzata nel modulo **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="fce13-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="fce13-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="fce13-106">**Cause**</span></span>

<span data-ttu-id="fce13-107">Il design dell'interfaccia utente è stato modificato e Microsoft Power Apps è ora incluso nel modello di personalizzazione standard.</span><span class="sxs-lookup"><span data-stu-id="fce13-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="fce13-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="fce13-108">**Resolution**</span></span>

<span data-ttu-id="fce13-109">Il modo in cui le Power Apps sono incorporate è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="fce13-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="fce13-110">Le Power Apps ora vengono aggiunte tramite il modello di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="fce13-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="fce13-111">È possibile aggiungere le Power Apps a quasi tutte le pagine in Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="fce13-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="fce13-112">Per informazioni su come incorporare Power Apps in Talent, vedere [Incorporare Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="fce13-112">For information about how to embed Power Apps in Talent, see [Embed Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="fce13-113">Qualsiasi cliente Power Apps che ha incorporato app prima della modifica deve eseguire l'aggiornamento al nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="fce13-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="fce13-114">Il pulsante **Power Apps** è disponibile nell'angolo superiore destro di quasi ogni pagina in Talent.</span><span class="sxs-lookup"><span data-stu-id="fce13-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="fce13-115">È possibile utilizzare questo pulsante per inserire app.</span><span class="sxs-lookup"><span data-stu-id="fce13-115">You can use this button to insert apps.</span></span>

<span data-ttu-id="fce13-116">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="fce13-116">Here is an example.</span></span>

1. <span data-ttu-id="fce13-117">Accedere a **Gestione dipendente \> Collegamenti \> Lavoratori \> Dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="fce13-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="fce13-118">Selezionare il pulsante **Power Apps**, quindi selezionare **Aggiungi un'app da Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="fce13-118">Select the **Power Apps** button, and then select **Add an app from Power Apps**.</span></span>

    ![Pulsante Power Apps](media/png.png)

3. <span data-ttu-id="fce13-120">Completare i campi nella finestra di dialogo **Aggiungi un'app da Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="fce13-120">Complete the fields in the **Add an app from Power Apps** dialog box.</span></span>

    ![Finestra di dialogo Aggiungi un'app da Power Apps](media/insert-powerapp.png)

<span data-ttu-id="fce13-122">In alternativa, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="fce13-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="fce13-123">Nella scheda **Opzioni** del riquadro azioni della pagina, nel gruppo **Personalizza**, selezionare **Personalizza questa pagina**.</span><span class="sxs-lookup"><span data-stu-id="fce13-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this page**.</span></span>

    ![Gruppo Personalizza nella scheda Opzioni](media/options.png)

    <span data-ttu-id="fce13-125">Viene visualizzata la barra degli strumenti di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="fce13-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="fce13-126">Nella barra degli strumenti, selezionare **Aggiungi un'app da Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="fce13-126">On the toolbar, select **Add an app from Power Apps**.</span></span>

    ![Aggiungere un'app da Power Apps utilizzando la barra degli strumenti di personalizzazione](media/powerapp-bar.png)
