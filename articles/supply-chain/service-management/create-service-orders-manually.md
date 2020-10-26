---
title: Creare ordini di assistenza manualmente
description: È possibile creare ordini di assistenza manualmente utilizzando un contratto di assistenza oppure il modulo **Ordini di assistenza**.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51cfdb94a368df9e7082af3c768c79df44000342
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978727"
---
# <a name="create-service-orders-manually"></a><span data-ttu-id="a7c74-103">Creare ordini di assistenza manualmente</span><span class="sxs-lookup"><span data-stu-id="a7c74-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a7c74-104">È possibile creare ordini di assistenza manualmente utilizzando un contratto di assistenza oppure il modulo **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="a7c74-105">È inoltre possibile creare un ordine di assistenza a partire da un progetto.</span><span class="sxs-lookup"><span data-stu-id="a7c74-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="a7c74-106">Gli ordini di assistenza possono essere creati utilizzando processi automatizzati.</span><span class="sxs-lookup"><span data-stu-id="a7c74-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="a7c74-107">Creare un ordine di assistenza manualmente da un contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="a7c74-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="a7c74-108">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="a7c74-109">Selezionare un contratto di assistenza oppure crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="a7c74-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="a7c74-110">Fare clic sulla scheda **Consegna** e nel gruppo **Creare** fare clic su **Ordini di assistenza pianificati** per aprire il modulo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-110">Click the **Deliver** tab and in the **Create** group click **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="a7c74-111">Creare un ordine di assistenza manualmente nel modulo Ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="a7c74-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="a7c74-112">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="a7c74-113">Premere CTRL+N per creare un nuovo ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="a7c74-113">Press Ctrl+N to create a new service order.</span></span>

3.  <span data-ttu-id="a7c74-114">Creare le righe dell'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="a7c74-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="a7c74-115">Se la casella di controllo <STRONG>Consenti senza contratto di assistenza</STRONG> del modulo <STRONG>Parametri di gestione assistenza</STRONG> è selezionata, è possibile registrare le transazioni dalle righe dell'ordine di assistenza senza collegare l'ordine a un contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="a7c74-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="a7c74-116">Se la casella di controllo è deselezionata, prima di registrare le righe dell'ordine di assistenza è necessario almeno collegare l'ordine creato manualmente a un progetto.</span><span class="sxs-lookup"><span data-stu-id="a7c74-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="a7c74-117">Creare un ordine di assistenza da un progetto</span><span class="sxs-lookup"><span data-stu-id="a7c74-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="a7c74-118">Fare clic su **Gestione progetti e contabilità** \> **Comune** \> **Progetti** \> **Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-118">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="a7c74-119">Nel **riquadro azioni** del modulo **Progetti**, fai clic sulla scheda **Gestisci** \> **Assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-119">In the **Projects** form, on the **Action Pane**, click the **Manage** tab \> click **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="a7c74-120">Utilizzare la procedura precedente per la creazione manuale di un ordine di assistenza nel modulo **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="a7c74-121">Nel campo **ID progetto** verrà visualizzato il riferimento del progetto.</span><span class="sxs-lookup"><span data-stu-id="a7c74-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="a7c74-122">Se la casella di controllo <STRONG>Consenti senza contratto di assistenza</STRONG> del modulo <STRONG>Parametri di gestione assistenza</STRONG> è selezionata, è possibile registrare le transazioni dalle righe dell'ordine di assistenza senza collegare l'ordine a un contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="a7c74-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="a7c74-123">Se la casella di controllo è deselezionata, prima di registrare le righe dell'ordine di assistenza è necessario almeno collegare l'ordine creato manualmente a un progetto.</span><span class="sxs-lookup"><span data-stu-id="a7c74-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="a7c74-124">Creare un ordine di assistenza dal modulo Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="a7c74-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="a7c74-125">È possibile creare un ordine di assistenza dal modulo **Ordini cliente** utilizzando la procedura guidata **Crea un nuovo ordine di assistenza in base all'ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="a7c74-126">Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini cliente** \> **Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-126">Click **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="a7c74-127">Aprire l'ordine cliente rilevante.</span><span class="sxs-lookup"><span data-stu-id="a7c74-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="a7c74-128">Nella scheda **Ordine cliente**, fare clic su **Ordine di assistenza** per avviare la procedura guidata **Crea un nuovo ordine di assistenza in base all'ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-128">On the **Sales order** tab, click **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="a7c74-129">Fare clic su **Avanti \>** e quindi completare i passaggi seguenti nella pagina **Seleziona contratto per ordine di assistenza**:</span><span class="sxs-lookup"><span data-stu-id="a7c74-129">Click **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="a7c74-130">Utilizzare il campo **Contratto di assistenza** per selezionare il contratto di assistenza a cui associare il nuovo ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="a7c74-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="a7c74-131">Facoltativo: utilizzare il campo **ID progetto** per associare l'ordine di assistenza a un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="a7c74-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="a7c74-132">Fare clic su **Avanti \>** e quindi completare i passaggi seguenti nella pagina **Crea riga ordine di assistenza**:</span><span class="sxs-lookup"><span data-stu-id="a7c74-132">Click **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="a7c74-133">Immettere una data e un'ora in cui iniziare la chiamata di assistenza nel campo **Ora assistenza preferita**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="a7c74-134">Facoltativo: modificare il testo nel campo **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="a7c74-135">Per impostazione predefinita, questo campo contiene la descrizione del contratto di assistenza selezionato nella finestra precedente.</span><span class="sxs-lookup"><span data-stu-id="a7c74-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="a7c74-136">Nel campo **Responsabile** selezionare l'ID del dipendente responsabile del contratto e, se conosciuto, l'ID del tecnico preferito dal cliente per l'esecuzione della chiamata di assistenza.</span><span class="sxs-lookup"><span data-stu-id="a7c74-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="a7c74-137">Nel campo **ID contatto** selezionare la persona all'interno della società del cliente che deve essere contattata riguardo all'ordine di assistenza specificato.</span><span class="sxs-lookup"><span data-stu-id="a7c74-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="a7c74-138">Fare clic su **Avanti \>**, quindi scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a7c74-138">Click **Next \>**, and then click **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="a7c74-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7c74-139">See also</span></span>

[<span data-ttu-id="a7c74-140">Ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="a7c74-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="a7c74-141">Creare ordini di assistenza automaticamente</span><span class="sxs-lookup"><span data-stu-id="a7c74-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="a7c74-142">[Crea ordini di assistenza (modulo di classe)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="a7c74-142">[Create service orders (class form)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span></span> 

