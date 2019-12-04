---
title: Incorporare app di Power Apps in Dynamics 365 - Core HR
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
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830211"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="a12f1-103">Incorporare app di Power Apps in Dynamics 365 - Core HR</span><span class="sxs-lookup"><span data-stu-id="a12f1-103">Embed Power Apps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a12f1-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a12f1-104">**Issue**</span></span>

<span data-ttu-id="a12f1-105">La voce di menu **Power Apps** non è più visualizzata nel modulo **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="a12f1-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="a12f1-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a12f1-106">**Cause**</span></span>

<span data-ttu-id="a12f1-107">Il design dell'interfaccia utente è stato modificato e Microsoft Power Apps è ora incluso nel modello di personalizzazione standard.</span><span class="sxs-lookup"><span data-stu-id="a12f1-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="a12f1-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="a12f1-108">**Resolution**</span></span>

<span data-ttu-id="a12f1-109">Il modo in cui le Power Apps sono incorporate è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="a12f1-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="a12f1-110">Le Power Apps ora vengono aggiunte tramite il modello di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a12f1-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="a12f1-111">È possibile aggiungere le Power Apps a quasi tutte le pagine in Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="a12f1-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="a12f1-112">Per informazioni su come incorporare Power Apps in Talent, vedere [Incorporare Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="a12f1-112">For information about how to embed Power Apps in Talent, see [Embed Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="a12f1-113">Qualsiasi cliente Power Apps che ha incorporato app prima della modifica deve eseguire l'aggiornamento al nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="a12f1-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="a12f1-114">Il pulsante **Power Apps** è disponibile nell'angolo superiore destro di quasi ogni pagina in Talent.</span><span class="sxs-lookup"><span data-stu-id="a12f1-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="a12f1-115">È possibile utilizzare questo pulsante per inserire le Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a12f1-115">You can use this button to insert Power Apps.</span></span>

<span data-ttu-id="a12f1-116">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="a12f1-116">Here is an example.</span></span>

1. <span data-ttu-id="a12f1-117">Accedere a **Gestione dipendente \> Collegamenti \> Lavoratori \> Dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="a12f1-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="a12f1-118">Selezionare il pulsante **Power Apps** e quindi selezionare **Inserisci una PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a12f1-118">Select the **Power Apps** button, and then select **Insert a PowerApp**.</span></span>

    ![Pulsante Power Apps](media/png.png)

3. <span data-ttu-id="a12f1-120">Completare i campi nella finestra di dialogo **Inserisci una PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a12f1-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Finestra di dialogo Inserisci una PowerApp](media/insert-powerapp.png)

<span data-ttu-id="a12f1-122">In alternativa, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a12f1-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="a12f1-123">Nella scheda **Opzioni** del riquadro azioni della pagina, nel gruppo **Personalizza**, selezionare **Personalizza modulo**.</span><span class="sxs-lookup"><span data-stu-id="a12f1-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Gruppo Personalizza nella scheda Opzioni](media/options.png)

    <span data-ttu-id="a12f1-125">Viene visualizzata la barra degli strumenti di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a12f1-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="a12f1-126">Nella barra degli strumenti, selezionare **Inserisci \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a12f1-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Inserire un app di Power Apps utilizzando la barra degli strumenti di personalizzazione](media/powerapp-bar.png)
