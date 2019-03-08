---
title: Impostare i modelli di valore
description: In questa procedura viene illustrato come creare un nuovo libro cespiti e associarlo a un gruppo cespite.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e067173b27488422fd05ad45f37528f00f04a2bd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "311797"
---
# <a name="set-up-value-models"></a><span data-ttu-id="b4a33-103">Impostare i modelli di valore</span><span class="sxs-lookup"><span data-stu-id="b4a33-103">Set up value models</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b4a33-104">In questa procedura viene illustrato come creare un nuovo libro cespiti e associarlo a un gruppo cespite.</span><span class="sxs-lookup"><span data-stu-id="b4a33-104">This procedure shows you to how create a new fixed asset book and associate it with a fixed asset group.</span></span> <span data-ttu-id="b4a33-105">Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="b4a33-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-book"></a><span data-ttu-id="b4a33-106">Creare un libro</span><span class="sxs-lookup"><span data-stu-id="b4a33-106">Create a book</span></span>
1. <span data-ttu-id="b4a33-107">Passare a Cespiti > Impostazione > Libri.</span><span class="sxs-lookup"><span data-stu-id="b4a33-107">Go to Fixed assets > Setup > Books.</span></span>
2. <span data-ttu-id="b4a33-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b4a33-108">Click New.</span></span>
3. <span data-ttu-id="b4a33-109">Nel campo Libro digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4a33-109">In the Book field, type a value.</span></span>
4. <span data-ttu-id="b4a33-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4a33-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="b4a33-111">Se Calcola ammortamento è selezionato, il libro cespiti associato verrà incluso nelle proposte di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="b4a33-111">If Calculate depreciation is selected, the associated asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="b4a33-112">Se non è selezionato, il libro cespiti non verrà ammortizzato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b4a33-112">If it is not selected, the asset book will not be automatically depreciated.</span></span>  
5. <span data-ttu-id="b4a33-113">Selezionare Sì nel campo Calcola ammortamento.</span><span class="sxs-lookup"><span data-stu-id="b4a33-113">Select Yes in the Calculate depreciation field.</span></span>
6. <span data-ttu-id="b4a33-114">Nel campo Profilo di ammortamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4a33-114">In the Depreciation profile field, enter or select a value.</span></span>
    * <span data-ttu-id="b4a33-115">Un profilo di ammortamento alternativo è anche noto come metodo di ammortamento alternativo.</span><span class="sxs-lookup"><span data-stu-id="b4a33-115">An alternative depreciation profile is also known as a switchover method of depreciation.</span></span> <span data-ttu-id="b4a33-116">La proposta di ammortamento passerà a questo profilo quando il profilo alternativo calcolerà un importo di ammortamento uguale o maggiore del profilo di ammortamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="b4a33-116">The depreciation proposal will switch to this profile when the alternative profile calculates a depreciation amount that is equal to or greater than the default depreciation profile.</span></span>  
    * <span data-ttu-id="b4a33-117">Parametri di ammortamento straordinario viene utilizzato per l'ammortamento aggiuntivo di un cespite in circostanze insolite.</span><span class="sxs-lookup"><span data-stu-id="b4a33-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="b4a33-118">È ad esempio possibile utilizzare questi parametri per registrare l'ammortamento causato da un disastro naturale.</span><span class="sxs-lookup"><span data-stu-id="b4a33-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
    * <span data-ttu-id="b4a33-119">Se Crea rettifiche all'ammortamento con rettifiche di base è selezionato, le rettifiche di ammortamento verranno automaticamente create quando il valore del cespite viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b4a33-119">If Create depreciation adjustments with basis adjustments is selected, depreciation adjustments will be automatically created when the value of the asset is updated.</span></span> <span data-ttu-id="b4a33-120">Se non è selezionato, il valore del cespite aggiornato influirà solo sui calcoli di ammortamento successivi.</span><span class="sxs-lookup"><span data-stu-id="b4a33-120">If it is not selected, the updated asset value will only affect depreciation calculations going forward.</span></span>  
7. <span data-ttu-id="b4a33-121">Selezionare Sì nel campo Crea rettifiche all'ammortamento con rettifiche di base.</span><span class="sxs-lookup"><span data-stu-id="b4a33-121">Select Yes in the Create depreciation adjustments with basis adjustments field.</span></span>
    * <span data-ttu-id="b4a33-122">Per impostazione predefinita, Ogni transazione libro cespiti verrà registrata nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="b4a33-122">By default, fixed asset book transactions will post to the general ledger.</span></span> <span data-ttu-id="b4a33-123">È possibile disabilitare la registrazione nella contabilità generale per il libro impostando il campo Registra nella contabilità generale su No.</span><span class="sxs-lookup"><span data-stu-id="b4a33-123">You can disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="b4a33-124">I libri che non vengono registrate nella contabilità generale viene in genere utilizzato a fini di reporting fiscale.</span><span class="sxs-lookup"><span data-stu-id="b4a33-124">Books that do not post to the general ledger are typically used for tax reporting purposes.</span></span> <span data-ttu-id="b4a33-125">Ciò offre flessibilità aggiuntiva per eliminare le transazioni storiche del libro cespiti perché non sono state impegnate nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="b4a33-125">This gives you additional flexibility to delete historical transactions for the asset book because they have not been committed to the general ledger.</span></span>  
    * <span data-ttu-id="b4a33-126">Il livello di registrazione assume il valore predefinito Livello corrente se il libro viene registrato nella contabilità generale e Nessuno se non viene registrato nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="b4a33-126">The Posting layer defaults to the Current layer if the book posts to general ledger, and None if it does not post to general ledger.</span></span> <span data-ttu-id="b4a33-127">Aggiornare il livello di registrazione se sono necessarie delle transazioni perché tale libro venga registrato in un altro livello.</span><span class="sxs-lookup"><span data-stu-id="b4a33-127">Update Posting layer if you need transactions for this book to be posted to a different layer.</span></span>  
8. <span data-ttu-id="b4a33-128">Nel campo Calendario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4a33-128">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="b4a33-129">I libri derivati registreranno transazioni in libri diversi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b4a33-129">Derived books will post transactions to different books at the same time.</span></span> <span data-ttu-id="b4a33-130">Le transazioni si creano con il libro principale e durante la registrazione, una copia esatta della transazione viene registrata nel libro derivato.</span><span class="sxs-lookup"><span data-stu-id="b4a33-130">You create the transactions with the primary book and during posting, an exact copy of the transaction is posted to the derived book.</span></span> <span data-ttu-id="b4a33-131">Non esiste un ricalcolo con le transazioni nei libri derivati, quindi non devono essere utilizzati per le transazioni di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="b4a33-131">There is no recalculation with derived book transactions, so it should not be used for depreciation transactions.</span></span>  

## <a name="associate-the-book-with-a-fixed-asset-group"></a><span data-ttu-id="b4a33-132">Associare il libro a un gruppo cespite</span><span class="sxs-lookup"><span data-stu-id="b4a33-132">Associate the book with a fixed asset group</span></span>
1. <span data-ttu-id="b4a33-133">Fare clic su Gruppi cespiti.</span><span class="sxs-lookup"><span data-stu-id="b4a33-133">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="b4a33-134">Nel campo Cespiti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4a33-134">In the Fixed asset group field, enter or select a value.</span></span>
3. <span data-ttu-id="b4a33-135">Immettere un numero nel campo Vita utile.</span><span class="sxs-lookup"><span data-stu-id="b4a33-135">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="b4a33-136">Si noti che il valore del campo Periodi di ammortamento viene calcolato dopo aver impostato Vita utile.</span><span class="sxs-lookup"><span data-stu-id="b4a33-136">Note that Depreciation periods is calculated after setting the Service life.</span></span>  
    * <span data-ttu-id="b4a33-137">È possibile impostare la convenzione di ammortamento come richiesto per scopi fiscali.</span><span class="sxs-lookup"><span data-stu-id="b4a33-137">You are able to set the depreciation convention as required for tax purposes.</span></span>  

