---
title: EUR-00015 Registrazione dell'ID IVA fornitore
description: In questa procedura viene descritto come aggiungere gli ID registrazione IVA e una partita IVA a un conto fornitore.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68475c96e7c85cc5a4c540441a4b1f3752ecf0bd
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852688"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a><span data-ttu-id="dd383-103">EUR-00015 Registrazione dell'ID IVA fornitore</span><span class="sxs-lookup"><span data-stu-id="dd383-103">EUR-00015 Registration of vendor VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd383-104">In questa procedura viene descritto come aggiungere gli ID registrazione IVA e una partita IVA a un conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="dd383-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="dd383-105">Questo processo è analogo per le persone giuridiche e clienti.</span><span class="sxs-lookup"><span data-stu-id="dd383-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="dd383-106">Prima di completare questa procedura è necessario impostare gli ID IVA.</span><span class="sxs-lookup"><span data-stu-id="dd383-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="dd383-107">Questa procedura si applica a tutti i paesi europei.</span><span class="sxs-lookup"><span data-stu-id="dd383-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="dd383-108">La procedura è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Germania.</span><span class="sxs-lookup"><span data-stu-id="dd383-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="dd383-109">Questa procedura è progettata per un amministratore della gestione dei dati, un responsabile della contabilità fornitori, o un responsabile della contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="dd383-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="dd383-110">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="dd383-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="dd383-111">Andare a Contabilità fornitori > Fornitori > Tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="dd383-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="dd383-112">Nell'elenco trovare e selezionare il fornitore DE-01001</span><span class="sxs-lookup"><span data-stu-id="dd383-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="dd383-113">Fare clic su ID registrazione.</span><span class="sxs-lookup"><span data-stu-id="dd383-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="dd383-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="dd383-114">Click Add.</span></span>
5. <span data-ttu-id="dd383-115">Selezionare ID IVA.</span><span class="sxs-lookup"><span data-stu-id="dd383-115">Select VAT ID.</span></span>
6. <span data-ttu-id="dd383-116">Nel campo Numero di registrazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd383-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="dd383-117">Specificare un'ID IVA in Germania per il fornitore selezionato.</span><span class="sxs-lookup"><span data-stu-id="dd383-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="dd383-118">L'ID deve corrispondere al formato specificato per il tipo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="dd383-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="dd383-119">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="dd383-119">Click the General tab.</span></span>
8. <span data-ttu-id="dd383-120">Nel campo Validità immettere una data.</span><span class="sxs-lookup"><span data-stu-id="dd383-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="dd383-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="dd383-121">Click Save.</span></span>
10. <span data-ttu-id="dd383-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="dd383-122">Click New.</span></span>
11. <span data-ttu-id="dd383-123">Digitare un valore nel campo Nome o Descrizione.</span><span class="sxs-lookup"><span data-stu-id="dd383-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="dd383-124">Ad esempio, immettere ITA.</span><span class="sxs-lookup"><span data-stu-id="dd383-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="dd383-125">Nel campo Paese/regione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd383-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="dd383-126">Selezionare, ad esempio ITA.</span><span class="sxs-lookup"><span data-stu-id="dd383-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="dd383-127">Selezionare Sì nel campo Principale per paese.</span><span class="sxs-lookup"><span data-stu-id="dd383-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="dd383-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="dd383-128">Click Save.</span></span>
15. <span data-ttu-id="dd383-129">Fare clic sulla scheda Panoramica.</span><span class="sxs-lookup"><span data-stu-id="dd383-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="dd383-130">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="dd383-130">Click Add.</span></span>
17. <span data-ttu-id="dd383-131">Nel campo Tipo di registrazione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd383-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="dd383-132">Selezionare, ad esempio, ID IVA.</span><span class="sxs-lookup"><span data-stu-id="dd383-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="dd383-133">Nel campo Numero di registrazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd383-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="dd383-134">Ad esempio, specificare un ID IVA in Italia.</span><span class="sxs-lookup"><span data-stu-id="dd383-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="dd383-135">L'ID deve avere lo stesso formato del tipo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="dd383-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="dd383-136">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="dd383-136">Click Save.</span></span>
20. <span data-ttu-id="dd383-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd383-137">Close the page.</span></span>
21. <span data-ttu-id="dd383-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="dd383-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="dd383-139">Selezionare, ad esempio, DE-01001.</span><span class="sxs-lookup"><span data-stu-id="dd383-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="dd383-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="dd383-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="dd383-141">Espandere la sezione Fattura e consegna.</span><span class="sxs-lookup"><span data-stu-id="dd383-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="dd383-142">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="dd383-142">Click Edit.</span></span>
25. <span data-ttu-id="dd383-143">Nel campo Partita IVA, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd383-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="dd383-144">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="dd383-144">Click Save.</span></span>

