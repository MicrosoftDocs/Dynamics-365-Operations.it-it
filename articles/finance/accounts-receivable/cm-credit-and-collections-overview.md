---
title: Panoramica di Credito e riscossioni
description: In questo argomento viene fornita una panoramica della funzionalità Credito e riscossioni.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ade76b822904f49135e07dfe0a39d2227dd1dd77
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992990"
---
# <a name="credit-and-collections-overview"></a><span data-ttu-id="98133-103">Panoramica di Credito e riscossioni</span><span class="sxs-lookup"><span data-stu-id="98133-103">Credit and collections overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98133-104">È possibile gestire i limiti di credito per i clienti ed eseguire attività di riscossione quando diventano necessarie.</span><span class="sxs-lookup"><span data-stu-id="98133-104">You can manage credit limits for your customers and perform collection activities when they become necessary.</span></span>

## <a name="credit-management"></a><span data-ttu-id="98133-105">Gestione crediti</span><span class="sxs-lookup"><span data-stu-id="98133-105">Credit management</span></span>

<span data-ttu-id="98133-106">La gestione dei crediti cliente consente di gestire i limiti di credito e di controllare il flusso degli ordini cliente attraverso il processo di registrazione in base a regole di credito create.</span><span class="sxs-lookup"><span data-stu-id="98133-106">Customer credit management lets you manage credit limits and control the flow of sales orders through the posting process, based on credit rules that you create.</span></span>

<span data-ttu-id="98133-107">Il processo di gestione dei crediti può includere alcuni o tutti i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="98133-107">The credit management process can include any of the following steps:</span></span>

- <span data-ttu-id="98133-108">Aggiornare attributi di credito per i clienti allo scopo di fornire ulteriori informazioni sulla loro affidabilità creditizia.</span><span class="sxs-lookup"><span data-stu-id="98133-108">Update credit attributes for customers to provide additional information about their credit worthiness.</span></span>
- <span data-ttu-id="98133-109">Creare limiti di credito per i clienti utilizzando correzioni dei limiti di credito.</span><span class="sxs-lookup"><span data-stu-id="98133-109">Create credit limits for customers by using credit limit adjustments.</span></span>
- <span data-ttu-id="98133-110">Creare limiti di credito temporanei per i clienti utilizzando correzioni dei limiti di credito.</span><span class="sxs-lookup"><span data-stu-id="98133-110">Create temporary credit limits for customers by using credit limit adjustments.</span></span> <span data-ttu-id="98133-111">In questo modo, è possibile aumentare o ridurre temporaneamente i limiti di credito dei clienti in base ai requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="98133-111">In this way, you can temporarily increase or decrease customer credit limits, based on business requirements.</span></span>
- <span data-ttu-id="98133-112">Aggiungere ulteriori informazioni che possono influire sul limite di credito come informazioni su assicurazione e garanzie.</span><span class="sxs-lookup"><span data-stu-id="98133-112">Add information that can affect the credit limit, such as information about insurance and guarantees.</span></span>
- <span data-ttu-id="98133-113">Crea gruppi di crediti cliente che collegano i clienti di modo che possano condividere un unico limite di credito.</span><span class="sxs-lookup"><span data-stu-id="98133-113">Create customer credit groups that link customers together so that they share a single credit limit.</span></span>
- <span data-ttu-id="98133-114">Assegnare punteggi di rischio ai clienti e quindi utilizzare tali punteggi per generare automaticamente limiti di credito per quei clienti utilizzando correzioni dei limiti di credito.</span><span class="sxs-lookup"><span data-stu-id="98133-114">Assign risk scores to customers, and then use the scores to automatically generate credit limits for those customers through credit limit adjustments.</span></span>
- <span data-ttu-id="98133-115">Creare regole di blocco che sospenderanno un ordine durante uno o più processi di registrazione in base a fattori quali rischio, termini di pagamento, limiti di credito, importi scaduti e percentuale del limite di credito utilizzato.</span><span class="sxs-lookup"><span data-stu-id="98133-115">Create blocking rules that put an order on hold during one or more posting processes, based on factors such as risk, payment terms, credit limits, overdue amounts, and the percentage of the credit limit that has been used.</span></span>
- <span data-ttu-id="98133-116">Gestire un elenco di ordini cliente sospesi, esaminare i motivi della sospensione e attenuare i problemi.</span><span class="sxs-lookup"><span data-stu-id="98133-116">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate issues.</span></span>
- <span data-ttu-id="98133-117">Rilasciare ordini cliente in modo da continuare il processo di registrazione degli stessi.</span><span class="sxs-lookup"><span data-stu-id="98133-117">Release sales orders so that they continue through the posting process.</span></span>
- <span data-ttu-id="98133-118">Configurare un flusso di lavoro per gestire l'approvazione delle modifiche a limiti di credito e dei rilasci di ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="98133-118">Set up a workflow to manage the approval of credit limit changes and sales order releases.</span></span>

## <a name="collections-management"></a><span data-ttu-id="98133-119">Gestione raccolte</span><span class="sxs-lookup"><span data-stu-id="98133-119">Collections management</span></span>

<span data-ttu-id="98133-120">La pagina **Riscossioni** fornisce una visualizzazione centralizzata per la gestione delle informazioni sulle riscossioni della contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="98133-120">The **Collections** page provides a centralized view where accounts receivable collections information is managed.</span></span> <span data-ttu-id="98133-121">I responsabili delle riscossioni possono utilizzare questa visualizzazione per gestire le riscossioni.</span><span class="sxs-lookup"><span data-stu-id="98133-121">Collections managers can use this centralized view to manage collections.</span></span> <span data-ttu-id="98133-122">Gli agenti di riscossione possono avviare il processo di riscossione dagli elenchi di clienti generati utilizzando criteri di riscossione predefiniti o dalla pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="98133-122">Collections agents can begin the collections process either from customer lists that are generated by using predefined collection criteria or from the **Customers** page.</span></span>

<span data-ttu-id="98133-123">Prima di iniziare a impostare o a utilizzare le riscossioni, è necessario comprendere i concetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="98133-123">Before you start to set up or work with collections, you should understand the following concepts:</span></span>

- <span data-ttu-id="98133-124">Gli snapshot di aging dei clienti contengono informazioni sui saldi con aging in un momento specifico nel tempo.</span><span class="sxs-lookup"><span data-stu-id="98133-124">Customer aging snapshots contain aged balance information at a specific point in time.</span></span>
- <span data-ttu-id="98133-125">I pool di clienti per riscossioni facilitano l'organizzazione del lavoro.</span><span class="sxs-lookup"><span data-stu-id="98133-125">Collections customer pools help you organize your work.</span></span>
- <span data-ttu-id="98133-126">Gli agenti di riscossione possono avere pool di clienti propri.</span><span class="sxs-lookup"><span data-stu-id="98133-126">Collections agents can have their own customer pools.</span></span>
- <span data-ttu-id="98133-127">Le pagine elenco consentono di organizzare casi, attività e clienti di riscossione.</span><span class="sxs-lookup"><span data-stu-id="98133-127">List pages organize collections customers, activities, and cases.</span></span>
- <span data-ttu-id="98133-128">Tutte le informazioni sulle riscossioni relative a un cliente si trovano in un'unica pagina in cui è possibile intraprendere le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="98133-128">All collections information for a customer is on one page, and you can take action from that page.</span></span>
- <span data-ttu-id="98133-129">È possibile rinunciare a interessi e commissioni, ripristinarli oppure stornarli in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="98133-129">Interest and fees can be waived, reinstated, or reversed in one step.</span></span>
- <span data-ttu-id="98133-130">È possibile creare transazioni di annullamento in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="98133-130">Write-off transactions can be created in one step.</span></span>
- <span data-ttu-id="98133-131">È possibile elaborare pagamenti NSF (Non Sufficient Funds, senza copertura) in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="98133-131">Not sufficient funds (NSF) payments can be processed in one step.</span></span>

<span data-ttu-id="98133-132">Per le descrizioni di questi concetti, vedere [Concetti chiave della gestione delle riscossioni](./cm-collections-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="98133-132">For descriptions of these concepts, see [Collections management key concepts](./cm-collections-concepts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98133-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="98133-133">Additional resources</span></span>

[<span data-ttu-id="98133-134">Impostazione dei parametri di gestione dei crediti cliente</span><span class="sxs-lookup"><span data-stu-id="98133-134">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="98133-135">Informazioni sull'impostazione della gestione dei crediti cliente</span><span class="sxs-lookup"><span data-stu-id="98133-135">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="98133-136">Aggiungere informazioni sulla gestione dei crediti per un cliente</span><span class="sxs-lookup"><span data-stu-id="98133-136">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="98133-137">Gruppi di crediti cliente</span><span class="sxs-lookup"><span data-stu-id="98133-137">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="98133-138">Correzioni dei limiti di credito dei clienti</span><span class="sxs-lookup"><span data-stu-id="98133-138">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="98133-139">Sospensioni credito per ordini cliente</span><span class="sxs-lookup"><span data-stu-id="98133-139">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="98133-140">Attività periodiche di gestione dei crediti cliente</span><span class="sxs-lookup"><span data-stu-id="98133-140">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)
