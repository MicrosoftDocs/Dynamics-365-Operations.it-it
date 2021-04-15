---
title: Impostare la riallocazione articolo per prelievo breve
description: In questo argomento viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti all'ubicazione a cui sono stati indirizzati.
author: ShylaThompson
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 90aeb860dc95a348b000a0f994fadc5cc9aea7e6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814418"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="db6ce-103">Impostare la riallocazione articolo per prelievo breve</span><span class="sxs-lookup"><span data-stu-id="db6ce-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="db6ce-104">In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati.</span><span class="sxs-lookup"><span data-stu-id="db6ce-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="db6ce-105">Il processo di riallocazione è controllato da una **Eccezione di lavoro** e utilizzato dal **lavoratore** di magazzino.</span><span class="sxs-lookup"><span data-stu-id="db6ce-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="db6ce-106">È possibile utilizzare i processi di riallocazione automatici, manuali o entrambi:</span><span class="sxs-lookup"><span data-stu-id="db6ce-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="db6ce-107">Riallocazione automatica: le direttive sull'ubicazione vengono utilizzate per determinare se le merci sono disponibili in un'altra ubicazione.</span><span class="sxs-lookup"><span data-stu-id="db6ce-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="db6ce-108">Se possibile, il lavoro verrà aggiornato e l'utente del magazzino verrà indirizzato all'ubicazione alternativa.</span><span class="sxs-lookup"><span data-stu-id="db6ce-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="db6ce-109">Riallocazione manuale: consente all'utente del magazzino di selezionare da una o più ubicazioni con quantità di merce senza prenotazione.</span><span class="sxs-lookup"><span data-stu-id="db6ce-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="db6ce-110">Automatico e manuale: se il sistema non è in grado di eseguire una riallocazione automatica e le ubicazioni sono disponibili con quantità non prenotate, all'utente verrà richiesto di selezionare un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="db6ce-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="db6ce-111">Imposta eccezioni lavoro</span><span class="sxs-lookup"><span data-stu-id="db6ce-111">Set up work exceptions</span></span>
<span data-ttu-id="db6ce-112">È possibile definire più eccezioni lavoro con diversi criteri di riallocazione articolo per consentire all'addetto al magazzino di scegliere uno in base alle esigenze di spedizione in corso di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="db6ce-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="db6ce-113">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="db6ce-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="db6ce-114">Nel **pannello di navigazione**, andare a **Gestione magazzino > Impostazione > Lavoro > Eccezioni lavoro**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="db6ce-115">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-115">Click **New**</span></span> 
3. <span data-ttu-id="db6ce-116">Nel campo **Codice di eccezione lavoro**, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="db6ce-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="db6ce-117">Questo sarà il titolo di questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="db6ce-117">This will be the title of this exception .</span></span> <span data-ttu-id="db6ce-118">Ad esempio, Prelievo manuale breve.</span><span class="sxs-lookup"><span data-stu-id="db6ce-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="db6ce-119">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="db6ce-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="db6ce-120">Questa sarà una breve descrizione dell'uso di questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="db6ce-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="db6ce-121">Ad esempio, Prelievo breve - articolo non disponibile.</span><span class="sxs-lookup"><span data-stu-id="db6ce-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="db6ce-122">Nel campo Tipo di **eccezione** seleziona **Prelievo in difetto**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="db6ce-123">Selezionare la casella di controllo **Correggi magazzino**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="db6ce-124">Se selezionata, questa opzione indica che l'inventario verrà rettificato automaticamente su 0 all'ubicazione del prelievo breve.</span><span class="sxs-lookup"><span data-stu-id="db6ce-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="db6ce-125">Nel campo **Codice tipo correzione predefinito**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="db6ce-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="db6ce-126">Ad esempio, in USMF è possibile selezionare **Remove Res Adj Out** . Ciascun codice del tipo di rettifica contiene quattro caratteristiche: nome, Descrizione, nome del giornale di inventario e **Rimuovi prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="db6ce-127">Se **Rimuovi prenotazioni** è abilitata, le prenotazioni della riga ordine di prelievo breve verranno rimosse.</span><span class="sxs-lookup"><span data-stu-id="db6ce-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="db6ce-128">Nel campo **Riallocazione articolo**, seleziona un valore, ad esempio Manuale.</span><span class="sxs-lookup"><span data-stu-id="db6ce-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="db6ce-129">Se si seleziona Manuale o Automatico e manuale, l'addetto al magazzino deve essere abilitato per utilizzare la riallocazione manuale.</span><span class="sxs-lookup"><span data-stu-id="db6ce-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="db6ce-130">Impostare un lavoratore per utilizzare la riallocazione manuale degli articoli</span><span class="sxs-lookup"><span data-stu-id="db6ce-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="db6ce-131">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="db6ce-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="db6ce-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="db6ce-132">Close the page.</span></span>
2. <span data-ttu-id="db6ce-133">Nel **pannello di navigazione**, andare a **Gestione magazzino > Impostazione > Lavoro > Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="db6ce-134">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-134">Click **Edit**.</span></span>
4. <span data-ttu-id="db6ce-135">Nell'elenco seleziona il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="db6ce-135">In the list, select worker.</span></span> <span data-ttu-id="db6ce-136">Ad esempio, Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="db6ce-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="db6ce-137">Espandi la Scheda dettaglio **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="db6ce-138">Nell'elenco, seleziona un **ID utente**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="db6ce-139">Ad esempio, 24.</span><span class="sxs-lookup"><span data-stu-id="db6ce-139">For example, 24.</span></span>
7. <span data-ttu-id="db6ce-140">Espandi la Scheda dettaglio **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="db6ce-141">Selezionare **Sì** nel campo **Consenti riallocazione manuale articolo**.</span><span class="sxs-lookup"><span data-stu-id="db6ce-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]