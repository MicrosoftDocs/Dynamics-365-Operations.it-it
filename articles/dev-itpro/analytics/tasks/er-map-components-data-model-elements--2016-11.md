---
title: ER Mapping dei componenti del formato creato agli elementi del modello dati (novembre 2016)
description: Nella seguente procedura viene illustrato come un utente con il ruolo di amministratore di sistema o sviluppatore per la creazione di report elettronici può eseguire il mapping di elementi del modello dati ai componenti della configurazione creazione di report elettronici (ER), che definisce un formato di documento elettronico per il dominio aziendale dei pagamenti.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a24ef0e091379f14a163a6385be988143a1ec608
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "323550"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a><span data-ttu-id="c9184-103">ER Mapping dei componenti del formato creato agli elementi del modello dati (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="c9184-103">ER Map components of the created format to data model elements (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9184-104">Nella seguente procedura viene illustrato come un utente con il ruolo di amministratore di sistema o sviluppatore per la creazione di report elettronici può eseguire il mapping di elementi del modello dati ai componenti della configurazione creazione di report elettronici (ER), che definisce un formato di documento elettronico per il dominio aziendale dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="c9184-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="c9184-105">Questo formato verrà utilizzato in seguito per generare documenti elettronici per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="c9184-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="c9184-106">In questo esempio, verrà creata una configurazione di formato per la società di esempio ‘Litware, Inc.’.</span><span class="sxs-lookup"><span data-stu-id="c9184-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="c9184-107">Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="c9184-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="c9184-108">Per completare questi passaggi, è necessario aver completato prima i passaggi della guida attività "Creare una configurazione di formato".</span><span class="sxs-lookup"><span data-stu-id="c9184-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="c9184-109">Selezionare una configurazione di formato</span><span class="sxs-lookup"><span data-stu-id="c9184-109">Select a format configuration</span></span>
1. <span data-ttu-id="c9184-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="c9184-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c9184-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="c9184-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="c9184-112">Nella struttura espandere "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="c9184-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="c9184-113">Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="c9184-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="c9184-114">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="c9184-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="c9184-115">Esegue il mapping dei componenti del formato a elementi del modello dati</span><span class="sxs-lookup"><span data-stu-id="c9184-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="c9184-116">Fare clic su Espandi/Comprimi.</span><span class="sxs-lookup"><span data-stu-id="c9184-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="c9184-117">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="c9184-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="c9184-118">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="c9184-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="c9184-119">Nella struttura selezionare 'Xml\Messaggio\ProcessingDate\DateTime'.</span><span class="sxs-lookup"><span data-stu-id="c9184-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="c9184-120">Nella struttura selezionare 'modello\ProcessingDateTime'.</span><span class="sxs-lookup"><span data-stu-id="c9184-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="c9184-121">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-121">Click Bind.</span></span>
7. <span data-ttu-id="c9184-122">Nella struttura selezionare 'Xml\Messaggio\MessageId\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="c9184-123">Nella struttura selezionare 'modello\MessageIdentification'.</span><span class="sxs-lookup"><span data-stu-id="c9184-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="c9184-124">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-124">Click Bind.</span></span>
10. <span data-ttu-id="c9184-125">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="c9184-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="c9184-126">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Importo\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="c9184-127">Nella struttura selezionare 'modello\Pagamenti\InstructedAmount'.</span><span class="sxs-lookup"><span data-stu-id="c9184-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="c9184-128">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-128">Click Bind.</span></span>
14. <span data-ttu-id="c9184-129">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\TransDate\DateTime'.</span><span class="sxs-lookup"><span data-stu-id="c9184-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="c9184-130">Nella struttura selezionare 'modello\Pagamenti\TransactionDate'.</span><span class="sxs-lookup"><span data-stu-id="c9184-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="c9184-131">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-131">Click Bind.</span></span>
17. <span data-ttu-id="c9184-132">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Descrizione\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="c9184-133">Nella struttura selezionare "modello\Pagamenti\Descrizione".</span><span class="sxs-lookup"><span data-stu-id="c9184-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="c9184-134">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-134">Click Bind.</span></span>
20. <span data-ttu-id="c9184-135">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Valuta\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="c9184-136">Nella struttura selezionare "modello\Pagamenti\Valuta".</span><span class="sxs-lookup"><span data-stu-id="c9184-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="c9184-137">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-137">Click Bind.</span></span>
23. <span data-ttu-id="c9184-138">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Id'.</span><span class="sxs-lookup"><span data-stu-id="c9184-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="c9184-139">Nella struttura selezionare 'modello\Pagamenti\End2EndID'.</span><span class="sxs-lookup"><span data-stu-id="c9184-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="c9184-140">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-140">Click Bind.</span></span>
26. <span data-ttu-id="c9184-141">Nella struttura espandere "modello\Pagamenti\Creditore".</span><span class="sxs-lookup"><span data-stu-id="c9184-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="c9184-142">Nella struttura espandere "modello\Pagamenti\Creditore\Conto".</span><span class="sxs-lookup"><span data-stu-id="c9184-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="c9184-143">Nella struttura espandere "modello\Pagamenti\Creditore\Agente".</span><span class="sxs-lookup"><span data-stu-id="c9184-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="c9184-144">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="c9184-145">Nella struttura selezionare "modello\Pagamenti\Creditore\Nome".</span><span class="sxs-lookup"><span data-stu-id="c9184-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="c9184-146">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-146">Click Bind.</span></span>
32. <span data-ttu-id="c9184-147">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\RoutingNumber\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="c9184-148">Nella struttura selezionare 'modello\Pagamenti\Creditore\Agente\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="c9184-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="c9184-149">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-149">Click Bind.</span></span>
35. <span data-ttu-id="c9184-150">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\AccountNumber\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="c9184-151">Nella struttura selezionare "modello\Pagamenti\Creditore\Conto\Numero".</span><span class="sxs-lookup"><span data-stu-id="c9184-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="c9184-152">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-152">Click Bind.</span></span>
38. <span data-ttu-id="c9184-153">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Nome\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="c9184-154">Nella struttura espandere "modello\Pagamenti\Debitore".</span><span class="sxs-lookup"><span data-stu-id="c9184-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="c9184-155">Nella struttura espandere "modello\Pagamenti\Debitore\Conto".</span><span class="sxs-lookup"><span data-stu-id="c9184-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="c9184-156">Nella struttura espandere "modello\Pagamenti\Debitore\Agente".</span><span class="sxs-lookup"><span data-stu-id="c9184-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="c9184-157">Nella struttura selezionare "modello\Pagamenti\Debitore\Nome".</span><span class="sxs-lookup"><span data-stu-id="c9184-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="c9184-158">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-158">Click Bind.</span></span>
44. <span data-ttu-id="c9184-159">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\RoutingNumber\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="c9184-160">Nella struttura selezionare 'modello\Pagamenti\Debtor\Agente\RoutingNumber'.</span><span class="sxs-lookup"><span data-stu-id="c9184-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="c9184-161">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-161">Click Bind.</span></span>
47. <span data-ttu-id="c9184-162">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\AccountNumber\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c9184-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="c9184-163">Nella struttura selezionare "modello\Pagamenti\Debitore\Conto\Numero".</span><span class="sxs-lookup"><span data-stu-id="c9184-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="c9184-164">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-164">Click Bind.</span></span>
50. <span data-ttu-id="c9184-165">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo'.</span><span class="sxs-lookup"><span data-stu-id="c9184-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="c9184-166">Nella struttura selezionare "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="c9184-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="c9184-167">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c9184-167">Click Bind.</span></span>
53. <span data-ttu-id="c9184-168">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c9184-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="c9184-169">Convalidare il mapping di formato</span><span class="sxs-lookup"><span data-stu-id="c9184-169">Validate format mapping</span></span>
1. <span data-ttu-id="c9184-170">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="c9184-170">Click Validate.</span></span>
    * <span data-ttu-id="c9184-171">Convalidare il nuovo mapping per assicurarsi che tutte le associazioni siano corrette.</span><span class="sxs-lookup"><span data-stu-id="c9184-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="c9184-172">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c9184-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="c9184-173">Modifica lo stato della versione corrente della configurazione del formato</span><span class="sxs-lookup"><span data-stu-id="c9184-173">Change status of the current version of format configuration</span></span>
    * <span data-ttu-id="c9184-174">Nei passaggi seguenti verrà modificato lo stato della configurazione del formato da Bozza a Completato per renderlo disponibile per la generazione di documenti.</span><span class="sxs-lookup"><span data-stu-id="c9184-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="c9184-175">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="c9184-175">Click Change status.</span></span>
2. <span data-ttu-id="c9184-176">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="c9184-176">Click Complete.</span></span>
3. <span data-ttu-id="c9184-177">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c9184-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="c9184-178">Ad esempio, 'versione 1'.</span><span class="sxs-lookup"><span data-stu-id="c9184-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="c9184-179">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c9184-179">Click OK.</span></span>
5. <span data-ttu-id="c9184-180">Selezionare la versione completata della configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="c9184-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="c9184-181">Si noti che la configurazione viene salvata come versione completata 1.1: versione 1 del formato in base alla versione 1 del modello dati.</span><span class="sxs-lookup"><span data-stu-id="c9184-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="c9184-182">Definisce la data di validità della versione del formato completata</span><span class="sxs-lookup"><span data-stu-id="c9184-182">Define effective date for completed version of format</span></span>
    * <span data-ttu-id="c9184-183">Ciascuna versione del formato può essere configurata come disponibile per l'utilizzo a partire da una determinata data.</span><span class="sxs-lookup"><span data-stu-id="c9184-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="c9184-184">Quando più versioni di formato sono attive in una determinata data, il formato più recente (in base al numero di versione) verrà selezionato per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c9184-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="c9184-185">Il valore della data della sessione viene utilizzato per la selezione della versione appropriata.</span><span class="sxs-lookup"><span data-stu-id="c9184-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="c9184-186">Limitare l'accesso al formato creato da società</span><span class="sxs-lookup"><span data-stu-id="c9184-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="c9184-187">Espandere la sezione Codici paese ISO.</span><span class="sxs-lookup"><span data-stu-id="c9184-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="c9184-188">Ogni accesso al formato può essere limitato identificando particolari paesi in cui un formato è applicabile.</span><span class="sxs-lookup"><span data-stu-id="c9184-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="c9184-189">Se l'elenco dei paesi per il formato specifico è vuoto, il formato può essere utilizzato in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="c9184-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="c9184-190">Quando alcuni codici paese ISO vengono immessi nell'elenco di paesi, il formato può essere utilizzato solo nelle società se nell'indirizzo principale è presente il codice paese.</span><span class="sxs-lookup"><span data-stu-id="c9184-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  

