---
title: Fasi dell'ordine di assistenza
description: Tramite la definizione delle fasi di un ordine di assistenza e la loro assegnazione ai lavoratori, è possibile controllare il flusso di un ordine di assistenza tramite le attività che varie persone eseguono nell'organizzazione che presta tale servizio.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eab1b10e8c8782306c1c2d892f965dc0795c69a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224404"
---
# <a name="service-order-stages"></a><span data-ttu-id="58be0-103">Fasi dell'ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="58be0-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="58be0-104">È possibile impostare le fasi di un ordine di assistenza per definire le attività da completare, l'ordine in cui vengono completate e i lavoratori responsabili del loro completamento.</span><span class="sxs-lookup"><span data-stu-id="58be0-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="58be0-105">Tramite la definizione delle fasi di un ordine di assistenza e la loro assegnazione ai lavoratori, è possibile controllare il flusso di un ordine di assistenza tramite le attività che varie persone eseguono nell'organizzazione che presta tale servizio.</span><span class="sxs-lookup"><span data-stu-id="58be0-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="58be0-106">La sequenza delle fasi deve includere una fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="58be0-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="58be0-107">È inoltre possibile definire le azioni consentite a ogni fase.</span><span class="sxs-lookup"><span data-stu-id="58be0-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="58be0-108">Ad esempio, se si deseleziona la casella di controllo **Registrazione** per tutte le fasi eccetto la fase finale, si impedisce agli ordini di assistenza di essere registrati prima che vengano elaborati tramite la sequenza completa di fasi.</span><span class="sxs-lookup"><span data-stu-id="58be0-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="58be0-109">Creazione di un ramo nelle fasi di un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="58be0-109">Branching in service order stages</span></span>

<span data-ttu-id="58be0-110">Quando si imposta una fase di assistenza, è possibile creare più opzioni, o più rami, da cui scegliere per la fase di assistenza successiva.</span><span class="sxs-lookup"><span data-stu-id="58be0-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="58be0-111">Tutti i rami creati sono disponibili per la selezione dal completamento della fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="58be0-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="58be0-112">Ad esempio, si imposta **Pianificazione** come fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="58be0-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="58be0-113">Si creano due fasi denominate **In corso** e **Annulla**, quindi si seleziona **Pianificazione** come elemento principale.</span><span class="sxs-lookup"><span data-stu-id="58be0-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="58be0-114">Assegnare la fase **Pianificazione** all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="58be0-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="58be0-115">Quando la fase di pianificazione dell'ordine cliente viene completata, è possibile selezionare la fase **In corso** se l'ordine cliente è pronto a lavorare oppure è possibile selezionare la fase **Annulla** se l'ordine cliente viene annullato.</span><span class="sxs-lookup"><span data-stu-id="58be0-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="58be0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58be0-116">See also</span></span>

[<span data-ttu-id="58be0-117">Imposta le fasi dell'ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="58be0-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="58be0-118">Cambiare la fase dell'ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="58be0-118">Change the service order stage</span></span>](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]