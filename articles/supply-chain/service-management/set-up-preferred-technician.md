---
title: Impostare un tecnico preferito
description: È possibile selezionare qualsiasi lavoratore come tecnico preferito per un contratto o per un ordine di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a06ec39bd0552faf7961ae75ff393f0b8edac2eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991742"
---
# <a name="set-up-a-preferred-technician"></a><span data-ttu-id="e2abb-103">Impostare un tecnico preferito</span><span class="sxs-lookup"><span data-stu-id="e2abb-103">Set up a preferred technician</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e2abb-104">È possibile selezionare qualsiasi lavoratore come tecnico preferito per un contratto o per un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="e2abb-104">You can select any worker as a preferred technician for a service agreement or service order.</span></span> <span data-ttu-id="e2abb-105">Tuttavia, è consigliabile aggiungere il lavoratore al team di intervento appropriato in modo che venga incluso nel **Prospetto interventi**.</span><span class="sxs-lookup"><span data-stu-id="e2abb-105">However, it is a good idea to add the worker to the appropriate dispatch team so that the worker is included on the **Dispatch board**.</span></span>

## <a name="assign-employee-to-a-dispatch-team"></a><span data-ttu-id="e2abb-106">Assegnare un dipendente a un team di intervento</span><span class="sxs-lookup"><span data-stu-id="e2abb-106">Assign employee to a dispatch team</span></span>

1.  <span data-ttu-id="e2abb-107">Fare clic su **Risorse umane** \> **Comune** \> **Lavoratori** \> **Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="e2abb-107">Click **Human resources** \> **Common** \> **Workers** \> **Workers**.</span></span> <span data-ttu-id="e2abb-108">Fare doppio clic su un lavoratore per aprire la pagina dei dettagli relativi al lavoratore.</span><span class="sxs-lookup"><span data-stu-id="e2abb-108">Double-click a worker to open the worker details page.</span></span> <span data-ttu-id="e2abb-109">Nel **riquadro azioni**, fare clic su **Impostazione** \>**Team di intervento** per aprire il modulo **Lavoratori di intervento**.</span><span class="sxs-lookup"><span data-stu-id="e2abb-109">On the **Action Pane**, click **Setup** \>**Dispatch team** to open the **Dispatch workers** form.</span></span>

2.  <span data-ttu-id="e2abb-110">Nel campo **Team di intervento** selezionare il team a cui assegnare il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="e2abb-110">In the **Dispatch team** field, select the team to assign the worker to.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a><span data-ttu-id="e2abb-111">Assegnare un tecnico preferito a un contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="e2abb-111">Assign a preferred technician to a service agreement</span></span>

1.  <span data-ttu-id="e2abb-112">Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="e2abb-112">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="e2abb-113">Fare doppio clic su un contratto di assistenza per aprire il modulo dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="e2abb-113">Double-click a service agreement to open the details form.</span></span>

2.  <span data-ttu-id="e2abb-114">Nella scheda **Generale**, selezionare il campo **Tecnico preferito**, quindi selezionare un membro del team di intervento appropriato come tecnico preferito per il contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="e2abb-114">On the **General** tab, select the **Preferred technician** field, and then select a member of the appropriate dispatch team as the preferred technician for the service agreement.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-order"></a><span data-ttu-id="e2abb-115">Assegnare un tecnico preferito a un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="e2abb-115">Assign a preferred technician to a service order</span></span>

1.  <span data-ttu-id="e2abb-116">Fare clic su **Gestione assistenza** \> **Periodico** \> **Prospetto interventi**.</span><span class="sxs-lookup"><span data-stu-id="e2abb-116">Click **Service management** \> **Periodic** \> **Dispatch board**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="e2abb-117">Nel modulo <STRONG>Prospetto interventi</STRONG> specificare l'intervallo di date in cui devono rientrare le attività di intervento da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="e2abb-117">In the <STRONG>Dispatch board</STRONG> form, specify a date range for dispatch activities to view.</span></span> <span data-ttu-id="e2abb-118">Indicare inoltre se si desidera visualizzare le attività chiuse e limitare l'elenco delle attività di intervento ai team dei quali si è membri o che si è autorizzati a monitorare.</span><span class="sxs-lookup"><span data-stu-id="e2abb-118">Also, specify whether to display closed activities and whether to limit the dispatch activity list to teams that you belong to or are authorized to monitor.</span></span> <span data-ttu-id="e2abb-119">Scegliere <STRONG>OK</STRONG> per aprire il modulo <STRONG>Prospetto interventi</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e2abb-119">Click <STRONG>OK</STRONG> to open the <STRONG>Dispatch board</STRONG>.</span></span></P>



2.  <span data-ttu-id="e2abb-120">Selezionare la riga dell'attività di assistenza tecnica da modificare.</span><span class="sxs-lookup"><span data-stu-id="e2abb-120">Select the line of the service activity to modify.</span></span>

3.  <span data-ttu-id="e2abb-121">Nella scheda **Correlati** utilizzare l'elenco **Lavoratore** per impostare un membro del team di intervento appropriato come tecnico preferito per la chiamata di assistenza.</span><span class="sxs-lookup"><span data-stu-id="e2abb-121">On the **Related** tab, use the **Worker** list to assign a member of the appropriate dispatch team as the preferred technician for the service call.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2abb-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2abb-122">See also</span></span>

[<span data-ttu-id="e2abb-123">Panoramica sviluppo e definizione dei contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="e2abb-123">Develop and establish service agreements overview</span></span>](service-agreements.md)

[<span data-ttu-id="e2abb-124">Creare ordini di assistenza manualmente</span><span class="sxs-lookup"><span data-stu-id="e2abb-124">Create service orders manually</span></span>](create-service-orders-manually.md)

<span data-ttu-id="e2abb-125">[Contratti di assistenza (modulo)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="e2abb-125">[Service agreements (form)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span></span>
  


