---
title: Fasi dell'ordine di assistenza
description: Tramite la definizione delle fasi di un ordine di assistenza e la loro assegnazione ai lavoratori, è possibile controllare il flusso di un ordine di assistenza tramite le attività che varie persone eseguono nell'organizzazione che presta tale servizio.
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b924be95c7e60598879e4d0cfd03193fe888dd7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569707"
---
# <a name="service-order-stages"></a><span data-ttu-id="788d4-103">Fasi dell'ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="788d4-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="788d4-104">È possibile impostare le fasi di un ordine di assistenza per definire le attività da completare, l'ordine in cui vengono completate e i lavoratori responsabili del loro completamento.</span><span class="sxs-lookup"><span data-stu-id="788d4-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="788d4-105">Tramite la definizione delle fasi di un ordine di assistenza e la loro assegnazione ai lavoratori, è possibile controllare il flusso di un ordine di assistenza tramite le attività che varie persone eseguono nell'organizzazione che presta tale servizio.</span><span class="sxs-lookup"><span data-stu-id="788d4-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="788d4-106">La sequenza delle fasi deve includere una fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="788d4-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="788d4-107">È inoltre possibile definire le azioni consentite a ogni fase.</span><span class="sxs-lookup"><span data-stu-id="788d4-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="788d4-108">Ad esempio, se si deseleziona la casella di controllo **Registrazione** per tutte le fasi eccetto la fase finale, si impedisce agli ordini di assistenza di essere registrati prima che vengano elaborati tramite la sequenza completa di fasi.</span><span class="sxs-lookup"><span data-stu-id="788d4-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="788d4-109">Creazione di un ramo nelle fasi di un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="788d4-109">Branching in service order stages</span></span>

<span data-ttu-id="788d4-110">Quando si imposta una fase di assistenza, è possibile creare più opzioni, o più rami, da cui scegliere per la fase di assistenza successiva.</span><span class="sxs-lookup"><span data-stu-id="788d4-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="788d4-111">Tutti i rami creati sono disponibili per la selezione dal completamento della fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="788d4-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="788d4-112">Ad esempio, si imposta **Pianificazione** come fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="788d4-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="788d4-113">Si creano due fasi denominate **In corso** e **Annulla**, quindi si seleziona **Pianificazione** come elemento principale.</span><span class="sxs-lookup"><span data-stu-id="788d4-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="788d4-114">Assegnare la fase **Pianificazione** all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="788d4-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="788d4-115">Quando la fase di pianificazione dell'ordine cliente viene completata, è possibile selezionare la fase **In corso** se l'ordine cliente è pronto a lavorare oppure è possibile selezionare la fase **Annulla** se l'ordine cliente viene annullato.</span><span class="sxs-lookup"><span data-stu-id="788d4-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="788d4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="788d4-116">See also</span></span>

[<span data-ttu-id="788d4-117">Imposta le fasi dell'ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="788d4-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="788d4-118">Cambiare la fase dell'ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="788d4-118">Change the service order stage</span></span>](change-service-order-stage.md)

  


