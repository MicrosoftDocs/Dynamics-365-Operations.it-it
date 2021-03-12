---
title: Passa tra strutture fornitore
description: In questo argomento viene descritto come passare tra l'integrazione dei dati dei fornitori tra le app Finance and Operations e Dataverse.
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
ms.openlocfilehash: d2c22123d5f05945b34eb107c5b912852aec387a
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744467"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="74888-103">Passa tra strutture fornitore</span><span class="sxs-lookup"><span data-stu-id="74888-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="74888-104">Flusso di dati fornitore</span><span class="sxs-lookup"><span data-stu-id="74888-104">Vendor data flow</span></span> 

<span data-ttu-id="74888-105">Se si sceglie di utilizzare la tabella **Conto** per memorizzare i fornitori di tipo **Organizzazione** e la tabella **Contatto** per memorizzare i fornitori di tipo **Persona**, configurare i seguenti flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="74888-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="74888-106">In caso contrario, questa configurazione non è richiesta.</span><span class="sxs-lookup"><span data-stu-id="74888-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="74888-107">Utilizzare il progetto del fornitore esteso per i fornitori di tipo Organizzazione</span><span class="sxs-lookup"><span data-stu-id="74888-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="74888-108">Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="74888-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="74888-109">Verrà creato un flusso di lavoro per ogni modello.</span><span class="sxs-lookup"><span data-stu-id="74888-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="74888-110">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="74888-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="74888-111">Creare fornitori nella tabella Fornitori</span><span class="sxs-lookup"><span data-stu-id="74888-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="74888-112">Aggiornare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="74888-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="74888-113">Aggiornare fornitori nella tabella Fornitori</span><span class="sxs-lookup"><span data-stu-id="74888-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="74888-114">Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="74888-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="74888-115">Creare un nuovo processo del flusso di lavoro per la tabella **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nella tabella conto**.</span><span class="sxs-lookup"><span data-stu-id="74888-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="74888-116">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="74888-116">Then select **OK**.</span></span> <span data-ttu-id="74888-117">Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per la tabella **Conto**.</span><span class="sxs-lookup"><span data-stu-id="74888-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Creare fornitori nel processo flusso di lavoro tabella conto](media/create_process.png)

2. <span data-ttu-id="74888-119">Creare un nuovo processo del flusso di lavoro per la tabella **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nella tabella conto**.</span><span class="sxs-lookup"><span data-stu-id="74888-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="74888-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="74888-120">Then select **OK**.</span></span> <span data-ttu-id="74888-121">Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per la tabella **Conto**.</span><span class="sxs-lookup"><span data-stu-id="74888-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="74888-122">Creare un nuovo processo del flusso di lavoro per la tabella **Conto** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nella tabella fornitore**.</span><span class="sxs-lookup"><span data-stu-id="74888-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="74888-123">Creare un nuovo processo del flusso di lavoro per la tabella **Conto** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nella tabella fornitore**.</span><span class="sxs-lookup"><span data-stu-id="74888-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="74888-124">È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti.</span><span class="sxs-lookup"><span data-stu-id="74888-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="74888-125">Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.</span><span class="sxs-lookup"><span data-stu-id="74888-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Pulsante Converti in flusso di lavoro in background](media/background_workflow.png)

6. <span data-ttu-id="74888-127">Attivare i flussi di lavoro creati sulle tabelle **Conto** e **Fornitore** per iniziare a utilizzare la tabella **Conto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="74888-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="74888-128">Utilizzare il progetto del fornitore esteso per i fornitori di tipo Persona</span><span class="sxs-lookup"><span data-stu-id="74888-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="74888-129">Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="74888-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="74888-130">Verrà creato un flusso di lavoro per ogni modello.</span><span class="sxs-lookup"><span data-stu-id="74888-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="74888-131">Creare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="74888-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="74888-132">Creare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="74888-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="74888-133">Aggiornare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="74888-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="74888-134">Aggiornare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="74888-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="74888-135">Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="74888-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="74888-136">Creare un nuovo processo del flusso di lavoro per la tabella **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori di tipo Persona nella tabella contatti**.</span><span class="sxs-lookup"><span data-stu-id="74888-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="74888-137">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="74888-137">Then select **OK**.</span></span> <span data-ttu-id="74888-138">Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per la tabella **Contatto**.</span><span class="sxs-lookup"><span data-stu-id="74888-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="74888-139">Creare un nuovo processo del flusso di lavoro per la tabella **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori di tipo Persona nella tabella contatti**.</span><span class="sxs-lookup"><span data-stu-id="74888-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="74888-140">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="74888-140">Then select **OK**.</span></span> <span data-ttu-id="74888-141">Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per la tabella **Contatto**.</span><span class="sxs-lookup"><span data-stu-id="74888-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="74888-142">Creare un nuovo processo del flusso di lavoro per la tabella **Contatto** e selezionare il modello **Creare fornitori di tipo Persona nella tabella fornitore**.</span><span class="sxs-lookup"><span data-stu-id="74888-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="74888-143">Creare un nuovo processo del flusso di lavoro per la tabella **Contatto** e selezionare il modello **Aggiornare fornitori di tipo Persona nella tabella fornitore**.</span><span class="sxs-lookup"><span data-stu-id="74888-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="74888-144">È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti.</span><span class="sxs-lookup"><span data-stu-id="74888-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="74888-145">Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.</span><span class="sxs-lookup"><span data-stu-id="74888-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="74888-146">Attivare i flussi di lavoro creati sulle entità **Contatto** e **Fornitore** per iniziare a utilizzare le tabelle **Contatto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Persona**.</span><span class="sxs-lookup"><span data-stu-id="74888-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>
