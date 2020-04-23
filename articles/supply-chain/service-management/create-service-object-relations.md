---
title: Creare relazioni di oggetti assistenza
description: In questo argomento viene descritto come creare relazioni di oggetti assistenza per un contratto di assistenza e un ordine di assistenza.
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
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab5de850ef40c26e447b96d8f42ccf83fb490818
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202769"
---
# <a name="create-service-object-relations"></a><span data-ttu-id="97947-103">Creare relazioni di oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="97947-103">Create service object relations</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="97947-104">In questo argomento viene descritto come creare relazioni di oggetti assistenza per un contratto di assistenza e un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="97947-104">This topic describes how to create service object relations for a service agreement and a service order.</span></span> <span data-ttu-id="97947-105">Per creare una relazione dell'oggetto di assistenza, associare l'oggetto assistenza a un contratto o all'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="97947-105">When you a create service object relation, you associate the service object to a service agreement or service order.</span></span> <span data-ttu-id="97947-106">Quando un cliente richiede il servizio per un articolo che è un oggetto assistenza, è possibile selezionare l'oggetto assistenza dall'elenco delle relazioni di oggetti assistenza.</span><span class="sxs-lookup"><span data-stu-id="97947-106">When a customer requests service for an item that is a service object, you can select the service object from the list of service object relations.</span></span>

## <a name="create-a-service-object-relation-for-a-service-agreement"></a><span data-ttu-id="97947-107">Creare una relazione dell'oggetto di assistenza per un contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="97947-107">Create a service object relation for a service agreement</span></span>

<span data-ttu-id="97947-108">Utilizzare i seguenti passaggi per creare una relazione dell'oggetto di assistenza per un contratto di assistenza:</span><span class="sxs-lookup"><span data-stu-id="97947-108">Use the following steps to create a service object relation for a service agreement:</span></span>

1.  <span data-ttu-id="97947-109">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="97947-109">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="97947-110">Nell'elenco **Contratti di assistenza** selezionare un contratto di assistenza esistente, fare clic su **Nuovo** per creare un nuovo contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="97947-110">In the **Service agreements** list, select an existing service agreement, or click **New** to create a new service agreement.</span></span>

3.  <span data-ttu-id="97947-111">Nel **riquadro azioni** del modulo **Contratti di assistenza**, nel gruppo **Relazioni** della scheda **Contratto di assistenza** fare clic su **Oggetti assistenza**.</span><span class="sxs-lookup"><span data-stu-id="97947-111">In the **Service agreements** form, on the **Action Pane**, on the **Service agreement** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="97947-112">Nel modulo **Oggetti assistenza** fare clic su **Nuovo**, quindi selezionare un oggetto di assistenza per questo contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="97947-112">In the **Service objects** form, click **New**, and then select a service object for this service agreement.</span></span>

5.  <span data-ttu-id="97947-113">Per assegnare una distinta base (DBA) modello al contratto di assistenza fare clic su **Funzioni**, quindi selezionare **Collega DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="97947-113">To assign a template bill of materials (BOM) to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="97947-114">Nel modulo **Seleziona DBA modello**, selezionare un modello nel campo **DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="97947-114">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 

## <a name="create-a-service-object-relation-for-a-service-order"></a><span data-ttu-id="97947-115">Creare una relazione dell'oggetto di assistenza per un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="97947-115">Create a service object relation for a service order</span></span>

<span data-ttu-id="97947-116">Utilizzare i seguenti passaggi per creare una relazione dell'oggetto di assistenza per un ordine di assistenza:</span><span class="sxs-lookup"><span data-stu-id="97947-116">Use the following steps to create a service object relation for a service order:</span></span>

1.  <span data-ttu-id="97947-117">Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="97947-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="97947-118">Nell'elenco **Ordini di assistenza** selezionare un ordine di assistenza esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="97947-118">In the **Service orders** list, select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="97947-119">Nel **riquadro azioni** del modulo **Ordini di assistenza**, nel gruppo **Relazioni** della scheda **Ordine di assistenza** fare clic su **Oggetti assistenza**.</span><span class="sxs-lookup"><span data-stu-id="97947-119">In the **Service orders** form, on the **Action Pane**, on the **Service order** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="97947-120">Nel modulo **Oggetti assistenza** fare clic su **Nuovo**, quindi selezionare un oggetto di assistenza per questo ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="97947-120">In the **Service objects** form, click **New**, and then select a service object for this service order.</span></span>

5.  <span data-ttu-id="97947-121">Per assegnare una DBA modello al contratto di assistenza fare clic su **Funzioni**, quindi selezionare **Collega DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="97947-121">To assign a template BOM to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="97947-122">Nel modulo **Seleziona DBA modello**, selezionare un modello nel campo **DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="97947-122">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 


## <a name="see-also"></a><span data-ttu-id="97947-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97947-123">See also</span></span>

[<span data-ttu-id="97947-124">Panoramica oggetti di servizio</span><span class="sxs-lookup"><span data-stu-id="97947-124">Service objects overview</span></span>](service-objects.md)

[<span data-ttu-id="97947-125">Relazioni oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="97947-125">Service object relations</span></span>](service-object-relations.md)

[<span data-ttu-id="97947-126">DBA modello</span><span class="sxs-lookup"><span data-stu-id="97947-126">Template BOMs</span></span>](template-boms.md)

  


