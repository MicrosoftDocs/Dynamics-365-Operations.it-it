---
title: Salvare le guide attività in LCS e riprodurle nuovamente
description: In questo articolo viene descritto come salvare guide attività in Microsoft Dynamics Lifecycle Services(LCS) e riprodurle.
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
ms.openlocfilehash: c81c345932e0e3dce4b13104222ed9f668a3c460
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113178"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="fa4b3-103">Salvare le guide attività in LCS e riprodurle nuovamente</span><span class="sxs-lookup"><span data-stu-id="fa4b3-103">Save task guides to LCS and replay them</span></span>

<span data-ttu-id="fa4b3-104">**Dettagli ambiente**</span><span class="sxs-lookup"><span data-stu-id="fa4b3-104">**Environment details**</span></span> 

<span data-ttu-id="fa4b3-105">Microsoft Dynamics 365 Human Resources, distribuito tramite Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="fa4b3-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="fa4b3-106">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="fa4b3-106">**Issue**</span></span>

<span data-ttu-id="fa4b3-107">Il cliente desidera salvare nuove registrazioni attività nel progetto LCS e quindi riprodurre le guide attività salvate.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="fa4b3-108">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="fa4b3-108">**Resolution**</span></span>

<span data-ttu-id="fa4b3-109">Seguire la procedura seguente per salvare una registrazione attività in LCS.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="fa4b3-110">Accedere a LCS e selezionare il progetto.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="fa4b3-111">Selezionare il riquadro **Modellatore di processi aziendali**.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="fa4b3-112">Visualizzare la pagina nell'"Esperienza BPM aggiornata".</span><span class="sxs-lookup"><span data-stu-id="fa4b3-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="fa4b3-113">Selezionare una libreria, quindi **Copia**.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="fa4b3-114">Immettere un nome per il modello Modellatore di processi aziendali (BPM).</span><span class="sxs-lookup"><span data-stu-id="fa4b3-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="fa4b3-115">Accedi a Human Resources da LCS.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="fa4b3-116">Nel campo **Cerca**, immettere **guida**.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="fa4b3-117">Viene aperta la Guida di Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="fa4b3-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="fa4b3-118">Selezionare il pulsante **Aggiorna** per la configurazione della Guida di Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="fa4b3-119">La nuova libreria BPM viene visualizzata e dovrebbe essere attiva.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="fa4b3-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-120">Close the page.</span></span>
10. <span data-ttu-id="fa4b3-121">Creare una registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-121">Create a task recording.</span></span>
11. <span data-ttu-id="fa4b3-122">Al termine, selezionare **Salvare in Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Salvare in Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="fa4b3-124">Selezionare il nodo e la libreria BPM in cui salvare la registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="fa4b3-125">Seguire questi passaggi per riprodurre una guida attività da LCS.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="fa4b3-126">Avviare Registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-126">Start Task recorder.</span></span>
2. <span data-ttu-id="fa4b3-127">Selezionare **Apri da LCS**.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="fa4b3-128">Selezionare la libreria e il nodo BPM con la guida attività salvata.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="fa4b3-129">Aprire la guida attività.</span><span class="sxs-lookup"><span data-stu-id="fa4b3-129">Open the task guide.</span></span>
