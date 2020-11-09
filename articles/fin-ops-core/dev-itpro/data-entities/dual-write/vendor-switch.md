---
title: Passa tra strutture fornitore
description: In questo argomento viene descritto come passare tra l'integrazione dei dati dei fornitori tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997554"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="0f263-103">Passa tra strutture fornitore</span><span class="sxs-lookup"><span data-stu-id="0f263-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="0f263-104">Flusso di dati fornitore</span><span class="sxs-lookup"><span data-stu-id="0f263-104">Vendor data flow</span></span> 

<span data-ttu-id="0f263-105">Se si sceglie di utilizzare l'entità **Conto** per memorizzare i fornitori di tipo **Organizzazione** e l'entità **Contatto** per memorizzare i fornitori di tipo **Persona** , configurare i seguenti flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f263-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="0f263-106">In caso contrario, questa configurazione non è richiesta.</span><span class="sxs-lookup"><span data-stu-id="0f263-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="0f263-107">Utilizzare il progetto del fornitore esteso per i fornitori di tipo Organizzazione</span><span class="sxs-lookup"><span data-stu-id="0f263-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="0f263-108">Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f263-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="0f263-109">Verrà creato un flusso di lavoro per ogni modello.</span><span class="sxs-lookup"><span data-stu-id="0f263-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="0f263-110">Creare fornitori nell'entità Conto</span><span class="sxs-lookup"><span data-stu-id="0f263-110">Create Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="0f263-111">Creare fornitori nell'entità fornitori</span><span class="sxs-lookup"><span data-stu-id="0f263-111">Create Vendors in Vendors Entity</span></span>
+ <span data-ttu-id="0f263-112">Aggiornare fornitori nell'entità Conto</span><span class="sxs-lookup"><span data-stu-id="0f263-112">Update Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="0f263-113">Aggiornare fornitori nell'entità fornitori</span><span class="sxs-lookup"><span data-stu-id="0f263-113">Update Vendors in Vendors Entity</span></span>

<span data-ttu-id="0f263-114">Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="0f263-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="0f263-115">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nell'entità conto**.</span><span class="sxs-lookup"><span data-stu-id="0f263-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="0f263-116">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f263-116">Then select **OK**.</span></span> <span data-ttu-id="0f263-117">Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Conto**.</span><span class="sxs-lookup"><span data-stu-id="0f263-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Creare fornitori nel processo flusso di lavoro entità conto](media/create_process.png)

2. <span data-ttu-id="0f263-119">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nell'entità conto**.</span><span class="sxs-lookup"><span data-stu-id="0f263-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="0f263-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f263-120">Then select **OK**.</span></span> <span data-ttu-id="0f263-121">Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Conto**.</span><span class="sxs-lookup"><span data-stu-id="0f263-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="0f263-122">Creare un nuovo processo del flusso di lavoro per l'entità **Conto** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nell'entità fornitore**.</span><span class="sxs-lookup"><span data-stu-id="0f263-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Entity** workflow process template.</span></span>
4. <span data-ttu-id="0f263-123">Creare un nuovo processo del flusso di lavoro per l'entità **Conto** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nell'entità fornitore**.</span><span class="sxs-lookup"><span data-stu-id="0f263-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Entity** workflow process template.</span></span>
5. <span data-ttu-id="0f263-124">È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti.</span><span class="sxs-lookup"><span data-stu-id="0f263-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="0f263-125">Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.</span><span class="sxs-lookup"><span data-stu-id="0f263-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Pulsante Converti in flusso di lavoro in background](media/background_workflow.png)

6. <span data-ttu-id="0f263-127">Attivare i flussi di lavoro creati sulle entità **Conto** e **Fornitore** per iniziare a utilizzare l'entità **Conto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="0f263-127">Activate the workflows that you created for the **Account** and **Vendor** entities to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="0f263-128">Utilizzare il progetto del fornitore esteso per i fornitori di tipo Persona</span><span class="sxs-lookup"><span data-stu-id="0f263-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="0f263-129">Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f263-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="0f263-130">Verrà creato un flusso di lavoro per ogni modello.</span><span class="sxs-lookup"><span data-stu-id="0f263-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="0f263-131">Creare fornitori di tipo Persona nell'entità fornitori</span><span class="sxs-lookup"><span data-stu-id="0f263-131">Create Vendors of type Person in Vendors Entity</span></span>
+ <span data-ttu-id="0f263-132">Creare fornitori di tipo Persona nell'entità contatti</span><span class="sxs-lookup"><span data-stu-id="0f263-132">Create Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="0f263-133">Aggiornare fornitori di tipo Persona nell'entità contatti</span><span class="sxs-lookup"><span data-stu-id="0f263-133">Update Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="0f263-134">Aggiornare fornitori di tipo Persona nell'entità fornitori</span><span class="sxs-lookup"><span data-stu-id="0f263-134">Update Vendors of type Person in Vendors Entity</span></span>

<span data-ttu-id="0f263-135">Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="0f263-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="0f263-136">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori di tipo Persona nell'entità contatti**.</span><span class="sxs-lookup"><span data-stu-id="0f263-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="0f263-137">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f263-137">Then select **OK**.</span></span> <span data-ttu-id="0f263-138">Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Contatto**.</span><span class="sxs-lookup"><span data-stu-id="0f263-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="0f263-139">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori di tipo Persona nell'entità contatti**.</span><span class="sxs-lookup"><span data-stu-id="0f263-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="0f263-140">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f263-140">Then select **OK**.</span></span> <span data-ttu-id="0f263-141">Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Contatto**.</span><span class="sxs-lookup"><span data-stu-id="0f263-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="0f263-142">Creare un nuovo processo del flusso di lavoro per l'entità **Contatto** e selezionare il modello **Creare fornitori di tipo Persona nell'entità fornitore**.</span><span class="sxs-lookup"><span data-stu-id="0f263-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Entity** template.</span></span>
4. <span data-ttu-id="0f263-143">Creare un nuovo processo del flusso di lavoro per l'entità **Contatto** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori di tipo Persona nell'entità fornitore**.</span><span class="sxs-lookup"><span data-stu-id="0f263-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Entity** template.</span></span>
5. <span data-ttu-id="0f263-144">È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti.</span><span class="sxs-lookup"><span data-stu-id="0f263-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="0f263-145">Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.</span><span class="sxs-lookup"><span data-stu-id="0f263-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="0f263-146">Attivare i flussi di lavoro creati sulle entità **Contatto** e **Fornitore** per iniziare a utilizzare l'entità **Contatto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Persona**.</span><span class="sxs-lookup"><span data-stu-id="0f263-146">Activate the workflows that you created on the **Contact** and **Vendor** entities to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
