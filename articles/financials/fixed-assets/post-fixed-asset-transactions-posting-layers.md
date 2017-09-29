---
title: Registrare transazioni cespiti nei livelli di registrazione
description: "Questo articolo fornisce una panoramica delle funzionalità del livello di registrazione per le transazioni cespiti."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 10e7fc67f8f13a6363b4359fd1b7684f1b80675e
ms.contentlocale: it-it
ms.lasthandoff: 06/29/2017


---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a><span data-ttu-id="97182-103">Registrare transazioni cespiti nei livelli di registrazione</span><span class="sxs-lookup"><span data-stu-id="97182-103">Post fixed asset transactions to posting layers</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="97182-104">Questo articolo fornisce una panoramica delle funzionalità del livello di registrazione per le transazioni cespiti.</span><span class="sxs-lookup"><span data-stu-id="97182-104">This article gives an overview of posting layer functionality for fixed asset transactions.</span></span>

<span data-ttu-id="97182-105">L'ammortamento di un cespite viene spesso effettuato in vari modi per diversi scopi.</span><span class="sxs-lookup"><span data-stu-id="97182-105">A fixed asset is often depreciated in different ways for different purposes.</span></span> <span data-ttu-id="97182-106">L'ammortamento ai fini fiscali viene calcolato in base alle regole correnti per ottenere l'ammortamento più alto possibile al lordo d'imposta, tuttavia l'ammortamento ai fini della dichiarazione viene calcolato in base alle normative e agli standard contabili vigenti.</span><span class="sxs-lookup"><span data-stu-id="97182-106">Depreciation for tax purposes is calculated by using current tax rules to achieve the highest possible depreciation before taxes, but depreciation for reporting purposes is calculated according to accounting laws and standards.</span></span> <span data-ttu-id="97182-107">I diversi tipi di ammortamento vengono calcolati e registrati separatamente nei livelli di registrazione.</span><span class="sxs-lookup"><span data-stu-id="97182-107">The various kinds of depreciation are calculated and recorded separately in the posting layers.</span></span>

<span data-ttu-id="97182-108">Ciascun libro collegato a un cespite viene impostato per un particolare livello di registrazione con un obiettivo di ammortamento complessivo.</span><span class="sxs-lookup"><span data-stu-id="97182-108">Each book that is attached to a fixed asset is set up for a particular posting layer that has an overall depreciation objective.</span></span> <span data-ttu-id="97182-109">Sono disponibili dieci livelli di registrazione: Corrente, Operazioni, Imposta e sette livelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="97182-109">There are ten posting layers: Current, Operations, Tax, and seven Custom layers.</span></span> <span data-ttu-id="97182-110">È possibile anche disabilitare la registrazione nella contabilità generale per il libro impostando il campo Registra nella contabilità generale su No.</span><span class="sxs-lookup"><span data-stu-id="97182-110">You can also disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="97182-111">Il campo Livello di registrazione verrà impostato automaticamente su Nessuno.</span><span class="sxs-lookup"><span data-stu-id="97182-111">The Posting layer field is then automatically set to None.</span></span> <span data-ttu-id="97182-112">In genere i libri che non vengono registrati nella contabilità generale sono utilizzati a fini di reporting fiscale.</span><span class="sxs-lookup"><span data-stu-id="97182-112">Typically, books that don’t post to the general ledger are used for tax reporting purposes.</span></span> <span data-ttu-id="97182-113">Ciò offre flessibilità aggiuntiva per eliminare le transazioni storiche del libro cespiti perché non sono state impegnate nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="97182-113">This approach gives you the additional flexibility to delete historical transactions for the asset book, because they haven’t been committed to the general ledger.</span></span>

<span data-ttu-id="97182-114">I giornali di registrazione cespiti vengono definiti mediante la pagina  Nomi giornale di registrazione da Contabilità generale >Impostazione del giornale di registrazione > Nomi giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="97182-114">Fixed asset journals are defined by using the Journal names page at General ledger > Journal setup > Journal names.</span></span> <span data-ttu-id="97182-115">Ciascun giornale di registrazione in cui sia possibile registrare ammortamenti viene definito in base al relativo nome di giornale di registrazione per un solo livello di registrazione.</span><span class="sxs-lookup"><span data-stu-id="97182-115">Each journal that you can post depreciations in is defined by its journal name for only one posting layer.</span></span> <span data-ttu-id="97182-116">Il livello di registrazione nel giornale di registrazione non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="97182-116">The posting layer in the journal can’t be changed.</span></span> <span data-ttu-id="97182-117">Tale restrizione assicura che le transazioni per ciascun livello di registrazione vengono mantenute separate.</span><span class="sxs-lookup"><span data-stu-id="97182-117">This restriction helps guarantee that transactions for each posting layer are kept separate.</span></span> <span data-ttu-id="97182-118">Per ciascun livello di registrazione è necessario creare almeno un nome di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="97182-118">At least one journal name must be created for each posting layer.</span></span> <span data-ttu-id="97182-119">Se si utilizzano i libri che non vengono registrati nella contabilità generale, è inoltre necessario creare un giornale di registrazione in cui il livello di registrazione è Nessuno.</span><span class="sxs-lookup"><span data-stu-id="97182-119">If you’re using books that don’t post to the general ledger, you must also create a journal where the posting layer is set to None.</span></span>

<span data-ttu-id="97182-120">È possible designare conti CoGe per le transazioni cespiti nella pagina Profili registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="97182-120">You can designate ledger accounts for fixed asset transactions on the Fixed asset posting profiles page.</span></span> <span data-ttu-id="97182-121">Per ciascun profilo registrazione, è necessario selezionare il tipo di transazione e il libro pertinenti e quindi designare i conti CoGe.</span><span class="sxs-lookup"><span data-stu-id="97182-121">For each posting profile, you must select the relevant transaction type and book, and then designate the ledger accounts.</span></span> <span data-ttu-id="97182-122">Impostare un record di profilo registrazione per ciascun libro che verrà registrato nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="97182-122">Set up a posting profile record for each book that will post to the general ledger.</span></span>

> [!NOTE] 
> <span data-ttu-id="97182-123">L'utilizzo di libri derivati consente di registrare transazioni contemporaneamente in diversi livelli di registrazione.</span><span class="sxs-lookup"><span data-stu-id="97182-123">By using derived books, you can post transactions to different posting layers at the same time.</span></span> <span data-ttu-id="97182-124">Le transazioni del libro principale vengono create in un giornale di registrazione con il livello di registrazione corrispondente a quello del libro.</span><span class="sxs-lookup"><span data-stu-id="97182-124">You create the transactions of the primary book in a journal where the posting layer corresponds to the book posting layer.</span></span> <span data-ttu-id="97182-125">Durante la registrazione le transazioni del libro derivato vengono registrate nei livelli di registrazione appropriati.</span><span class="sxs-lookup"><span data-stu-id="97182-125">During posting, the derived book transactions are posted to the appropriate posting layers.</span></span>

<span data-ttu-id="97182-126">Per ulteriori informazioni, vedere [Libri derivati](derived-books.md) e [Registrazione con i libri derivati](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="97182-126">For more information see, [Derived books](derived-books.md) and [Posting with derived books](post-derived-value-models.md).</span></span>




