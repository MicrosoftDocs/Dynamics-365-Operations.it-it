---
title: Panoramica dei contratti di assistenza
description: Nel contratto di servizio, il cliente accetta un tempo minimo di risposta basato sulla data in cui la società di servizi registra l'uscita e quando il problema viene risolto.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01cdfe519e55ca2a9aa17f4ac181ee675b2793cf
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982357"
---
# <a name="service-level-agreements-overview"></a><span data-ttu-id="9711f-103">Panoramica dei contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="9711f-103">Service level agreements overview</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9711f-104">Un contratto di servizio (SLA) è un contratto tra una società di servizi e un cliente di servizio.</span><span class="sxs-lookup"><span data-stu-id="9711f-104">A service level agreement (SLA) is an agreement between a service company and a service customer.</span></span> <span data-ttu-id="9711f-105">Nel contratto di servizio, il cliente accetta un tempo minimo di risposta basato sulla data in cui la società di servizi registra l'uscita e quando il problema viene risolto.</span><span class="sxs-lookup"><span data-stu-id="9711f-105">In a SLA, the customer agrees to a minimum response time based on when the service company records the issue and when the issue is resolved.</span></span>

<span data-ttu-id="9711f-106">Un accordo di questo tipo offre un livello di servizio fornito ai clienti in modo standardizzato e risulta utile perché consente alla società di determinare con precisione la data entro la quale deve essere completato un lavoro.</span><span class="sxs-lookup"><span data-stu-id="9711f-106">A SLA enforces a standard level of service that is offered to customers, and also makes it transparent to a service company when a service job should be completed.</span></span>

<span data-ttu-id="9711f-107">Per offrire ai clienti diversi livelli di servizio, è possibile creare più accordi.</span><span class="sxs-lookup"><span data-stu-id="9711f-107">Any number of SLAs can be created to offer service customers different levels of service.</span></span>

## <a name="create-a-service-level-agreement"></a><span data-ttu-id="9711f-108">Creare un accordo sui livelli di servizio</span><span class="sxs-lookup"><span data-stu-id="9711f-108">Create a service level agreement</span></span>

1.  <span data-ttu-id="9711f-109">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Contratti di assistenza** \> **Accordi sui livelli di servizio**.</span><span class="sxs-lookup"><span data-stu-id="9711f-109">Click **Service management** \> **Setup** \> **Service agreements** \> **Service level agreements**.</span></span>

2.  <span data-ttu-id="9711f-110">Nel campo **Accordo sui livelli di servizio** selezionare un accordo sui livelli di servizio da associare al nuovo contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="9711f-110">Type a name for the service level agreement in the **Service level agreement** field.</span></span>

3.  <span data-ttu-id="9711f-111">Immettere il tempo che si desidera consentire per il completamento delle chiamate di assistenza collegate al contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="9711f-111">Type the time that you want to allow for completion of service calls that are attached to the service level agreement.</span></span> <span data-ttu-id="9711f-112">Selezionare un calendario se si desidera basare il contratto di assistenza su un calendario specifico.</span><span class="sxs-lookup"><span data-stu-id="9711f-112">Then select a calendar if you want to base the service level agreement on a specific calendar.</span></span>

## <a name="apply-a-service-level-agreement"></a><span data-ttu-id="9711f-113">Applicare un accordo sui livelli di servizio</span><span class="sxs-lookup"><span data-stu-id="9711f-113">Apply a service level agreement</span></span>

<span data-ttu-id="9711f-114">L'accordo sui livelli di servizi viene applicato direttamente a un contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="9711f-114">The SLA is applied directly to a service agreement.</span></span>

<span data-ttu-id="9711f-115">Gli ordini di assistenza creati manualmente e collegati a un contratto di assistenza associato a un accordo sui livelli di servizio vengono valutati in base all'accordo.</span><span class="sxs-lookup"><span data-stu-id="9711f-115">Service orders that you create manually and attach to a service agreement that has an SLA are measured against that SLA.</span></span>

<span data-ttu-id="9711f-116">Gli ordini di assistenza creati automaticamente non vengono collegati a un accordo sui livelli di servizio.</span><span class="sxs-lookup"><span data-stu-id="9711f-116">Service orders that you create automatically are not attached to an SLA.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a><span data-ttu-id="9711f-117">Applicare l'accordo sui livelli di servizio al contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="9711f-117">Apply the service level agreement to the service agreement</span></span>

1.  <span data-ttu-id="9711f-118">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="9711f-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="9711f-119">Selezionare il contratto di assistenza in cui si desidera applicare il contratto di assistenza e fare clic su **Modifica** nel **riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="9711f-119">Select the service agreement that you want to apply the SLA to, and then click **Edit** on the **Action Pane**.</span></span>

2.  <span data-ttu-id="9711f-120">Nel campo **Accordo sui livelli di servizio**, selezionare il contratto di servizio da assegnare.</span><span class="sxs-lookup"><span data-stu-id="9711f-120">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a><span data-ttu-id="9711f-121">Applicare l'accordo sui livelli di servizio al gruppo dei contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="9711f-121">Apply the service level agreement to the service agreement group</span></span>

1.  <span data-ttu-id="9711f-122">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Contratti di assistenza** \> **Gruppi contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="9711f-122">Click **Service management** \> **Setup** \> **Service agreements** \> **Service agreement groups**.</span></span>

2.  <span data-ttu-id="9711f-123">Nel campo **Accordo sui livelli di servizio**, selezionare il contratto di servizio da assegnare.</span><span class="sxs-lookup"><span data-stu-id="9711f-123">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="track-time-on-a-service-order-against-an-sla"></a><span data-ttu-id="9711f-124">Tenere traccia del tempo in un ordine di assistenza in base a un accordo sui livelli di servizio</span><span class="sxs-lookup"><span data-stu-id="9711f-124">Track time on a service order against an SLA</span></span>

<span data-ttu-id="9711f-125">Quando si crea un nuovo ordine di assistenza per un contratto di assistenza a cui è assegnato il contratto di assistenza, l'intervallo di tempo per la consegna di servizio inizia e il sistema inizia a tenere traccia del tempo di consegna.</span><span class="sxs-lookup"><span data-stu-id="9711f-125">When you create a new service order for a service agreement that an SLA is assigned to, the time interval for the delivery of the service is initiated, and the system starts to track the delivery time.</span></span> <span data-ttu-id="9711f-126">Inoltre, è possibile impostare le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="9711f-126">Additionally, you can set the following options:</span></span>

  - <span data-ttu-id="9711f-127">È possibile iniziare e interrompere la registrazione del tempo nell'ordine di assistenza per registrare il tempo complessivo impiegato per eseguire gli ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="9711f-127">You can start and stop time recording on the service order to register the total amount of time that is spent on service orders.</span></span>

  - <span data-ttu-id="9711f-128">È possibile monitorare la conformità con l'intervallo di tempo impostato nell'accordo sui livelli di servizio.</span><span class="sxs-lookup"><span data-stu-id="9711f-128">You can monitor compliance with the time interval that is set in the service level agreement.</span></span>

  - <span data-ttu-id="9711f-129">È possibile definire i codici motivo che dovranno essere impostati se l'intervallo di tempo specificato nell'accordo sui livelli di servizio viene superato.</span><span class="sxs-lookup"><span data-stu-id="9711f-129">You can define reason codes that must be set if the time interval of the service level agreement is exceeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="9711f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9711f-130">See also</span></span>

[<span data-ttu-id="9711f-131">Visualizzare la conformità ai contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="9711f-131">View compliance with service level agreements</span></span>](view-compliance-with-service-level-agreements.md)

  


