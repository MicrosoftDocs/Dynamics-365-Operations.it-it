---
title: Creare richieste di intervento di manutenzione
description: In questo argomento viene illustrato come creare una richiesta di intervento di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e97d96a5485f17d0abc7c2fc2f8c4fdf4bbd4bb4
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024639"
---
# <a name="create-maintenance-requests"></a><span data-ttu-id="10446-103">Creare richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="10446-103">Create maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="10446-104">Le richieste di intervento di manutenzione può essere utilizzata se gli addetti alla manutenzione o i lavoratori del reparto produzione scoprono attrezzature che richiede la riparazione, ma il processo di riparazione non può essere eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="10446-104">Maintenance requests can be used if maintenance workers or production workers discover that equipment requires repair, but the repair job can't be done right away.</span></span>

<span data-ttu-id="10446-105">**Esempio:** mentre l'addetto alla manutenzione effettua una riparazione, scopre che un altro cespite nello stesso ubicazione ha bisogno di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="10446-105">**Example:** While a maintenance worker is making a repair, she discovers that another asset at the same location must be serviced.</span></span> <span data-ttu-id="10446-106">Tuttavia, l'addetto non ha il tempo o pezzi di ricambio necessari per eseguire il processo di riparazione.</span><span class="sxs-lookup"><span data-stu-id="10446-106">However, the maintenance worker doesn't have the time or the required spare parts to do the repair job.</span></span> <span data-ttu-id="10446-107">A tale scopo, crea una richiesta di intervento di manutenzione sul cespite e immette una breve descrizione del problema.</span><span class="sxs-lookup"><span data-stu-id="10446-107">Therefore, she creates a maintenance request on the asset and enters a short description of the issue.</span></span>

<span data-ttu-id="10446-108">La sezione **Richieste di interventi di manutenzione attive** del riquadro **Informazioni correlate** sul lato destro della pagina **Tutti i cespiti** o **Cespiti attivi** (**Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**) mostra le richieste attive collegate al cespite selezionato.</span><span class="sxs-lookup"><span data-stu-id="10446-108">The **Active maintenance requests** section of the **Related information** pane on the right side of the **All assets** or **Active assets** page (**Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**) shows the active maintenance requests that are attached to the selected asset.</span></span>

1. <span data-ttu-id="10446-109">Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.</span><span class="sxs-lookup"><span data-stu-id="10446-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="10446-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="10446-110">Select **New**.</span></span>
3. <span data-ttu-id="10446-111">Nella finestra di dialogo **Crea richiesta**, nel campo **Tipo di richiesta di intervento di manutenzione**, selezionare il tipo di richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="10446-111">In the **Create request** dialog box, in the **Maintenance request type** field, select the type of maintenance request.</span></span> <span data-ttu-id="10446-112">Tipo predefinito viene suggerito.</span><span class="sxs-lookup"><span data-stu-id="10446-112">A default type is suggested.</span></span>
4. <span data-ttu-id="10446-113">Nel campo **Descrizione**, immettere un nome o un titolo che brevemente descrivono la richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="10446-113">In the **Description** field, enter a name or title that briefly describes the maintenance request.</span></span>
5. <span data-ttu-id="10446-114">Nei campi **Unità funzionale** e **Cespite**, selezionare una unità funzionale o un cespite, o una combinazione dei due, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="10446-114">In the **Functional location** and **Asset** fields, select a functional location or an asset, or a combination of a functional location and an asset, as you require.</span></span> <span data-ttu-id="10446-115">È possibile creare una richiesta di intervento di manutenzione senza selezionare un cespite e il cespite può essere aggiunti successivamente alla richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="10446-115">You can create a maintenance request without selecting an asset, and the asset can be added to the maintenance request later.</span></span> <span data-ttu-id="10446-116">Se l'addetto alla manutenzione che ha eseguito l'accesso è correlato a una risorsa correlata a un cespite, il campo **Cespite** viene impostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10446-116">If the maintenance worker who is signed in is related to a resource that is related to an asset, the **Asset** field is automatically set.</span></span>

    <span data-ttu-id="10446-117">Se una richiesta di intervento di manutenzione è già collegata al cespite selezionato, una barra dei messaggi viene visualizzata nella parte superiore della finestra  dialogo **Crea richiesta** per segnalare l'ID della richiesta di intervento di manutenzione esistente.</span><span class="sxs-lookup"><span data-stu-id="10446-117">If a maintenance request is already attached to the selected asset, a message bar appears at the top of the **Create request** dialog box to notify you about the ID of the existing maintenance request.</span></span> <span data-ttu-id="10446-118">La barra dei messaggi anche informa se il cespite è coperto da un contratto di garanzia.</span><span class="sxs-lookup"><span data-stu-id="10446-118">A message bar also notifies you if the asset is covered by a warranty agreement.</span></span>

6. <span data-ttu-id="10446-119">Nel campo **Livello servizio**, selezionare un livello di servizio che indica l'urgenza della richiesta.</span><span class="sxs-lookup"><span data-stu-id="10446-119">In the **Service level** field, select a service level that indicates the urgency of the request.</span></span>
7. <span data-ttu-id="10446-120">Se è stato selezionato un cespite nel passaggio 5, è possibile utilizzare i campi **Sintomo problema**, **Area problema** e **Tipo di problema** per creare una registrazione del problema.</span><span class="sxs-lookup"><span data-stu-id="10446-120">If you selected an asset in step 5, you can use the **Fault symptom**, **Fault area**, and **Fault type** fields to create a fault registration.</span></span>
8. <span data-ttu-id="10446-121">Se la richiesta di intervento di manutenzione ha determinato tempi di fermo per la manutenzione, immettere la data di inizio e di fine dei tempi di fermo.</span><span class="sxs-lookup"><span data-stu-id="10446-121">If the maintenance request has caused maintenance downtime, enter the start date and time of the downtime.</span></span>

    <span data-ttu-id="10446-122">Il campo **Avviato da** viene impostato automaticamente sul tuo nome.</span><span class="sxs-lookup"><span data-stu-id="10446-122">The **Started by** field is automatically set to your name.</span></span>

10. <span data-ttu-id="10446-123">Il campo **Inizio effettivo** viene impostato automaticamente sulla data e ora corrente.</span><span class="sxs-lookup"><span data-stu-id="10446-123">The **Actual start** field is automatically set to the current date and time.</span></span> <span data-ttu-id="10446-124">Tuttavia, è possibile modificare il valore in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="10446-124">However, you can change the value as you require.</span></span>
11. <span data-ttu-id="10446-125">Nel campo **Note**, immettere eventuali note aggiuntive necessarie.</span><span class="sxs-lookup"><span data-stu-id="10446-125">In the **Notes** field, enter any additional notes that are required.</span></span>
12. <span data-ttu-id="10446-126">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="10446-126">Select **OK**.</span></span>

![Figura 1](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a><span data-ttu-id="10446-128">Elaborazione successiva delle richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="10446-128">Subsequent processing of maintenance requests</span></span>

<span data-ttu-id="10446-129">Dopo che una richiesta di intervento di manutenzione viene creata, ma prima che venga convertita in ordine di lavoro, le varie informazioni relative devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="10446-129">After a maintenance request is created, but before it's converted to a work order, various information should be updated on it.</span></span> <span data-ttu-id="10446-130">In genere, un addetto alla pianificazione o un altro dipendente amministrativo completa questa attività.</span><span class="sxs-lookup"><span data-stu-id="10446-130">Typically, a planner or another administrative employee completes this task.</span></span>

- <span data-ttu-id="10446-131">Nella pagina **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**, selezionare la richiesta da gestire, quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="10446-131">On the **All maintenance requests** or **Active maintenance requests** page, select the request to work with, and then select **Edit**.</span></span>

<span data-ttu-id="10446-132">Nella visualizzazione dettagli, è possibile aggiornare vari dati.</span><span class="sxs-lookup"><span data-stu-id="10446-132">In the details view, you can update various information.</span></span> <span data-ttu-id="10446-133">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="10446-133">Here are some examples:</span></span>

- <span data-ttu-id="10446-134">Selezionare e verificare il cespite.</span><span class="sxs-lookup"><span data-stu-id="10446-134">Select and verify the asset.</span></span> <span data-ttu-id="10446-135">Se è necessario selezionare un cespite diverso successivamente, è possibile impostare l'opzione **Cespite verificato** su **No**.</span><span class="sxs-lookup"><span data-stu-id="10446-135">If you must select a different asset later, you can set the **Asset verified** option to **No**.</span></span>
- <span data-ttu-id="10446-136">Selezionare un gruppo di addetti alla manutenzione e/o un addetto alla manutenzione.</span><span class="sxs-lookup"><span data-stu-id="10446-136">Select a responsible maintenance worker group and/or a responsible maintenance worker.</span></span> <span data-ttu-id="10446-137">Per ulteriori informazioni sull'impostazione richiesta, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="10446-137">For more information about the required setup, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>
- <span data-ttu-id="10446-138">Selezionare un tipo di processo di manutenzione e, se queste informazioni sono rilevanti, una variante correlata del processo di manutenzione e una mansione qualificata per il processo.</span><span class="sxs-lookup"><span data-stu-id="10446-138">Select a maintenance job type and, if this information is relevant, a related maintenance job variant and a job trade.</span></span>
- <span data-ttu-id="10446-139">Nei campi **Longitudine** e **Latitudine**, immettere le coordinate geografiche.</span><span class="sxs-lookup"><span data-stu-id="10446-139">In the **Latitude** and **Longitude** fields, enter geographic coordinates.</span></span> <span data-ttu-id="10446-140">Tutte le coordinate aggiunti alla richiesta di intervento di manutenzione verranno trasferite automaticamente a un ordine di lavoro correlato.</span><span class="sxs-lookup"><span data-stu-id="10446-140">Any coordinates that are added to a maintenance request are automatically transferred to a related work order.</span></span> 

![Figura 2](media/04-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="10446-142">Se si seleziona un cespite quando si crea una richiesta di intervento di manutenzione, è possibile aggiungere un solo problema al cespite.</span><span class="sxs-lookup"><span data-stu-id="10446-142">If you select an asset when you create a maintenance request, you can add one fault to the asset.</span></span> <span data-ttu-id="10446-143">Dopo che la richiesta di intervento di manutenzione è stata creata, è possibile aggiungere più problemi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="10446-143">After the maintenance request has been created, you can add more faults, as you require.</span></span> <span data-ttu-id="10446-144">Per aggiungere problemi, selezionare **Errore del cespite** nella pagina **Tutte le richieste di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="10446-144">To add faults, select **Asset fault** on the **All maintenance requests** page.</span></span>
