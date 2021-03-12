---
title: Ammortamento cespiti
description: In questo argomento viene fornita una panoramica dell'ammortamento dei cespiti.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b399ab3df9bddbce8b96752ef344bf93cb2563c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969105"
---
# <a name="fixed-asset-depreciation"></a><span data-ttu-id="baa49-103">Ammortamento cespiti</span><span class="sxs-lookup"><span data-stu-id="baa49-103">Fixed asset depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="baa49-104">In questo argomento viene fornita una panoramica dell'ammortamento dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="baa49-104">This topic provides an overview of depreciation for fixed assets.</span></span>

<span data-ttu-id="baa49-105">Per ammortamento si intende una transazione periodica che di solito determina una riduzione del valore dei cespiti nello stato patrimoniale e viene addebitata come spesa in un conto profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="baa49-105">Depreciation is a periodic transaction that typically reduces the value of the fixed asset on the balance sheet, and is charged as an expenditure to a profit and loss account.</span></span> <span data-ttu-id="baa49-106">Di conseguenza, per l'accredito dell'ammortamento periodico nello stato patrimoniale viene in genere utilizzato un conto principale.</span><span class="sxs-lookup"><span data-stu-id="baa49-106">Therefore, a main account is typically used to credit the periodic depreciation on the balance sheet.</span></span> <span data-ttu-id="baa49-107">Un conto di contropartita è un conto nella parte profitti e perdite del piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="baa49-107">An offset account is an account in the profit and loss part of the chart of accounts.</span></span>

## <a name="depreciation-adjustment"></a><span data-ttu-id="baa49-108">Rettifica dell'ammortamento</span><span class="sxs-lookup"><span data-stu-id="baa49-108">Depreciation adjustment</span></span>
<span data-ttu-id="baa49-109">In genere, viene registrata come rettifica dell'ammortamento solo una correzione apportata a una transazione di ammortamento già registrata.</span><span class="sxs-lookup"><span data-stu-id="baa49-109">Usually, only a correction to a posted depreciation transaction is posted as a depreciation adjustment.</span></span> <span data-ttu-id="baa49-110">Di conseguenza, sia il conto principale che il conto di contropartita vengono impostati analogamente ai conti per l'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="baa49-110">Therefore, both the main account and the offset account are set up just like the accounts for depreciation.</span></span> <span data-ttu-id="baa49-111">Una rettifica dell'ammortamento può essere costituita da un importo positivo o negativo, ma la funzionalità del conto principale (come conto dello stato patrimoniale) e del conto di contropartita (solitamente come conto profitti e perdite) rimane la stessa.</span><span class="sxs-lookup"><span data-stu-id="baa49-111">A depreciation adjustment can be either a positive amount or a negative amount, but the functionality of the main account (as a balance sheet account) and the functionality of the offset account (usually as a profit and loss account) remain the same.</span></span>

## <a name="extraordinary-depreciation"></a><span data-ttu-id="baa49-112">Ammort. straordinario</span><span class="sxs-lookup"><span data-stu-id="baa49-112">Extraordinary depreciation</span></span>
<span data-ttu-id="baa49-113">L'ammortamento straordinario funziona come l'ammortamento normale.</span><span class="sxs-lookup"><span data-stu-id="baa49-113">Extraordinary depreciation works like basic depreciation.</span></span> <span data-ttu-id="baa49-114">Di conseguenza, un conto principale viene utilizzato per accreditare l'importo di ammortamento nello stato patrimoniale e ridurre il valore del cespite.</span><span class="sxs-lookup"><span data-stu-id="baa49-114">Therefore, a main account is used to credit the depreciation amount to the balance sheet and reduce the value of the fixed asset.</span></span> <span data-ttu-id="baa49-115">Un conto di contropartita è un conto profitti e perdite, in cui l'ammortamento calcolato per il periodo fiscale viene addebitato come spesa.</span><span class="sxs-lookup"><span data-stu-id="baa49-115">An offset account is a profit and loss account, where the depreciation that is calculated for the fiscal period is charged as an expenditure.</span></span> 

<span data-ttu-id="baa49-116">L'ammortamento straordinario è indipendente dall'ammortamento normale.</span><span class="sxs-lookup"><span data-stu-id="baa49-116">Extraordinary depreciation works independently of basic depreciation.</span></span> <span data-ttu-id="baa49-117">Poiché è considerato un tipo di transazione separato, è possibile registrarlo e dichiararlo in modo distinto dall'ammortamento normale.</span><span class="sxs-lookup"><span data-stu-id="baa49-117">By having extraordinary depreciation as a separate transaction type, you can post and report the extraordinary depreciation separately from the basic depreciation.</span></span>

## <a name="special-depreciation-allowance"></a><span data-ttu-id="baa49-118">Fondo di ammortamento speciale</span><span class="sxs-lookup"><span data-stu-id="baa49-118">Special depreciation allowance</span></span>
<span data-ttu-id="baa49-119">I fondi di ammortamento speciale consentono di applicare importi di ammortamento aggiuntivi durante il primo anno in cui un cespite viene messo in servizio e ammortizzato.</span><span class="sxs-lookup"><span data-stu-id="baa49-119">You can use special depreciation allowances to take extra depreciation amounts during the first year that an asset is put in service and depreciated.</span></span> <span data-ttu-id="baa49-120">I fondi di ammortamento speciale devono essere applicati prima di qualsiasi altro calcolo dell'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="baa49-120">Special depreciation allowances must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="baa49-121">Poiché i fondi di ammortamento speciale sono spesso sconosciuti fino a una fase successiva nella vita utile del cespite, è preferibile utilizzare questo tipo di ammortamento con un libro che non viene registrato nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="baa49-121">Because special depreciation allowances are often unknown until later in the service life of the fixed asset, it's best to use this type of depreciation with a book that doesn't post to the general ledger.</span></span> <span data-ttu-id="baa49-122">È possibile utilizzare la funzione periodica Elimina transazioni non registrate nella contabilità generale per eliminare lo storico transazioni per questi libri.</span><span class="sxs-lookup"><span data-stu-id="baa49-122">You can use the Delete transactions not posted to general ledger periodic function to delete the transaction history for these books.</span></span> <span data-ttu-id="baa49-123">È quindi possibile eliminare lo storico di ammortamento per il libro cespiti, registrare il fondo di ammortamento speciale quando è noto e quindi registrare le transazioni di ammortamento rimanenti per l'anno.</span><span class="sxs-lookup"><span data-stu-id="baa49-123">You can then delete the depreciation history for the fixed asset book, post the special depreciation allowance when it's known, and then post the remaining depreciation transactions for the year.</span></span> 

<span data-ttu-id="baa49-124">È possibile creare un numero illimitato di record di fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="baa49-124">You can create an unlimited number of special depreciation allowance records.</span></span> <span data-ttu-id="baa49-125">Una volta assegnati tali record a un libro gruppo cespite, questi record vengono applicati al libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="baa49-125">After you assign those records to an asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="baa49-126">Un fondo di ammortamento speciale viene immesso sotto forma di percentuale o di importo fisso.</span><span class="sxs-lookup"><span data-stu-id="baa49-126">A special depreciation allowance is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="baa49-127">Quando si registrano le proposte di ammortamento, le transazioni relative a questo tipo di ammortamento vengono registrate nel libro come transazioni distinte dalle altre.</span><span class="sxs-lookup"><span data-stu-id="baa49-127">When you post depreciation proposals, special depreciation allowance transactions are posted to the book as transactions that are separate from the depreciation transactions.</span></span>

## <a name="depreciation-calendars"></a><span data-ttu-id="baa49-128">Calendari di ammortamento</span><span class="sxs-lookup"><span data-stu-id="baa49-128">Depreciation calendars</span></span>
<span data-ttu-id="baa49-129">Ciascun libro è associato a un calendario utilizzato per l'ammortamento dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="baa49-129">Each book has a calendar that is used when you depreciate fixed assets.</span></span> <span data-ttu-id="baa49-130">Il libro utilizzerà il calendario fiscale per la contabilità generale per impostazione predefinita se non si specifica un calendario per il libro.</span><span class="sxs-lookup"><span data-stu-id="baa49-130">By default, if you don't indicate a calendar on the book, the book uses the ledger fiscal calendar.</span></span> <span data-ttu-id="baa49-131">È necessario selezionare un calendario fiscale per un libro quando il profilo di ammortamento associato al libro utilizza un anno fiscale di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="baa49-131">You must select a fiscal calendar for a book when the depreciation profile that is associated with the book uses a fiscal depreciation year.</span></span> 

<span data-ttu-id="baa49-132">È possibile creare calendari condivisi utilizzando la pagina **Calendari fiscali** nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="baa49-132">You can create shared calendars by using the **Fiscal calendars** page in General ledger.</span></span>

<span data-ttu-id="baa49-133">Per ulteriori informazioni, vedere [Metodi e convenzioni di ammortamento](depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="baa49-133">For more information, see [Depreciation methods and conventions](depreciation-methods-conventions.md).</span></span>



