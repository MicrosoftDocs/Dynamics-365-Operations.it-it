---
title: Sottoporre a ispezione i resi
description: Sottoporre a ispezione i resi.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 82d94e055326e598113822b8d7c4852b7dcb0c4e
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---


# <a name="take-returned-items-through-inspection"></a><span data-ttu-id="43a9c-103">Sottoporre a ispezione i resi</span><span class="sxs-lookup"><span data-stu-id="43a9c-103">Take returned items through inspection</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="43a9c-104">Fare clic su **Gestione articoli** \> **Periodico** \> **Gestione qualità** \> **Ordini di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="43a9c-104">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="43a9c-105">Individuare la riga di ordine che corrisponde all'articolo di reso sottoposto a ispezione.</span><span class="sxs-lookup"><span data-stu-id="43a9c-105">Locate the order line that corresponds to the returned item that you are inspecting.</span></span>

    > [!NOTE]
    > <P><span data-ttu-id="43a9c-106">È possibile associare un ordine di quarantena a un solo numero articolo.</span><span class="sxs-lookup"><span data-stu-id="43a9c-106">A quarantine order can be associated with just a single item number.</span></span> <span data-ttu-id="43a9c-107">Se dieci articoli con numeri differenti vengono restituiti in un'unica spedizione e messi in quarantena, verranno creati dieci ordini di quarantena distinti.</span><span class="sxs-lookup"><span data-stu-id="43a9c-107">If 10 items that have different item numbers are returned in a single shipment and sent to quarantine, 10 individual quarantine orders are created.</span></span></P>

3.  <span data-ttu-id="43a9c-108">Una volta esaminato l'articolo, selezionare un valore nel campo **Codice smaltimento** per indicare le operazioni da eseguire relativamente all'articolo e la modalità di gestione delle transazioni finanziarie correlate.</span><span class="sxs-lookup"><span data-stu-id="43a9c-108">After examining the item, make a selection in the **Disposition code** field to indicate what should be done with the item and how to handle the related financial transaction.</span></span> <span data-ttu-id="43a9c-109">È ad esempio possibile specificare di restituire l'articolo al magazzino e rimborsare il cliente, scartare l'articolo e inviare al cliente un articolo sostitutivo oppure restituire l'articolo al cliente senza procedere a un accredito.</span><span class="sxs-lookup"><span data-stu-id="43a9c-109">Examples include returning the item to stock and refunding the customer, scrapping the item and sending a replacement to the customer, or returning the item to the customer without credit.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="43a9c-110">Se non è possibile assegnare lo stesso codice smaltimento a più articoli resi inclusi in un lotto, è necessario dividere l'ordine di quarantena (<STRONG>Funzioni</STRONG> &gt; <STRONG>Dividi</STRONG>) per assegnare un codice smaltimento diverso a ogni lotto secondario.</span><span class="sxs-lookup"><span data-stu-id="43a9c-110">If multiple returned items in a single item number batch cannot be assigned the same disposition code, you must split the quarantine order (<STRONG>Functions</STRONG> &gt; <STRONG>Split</STRONG>) to assign a different disposition code to each sub-batch.</span></span></P>


4.  <span data-ttu-id="43a9c-111">Al termine dell'ispezione, fare clic su **Dichiarazione di finito** per rilasciare gli articoli di reso e creare un inserimento nel giornale di registrazione arrivi articoli.</span><span class="sxs-lookup"><span data-stu-id="43a9c-111">When you are finished with the inspection, click **Report as finished** to release the returned items and create an item arrival journal entry.</span></span> <span data-ttu-id="43a9c-112">La persona o il reparto che riceverà gli articoli si occuperà di elaborare il giornale di registrazione in base agli articoli che devono essere restituiti al magazzino.</span><span class="sxs-lookup"><span data-stu-id="43a9c-112">The person or department that receives the items then processes the journal for the items to be returned to inventory.</span></span>
    
    <span data-ttu-id="43a9c-113">oppure</span><span class="sxs-lookup"><span data-stu-id="43a9c-113">–or–</span></span>
    
    <span data-ttu-id="43a9c-114">Terminare l'ordine di quarantena e inviare di nuovo gli articoli al magazzino utilizzando una delle funzioni **Scorte**.</span><span class="sxs-lookup"><span data-stu-id="43a9c-114">End the quarantine order, and move the items back into inventory directly by using one of the **Inventory** functions.</span></span>

5.  <span data-ttu-id="43a9c-115">Chiudere il modulo per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="43a9c-115">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="43a9c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43a9c-116">See also</span></span>

[<span data-ttu-id="43a9c-117">Specificare la modalità di smaltimento dei resi</span><span class="sxs-lookup"><span data-stu-id="43a9c-117">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

  



