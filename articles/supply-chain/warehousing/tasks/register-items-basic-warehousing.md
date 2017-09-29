--- 
title: Registrare articoli per un articolo abilitato a immagazzinaggio di base tramite un giornale di registrazione arrivi
description: "Questa procedura mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizza la funzionalità di gestione magazzino di base nel modulo Gestione articoli."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a5fa86bace459d694ab0a2ec289e11b0e4420932
ms.openlocfilehash: 184f38347e2525f3efef9b0d55003a94a75380d4
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="f3043-103">Registrare articoli per un articolo abilitato a immagazzinaggio di base tramite un giornale di registrazione arrivi</span><span class="sxs-lookup"><span data-stu-id="f3043-103">Register items for a basic warehousing enabled item using an item arrival journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3043-104">Questa procedura mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizza la funzionalità di gestione magazzino di base nel modulo Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="f3043-104">This procedure shows you how to register items using the item arrival journal when you are using “basic warehousing” in the Inventory management module.</span></span> <span data-ttu-id="f3043-105">Questa operazione viene generalmente effettuata da un addetto al ricevimento.</span><span class="sxs-lookup"><span data-stu-id="f3043-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="f3043-106">È possibile eseguire questa procedura utilizzando la società di dati dimostrativi USMF con i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="f3043-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="f3043-107">Se non si utilizza USMF, è necessario disporre di un ordine fornitore confermato con una riga ordine fornitore aperta prima di iniziare questa guida.</span><span class="sxs-lookup"><span data-stu-id="f3043-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="f3043-108">L'articolo nella riga deve essere stoccato e non deve utilizzare le varianti prodotto né avere dimensioni di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="f3043-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="f3043-109">L'articolo deve essere associato a un gruppo di dimensioni di immagazzinamento in cui sito e magazzino siano attivi.</span><span class="sxs-lookup"><span data-stu-id="f3043-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="f3043-110">Creare un'intestazione di giornale di registrazione arrivi articoli</span><span class="sxs-lookup"><span data-stu-id="f3043-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="f3043-111">Andare a Gestione articoli > Inserimenti nel giornale di registrazione > Arrivo articoli > Arrivo articoli.</span><span class="sxs-lookup"><span data-stu-id="f3043-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="f3043-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f3043-112">Click New.</span></span>
3. <span data-ttu-id="f3043-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f3043-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="f3043-114">Se si utilizza USMF, è possibile digitare WHS.</span><span class="sxs-lookup"><span data-stu-id="f3043-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="f3043-115">Se si utilizzano altri dati, il giornale di registrazione di cui è stato scelto il nome deve avere le proprietà Verifica ubicazione prelievo e Gestione quarantena impostate su No.</span><span class="sxs-lookup"><span data-stu-id="f3043-115">If you’re using other data, the journal whose name you choose has to have the following properties: cheque picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="f3043-116">Digitare un valore nel campo Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="f3043-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="f3043-117">Si tratta dell'ID del documento di trasporto rilasciato dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="f3043-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="f3043-118">Aggiungere un numero univoco.</span><span class="sxs-lookup"><span data-stu-id="f3043-118">Add a unique number.</span></span>  
5. <span data-ttu-id="f3043-119">Nel campo Numero selezionare l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="f3043-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="f3043-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f3043-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="f3043-121">Aggiungere righe a un giornale di registrazione arrivi articoli</span><span class="sxs-lookup"><span data-stu-id="f3043-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="f3043-122">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="f3043-122">Click Functions.</span></span>
2. <span data-ttu-id="f3043-123">Fare clic su Crea righe.</span><span class="sxs-lookup"><span data-stu-id="f3043-123">Click Create lines.</span></span>
    * <span data-ttu-id="f3043-124">Le righe possono essere immesse manualmente nel giornale di registrazione o essere create automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f3043-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="f3043-125">Verrà indicato come crearle automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f3043-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="f3043-126">Selezionare o deselezionare la casella di controllo Inizializza quantità.</span><span class="sxs-lookup"><span data-stu-id="f3043-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="f3043-127">In questo modo verrà inizializzata la quantità nelle righe del giornale di registrazione con la quantità non registrata dalla riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="f3043-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="f3043-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f3043-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="f3043-129">Registra il giornale</span><span class="sxs-lookup"><span data-stu-id="f3043-129">Post the journal</span></span>
1. <span data-ttu-id="f3043-130">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="f3043-130">Click Post.</span></span>
2. <span data-ttu-id="f3043-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f3043-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="f3043-132">Generare l'entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="f3043-132">Generate the product receipt</span></span>
1. <span data-ttu-id="f3043-133">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="f3043-133">Click Functions.</span></span>
2. <span data-ttu-id="f3043-134">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="f3043-134">Click Product receipt.</span></span>
3. <span data-ttu-id="f3043-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f3043-135">Click OK.</span></span>


