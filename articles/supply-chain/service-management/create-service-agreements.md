---
title: Creare contratti di assistenza
description: In questo argomento viene descritto come utilizzare le funzionalità dei moduli Gestione assistenza e Gestione progetti e contabilità per creare i contratti di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a1a47761869a4190eac6dc9e069a6b520bf7a1d
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985144"
---
# <a name="create-service-agreements"></a><span data-ttu-id="ce0d0-103">Creare contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="ce0d0-103">Create service agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce0d0-104">In questo argomento viene descritto come utilizzare le funzionalità dei moduli Gestione assistenza e Gestione progetti e contabilità per creare i contratti di assistenza.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-104">This topic describes how to use features in the Service management and the Project management and accounting modules to create service agreements.</span></span>

## <a name="create-a-service-agreement-from-service-management"></a><span data-ttu-id="ce0d0-105">Creare un contratto di assistenza da Gestione assistenza</span><span class="sxs-lookup"><span data-stu-id="ce0d0-105">Create a service agreement from Service management</span></span>

1. <span data-ttu-id="ce0d0-106">Passare a **Gestione assistenza**.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-106">Navigate to **Service management**.</span></span>
2. <span data-ttu-id="ce0d0-107">Fare clic sul pulsante **Contratti di assistenza** per creare una nuova riga del contratto di assistenza nell'intestazione della pagina.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-107">Click **Service agreements** to create a new service agreement line in the page header.</span></span> 
3. <span data-ttu-id="ce0d0-108">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-108">Click **New**.</span></span> <span data-ttu-id="ce0d0-109">Immettere una descrizione, selezionare un riferimento a un progetto nel campo **ID progetto** e completare i campi e le righe relativi al contratto di assistenza rimanenti.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-109">Enter a description, select a reference to a project in the **Project ID** field, and fill in the rest of the fields and lines for the service agreement.</span></span> <span data-ttu-id="ce0d0-110">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-110">Click **Save**.</span></span>
4. <span data-ttu-id="ce0d0-111">Fare clic sulla scheda **Relazioni** e selezionare **Oggetti assistenza** o **Attività di assistenza tecnica** per creare relazioni di oggetti assistenza o di attività di assistenza tecnica per il contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-111">On the **Relations** tab, select **Service objects** or **Service tasks** to create service object relations or service task relations for the service agreement.</span></span> <span data-ttu-id="ce0d0-112">Gli oggetti assistenza e le attività di assistenza tecnica per cui sono state create relazioni possono essere collegati alle righe del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-112">The service objects and tasks that you have created relations for can be attached on the lines of the service agreement.</span></span>
5. <span data-ttu-id="ce0d0-113">Nella metà inferiore della pagina creare le righe del contratto di assistenza procedendo manualmente oppure copiandole da un modello di assistenza o da un altro contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-113">In the lower half of the page, create service agreement lines by copying lines from a service template, another service agreement, or manually creating the service-agreement lines.</span></span>

> [!NOTE]
> <span data-ttu-id="ce0d0-114">Se le righe vengono copiate da un altro contratto di assistenza, è possibile indicare se si desidera copiare anche le relazioni di oggetti assistenza e di attività di assistenza tecnica.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-114">If you copy lines into the service agreement from another service agreement, you can indicate whether you also want to copy service object and service task relations.</span></span> <span data-ttu-id="ce0d0-115">In caso affermativo, le relazioni copiate verranno aggiunte a quelle esistenti nel contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-115">If you copy these relations, they are added to any existing relations on the service agreement.</span></span> <span data-ttu-id="ce0d0-116">Se invece si copiano le righe del contratto di assistenza da un modello di assistenza, nelle righe del nuovo contratto le relazioni di oggetti assistenza e di attività di assistenza tecnica verranno copiate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-116">If you copy service-agreement lines from a service template, the service-object and service-task relations are automatically copied as service-object relations and service-task relations on the new service-agreement lines.</span></span>

## <a name="create-service-agreement-lines-manually"></a><span data-ttu-id="ce0d0-117">Creare manualmente righe di contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="ce0d0-117">Create service agreement lines manually</span></span>

1. <span data-ttu-id="ce0d0-118">Dalla pagina **Contratti di assistenza** aggiungere una riga del contratto di assistenza nella griglia di righe.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-118">From the **Service agreements** page, add a service agreement line in the lines grid.</span></span> 
2. <span data-ttu-id="ce0d0-119">Immettere le informazioni appropriate per la riga del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-119">Enter the appropriate information for the service agreement line.</span></span> 
3. <span data-ttu-id="ce0d0-120">Premere **CTRL+S** per salvare la riga, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-120">Press **CTRL+S** to save the line, and then close the page.</span></span>

## <a name="create-a-service-agreement-from-project"></a><span data-ttu-id="ce0d0-121">Creare un contratto di assistenza mediante Gestione progetti</span><span class="sxs-lookup"><span data-stu-id="ce0d0-121">Create a service agreement from Project</span></span>

1. <span data-ttu-id="ce0d0-122">Fare clic su **Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-122">Click **Project management and accounting**.</span></span>
2. <span data-ttu-id="ce0d0-123">Fare clic su **Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-123">Click **All projects**.</span></span>
3. <span data-ttu-id="ce0d0-124">Selezionare il progetto dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-124">Select the project from the list.</span></span>
4. <span data-ttu-id="ce0d0-125">Nel **riquadro azioni** fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-125">On the **Action Pane**, click **Manage**.</span></span> <span data-ttu-id="ce0d0-126">Nel gruppo azioni **Nuovo**, fare clic su **Assistenza** e **Contratto di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-126">In the **New** Action group, click **Service** and select **Service agreement**.</span></span>
5. <span data-ttu-id="ce0d0-127">Completare i passaggi della sezione **Creare un contratto di assistenza** descritta in precedenza in questo argomento, per inserire il riferimento del progetto.</span><span class="sxs-lookup"><span data-stu-id="ce0d0-127">Follow the steps in the section titled **Create a service agreement** as described earlier in this topic to enter the project reference.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ce0d0-128">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ce0d0-128">Related topics</span></span>

[<span data-ttu-id="ce0d0-129">Panoramica sviluppo e definizione dei contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="ce0d0-129">Develop and establish service agreements overview</span></span>](service-agreements.md)


