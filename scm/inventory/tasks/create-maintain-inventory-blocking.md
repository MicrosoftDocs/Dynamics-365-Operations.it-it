---
title: Creare e gestire un blocco scorte
description: Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte.
author: perlynne
manager: AnnBe
ms.date: 12/02/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 7272349cf16b9459823a752b8d3df915f42606ef
ms.contentlocale: it-it
ms.lasthandoff: 09/12/2017

---
# <a name="create-and-maintain-inventory-blocking"></a><span data-ttu-id="8e1b5-103">Creare e gestire un blocco scorte</span><span class="sxs-lookup"><span data-stu-id="8e1b5-103">Create and maintain inventory blocking</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e1b5-104">Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="8e1b5-105">È possibile eseguire la procedura utilizzando la società di dati dimostrativi USMF con i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="8e1b5-106">È necessario disporre di un articolo con scorte disponibili fisiche disponibili prima di iniziare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="8e1b5-107">Creare un blocco scorte</span><span class="sxs-lookup"><span data-stu-id="8e1b5-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="8e1b5-108">Andare a Gestione articoli > Attività periodiche > Blocco scorte.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-108">Go to Inventory management > Periodic tasks > Inventory blocking.</span></span>
2. <span data-ttu-id="8e1b5-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-109">Click New.</span></span>
3. <span data-ttu-id="8e1b5-110">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-110">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8e1b5-111">Selezionare dall'elenco l'articolo da scegliere.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-111">In the list, select the item you want to choose.</span></span>
    * <span data-ttu-id="8e1b5-112">Selezionare un numero di articolo con scorte fisiche disponibili che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="8e1b5-113">Se si utilizza USMF, è possibile selezionare l'articolo M9201.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-113">If you’re using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="8e1b5-114">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-114">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8e1b5-115">Se si utilizza l'articolo M9201, è necessario selezionare un valore inferiore a 200.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-115">If you’re using item M9201, you need to select less than 200.</span></span>  
6. <span data-ttu-id="8e1b5-116">Attivare/disattivare l'espansione della sezione Dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-116">Toggle the expansion of the Inventory dimensions section.</span></span>
7. <span data-ttu-id="8e1b5-117">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-117">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="8e1b5-118">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-118">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8e1b5-119">Se si utilizza l'articolo M9201, è possibile selezionare il magazzino 51.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-119">If you’re using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="8e1b5-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-120">Click Save.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="8e1b5-121">Aggiornare le condizioni del blocco scorte</span><span class="sxs-lookup"><span data-stu-id="8e1b5-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="8e1b5-122">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8e1b5-123">Aggiornare il campo quantità in magazzino in base alla quantità da bloccare.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="8e1b5-124">Nel campo Data prevista immettere una data.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-124">In the Expected date field, enter a date.</span></span>
    * <span data-ttu-id="8e1b5-125">Potrebbe essere utile indicare il momento in cui si prevede che le scorte bloccate diventino disponibili per la prenotazione assegnando una data prevista.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="8e1b5-126">Se l'opzione Entrate previste è selezionata per il blocco scorte, impostazione predefinita quando si crea manualmente un blocco, tale data verrà visualizzata sulla transazione prevista.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="8e1b5-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-127">Click Save.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="8e1b5-128">Rimuovere il blocco scorte</span><span class="sxs-lookup"><span data-stu-id="8e1b5-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="8e1b5-129">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-129">Click Delete.</span></span>
2. <span data-ttu-id="8e1b5-130">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-130">Click Yes.</span></span>
3. <span data-ttu-id="8e1b5-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-131">Close the page.</span></span>
