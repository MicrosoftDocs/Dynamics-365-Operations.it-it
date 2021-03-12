---
title: Creare un ordine di sostituzione articolo
description: Gli ordini di sostituzione articolo vengono in genere creati dopo la restituzione e l'ispezione di un prodotto.
author: josaw1
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0006ea9ec64cd95a709ec91509cb3a9828df160
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996653"
---
# <a name="create-an-item-replacement-order"></a><span data-ttu-id="2b2ef-103">Creare un ordine di sostituzione articolo</span><span class="sxs-lookup"><span data-stu-id="2b2ef-103">Create an item replacement order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2b2ef-104">Gli ordini di sostituzione articolo vengono in genere creati dopo la restituzione e l'ispezione di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-104">Item replacement orders are usually created after a product is returned and inspected.</span></span> <span data-ttu-id="2b2ef-105">Tuttavia, quando un articolo deve essere sostituito prima della restituzione, oppure quando un articolo non viene restituito, è possibile creare un ordine di sostituzione articolo immediatamente dopo la creazione di un ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-105">However, when an item must be replaced before it has been returned, or when the original item will not be returned, you can create an item replacement order immediately after you create a return order.</span></span>

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a><span data-ttu-id="2b2ef-106">Creare un ordine sostitutivo dopo che viene visualizzato un articolo che viene restituito</span><span class="sxs-lookup"><span data-stu-id="2b2ef-106">Create a replacement order after you receive an item that is returned</span></span>

1.  <span data-ttu-id="2b2ef-107">Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-107">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="2b2ef-108">Creare un nuovo ordine di reso o selezionare un ordine di reso dall'elenco per aprire il modulo **Ordine di reso - Codice NAR: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-108">Create a new return order, or select a returned order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="2b2ef-109">Fare clic su **Riga reso** quindi selezionare **Articolo sostitutivo**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-109">Click **Return line**, and then select **Replacement item**.</span></span>

4.  <span data-ttu-id="2b2ef-110">Selezionare l'articolo da sostituire con il reso.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-110">Select the item to replace the returned item with.</span></span> <span data-ttu-id="2b2ef-111">Immettere le specifiche dell'articolo e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-111">Enter the item specifications, and then click **Apply**.</span></span>

5.  <span data-ttu-id="2b2ef-112">Fare clic su **Documento di trasporto** per generare il documento di trasporto per l'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-112">Click **Packing slip** to generate the packing slip for the return order.</span></span> <span data-ttu-id="2b2ef-113">Un ordine cliente viene generato per un articolo sostitutivo selezionato.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-113">A sales order is generated for the replacement item that you selected.</span></span>
    
    <span data-ttu-id="2b2ef-114">Dopo che l'ordine cliente viene creato dell'articolo sostitutivo, i contratti di vendita vengono cercati automaticamente e se è presente un contratto di vendita applicabile, viene applicato all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-114">After the sales order is created for the replacement item, sales agreements are automatically searched and if there is an applicable sales agreement, it is applied to the sales order.</span></span>

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a><span data-ttu-id="2b2ef-115">Creare un ordine sostitutivo prima di ricevere un articolo che verrà restituito</span><span class="sxs-lookup"><span data-stu-id="2b2ef-115">Create a replacement order before you receive an item that will be returned</span></span>

1.  <span data-ttu-id="2b2ef-116">Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-116">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="2b2ef-117">Creare un nuovo ordine di reso o selezionare un ordine di reso dall'elenco per aprire il modulo **Ordine di reso - Codice NAR: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-117">Create a new return order, or select a return order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="2b2ef-118">Fare clic su **Trova ordine cliente** se si desidera identificare l'ordine cliente per il reso.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-118">Click **Find sales order** if you want to identify the sales order for the returned item.</span></span> <span data-ttu-id="2b2ef-119">Completare il modulo **Trova ordine cliente** quindi fare clic su **OK** per chiudere il modulo e tornare al modulo **Ordine di reso - Codice NAR: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-119">Complete the **Find sales order** form and then click **OK** to close the form and return to the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="2b2ef-120">La riga di ordine cliente per il reso viene copiata nell'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-120">The sales order line for the returned item is copied to the return order.</span></span>

4.  <span data-ttu-id="2b2ef-121">Fare clic su **Ordine sostitutivo** per aprire il modulo **Crea ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-121">Click **Replacement order** to open the **Create sales order** form.</span></span>

5.  <span data-ttu-id="2b2ef-122">Selezionare la casella di controllo **Copia righe ordine di reso** per trasferire i dettagli dall'ordine di reso selezionato nel modulo **Ordine di reso - Codice NAR: %1, %2** all'ordine cliente corrente.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-122">Select the **Copy return order lines** check box to transfer details from the return order you selected on the **Return order - RMA number: %1, %2** form to this sales order.</span></span>

6.  <span data-ttu-id="2b2ef-123">Immettere o modificare i dettagli, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-123">Enter or modify details, as required.</span></span>
    
    <span data-ttu-id="2b2ef-124">Se è stato identificato l'ordine cliente al passaggio 3 e se la riga ordine cliente per il reso è collegata a un contratto di vendita, l'identificatore del contratto di vendita applicabile per l'ordine di sostituzione articolo verrà automaticamente visualizzato nel campo **ID contratto di vendita**.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-124">If you identified the sales order in step 3, and if the sales order line for the returned item is linked to a sales agreement, the identifier of the applicable sales agreement for the item replacement order will be automatically displayed in the **Sales agreement ID** field.</span></span>

7.  <span data-ttu-id="2b2ef-125">Fare clic su **OK** per chiudere il modulo **Crea ordine cliente** e aprire il modulo **Ordine cliente**, in cui è possibile continuare a immettere le informazioni per il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-125">Click **OK** to close the **Create sales order** form and open the **Sales order** form, where you can continue to enter information for the new sales order.</span></span> <span data-ttu-id="2b2ef-126">Tutte le righe degli ordini di reso applicabili verranno copiate nel nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-126">Any applicable return order lines will be copied to the new sales order.</span></span> 
    
    <span data-ttu-id="2b2ef-127">Se l'identificatore del contratto di vendita viene visualizzato automaticamente nel campo **ID contratto di vendita**, il contratto di vendita è stato collegato all'intestazione ordine cliente dell'ordine di sostituzione articolo.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-127">If the identifier of the sales agreement is automatically displayed in the **Sales agreement ID** field, then the sales agreement has been linked to the sales order header for the item replacement order.</span></span> <span data-ttu-id="2b2ef-128">Se è presente un impegno applicabile nel contratto di vendita che non è stato ancora compiuto e l'ordine cliente viene creato prima della scadenza del contratto di vendita, viene stabilito un collegamento tra la riga contratto di vendita e la riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-128">If there is an applicable commitment in the sales agreement that has not been fulfilled yet, and the sales order is created before the sales agreement expires, a link is established between the sales agreement line and the sales order line.</span></span> <span data-ttu-id="2b2ef-129">Di conseguenza, le informazioni del contratto di vendita, ad esempio il prezzo dell'articolo, vengono copiate nella nuova riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2b2ef-129">Therefore, information from the sales agreement, such as item price, is copied to the new sales order line.</span></span> 
  


