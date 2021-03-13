---
title: Assegnazione e sostituzioni IVA
description: Questa procedura dimostra come assegnare fasce IVA ai canali di commercio.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c6e1de5046a3ce5d896ba3686a28d6d474d4268
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020730"
---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="c8ae9-103">Assegnazione e sostituzioni IVA</span><span class="sxs-lookup"><span data-stu-id="c8ae9-103">Sales tax assignment and overrides</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c8ae9-104">Questa procedura dimostra come assegnare fasce IVA ai canali di commercio.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-104">This procedure demonstrates how to assign sales tax groups to commerce channels.</span></span> <span data-ttu-id="c8ae9-105">Inoltre illustra il processo di creare una nuova forzatura IVA e assegnarla ad un gruppo di forzatura IVA esistente.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="c8ae9-106">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="c8ae9-107">Passare a Retail e Commerce > Canali > Punti vendita > Tutti i punti vendita.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-107">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="c8ae9-108">Nella lista, fare clic sul collegamento ID canale per "Houston".</span><span class="sxs-lookup"><span data-stu-id="c8ae9-108">In the list, click the Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="c8ae9-109">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-109">Click Edit.</span></span>
    * <span data-ttu-id="c8ae9-110">Il campo "Fascia IVA" contiene l'elenco di fasce IVA della società corrente.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-110">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="c8ae9-111">Il gruppo attualmente assegnato è una fascia IVA generica "Texas".</span><span class="sxs-lookup"><span data-stu-id="c8ae9-111">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="c8ae9-112">Ci sono inoltre fasce IVA per "Washington" e "Washington, King County".</span><span class="sxs-lookup"><span data-stu-id="c8ae9-112">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="c8ae9-113">Le fasce IVA possono includere imposte applicabili a più comuni.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-113">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="c8ae9-114">Il campo "Forzatura IVA" è dove i gruppi di forzatura IVA possono essere mappati al canale.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-114">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="c8ae9-115">I gruppi di forzatura IVA possono essere usati per raggruppare le forzature IVA che funzionano per più punti vendita.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-115">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="c8ae9-116">Piuttosto che manualmente assegnare le forzature IVA una per una, il gruppo può essere creato ed assegnato direttamente ai canali per risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-116">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="c8ae9-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-117">Click Save.</span></span>
5. <span data-ttu-id="c8ae9-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-118">Close the page.</span></span>
6. <span data-ttu-id="c8ae9-119">Passare a Retail e Commerce > Impostazione canale > IVA > Forzature IVA.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-119">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="c8ae9-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-120">Click New.</span></span>
8. <span data-ttu-id="c8ae9-121">Nel campo Forzatura IVA fornire un nome per la nuova forzatura.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-121">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="c8ae9-122">Nel campo Descrizione immettere una descrizione della forzatura.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-122">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="c8ae9-123">Impostare lo stato su "Abilitazione".</span><span class="sxs-lookup"><span data-stu-id="c8ae9-123">Set the status to "Enable."</span></span>
11. <span data-ttu-id="c8ae9-124">Espandere o comprimere la sezione Forzatura.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-124">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="c8ae9-125">Selezionare un'opzione nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-125">In the Type field, select an option.</span></span>
    * <span data-ttu-id="c8ae9-126">Le fasce IVA degli articoli possono essere usate per sostituire imposte per articoli specifici che appartengono alla fascia.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-126">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="c8ae9-127">Per esempio, i prodotti alimentari sono tassati tipicamente diversamente dai beni durevoli e hanno probabilmente la propria gascia IVA.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-127">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span> <span data-ttu-id="c8ae9-128">Le fasce IVA sono gruppi di imposte che sono applicabili ad un canale particolare.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-128">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="c8ae9-129">Per esempio, se un canale vende sia al dettaglio che tra imprese, fasce IVA differenti possono essere usate.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-129">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="c8ae9-130">Tutte le imposte applicabili sarebbero mappate alla fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-130">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="c8ae9-131">Ora potete selezionare le imposte "Da" e "A" o "Da gruppo di imposta" e "A gruppo di imposta" per creare la forzatura IVA.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-131">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span> <span data-ttu-id="c8ae9-132">Il campo "Da" indica l'imposta o il gruppo di imposta da forzare.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-132">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="c8ae9-133">La forzatura tramite fascia IVA degli articoli fornisce opzioni differenti dalla forzatura tramite fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-133">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span> <span data-ttu-id="c8ae9-134">Le forzature IVA possono essere impostate per sostituire imposte su intere transazioni o su righe particolari nella transazione.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-134">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="c8ae9-135">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-135">Click Save.</span></span>
14. <span data-ttu-id="c8ae9-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-136">Close the page.</span></span>
15. <span data-ttu-id="c8ae9-137">Passare a Retail e Commerce > Impostazione canale > IVA > Gruppi di forzatura IVA.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-137">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="c8ae9-138">In questo passaggio si assegnerà la forzatura IVA appena creata al gruppo di forzatura IVA assegnato al canale di Houston.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-138">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="c8ae9-139">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-139">Click Edit.</span></span>
17. <span data-ttu-id="c8ae9-140">Espandere o comprimere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-140">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="c8ae9-141">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-141">Click Add.</span></span>
19. <span data-ttu-id="c8ae9-142">Nel campo Forzatura IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-142">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="c8ae9-143">Selezionare la forzatura IVA precedentemente creata dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-143">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="c8ae9-144">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-144">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="c8ae9-145">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-145">Click Save.</span></span>

