---
title: Esecuzione programmata
description: In questo argomento viene descritta l'esecuzione programmata in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8d9c8afc139c96e32efb3161d35fde685b8abcc5
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874672"
---
# <a name="scheduled-execution"></a><span data-ttu-id="2054c-103">Esecuzione programmata</span><span class="sxs-lookup"><span data-stu-id="2054c-103">Scheduled execution</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="2054c-104">È possibile utilizzare i livelli di servizio di ordine di lavoro per impostare l'esecuzione programmata</span><span class="sxs-lookup"><span data-stu-id="2054c-104">You can use work order service levels to set up scheduled execution.</span></span> <span data-ttu-id="2054c-105">(per ulteriori informazioni sui livelli di servizio di ordine di lavoro, vedere [Descrizione e livello del servizio](service-level-and-description.md)). L'esecuzione programmata fornisce flessibilità nella pianificazione del lavoro degli addetti della manutenzione, poiché è possibile impostare requisiti più dettagliati o meno dettagliati per l'intervallo durante il quale un ordine di lavoro deve essere completato.</span><span class="sxs-lookup"><span data-stu-id="2054c-105">(For more information about work order service levels, see [Service level and description](service-level-and-description.md).) Scheduled execution provides flexibility in work planning for maintenance workers, because you can set up more detailed or less detailed requirements for the interval that a work order should be completed during.</span></span> <span data-ttu-id="2054c-106">Ad esempio, un addetto alla manutenzione che completa un processo prima del previsto in un impianto di produzione potrebbe essere in grado di passare a un altro processo pianificato per la settimana corrente ma non necessariamente per il giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="2054c-106">For example, a maintenance worker who completes a job faster than expected in a production facility might be able to move on to another nearby job that was planned for the current week but not necessarily for the current day.</span></span> <span data-ttu-id="2054c-107">Questo approccio consente l'ottimizzazione della pianificazione del lavoratore e del completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="2054c-107">This approach allows for optimization of worker planning and job completion.</span></span>

<span data-ttu-id="2054c-108">La configurazione dell'esecuzione programmata, correlata agli ordini di lavoro, può essere generica o specifica.</span><span class="sxs-lookup"><span data-stu-id="2054c-108">Scheduled execution setup, which is related to work orders, can be generic or specific.</span></span> <span data-ttu-id="2054c-109">È possibile impostare righe generiche che non sono limitate a specifici tipi di ordini di lavoro, tipi di cespite e così via.</span><span class="sxs-lookup"><span data-stu-id="2054c-109">You can set up generic lines that aren't limited to specific work order types, asset types, and so on.</span></span> <span data-ttu-id="2054c-110">In alternativa, è possibile creare righe di esecuzione programmata applicabili a uno specifico tipo di ordine di lavoro, tipo di cespite, tipo di processo di manutenzione e così via.</span><span class="sxs-lookup"><span data-stu-id="2054c-110">Alternatively, you can create scheduled execution lines that apply to a specific work order type, asset type, maintenance job type, and so on.</span></span>

1. <span data-ttu-id="2054c-111">Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Esecuzione programmata**.</span><span class="sxs-lookup"><span data-stu-id="2054c-111">Select **Asset management** \> **Setup** \> **Work orders** \> **Scheduled execution**.</span></span>
2. <span data-ttu-id="2054c-112">Selezionare **Nuovo** per creare una riga di esecuzione programmata.</span><span class="sxs-lookup"><span data-stu-id="2054c-112">Select **New** to create a scheduled execution line.</span></span>
3. <span data-ttu-id="2054c-113">Nei campi **Unità funzionale**, **Tipo di ordine di lavoro**, **Tipo di cespite**, **Produttore**, **Modello**, **Categoria tipi di processo di manutenzione**, **Tipo di processo di manutenzione**, **Variante tipi di processo di manutenzione** e **Settore**, selezionare i valori necessari.</span><span class="sxs-lookup"><span data-stu-id="2054c-113">In the **Functional location**, **Work order type**, **Asset type**, **Manufacturer**, **Model**, **Maintenance job type category**, **Maintenance job type**, **Maintenance job type variant**, and **Trade** fields, select values as you require.</span></span>
4. <span data-ttu-id="2054c-114">Nel campo **Livello servizio**, selezionare un livello di servizio di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2054c-114">In the **Service level** field, select a work order service level.</span></span> <span data-ttu-id="2054c-115">Se si lascia vuoto questo campo, si crea il tipo di riga di esecuzione programmata.</span><span class="sxs-lookup"><span data-stu-id="2054c-115">If you leave this field blank, you make the most generic type of scheduled execution line.</span></span> <span data-ttu-id="2054c-116">Per un esempio di riga generica, vedere il primo record nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="2054c-116">For an example of a generic line, see the first record in the illustration that follows.</span></span> <span data-ttu-id="2054c-117">Tale riga consente la programmazione di tutti gli ordini di lavoro che non hanno alcun livello di servizio di ordine di lavoro a una data e un'ora specifiche.</span><span class="sxs-lookup"><span data-stu-id="2054c-117">That line enables all work orders that have no work order service level to be scheduled for a specific date and time.</span></span>
5. <span data-ttu-id="2054c-118">Nel campo **Esecuzione programmata**, selezionare l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2054c-118">In the **Scheduled execution** field, select the time interval.</span></span>
6. <span data-ttu-id="2054c-119">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2054c-119">Select **Save**.</span></span>

![Figura 1](media/20-setup-for-work-orders.png)
