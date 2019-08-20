---
title: Creare un metodo di assegnazione punteggi per RdO
description: Questa procedura indica come creare un metodo di assegnazione del punteggio.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6cbbc941b810cd8e5db5ba15a23dc6bd72a29506
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838072"
---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="3de49-103">Creare un metodo di assegnazione punteggi per RdO</span><span class="sxs-lookup"><span data-stu-id="3de49-103">Create a scoring method for RFQs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3de49-104">Questa procedura indica come creare un metodo di assegnazione del punteggio.</span><span class="sxs-lookup"><span data-stu-id="3de49-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="3de49-105">Un metodo di assegnazione del punteggio è un insieme dei criteri che possono essere usati per confrontare le offerte che sono inviate in risposta ad una richiesta di offerta (RdO).</span><span class="sxs-lookup"><span data-stu-id="3de49-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="3de49-106">Ad esempio, potrebbe essere utile valutare le prestazioni passate di un fornitore o valutare se la società rispetta le esigenze dell'ambiente o se è un buon collaboratore, oppure confrontare le offerte in base al prezzo.</span><span class="sxs-lookup"><span data-stu-id="3de49-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="3de49-107">Il metodo di assegnazione del punteggio può essere associato a un tipo di sollecito come metodo predefinito per le RdO di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="3de49-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="3de49-108">Queste attività verranno in genere svolte da un responsabile degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="3de49-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="3de49-109">È necessario impostare le classificazioni del contratto di acquisto prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="3de49-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="3de49-110">Andare ad Approvvigionamento > Impostazioni > Richiesta di offerta > Metodo di assegnazione del punteggio.</span><span class="sxs-lookup"><span data-stu-id="3de49-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="3de49-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3de49-111">Click New.</span></span>
3. <span data-ttu-id="3de49-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3de49-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="3de49-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3de49-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3de49-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3de49-114">Click Save.</span></span>
6. <span data-ttu-id="3de49-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3de49-115">Click New.</span></span>
7. <span data-ttu-id="3de49-116">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3de49-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="3de49-117">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3de49-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3de49-118">Questa descrizione è mostrata con il nome del metodo di assegnazione del punteggio quando un metodo viene selezionato per una RdO.</span><span class="sxs-lookup"><span data-stu-id="3de49-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="3de49-119">Nel campo Da immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3de49-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="3de49-120">L'intervallo limita che cosa l'addetto all'approvvigionamento può immettere come punteggio.</span><span class="sxs-lookup"><span data-stu-id="3de49-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="3de49-121">Quando ci sono più criteri di assegnazione del punteggio per una RdO, i punteggi inseriti si aggiungono l'un l'altro e la somma è messa a disposizione per permettere che le offerte siano confrontate.</span><span class="sxs-lookup"><span data-stu-id="3de49-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="3de49-122">Nel campo A immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3de49-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="3de49-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3de49-123">Click New.</span></span>
12. <span data-ttu-id="3de49-124">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3de49-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="3de49-125">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3de49-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="3de49-126">Nel campo Da immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3de49-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="3de49-127">Nel campo A immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3de49-127">In the Range to field, enter a number.</span></span>

