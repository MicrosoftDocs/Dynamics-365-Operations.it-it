---
title: Tipi di richieste di intervento di manutenzione
description: In questo argomento viene illustrato come impostare i tipi di richieste di intervento di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e4f622cda62cad13a8146cbc26bc2e5f1a45222
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261191"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="a302d-103">Tipi di richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="a302d-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a302d-104">I tipi di richieste di intervento di manutenzione vengono utilizzati per classificare le richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a302d-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="a302d-105">Ad esempio, potrebbero esserci tipi di richieste di intervento di manutenzione correlati alla manutenzione preventiva e alla manutenzione correttiva.</span><span class="sxs-lookup"><span data-stu-id="a302d-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="a302d-106">Oppure avere un tipo particolare di richiesta di intervento di manutenzione utilizzato per gestire la riparazione cespiti (riparazione in deposito).</span><span class="sxs-lookup"><span data-stu-id="a302d-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="a302d-107">Un tipo di richiesta di intervento di manutenzione definisce il rapporto con un gruppo di stati del ciclo di vita delle richiesta di intervento di manutenzione (modello del ciclo di vita di manutenzione).</span><span class="sxs-lookup"><span data-stu-id="a302d-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="a302d-108">I modelli del ciclo di vita delle richiesta di intervento di manutenzione definiscono gli stati del ciclo di vita che possono essere impostati per una richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a302d-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="a302d-109">(Esempi degli stati del ciclo di vita delle richieste di intervento di manutenzione includono **Creato**, **Attivo** e **Finito**).</span><span class="sxs-lookup"><span data-stu-id="a302d-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="a302d-110">Selezionare **Gestione cespiti** \> **Impostazione** \> **Richieste di intervento di manutenzione** \> **Tipi di richieste di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="a302d-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="a302d-111">Selezionare **Nuovo** per creare un tipo di richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a302d-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="a302d-112">Nel campo **Tipo di richiesta di intervento di manutenzione**, immettere un ID per il tipo di richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a302d-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="a302d-113">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="a302d-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="a302d-114">Nella scheda Dettaglio **Generale** selezionare un modello del ciclo di vita delle richieste di intervento di manutenzione nel campo **Modello del ciclo di vita delle richieste di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="a302d-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="a302d-115">Nel campo **Tipo di ordine di lavoro** selezionare un tipo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a302d-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="a302d-116">Quando una richiesta di intervento di manutenzione viene convertita in ordine di lavoro, l'ordine di lavoro assume automaticamente il tipo di ordine di lavoro correlato al tipo di richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a302d-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="a302d-117">Nella figura seguente è illustrato un esempio della pagina **Tipi di richieste di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="a302d-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Pagina Tipi di richieste di intervento di manutenzione](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]