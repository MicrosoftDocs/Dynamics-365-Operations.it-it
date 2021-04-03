---
title: Annulla ordini di assistenza
description: È possibile annullare un ordine di assistenza o una riga di ordine di assistenza a partire dall'ordine stesso oppure è possibile annullare più ordini di assistenza eseguendo un processo periodico.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a253a9c9ae4d7c34403db9bb5f3d63bc77e11101
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259676"
---
# <a name="cancel-service-orders"></a><span data-ttu-id="edc64-103">Annulla ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="edc64-103">Cancel service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="edc64-104">È possibile annullare un ordine di assistenza o una riga di ordine di assistenza a partire dall'ordine stesso oppure è possibile annullare più ordini di assistenza eseguendo un processo periodico.</span><span class="sxs-lookup"><span data-stu-id="edc64-104">You can cancel a service order or service order line from the service order itself, or you can cancel multiple service orders by running a periodic job.</span></span>


> [!NOTE]
> <P><span data-ttu-id="edc64-105">Un ordine di assistenza non può essere annullato se la relativa fase non consente l'annullamento, se contiene richieste articoli o se è già stato registrato.</span><span class="sxs-lookup"><span data-stu-id="edc64-105">Service orders cannot be canceled if the stage of the service order does not allow cancelation, if the service order has item requirements, or if the service order has already been posted.</span></span></P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a><span data-ttu-id="edc64-106">Annullare un ordine di assistenza nel modulo Ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="edc64-106">Cancel a service order in the Service orders form</span></span>

1.  <span data-ttu-id="edc64-107">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="edc64-107">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="edc64-108">Selezionare l'ordine di assistenza e fare clic su **Annulla ordine** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="edc64-108">Select the service order, and on the Action Pane, click **Cancel order**.</span></span>

## <a name="cancel-a-service-order-line"></a><span data-ttu-id="edc64-109">Annullare una riga di ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="edc64-109">Cancel a service order line</span></span>

1.  <span data-ttu-id="edc64-110">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="edc64-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="edc64-111">Fare doppio clic sull'ordine di assistenza contenente la riga che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="edc64-111">Double-click the service order that contains the line you want to cancel.</span></span>

2.  <span data-ttu-id="edc64-112">Selezionare la riga di ordine di assistenza che si desidera annullare, quindi fare clic su **Annulla riga ordine** per modificare lo stato della riga in **Annullata**.</span><span class="sxs-lookup"><span data-stu-id="edc64-112">Select the service order line that you want to cancel, and then click **Cancel order line** to change the status of the line to **Canceled**.</span></span>


> [!TIP]
> <P><span data-ttu-id="edc64-113">Per revocare l'annullamento di una riga di ordine di assistenza e impostare di nuovo lo stato su <STRONG>Creato</STRONG>, fare clic su <STRONG>Revoca annullamento</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="edc64-113">To reverse the cancellation of a service order line and change the status back to <STRONG>Created</STRONG>, click <STRONG>Revoke cancel</STRONG>.</span></span></P>


## <a name="cancel-multiple-service-orders"></a><span data-ttu-id="edc64-114">Annullare più ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="edc64-114">Cancel multiple service orders</span></span>

1.  <span data-ttu-id="edc64-115">Fare clic su **Gestione assistenza** \> **Periodico** \> **Ordini di assistenza** \> **Annulla ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="edc64-115">Click **Service management** \> **Periodic** \> **Service orders** \> **Cancel service orders**.</span></span>

2.  <span data-ttu-id="edc64-116">Fare clic sul pulsante **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="edc64-116">Click the **Select** button.</span></span>

3.  <span data-ttu-id="edc64-117">Nella colonna **Criteri** del modulo **Richiesta info** selezionare gli ordini di assistenza che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="edc64-117">In the **Inquiry** form, in the **Criteria** column, select the service orders that you want to cancel.</span></span>

4.  <span data-ttu-id="edc64-118">Fare clic su **OK** per chiudere il modulo **Richiesta info**.</span><span class="sxs-lookup"><span data-stu-id="edc64-118">Click **OK** to close the **Inquiry** form.</span></span>

5.  <span data-ttu-id="edc64-119">Selezionare la casella di controllo **Mostra Registro informazioni** per generare un Registro informazioni in cui sono riportati gli ordini di assistenza annullati.</span><span class="sxs-lookup"><span data-stu-id="edc64-119">Select the **Show Infolog** check box to generate an Infolog that lists the canceled service orders.</span></span>

6.  <span data-ttu-id="edc64-120">Selezionare la casella di controllo **Revoca annullamento** se si desidera revocare lo stato **Annullato** di un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="edc64-120">Select the **Revoke cancel** check box if you want to reverse the **Canceled** status of a service order.</span></span>

7.  <span data-ttu-id="edc64-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="edc64-121">Click **OK**.</span></span>

<span data-ttu-id="edc64-122">Gli ordini di assistenza selezionati verranno annullati o il relativo stato di avanzamento verrà reimpostato da **Annullato** a **In corso**.</span><span class="sxs-lookup"><span data-stu-id="edc64-122">The selected service orders are either canceled or their progress status of **Canceled** has been reversed to **In process**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="edc64-123">Se si seleziona la casella di controllo <STRONG>Revoca annullamento</STRONG>, gli ordini di assistenza con stato di avanzamento <STRONG>Annullato</STRONG> verranno revocati e quelli con stato di avanzamento <STRONG>In corso</STRONG> non verranno annullati.</span><span class="sxs-lookup"><span data-stu-id="edc64-123">If you select the <STRONG>Revoke cancel</STRONG> check box, service orders with a progress status of <STRONG>Canceled</STRONG> are reversed and service orders with a progress status of <STRONG>In process</STRONG> are not canceled.</span></span></P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]