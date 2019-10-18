---
title: Impostare criteri di fatture fornitore
description: In questo argomento viene spiegato come impostare i criteri di fatture fornitore.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72f017294c976dcd1b7ddda01ac9e39252f036d6
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250281"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="b9968-103">Impostare criteri di fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="b9968-103">Set up vendor invoice policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b9968-104">In questo argomento viene spiegato come impostare i criteri di fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="b9968-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="b9968-105">I criteri fattura fornitore vengono eseguiti quando si registra una fattura fornitore tramite la pagina Fattura fornitore e quando si apre la pagina violazioni dei criteri per fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="b9968-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="b9968-106">È inoltre possibile configurare il flusso di lavoro delle fatture fornitore affinché i criteri fatture fornitore vengano eseguiti ogni volta che si invia una fattura al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9968-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="b9968-107">I criteri fatture fornitore non sono applicabili alle fatture create nel registro fatture o nel giornale di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="b9968-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="b9968-108">La convalida di abbinamento fatture non utilizza i criteri fatture fornitore, ma viene invece impostata nella pagina Parametri contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="b9968-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="b9968-109">Questa registrazione utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="b9968-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="b9968-110">Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni.</span><span class="sxs-lookup"><span data-stu-id="b9968-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="b9968-111">Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture.</span><span class="sxs-lookup"><span data-stu-id="b9968-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="b9968-112">Eseguire le operazioni preliminari alla creazione dei criteri fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="b9968-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="b9968-113">Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione > Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="b9968-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="b9968-114">Selezionare la scheda **Convalida fattura**.</span><span class="sxs-lookup"><span data-stu-id="b9968-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="b9968-115">Selezionare o deselezionare la casella di controllo **Aggiorna automaticamente lo stato dell'intestazione fattura**.</span><span class="sxs-lookup"><span data-stu-id="b9968-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="b9968-116">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9968-116">Select **OK**.</span></span>
5. <span data-ttu-id="b9968-117">Nel campo **Registra fattura con discrepanze**, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="b9968-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="b9968-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b9968-118">Close the page.</span></span>
7. <span data-ttu-id="b9968-119">Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione criteri > Criteri fatture fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b9968-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="b9968-120">Selezionare **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="b9968-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="b9968-121">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b9968-121">Select **Add**.</span></span>
10. <span data-ttu-id="b9968-122">Chiudere la pagina per tornare alla home page.</span><span class="sxs-lookup"><span data-stu-id="b9968-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="b9968-123">Creare i tipi di regole dei criteri per fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="b9968-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="b9968-124">Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione criteri > Tipi di regole dei criteri per le fatture fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b9968-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="b9968-125">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b9968-125">Select **New**.</span></span>
3. <span data-ttu-id="b9968-126">Immettere valori nei campi **Nome regola** e **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="b9968-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="b9968-127">Nel campo **Nome query**, selezionare il pulsante a discesa per aprire la ricerca, quindi selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="b9968-127">In the **Query name** field, select the drop-down button to open the lookup, then selec the desired record.</span></span>
5. <span data-ttu-id="b9968-128">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b9968-128">Select **Save**.</span></span>
6. <span data-ttu-id="b9968-129">Chiudere la pagina per tornare alla home page.</span><span class="sxs-lookup"><span data-stu-id="b9968-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="b9968-130">Definire una regola dei criteri fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="b9968-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="b9968-131">Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione criteri > Criteri fatture fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b9968-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="b9968-132">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b9968-132">Select **New**.</span></span>
3. <span data-ttu-id="b9968-133">Immettere valori nei campi **Nome** e **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="b9968-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="b9968-134">Espandere o comprimere la sezione **Organizzazioni criteri**.</span><span class="sxs-lookup"><span data-stu-id="b9968-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="b9968-135">Nella struttura selezionare **Contoso Entertainment Systems USA**.</span><span class="sxs-lookup"><span data-stu-id="b9968-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="b9968-136">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b9968-136">Select **Add**.</span></span>
7. <span data-ttu-id="b9968-137">Espandere o comprimere la sezione **Regole dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="b9968-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="b9968-138">Selezionare **Crea regola dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="b9968-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="b9968-139">Nel campo **Descrizione regola dei criteri**, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="b9968-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="b9968-140">Selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="b9968-140">Select **Filter**.</span></span>
11. <span data-ttu-id="b9968-141">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b9968-141">Select **Add**.</span></span> <span data-ttu-id="b9968-142">Selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="b9968-142">Select the desired record.</span></span>
12. <span data-ttu-id="b9968-143">Nei campi **Tabella**, **Tabella derivata**, **Campo** selezionare o immettere le opzioni dai menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="b9968-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="b9968-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b9968-144">Close the page.</span></span>
14. <span data-ttu-id="b9968-145">Digitare un valore nel campo **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="b9968-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="b9968-146">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9968-146">Select **OK**.</span></span>
16. <span data-ttu-id="b9968-147">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9968-147">Select **OK**.</span></span>
17. <span data-ttu-id="b9968-148">Chiudere le pagine per tornare alla home page.</span><span class="sxs-lookup"><span data-stu-id="b9968-148">Close the pages to return to the home page.</span></span>

