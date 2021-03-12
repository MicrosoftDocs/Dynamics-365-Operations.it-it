---
title: Cercare o risolvere eccezioni
description: I criteri fattura fornitore vengono eseguiti quando si registra una fattura fornitore tramite la pagina Fattura fornitore e quando si apre la pagina violazioni dei criteri per fatture fornitore.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 727676d060b77633d4ff4f31dabbd7825ca19aca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971780"
---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="d4467-103">Cercare o risolvere eccezioni</span><span class="sxs-lookup"><span data-stu-id="d4467-103">Research or resolve exceptions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d4467-104">I criteri fattura fornitore vengono eseguiti quando si registra una fattura fornitore tramite la pagina Fattura fornitore e quando si apre la pagina violazioni dei criteri per fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="d4467-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="d4467-105">È inoltre possibile configurare il flusso di lavoro delle fatture fornitore affinché i criteri fatture fornitore vengano eseguiti ogni volta che si invia una fattura al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d4467-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="d4467-106">I criteri fatture fornitore non sono applicabili alle fatture create nel registro fatture o nel giornale di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="d4467-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="d4467-107">La convalida di abbinamento fatture non utilizza i criteri fatture fornitore, ma viene invece impostata nella pagina Parametri contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="d4467-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="d4467-108">Questa registrazione utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="d4467-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="d4467-109">Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni.</span><span class="sxs-lookup"><span data-stu-id="d4467-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="d4467-110">Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture.</span><span class="sxs-lookup"><span data-stu-id="d4467-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="d4467-111">Eseguire le operazioni preliminari alla creazione dei criteri fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="d4467-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="d4467-112">Andare a Contabilità fornitori > Impostazioni > Parametri contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="d4467-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="d4467-113">Fare clic sulla scheda Convalida fattura.</span><span class="sxs-lookup"><span data-stu-id="d4467-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="d4467-114">Selezionare o deselezionare la casella di controllo Aggiorna automaticamente lo stato dell'intestazione fattura.</span><span class="sxs-lookup"><span data-stu-id="d4467-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="d4467-115">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d4467-115">Click OK.</span></span>
5. <span data-ttu-id="d4467-116">Nel campo Registra fattura con discrepanze, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="d4467-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="d4467-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4467-117">Close the page.</span></span>
7. <span data-ttu-id="d4467-118">Andare a Contabilità fornitori > Impostazione criteri > Criteri fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="d4467-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="d4467-119">Fare clic su Parametri.</span><span class="sxs-lookup"><span data-stu-id="d4467-119">Click Parameters.</span></span>
9. <span data-ttu-id="d4467-120">Fare clic su btnAdd.</span><span class="sxs-lookup"><span data-stu-id="d4467-120">Click btnAdd.</span></span>
10. <span data-ttu-id="d4467-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4467-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="d4467-122">Creare i tipi di regole dei criteri per fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="d4467-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="d4467-123">Andare a Contabilità fornitori > Impostazione criteri > Tipi di regole dei criteri per le fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="d4467-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="d4467-124">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d4467-124">Click New.</span></span>
3. <span data-ttu-id="d4467-125">Digitare un valore nel campo Regola.</span><span class="sxs-lookup"><span data-stu-id="d4467-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="d4467-126">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4467-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4467-127">Nel campo Nome query fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d4467-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d4467-128">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d4467-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d4467-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4467-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d4467-130">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d4467-130">Click Save.</span></span>
9. <span data-ttu-id="d4467-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4467-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="d4467-132">Definire una regola dei criteri fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="d4467-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="d4467-133">Andare a Contabilità fornitori > Impostazione criteri > Criteri fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="d4467-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="d4467-134">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d4467-134">Click New.</span></span>
3. <span data-ttu-id="d4467-135">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d4467-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d4467-136">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4467-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4467-137">Espandere o comprimere la sezione Organizzazioni criteri.</span><span class="sxs-lookup"><span data-stu-id="d4467-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="d4467-138">Nella struttura selezionare "Contoso Entertainment Systems USA"</span><span class="sxs-lookup"><span data-stu-id="d4467-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="d4467-139">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="d4467-139">Click Add.</span></span>
8. <span data-ttu-id="d4467-140">Espandere o comprimere la sezione Regole dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d4467-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="d4467-141">Fare clic su Crea regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d4467-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="d4467-142">Nel campo Descrizione regola dei criteri, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="d4467-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="d4467-143">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="d4467-143">Click Filter.</span></span>
12. <span data-ttu-id="d4467-144">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="d4467-144">Click Add.</span></span>
13. <span data-ttu-id="d4467-145">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4467-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="d4467-146">Nel campo Tabella fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d4467-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="d4467-147">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4467-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="d4467-148">Nel campo Tabella derivata fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d4467-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="d4467-149">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4467-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="d4467-150">Nel campo Campo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d4467-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="d4467-151">Digitare un valore nel campo Campo.</span><span class="sxs-lookup"><span data-stu-id="d4467-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="d4467-152">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4467-152">Close the page.</span></span>
21. <span data-ttu-id="d4467-153">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="d4467-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="d4467-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d4467-154">Click OK.</span></span>
23. <span data-ttu-id="d4467-155">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d4467-155">Click OK.</span></span>
24. <span data-ttu-id="d4467-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4467-156">Close the page.</span></span>
25. <span data-ttu-id="d4467-157">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4467-157">Close the page.</span></span>

