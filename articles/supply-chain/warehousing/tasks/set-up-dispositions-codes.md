--- 
title: Impostare codici di smaltimento
description: "Questa procedura riguarda l'impostazione di un codice smaltimento che può essere utilizzato in un dispositivo mobile per il processo di ricezione dell'ordine di reso."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: dc014e499d5705b8ad72bc502969a6102d89ae36
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-dispositions-codes"></a><span data-ttu-id="c41f3-103">Impostare codici di smaltimento</span><span class="sxs-lookup"><span data-stu-id="c41f3-103">Set up dispositions codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c41f3-104">Questa procedura riguarda l'impostazione di un codice smaltimento che può essere utilizzato in un dispositivo mobile per il processo di ricezione dell'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="c41f3-104">This procedure focuses on the setup of a disposition code that can be used on a mobile device for the return order receiving process.</span></span> <span data-ttu-id="c41f3-105">I codici smaltimento sono una raccolta di regole che possono essere utilizzate quando gli articoli vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="c41f3-105">Disposition codes are a collection of rules that can be used when items are received.</span></span> <span data-ttu-id="c41f3-106">Ad esempio, quando un utente di lavoro utilizza un dispositivo mobile per ricevere articoli danneggiati, l'utente deve digitalizzare un codice smaltimento per gli articoli danneggiati.</span><span class="sxs-lookup"><span data-stu-id="c41f3-106">For example, when a work user uses a mobile device to receive items that were damaged, the user must scan a disposition code for damaged items.</span></span> <span data-ttu-id="c41f3-107">Lo stato di inventario delle merci ricevute, il modello di lavoro e la direttiva ubicazione possono essere determinate dal codice smaltimento digitalizzato.</span><span class="sxs-lookup"><span data-stu-id="c41f3-107">The inventory status of the goods received, the work template, and the location directive can be determined from the scanned disposition code.</span></span> <span data-ttu-id="c41f3-108">Per il processo di ricezione dell'ordine fornitore e il processo di dichiarazione di finito degli ordini di produzione, l'utilizzo di un codice smaltimento è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c41f3-108">For the purchase order receiving process and the production order report as finished process, the use of a disposition code is optional.</span></span> <span data-ttu-id="c41f3-109">Per il processo di ricevimento reso dell'ordine cliente, se gli articoli vengono registrati tramite un dispositivo mobile, l'utilizzo del codice smaltimento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c41f3-109">For the sales order return receiving process, if the items are registered using a mobile device, the use of disposition code is mandatory.</span></span>  <span data-ttu-id="c41f3-110">Questa guida è stata creata utilizzando la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="c41f3-110">This guide was created using the demo data company USMF.</span></span> <span data-ttu-id="c41f3-111">Questa procedura è destinata al responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="c41f3-111">This procedure is intended for the warehouse manager.</span></span> 

1. <span data-ttu-id="c41f3-112">Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Codici smaltimento.</span><span class="sxs-lookup"><span data-stu-id="c41f3-112">Go to Warehouse management > Setup > Mobile device > Disposition codes.</span></span>
2. <span data-ttu-id="c41f3-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c41f3-113">Click New.</span></span>
    * <span data-ttu-id="c41f3-114">Creare un nuovo codice smaltimento da utilizzare per i resi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c41f3-114">Create a new disposition code to use for customer returns.</span></span>  
3. <span data-ttu-id="c41f3-115">Nel campo Codice smaltimento digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c41f3-115">In the Disposition code field, type a value.</span></span>
4. <span data-ttu-id="c41f3-116">Nel campo Stato inventario selezionare uno stato in cui sia presente il blocco scorte.</span><span class="sxs-lookup"><span data-stu-id="c41f3-116">In the Inventory status field, select an inventory status where there is inventory blocking.</span></span>
    * <span data-ttu-id="c41f3-117">Se si utilizza USMF, selezionare l'opzione di bloccaggio.</span><span class="sxs-lookup"><span data-stu-id="c41f3-117">If you're using USMF, select 'Blocking'.</span></span> <span data-ttu-id="c41f3-118">È possibile aggiungere lo stato delle scorte al codice smaltimento per sostituire lo stato predefinito sulle righe ordine.</span><span class="sxs-lookup"><span data-stu-id="c41f3-118">You can add an inventory status to the disposition code to override the default status that’s on the order lines.</span></span>  
5. <span data-ttu-id="c41f3-119">Digitare un valore nel campo Modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c41f3-119">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="c41f3-120">Facoltativo: selezionare un codice del modello di lavoro associato a un ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="c41f3-120">Optional: Select a work template code that is associated with a return order.</span></span> <span data-ttu-id="c41f3-121">Se nessun valore viene specificato, il modello di lavoro verrà risolto utilizzando le regole standard configurate nel sistema.</span><span class="sxs-lookup"><span data-stu-id="c41f3-121">If no value is provided, the work template will be resolved using the standard rules configured in your system.</span></span> <span data-ttu-id="c41f3-122">La selezione di un modello di lavoro limiterà i processi con cui il codice smaltimento specifico può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c41f3-122">Selecting a work template will limit the processes this disposition code can be used with.</span></span> <span data-ttu-id="c41f3-123">Ad esempio, se un codice smaltimento ha un modello di lavoro con un ordine di lavoro di tipo ordine fornitore, non può essere utilizzato per registrare gli articoli restituiti dai clienti.</span><span class="sxs-lookup"><span data-stu-id="c41f3-123">For example, if a disposition code has a work template with a work order of type purchase order, it can’t be used to register items that are returned by customers.</span></span>  
6. <span data-ttu-id="c41f3-124">Nel campo Codice smaltimento reso digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c41f3-124">In the Return disposition code field, type a value.</span></span>
    * <span data-ttu-id="c41f3-125">Il codice smaltimento di reso determina il resto del processo di ordine di reso per gli articoli registrati.</span><span class="sxs-lookup"><span data-stu-id="c41f3-125">The return disposition code determines the remainder of the return order process for the items registered.</span></span> <span data-ttu-id="c41f3-126">In questo esempio, il cliente deve ricevere una nota di accredito.</span><span class="sxs-lookup"><span data-stu-id="c41f3-126">In this example, the customer should receive a credit note.</span></span> <span data-ttu-id="c41f3-127">Aggiungere un codice smaltimento di reso contenente un'azione di tipo Avere.</span><span class="sxs-lookup"><span data-stu-id="c41f3-127">Add a returns disposition code that contains an action Credit.</span></span>  


