---
title: I record cliente non vengono visualizzati in Commerce Headquarters
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i record cliente non vengono visualizzati immediatamente in Commerce Headquarters.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b8d065dd104df616ba8f10f7813e74c900fdcf77
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018484"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a><span data-ttu-id="d6dfc-103">I record cliente non vengono visualizzati in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="d6dfc-103">Customer records don't appear in Commerce headquarters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d6dfc-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i record cliente non vengono visualizzati immediatamente in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-104">This topic provides troubleshooting guidance that can help when customer records don't immediately appear in Commerce headquarters.</span></span>

## <a name="description"></a><span data-ttu-id="d6dfc-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6dfc-105">Description</span></span>

<span data-ttu-id="d6dfc-106">Quando si crea un nuovo record cliente utilizzando il flusso di registrazione nella vetrina e-commerce, il record cliente corrispondente non viene visualizzato immediatamente in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-106">When you create a new customer record by using the sign-up flow in the e-commerce storefront, the corresponding customer record doesn't immediately appear in Commerce headquarters.</span></span>

## <a name="resolution"></a><span data-ttu-id="d6dfc-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d6dfc-107">Resolution</span></span>

### <a name="disable-customer-creation-in-async-mode"></a><span data-ttu-id="d6dfc-108">Disabilitare la creazione di clienti in modalità asincrona</span><span class="sxs-lookup"><span data-stu-id="d6dfc-108">Disable customer creation in async mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6dfc-109">Se si disabilita la creazione di clienti in modalità asincrona, le prestazioni del sistema potrebbero risentirne, poiché la creazione di ogni record produrrà una richiesta in tempo reale a Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-109">If you disable asynchronous customer creation, system performance could be affected, because creation of each record will produce a real-time request to Commerce headquarters.</span></span> <span data-ttu-id="d6dfc-110">Inoltre, se Commerce Headquarters è inattivo (ad esempio, durante i flussi di manutenzione), qualsiasi nuovo flusso di creazione di clienti produrrà errori.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-110">In addition, if Commerce headquarters is down (for example, during servicing flows), any new customer creation flows will produce errors.</span></span>

<span data-ttu-id="d6dfc-111">Per disabilitare la creazione di cliente in modalità asincrona in Commerce Headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-111">To disable customer creation in async mode in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d6dfc-112">Selezionare **Retail e Commerce \> Impostazione canale \> Impostazione punto vendita online \> Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-112">Go to **Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="d6dfc-113">Se non si utilizzando già un profilo di funzionalità per il canale online, crearne uno.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-113">If you aren't already using a functionality profile for your online channel, create one.</span></span>
1. <span data-ttu-id="d6dfc-114">Assicurarsi che l'opzione **Crea cliente in modalità asincrona** sia impostata su **No**.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-114">Make sure that the **Create customer in async mode** option is set to **No**.</span></span>
1. <span data-ttu-id="d6dfc-115">Andare a **Retail e Commerce \> Canali \> Punti vendita online**.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-115">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="d6dfc-116">Selezionare il punto vendita online per cui disabilitare la creazione di clienti in modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-116">Select the online store to disable asynchronous customer creation for.</span></span>
1. <span data-ttu-id="d6dfc-117">Nella scheda **Generale**, assicurarsi che il campo **Profilo funzionalità** sia impostato sul profilo di funzionalità che si sta utilizzando per il canale online.</span><span class="sxs-lookup"><span data-stu-id="d6dfc-117">On the **General** tab, make sure that the **Functionality profile** field is set to the functionality profile that you're using for your online channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6dfc-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d6dfc-118">Additional resources</span></span>

[<span data-ttu-id="d6dfc-119">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="d6dfc-119">Setup a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
