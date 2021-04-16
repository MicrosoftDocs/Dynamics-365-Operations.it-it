---
title: Aggiungere registrazioni di errore all'ordine di lavoro
description: In questo argomento viene descritto come aggiungere registrazioni di errore agli ordini di lavoro in Gestione cespiti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0a79986e3b477865bc1816a1d28c1b7094ae3974
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809808"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="ad3f7-103">Aggiungere errore all'ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="ad3f7-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="ad3f7-104">È possibile aggiungere registrazioni di errore impostate in Designer errori a un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="ad3f7-105">Uno o più record di errore devono essere collegati ai tipi di cespite utilizzati per il cespite selezionato nell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="ad3f7-106">Per ulteriori informazioni sull'impostazione, vedere [Gestione errori](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="ad3f7-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="ad3f7-107">Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ad3f7-108">Selezionare l'ordine di lavoro per effettuare una registrazione dell'errore, quindi nel riquadro azioni, nella scheda **Ordine di lavoro**, nel gruppo **Cespite**, selezionare **Errore di cespite**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="ad3f7-109">Nella Scheda dettaglio **Sintomi** selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="ad3f7-110">Un numero di errore sequenziale viene automaticamente inserito nel campo **Errore**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="ad3f7-111">Selezionare il sintomo pertinente nel campo **Sintomo errore**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="ad3f7-112">Nei campi **Area di errore** e **Tipo di errore**, selezionare i valori appropriati.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="ad3f7-113">La data corrente viene inserita automaticamente nel campo **Data errore**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="ad3f7-114">È possibile selezionare una data diversa in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="ad3f7-115">Nella Scheda dettaglio **Cause del sintomo selezionato**, aggiungere una riga che descrive la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="ad3f7-116">Nella Scheda dettaglio **Rimedi per sintomo selezionato**, aggiungere una riga che descrive una possibile soluzione per il problema.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="ad3f7-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-117">Select **Save**.</span></span>

<span data-ttu-id="ad3f7-118">Nella figura seguente viene illustrato un esempio di una registrazione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-118">The illustration below shows an example of a fault registration.</span></span>

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="ad3f7-120">Visualizzare gli errori registrati nei cespiti</span><span class="sxs-lookup"><span data-stu-id="ad3f7-120">View asset faults</span></span>

<span data-ttu-id="ad3f7-121">Nell'elenco **Errori di cespite**, è possibile ottenere una panoramica di tutti gli errori registrati nei cespiti.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="ad3f7-122">Nella pagina elenco **Errori di cespite**, è possibile ottenere una panoramica di tutti gli errori registrati nei cespiti.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="ad3f7-123">Per aprire la pagina, selezionare **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Errori di cespite**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="ad3f7-124">Stampare il report degli errori di cespite</span><span class="sxs-lookup"><span data-stu-id="ad3f7-124">Print asset fault report</span></span>

<span data-ttu-id="ad3f7-125">Nella pagina elenco **Tutti i cespiti**, è possibile stampare un report degli errori di cespite contenente tutte le registrazioni di errore e una panoramica grafica delle statistiche degli errori.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="ad3f7-126">Selezionare **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="ad3f7-127">Selezionare tutti i cespiti per cui stampare il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="ad3f7-128">Nel riquadro azioni, scheda **Generale**, gruppo **Report**, selezionare **Errore di cespite**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="ad3f7-129">Immettere un periodo specifico oppure selezionare un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="ad3f7-130">Selezionare **OK** per stampare il report.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="ad3f7-131">Per stampare un report degli errori per vari cespiti o tipi di cespite, selezionare **Gestione cespiti** > **Report** > **Cespiti** > **Errore di cespite**.</span><span class="sxs-lookup"><span data-stu-id="ad3f7-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]