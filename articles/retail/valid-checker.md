---
title: Controllo di coerenza per le transazioni di vendita al dettaglio
description: In questo argomento viene descritta la funzionalità di controllo di coerenza per le transazioni di vendita al dettaglio in Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: db01a12b92574b41f1f4fe7281c23992e0d36027
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "302491"
---
# <a name="retail-transaction-consistency-checker"></a><span data-ttu-id="b5a36-103">Controllo di coerenza per le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="b5a36-103">Retail transaction consistency checker</span></span>


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="b5a36-104">In questo argomento viene descritta la funzionalità di controllo di coerenza per le transazioni di vendita al dettaglio introdotta in Microsoft Dynamics 365 for Finance and Operations, versione 8.1.3.</span><span class="sxs-lookup"><span data-stu-id="b5a36-104">This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span></span> <span data-ttu-id="b5a36-105">Il controllo di coerenza identifica e isole le transazioni incoerenti prima che vengano prelevate dal processo di registrazione rendiconti.</span><span class="sxs-lookup"><span data-stu-id="b5a36-105">The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</span></span>

<span data-ttu-id="b5a36-106">Quando un rendiconto viene registrato in Retail, la registrare può non riuscire a causa di dati incoerenti nelle tabelle di transazioni di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b5a36-106">When a statement is posted in Retail, posting can fail due to inconsistent data in the retail transaction tables.</span></span> <span data-ttu-id="b5a36-107">Il problema sui dati può essere causato da problemi non previsti nell'applicazione POS o da transazioni importate in modo non corretto da sistemi POS di terze parti.</span><span class="sxs-lookup"><span data-stu-id="b5a36-107">The data issue may be caused by by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</span></span> <span data-ttu-id="b5a36-108">Esempi di come le incoerenze possono essere visualizzate includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5a36-108">Examples of how these inconsistencies may appear include:</span></span> 

  - <span data-ttu-id="b5a36-109">Il totale delle transazioni nella tabella di intestazione non corrisponde al totale delle transazioni nelle righe.</span><span class="sxs-lookup"><span data-stu-id="b5a36-109">The transaction total on the header table does not match the transaction total on the lines.</span></span>
  - <span data-ttu-id="b5a36-110">Il conteggio delle righe nella tabella di intestazione non corrisponde al numero di righe nella tabella di transazioni.</span><span class="sxs-lookup"><span data-stu-id="b5a36-110">The line count on the header table does not match with the number of lines in the transaction table.</span></span>
  - <span data-ttu-id="b5a36-111">Le imposte nella tabella di intestazione non corrispondono all'importo delle imposte nelle righe.</span><span class="sxs-lookup"><span data-stu-id="b5a36-111">Taxes on the header table do not match the tax amount on the lines.</span></span> 
  
<span data-ttu-id="b5a36-112">Quando il processo di registrazione rendiconti preleva transazioni incoerenti, vengono creati giornali di registrazione pagamenti e fatture di vendita incoerenti e di conseguenza tutto il processo di registrazione rendiconti ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b5a36-112">When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</span></span> <span data-ttu-id="b5a36-113">Il recupero dei rendiconti da uno stato di questo tipo prevede rettifiche complessi di dati in più tabelle di transazioni.</span><span class="sxs-lookup"><span data-stu-id="b5a36-113">Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</span></span> <span data-ttu-id="b5a36-114">Il controllo di coerenza per le transazioni di vendita al dettaglio consente di evitare questi problemi.</span><span class="sxs-lookup"><span data-stu-id="b5a36-114">The retail transaction consistency checker prevents such issues.</span></span>

<span data-ttu-id="b5a36-115">Nel grafico seguente è illustrato il processo di registrazione con il controllo di coerenza per le transazioni.</span><span class="sxs-lookup"><span data-stu-id="b5a36-115">The following chart illustrates the posting process with the transaction consistency checker.</span></span>

<span data-ttu-id="b5a36-116">![Processo di registrazione dei rendiconto con il controllo di coerenza per le transazioni di vendita al dettaglio](./media/validchecker.png "Processo di registrazione dei rendiconto con il controllo di coerenza per le transazioni di vendita al dettaglio")</span><span class="sxs-lookup"><span data-stu-id="b5a36-116">![Statement posting process with retail transaction consistency checker](./media/validchecker.png "Statement posting process with retail transsaction consistency checker")</span></span>

<span data-ttu-id="b5a36-117">Il processo batch **Convalida transazioni punto vendita** controlla la coerenza delle tabelle di transazioni di vendita al dettaglio per gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="b5a36-117">The **Validate store transactions** batch process checks the consistency of the retail transaction tables for the following scenarios.</span></span>

- <span data-ttu-id="b5a36-118">Conto cliente - Verifica che il conto cliente presente nelle tabelle di transazioni di vendita al dettaglio sia presente nei dati master cliente della sede centrale.</span><span class="sxs-lookup"><span data-stu-id="b5a36-118">Customer account - Validates that the customer account in the retail transaction tables exists in the HQ customer master.</span></span>
- <span data-ttu-id="b5a36-119">Conteggio righe - Verifica che il numero di righe, come acquisito nella di intestazione delle transazioni, corrisponda al numero di righe nelle tabelle di transazioni vendite.</span><span class="sxs-lookup"><span data-stu-id="b5a36-119">Line count - Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</span></span>

## <a name="set-up-the-consistency-checker"></a><span data-ttu-id="b5a36-120">Impostare il controllo di coerenza</span><span class="sxs-lookup"><span data-stu-id="b5a36-120">Set up the consistency checker</span></span>
<span data-ttu-id="b5a36-121">Configurare il processo batch "Convalida transazioni punto vendita" in **Vendita al dettaglio \> Vendita al dettaglio IT \> Registrazione POS** per esecuzioni periodiche.</span><span class="sxs-lookup"><span data-stu-id="b5a36-121">Configure the "Validate store transactions" batch process, at **Retail \> Retail IT \> POS posting**, for periodic runs.</span></span> <span data-ttu-id="b5a36-122">Il processo batch può essere programmato in base alla gerarchia organizzativa, in modo analogo a come vengono impostati i processi "Calcola rendiconti in batch" e "Registra rendiconti in batch".</span><span class="sxs-lookup"><span data-stu-id="b5a36-122">The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</span></span> <span data-ttu-id="b5a36-123">Si consiglia di configurare questo processo batch per più esecuzioni giornaliere e di programmarlo in modo che venga eseguito al termine di ogni esecuzione del processo P.</span><span class="sxs-lookup"><span data-stu-id="b5a36-123">We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</span></span>

## <a name="results-of-validation-process"></a><span data-ttu-id="b5a36-124">Risultati del processo di convalida</span><span class="sxs-lookup"><span data-stu-id="b5a36-124">Results of validation process</span></span>
<span data-ttu-id="b5a36-125">I risultati della verifica di convalida eseguita dal processo batch sono contrassegnati sulla transazione di vendita al dettaglio appropriata.</span><span class="sxs-lookup"><span data-stu-id="b5a36-125">The results of the validation check by the batch process are tagged on the appropriate retail transaction.</span></span> <span data-ttu-id="b5a36-126">Il campo **Stato convalida** nel record di transazione di vendita al dettaglio è impostato su **Operazione completata** o **Errore** e la data dell'ultima convalida viene visualizzata nel campo **Ora ultima convalida**.</span><span class="sxs-lookup"><span data-stu-id="b5a36-126">The **Validation status** field on the retail transaction record is either set to **Successful** or **Error**, and the date of the last validation run appears on the **Last validation time** field.</span></span>

<span data-ttu-id="b5a36-127">Per visualizzare più testo descrittivo dell'errore relativo a una mancata convalida, selezionare il record di transazione di punto vendita al dettaglio e fare clic sul pulsante **Errori di convalida**.</span><span class="sxs-lookup"><span data-stu-id="b5a36-127">To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the **Validation errors** button.</span></span>

<span data-ttu-id="b5a36-128">Le transazioni che non superano il controllo di convalida e quelle non ancora convalidate non verranno inserite nei rendiconti.</span><span class="sxs-lookup"><span data-stu-id="b5a36-128">Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</span></span> <span data-ttu-id="b5a36-129">Durante il processo di calcolo dei rendiconti, agli utenti verrà comunicato se sono presenti transazioni che sarebbe stato possibile includere nel rendiconto, ma non lo sono state.</span><span class="sxs-lookup"><span data-stu-id="b5a36-129">During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</span></span>

<span data-ttu-id="b5a36-130">Se viene rilevato un errore di convalida, per correggerlo è necessario contattare il servizio di supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5a36-130">If a validation error is found, the only way to fix the error is to contact Microsoft Support.</span></span> <span data-ttu-id="b5a36-131">In una versione futura, verrà aggiunta la possibilità per gli utenti di correggere i record con errore nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b5a36-131">In a future release, capability will be added so that users can fix the records that failed through the user interface.</span></span> <span data-ttu-id="b5a36-132">Verranno rese disponibili anche funzionalità di registrazione e controllo per tenere traccia dello storico delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="b5a36-132">Logging and auditing capabilities will also be made available to trace the history of the modifications.</span></span>

> [!NOTE]
> <span data-ttu-id="b5a36-133">Regole di convalida aggiuntive supportare più scenari verranno aggiunte in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="b5a36-133">Additional validation rules to support more scenarios will be added in a future release.</span></span>
