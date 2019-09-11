---
title: Aggiungere registrazioni di errore all'ordine di lavoro
description: In questo argomento viene descritto come aggiungere registrazioni di errore agli ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875740"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="54780-103">Aggiungere registrazioni di errore all'ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="54780-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="54780-104">È possibile aggiungere registrazioni di errore impostate in Designer errori a un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="54780-104">You can add faults set up in the fault designer to a work order.</span></span> <span data-ttu-id="54780-105">Il cespite selezionato nell'ordine di lavoro deve contenere tipi di cespite che hanno uno o più record di errore ad esso collegati.</span><span class="sxs-lookup"><span data-stu-id="54780-105">The asset selected in the work order must contain asset types that have one or more fault records connected to it.</span></span> <span data-ttu-id="54780-106">Per ulteriori informazioni, leggere la sezione [Gestione errori](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="54780-106">Read more about setup in the [Fault management](../setup-for-work-orders/fault-management.md) section.</span></span>

1. <span data-ttu-id="54780-107">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="54780-107">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="54780-108">Nell'elenco, selezionare l'ordine di lavoro in cui si desidera effettuare una registrazione di errore e fare clic su **Errore di cespite**.</span><span class="sxs-lookup"><span data-stu-id="54780-108">In the list, select the work order on which you want to make a fault registration and click **Asset fault**.</span></span>

3. <span data-ttu-id="54780-109">Nella Scheda dettaglio **Sintomi** fare clic su **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="54780-109">On the **Symptoms** FastTab, click **Add line**.</span></span> <span data-ttu-id="54780-110">Un numero di errore sequenziale viene automaticamente inserito nel campo **Errore**.</span><span class="sxs-lookup"><span data-stu-id="54780-110">A sequential fault number is automatically inserted in the **Fault** field.</span></span>

4. <span data-ttu-id="54780-111">Selezionare il sintomo pertinente nel campo **Sintomo errore**.</span><span class="sxs-lookup"><span data-stu-id="54780-111">Select the relevant symptom in the **Fault symptom** field.</span></span>

5. <span data-ttu-id="54780-112">Selezionare **Area di errore** e **Tipo di errore**.</span><span class="sxs-lookup"><span data-stu-id="54780-112">Select **Fault area** and **Fault type**.</span></span>

6. <span data-ttu-id="54780-113">La data corrente viene inserita automaticamente nel campo **Data errore**.</span><span class="sxs-lookup"><span data-stu-id="54780-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="54780-114">Se necessario, è possibile selezionare un'altra data.</span><span class="sxs-lookup"><span data-stu-id="54780-114">You can select another date, if necessary.</span></span>

7. <span data-ttu-id="54780-115">Nella Scheda dettaglio **Cause del sintomo selezionato**, aggiungere una riga che descrive la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="54780-115">On the **Causes for selected symptom** FastTab, add a line describing the cause of the problem.</span></span>

8. <span data-ttu-id="54780-116">Nella Scheda dettaglio **Rimedi per sintomo selezionato**, aggiungere una riga che descrive una possibile soluzione per il problema.</span><span class="sxs-lookup"><span data-stu-id="54780-116">On the **Remedies for selected symptom** FastTab, add a line describing a possible solution to the problem.</span></span>

9. <span data-ttu-id="54780-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="54780-117">Click **Save**.</span></span>

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="54780-119">Visualizzare gli errori registrati nei cespiti</span><span class="sxs-lookup"><span data-stu-id="54780-119">View asset faults</span></span>

<span data-ttu-id="54780-120">Nell'elenco **Errori di cespite**, è possibile ottenere una panoramica di tutti gli errori registrati nei cespiti.</span><span class="sxs-lookup"><span data-stu-id="54780-120">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="54780-121">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Errori di cespite** per aprire l'elenco.</span><span class="sxs-lookup"><span data-stu-id="54780-121">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults** to open the list.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="54780-122">Stampare il report degli errori di cespite</span><span class="sxs-lookup"><span data-stu-id="54780-122">Print asset fault report</span></span>

<span data-ttu-id="54780-123">Nella pagina elenco **Tutti i cespiti**, è possibile stampare un report degli errori di cespite contenente tutte le registrazioni di errore nonché una panoramica grafica delle statistiche degli errori.</span><span class="sxs-lookup"><span data-stu-id="54780-123">From the **All assets** list page, you can print an asset fault report displaying all fault registrations as well as a graphic overview of fault statistics.</span></span>

1. <span data-ttu-id="54780-124">Fare clic su **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="54780-124">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="54780-125">Nell'elenco **Cespiti**, selezionare il cespite per il quale si desidera stampare un report degli errori.</span><span class="sxs-lookup"><span data-stu-id="54780-125">In the **Assets** list, select the asset for which you want to print a fault report.</span></span>

3. <span data-ttu-id="54780-126">Nella scheda **Generale** > **Sezione report**, fare clic su **Errore di cespite**.</span><span class="sxs-lookup"><span data-stu-id="54780-126">On the **General** tab > **Reports section**, click **Asset fault**.</span></span>

4. <span data-ttu-id="54780-127">Inserire un periodo specifico oppure selezionare un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="54780-127">Insert a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="54780-128">Fare clic su **OK** per stampare il report.</span><span class="sxs-lookup"><span data-stu-id="54780-128">Click **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="54780-129">È inoltre possibile stampare un report degli errori per vari cespiti o tipi di cespite facendo clic su **Gestione cespiti** > **Report** > **Cespiti** > **Errore di cespite**.</span><span class="sxs-lookup"><span data-stu-id="54780-129">You can also print a fault report for several assets or asset types by clicking **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

