---
title: Salvare le guide attività in LCS e riprodurle nuovamente
description: In questo argomento viene descritto come salvare guide attività in Microsoft Dynamics Lifecycle Services(LCS) e riprodurle.
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
ms.openlocfilehash: 40b4c3154a04a557b8a670e1f1ae3722c71122fe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "305018"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="a3be2-103">Salvare le guide attività in LCS e riprodurle nuovamente</span><span class="sxs-lookup"><span data-stu-id="a3be2-103">Save task guides to LCS and replay them</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a3be2-104">**Dettagli ambiente**</span><span class="sxs-lookup"><span data-stu-id="a3be2-104">**Environment details**</span></span> 

<span data-ttu-id="a3be2-105">Microsoft Dynamics 365 for Talent, distribuito tramite Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="a3be2-105">Microsoft Dynamics 365 for Talent, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="a3be2-106">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="a3be2-106">**Issue**</span></span>

<span data-ttu-id="a3be2-107">Il cliente desidera salvare nuove registrazioni attività nel progetto LCS e quindi riprodurre le guide attività salvate.</span><span class="sxs-lookup"><span data-stu-id="a3be2-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="a3be2-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="a3be2-108">**Resolution**</span></span>

<span data-ttu-id="a3be2-109">Seguire la procedura seguente per salvare una registrazione attività in LCS.</span><span class="sxs-lookup"><span data-stu-id="a3be2-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="a3be2-110">Accedere a LCS e selezionare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a3be2-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="a3be2-111">Selezionare il riquadro **Modellatore di processi aziendali**.</span><span class="sxs-lookup"><span data-stu-id="a3be2-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="a3be2-112">Visualizzare la pagina nell'"Esperienza BPM aggiornata".</span><span class="sxs-lookup"><span data-stu-id="a3be2-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="a3be2-113">Selezionare una libreria, quindi **Copia**.</span><span class="sxs-lookup"><span data-stu-id="a3be2-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="a3be2-114">Immettere un nome per il modello Modellatore di processi aziendali (BPM).</span><span class="sxs-lookup"><span data-stu-id="a3be2-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="a3be2-115">Accedere a Talent da LCS.</span><span class="sxs-lookup"><span data-stu-id="a3be2-115">Sign in to Talent from LCS.</span></span>
7. <span data-ttu-id="a3be2-116">Nel campo **Cerca**, immettere **guida**.</span><span class="sxs-lookup"><span data-stu-id="a3be2-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="a3be2-117">Viene aperta la Guida di Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="a3be2-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="a3be2-118">Selezionare il pulsante **Aggiorna** per la configurazione della Guida di Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="a3be2-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="a3be2-119">La nuova libreria BPM viene visualizzata e dovrebbe essere attiva.</span><span class="sxs-lookup"><span data-stu-id="a3be2-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="a3be2-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a3be2-120">Close the page.</span></span>
10. <span data-ttu-id="a3be2-121">Creare una registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="a3be2-121">Create a task recording.</span></span>
11. <span data-ttu-id="a3be2-122">Al termine, selezionare **Salvare in Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="a3be2-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Salvare in Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="a3be2-124">Selezionare il nodo e la libreria BPM in cui salvare la registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="a3be2-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="a3be2-125">Seguire questi passaggi per riprodurre una guida attività da LCS.</span><span class="sxs-lookup"><span data-stu-id="a3be2-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="a3be2-126">Avviare Registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="a3be2-126">Start Task recorder.</span></span>
2. <span data-ttu-id="a3be2-127">Selezionare **Apri da LCS**.</span><span class="sxs-lookup"><span data-stu-id="a3be2-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="a3be2-128">Selezionare la libreria e il nodo BPM con la guida attività salvata.</span><span class="sxs-lookup"><span data-stu-id="a3be2-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="a3be2-129">Aprire la guida attività.</span><span class="sxs-lookup"><span data-stu-id="a3be2-129">Open the task guide.</span></span>
