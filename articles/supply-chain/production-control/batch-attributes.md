---
title: Attributi batch
description: Questo argomento fornisce informazioni sugli attributi batch. Gli attributi batch sono caratteristiche delle materie prime e dei prodotti finiti che costituiscono i lotti di magazzino. L'argomento illustra inoltre come assegnare gli attributi batch e come cercarli quando si prenotano i batch.
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 56691376b639e20751b24e25343d8c71c631ad66
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="batch-attributes"></a><span data-ttu-id="5da49-105">Attributi batch</span><span class="sxs-lookup"><span data-stu-id="5da49-105">Batch attributes</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="5da49-106">Questo argomento fornisce informazioni sugli attributi batch.</span><span class="sxs-lookup"><span data-stu-id="5da49-106">This topic provides information about batch attributes.</span></span> <span data-ttu-id="5da49-107">Gli attributi batch sono caratteristiche delle materie prime e dei prodotti finiti che costituiscono i lotti di magazzino.</span><span class="sxs-lookup"><span data-stu-id="5da49-107">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="5da49-108">L'argomento illustra inoltre come assegnare gli attributi batch e come cercarli quando si prenotano i batch.</span><span class="sxs-lookup"><span data-stu-id="5da49-108">The topic also explains how to assign batch attributes, and how you can search on them when you reserve batches.</span></span>

<span data-ttu-id="5da49-109">Gli attributi batch sono caratteristiche delle materie prime e dei prodotti finiti che costituiscono i lotti di magazzino.</span><span class="sxs-lookup"><span data-stu-id="5da49-109">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="5da49-110">Gli attributi lotto possono variare in base a diversi fattori, ad esempio le condizioni ambientali o la qualità delle materie prime utilizzate per produrre il lotto.</span><span class="sxs-lookup"><span data-stu-id="5da49-110">Batch attributes can vary, depending on factors such as environmental conditions, the quality of the raw materials that are used to produce the batch, or the outcome of the finished product.</span></span> <span data-ttu-id="5da49-111">Il numero e i tipi degli attributi batch utilizzati possono variare notevolmente da un settore a un altro.</span><span class="sxs-lookup"><span data-stu-id="5da49-111">The number and types of batch attributes that are used can vary widely from one industry to another.</span></span> <span data-ttu-id="5da49-112">Di seguito vengono riportati due esempi di utilizzo degli attributi batch:</span><span class="sxs-lookup"><span data-stu-id="5da49-112">Here are two examples that show how to use batch attributes:</span></span>

-   <span data-ttu-id="5da49-113">Nel settore caseario il latte, ovvero una delle materie prime utilizzate per la produzione del formaggio, potrebbe essere associato ad attributi quali contenuto di grasso e peso percentuale.</span><span class="sxs-lookup"><span data-stu-id="5da49-113">In the cheese industry, milk, which is one of the raw materials that are used to produce the cheese, can have attributes such as fat content and percentage weight.</span></span> <span data-ttu-id="5da49-114">Il formaggio prodotto dal latte può essere associato ad altri attributi, ad esempio umidità ed età.</span><span class="sxs-lookup"><span data-stu-id="5da49-114">The cheese that is produced from the milk can have other attributes, such as moisture and age.</span></span>
-   <span data-ttu-id="5da49-115">Nel settore dell'acciaieria il ferro prodotto potrebbe essere associato ad attributi quali le percentuali di contenuto di magnesio, di argento e di zinco.</span><span class="sxs-lookup"><span data-stu-id="5da49-115">In the steel industry, the iron that is produced might have attributes such as the percentages of magnesium content, silver content, and zinc content.</span></span>

<span data-ttu-id="5da49-116">Per gestire meglio il numero e i tipi di attributi, è possibile utilizzare i gruppi di attributi batch.</span><span class="sxs-lookup"><span data-stu-id="5da49-116">To better manage the number and types of attributes, you can use batch attribute groups.</span></span> <span data-ttu-id="5da49-117">In questo modo, non è necessario aggiungere ogni attributo singolarmente.</span><span class="sxs-lookup"><span data-stu-id="5da49-117">In this way, you don't have to add each attribute individually.</span></span>

## <a name="assign-batch-attributes"></a><span data-ttu-id="5da49-118">Assegnare attributi batch</span><span class="sxs-lookup"><span data-stu-id="5da49-118">Assign batch attributes</span></span>
<span data-ttu-id="5da49-119">È possibile assegnare attributi batch a singoli articoli contenuti in lotti di magazzino oppure è possibile assegnarli agli articoli associati a clienti specifici.</span><span class="sxs-lookup"><span data-stu-id="5da49-119">You can assign batch attributes to individual products that are held in inventory batches, or you can assign them to products that are associated with specific customers.</span></span> <span data-ttu-id="5da49-120">Prima di poter assegnare un attributo batch al livello del cliente, è necessario assegnarlo al livello dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="5da49-120">Before you can assign a batch attribute at the customer level, you must assign it at the product level.</span></span> <span data-ttu-id="5da49-121">Per l'articolo la dimensione del batch deve essere impostata su **attiva** nel gruppo di dimensioni di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="5da49-121">The product must have the batch dimension set to **Active** in the tracking dimension group.</span></span> <span data-ttu-id="5da49-122">Per assegnare un attributo batch a un singolo articolo, utilizzare il modulo Specifico del prodotto.</span><span class="sxs-lookup"><span data-stu-id="5da49-122">To assign a batch attribute to an individual product, use the product-specific page.</span></span> <span data-ttu-id="5da49-123">Se l'attributo è specifico di un articolo per un cliente, utilizzare il modulo Specifico del cliente.</span><span class="sxs-lookup"><span data-stu-id="5da49-123">If the attribute is specific to a product for a customer, use the customer-specific page.</span></span> <span data-ttu-id="5da49-124">Quando si aggiunge un attributo a un articolo, si definiscono anche altri parametri.</span><span class="sxs-lookup"><span data-stu-id="5da49-124">When you add an attribute to a product, you also define other parameters.</span></span> <span data-ttu-id="5da49-125">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="5da49-125">Here are some examples:</span></span>

-   <span data-ttu-id="5da49-126">Intervalli minimo e massimo per un attributo di tipo **Intero** o **Frazione**.</span><span class="sxs-lookup"><span data-stu-id="5da49-126">The minimum and maximum ranges for an attribute of the **Integer** or **Fraction** type.</span></span>
-   <span data-ttu-id="5da49-127">Azioni tolleranza per un attributo di tipo **Intero** o **Frazione**.</span><span class="sxs-lookup"><span data-stu-id="5da49-127">The tolerance actions for an attribute of the **Integer** or **Fraction** type.</span></span> <span data-ttu-id="5da49-128">L'azione può essere un messaggio di avviso o un messaggio di errore se il valore dell'attributo non rientra nell'intervallo minimo e massimo.</span><span class="sxs-lookup"><span data-stu-id="5da49-128">If the value of the attribute falls outside the minimum and maximum range, the action can be either a warning message or an error message.</span></span>
-   <span data-ttu-id="5da49-129">Valore di destinazione per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="5da49-129">The target value for the attribute.</span></span> <span data-ttu-id="5da49-130">Si tratta del valore ottimale dell'attributo ed è applicabile a tutti i tipi di attributo.</span><span class="sxs-lookup"><span data-stu-id="5da49-130">This value is the optimal value of the attribute, and it applies to all attribute types.</span></span>

<span data-ttu-id="5da49-131">È possibile accedere a queste pagine per i prodotti selezionati nella pagina elenco **Prodotti rilasciati** in Gestione informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="5da49-131">You can access the pages for products that you select on the **Released products** page in Product information management.</span></span> <span data-ttu-id="5da49-132">Dopo avere assegnato attributi batch a un prodotto, è possibile aggiungere valori specifici agli attributi nella pagina **Attributi lotto di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="5da49-132">After you assign batch attributes to a product, you can add specific values to the attributes on the **Inventory batch attributes** page.</span></span>

## <a name="reserve-batches"></a><span data-ttu-id="5da49-133">Prenotazione di batch</span><span class="sxs-lookup"><span data-stu-id="5da49-133">Reserve batches</span></span>
<span data-ttu-id="5da49-134">È possibile eseguire ricerche negli attributi batch quando si eseguono prenotazioni batch per un ordine cliente allo scopo di evadere l'ordine di un cliente, o quando si prelevano e si prenotano batch per un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="5da49-134">You can search on batch attributes when you do batch reservations for a sales order to fulfill a customer's order, or when you pick and reserve batches for a production order.</span></span> <span data-ttu-id="5da49-135">La ricerca consente di trovare il lotto di magazzino che contiene il prodotto con gli attributi batch desiderati.</span><span class="sxs-lookup"><span data-stu-id="5da49-135">The search helps locate an inventory batch that contains the product that has the batch attribute that you want.</span></span> <span data-ttu-id="5da49-136">Dopo aver trovato il batch, è possibile prenotare l'articolo sulla riga di transazione di magazzino di origine.</span><span class="sxs-lookup"><span data-stu-id="5da49-136">After you locate the batch or batches, you can reserve the product to the originating inventory transaction line.</span></span>




