---
title: Creare ordini di assistenza automaticamente
description: "È possibile creare ordini di assistenza per uno o più contratti di assistenza."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: ee68190b117b974ff4131f5d2237d138cac1fda3
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="create-service-orders-automatically"></a><span data-ttu-id="89145-103">Creare ordini di assistenza automaticamente</span><span class="sxs-lookup"><span data-stu-id="89145-103">Create service orders automatically</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="89145-104">È possibile creare ordini di assistenza per uno o più contratti di assistenza.</span><span class="sxs-lookup"><span data-stu-id="89145-104">You can create service orders for one service agreement or for several service agreements.</span></span> <span data-ttu-id="89145-105">Dopo la creazione è possibile visualizzare gli ordini di assistenza nel modulo **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="89145-105">When they are created, you can view your service orders in the **Service orders** form.</span></span>

<span data-ttu-id="89145-106">Gli ordini di assistenza vengono creati solo per il periodo di validità del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="89145-106">Service orders are created only for the valid period of the service agreement.</span></span> <span data-ttu-id="89145-107">Se l'intervallo specificato nel modulo **Crea ordini di assistenza** inizia prima della data di inizio o termina dopo la data di fine del contratto di assistenza, gli ordini di assistenza verranno creati solo per la parte dell'intervallo compresa nel periodo del contratto.</span><span class="sxs-lookup"><span data-stu-id="89145-107">If the interval that you specify in the **Create service orders** form is before the starting date or after the ending date of the service agreement, service orders are created only for the part of the interval that is within the service agreement dates.</span></span>

<span data-ttu-id="89145-108">Quando si creano manualmente o automaticamente ordini di assistenza dalla riga del contratto di assistenza, l'ordine di assistenza deve rientrare nell'intervallo di tempo definito dalle date di inizio e fine relative alla riga, a meno che la data di fine nella riga non sia specificata.</span><span class="sxs-lookup"><span data-stu-id="89145-108">When you create service orders manually or automatically from the service agreement line, the service order must be in the time interval that is defined by the starting and ending dates for the line, unless you do not specify an ending date on the line.</span></span>

## <a name="create-service-orders-automatically-for-a-service-agreement"></a><span data-ttu-id="89145-109">Creare ordini di assistenza automaticamente per un contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="89145-109">Create service orders automatically for a service agreement</span></span>

1.  <span data-ttu-id="89145-110">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="89145-110">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="89145-111">Selezionare un contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="89145-111">Select a service agreement.</span></span>

3.  <span data-ttu-id="89145-112">Fare clic sulla scheda **Consegna**, quindi fare clic su **Ordini di assistenza pianificati**.</span><span class="sxs-lookup"><span data-stu-id="89145-112">Click the **Deliver** tab, and then click **Planned service orders**.</span></span>

4.  <span data-ttu-id="89145-113">Specificare una data nei campi **Dal** e **Al** per definire il periodo di assistenza.</span><span class="sxs-lookup"><span data-stu-id="89145-113">Specify dates in the **From date** and **To date** fields to define the service period.</span></span>

5.  <span data-ttu-id="89145-114">Selezionare la casella di controllo **Mostra Registro informazioni** per visualizzare l'elenco degli ordini di assistenza creati.</span><span class="sxs-lookup"><span data-stu-id="89145-114">Select the **Show Infolog** check box to display a list of the service orders that are created.</span></span>

6.  <span data-ttu-id="89145-115">Selezionare i tipi di transazioni nel gruppo di campi **Includi tipi di transazioni**.</span><span class="sxs-lookup"><span data-stu-id="89145-115">Select transaction types in the **Include transaction types** field group.</span></span> <span data-ttu-id="89145-116">I tipi di transazione rappresentano le righe create nel contratto di assistenza e ciascun tipo di transazione selezionato determina la generazione di più ordini di assistenza, a seconda dell'intervallo di assistenza specificato nella riga del contratto.</span><span class="sxs-lookup"><span data-stu-id="89145-116">The transaction types represent the lines that are created in the service agreement, and each transaction type that you select generates several service orders, depending on the service interval that is specified on the service agreement line.</span></span>

7.  <span data-ttu-id="89145-117">Selezionare la casella di controllo **Continua** per creare gli eventuali ordini di assistenza mancanti all'interno di una serie di ordini continua.</span><span class="sxs-lookup"><span data-stu-id="89145-117">To create any service orders that are missing from continuous series of service orders, select the **Continuous** check box.</span></span>

8.  <span data-ttu-id="89145-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89145-118">Click **OK**.</span></span>

## <a name="create-service-orders-automatically-for-several-service-agreements"></a><span data-ttu-id="89145-119">Creare ordini di assistenza automaticamente per più contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="89145-119">Create service orders automatically for several service agreements</span></span>

1.  <span data-ttu-id="89145-120">Fare clic su **Gestione assistenza** \> **Periodico** \> **Ordini di assistenza** \> **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="89145-120">Click **Service management** \> **Periodic** \> **Service orders** \> **Create service orders**.</span></span>

2.  <span data-ttu-id="89145-121">Fare clic su **Seleziona** per operare le selezioni di aggiunta o rimozione dei criteri utilizzati per creare gli ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="89145-121">Click **Select** to make selections to add or remove criteria to use to create service orders.</span></span>

3.  <span data-ttu-id="89145-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89145-122">Click **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="89145-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89145-123">See also</span></span>

[<span data-ttu-id="89145-124">Ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="89145-124">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="89145-125">Creare ordini di assistenza automaticamente</span><span class="sxs-lookup"><span data-stu-id="89145-125">Automatically creating service orders</span></span>](auto-create-service-orders.md)

  



