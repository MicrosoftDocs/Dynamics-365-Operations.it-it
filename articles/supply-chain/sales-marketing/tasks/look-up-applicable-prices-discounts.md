---
title: Cercare i prezzi e gli sconti applicabili
description: Questa procedura illustra come trovare il prezzo e/o lo sconto per un prodotto che è attualmente valido per un cliente specifico, senza creare un ordine cliente.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9bd85d9cd2d7273ad6e05d794a96e4d6a8d7c526
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010774"
---
# <a name="look-up-applicable-prices-and-discounts"></a><span data-ttu-id="3e478-103">Cercare i prezzi e gli sconti applicabili</span><span class="sxs-lookup"><span data-stu-id="3e478-103">Look up applicable prices and discounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3e478-104">Questa procedura illustra come trovare il prezzo e/o lo sconto per un prodotto che è attualmente valido per un cliente specifico, senza creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3e478-104">This procedure shows how to find the price and/or discount for a product which is currently valid for a specific customer, without creating a sales order.</span></span> <span data-ttu-id="3e478-105">La procedura viene eseguita tramite un esempio specifico che è necessario seguire utilizzando la società dimostrativa USMF per selezionare i valori necessari.</span><span class="sxs-lookup"><span data-stu-id="3e478-105">The procedure walks through a specific example, and you need follow the example using the USMF demo company in order to select the necessary values.</span></span>


## <a name="find-the-applicable-price"></a><span data-ttu-id="3e478-106">Individuare il prezzo applicabile</span><span class="sxs-lookup"><span data-stu-id="3e478-106">Find the applicable price</span></span>
1. <span data-ttu-id="3e478-107">Andare a Vendite e marketing > Prezzi e sconti > Trova prezzi.</span><span class="sxs-lookup"><span data-stu-id="3e478-107">Go to Sales and marketing > Prices and discounts > Find prices.</span></span>
2. <span data-ttu-id="3e478-108">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3e478-108">In the Customer account field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="3e478-109">Trovare e selezionare il record cliente US-001.</span><span class="sxs-lookup"><span data-stu-id="3e478-109">In the list, find and select customer US-001.</span></span>
4. <span data-ttu-id="3e478-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3e478-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="3e478-111">Nel campo Numero articolo digitare "T0004".</span><span class="sxs-lookup"><span data-stu-id="3e478-111">In the Item number field, type 'T0004'.</span></span>
    * <span data-ttu-id="3e478-112">Per impostazione predefinita, il campo Quantità è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="3e478-112">By default, the Quantity field is set to 1.</span></span> <span data-ttu-id="3e478-113">Tuttavia, se si conosce la dimensione dell'ordine che il cliente intende effettuare per il prodotto, immettere tale valore.</span><span class="sxs-lookup"><span data-stu-id="3e478-113">However, if you know the size of the order that the customer intends to place for the product in question, then enter this value instead.</span></span> <span data-ttu-id="3e478-114">Queste informazioni sono rilevanti se per gli accordi commerciali con il cliente sono presenti intervalli di quantità, ovvero se il prezzo del prodotto dipende dalla quantità minima acquistata.</span><span class="sxs-lookup"><span data-stu-id="3e478-114">This information is relevant if the trade agreements with the customer have quantity breaks, that is, the product's price depends on the minimum quantity purchased.</span></span>  
6. <span data-ttu-id="3e478-115">Nel campo Data immettere una data in cui si prevede che il cliente effettui un ordine.</span><span class="sxs-lookup"><span data-stu-id="3e478-115">In the Date field, enter a date for when the customer expects to place an order.</span></span> 
    * <span data-ttu-id="3e478-116">La data può essere quella odierna o una qualsiasi data nel futuro.</span><span class="sxs-lookup"><span data-stu-id="3e478-116">The date can be today's date or any date in the future.</span></span>  
    * <span data-ttu-id="3e478-117">Il sistema ora restituisce il prezzo valido per il prodotto selezionato una volta acquistato dal cliente selezionato nella data indicata con una quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="3e478-117">The system now returns the price that is valid for the selected product when bought by the selected customer on the selected date with a specified quantity.</span></span> <span data-ttu-id="3e478-118">In questo esempio, se il cliente US-001 acquista oggi un'unità di prodotto T0004, vengono addebitati 350 EUR per unità.</span><span class="sxs-lookup"><span data-stu-id="3e478-118">In this example, if the customer US-001 bought 1 unit of product T0004 today, they would be charged 350 CAD a unit.</span></span> <span data-ttu-id="3e478-119">Il prezzo viene ricavato da un accordo commerciale con il cliente esistente e attivo.</span><span class="sxs-lookup"><span data-stu-id="3e478-119">This price comes from an existing and active trade agreement with the customer.</span></span>      <span data-ttu-id="3e478-120">Altri campi nella pagina forniscono ulteriori dettagli sul prezzo e sul costo del prodotto (se impostati nella rappresentazione generale prodotto) e sulla redditività calcolata.</span><span class="sxs-lookup"><span data-stu-id="3e478-120">Other fields on the page provide more details about the product price and product cost (if set up on the product master), and calculated profitability.</span></span>  
    * <span data-ttu-id="3e478-121">Se l'opzione Mostra varianti prodotti correlate è selezionata, significa che sono presenti accordi commerciali aggiuntivi per le varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="3e478-121">If the Show related product variants option is selected, it means that there are additional trade agreements for product's variants.</span></span>  
7. <span data-ttu-id="3e478-122">Selezionare la casella di controllo Mostra varianti prodotti correlate.</span><span class="sxs-lookup"><span data-stu-id="3e478-122">Click the Show related product variants checkbox.</span></span>
    * <span data-ttu-id="3e478-123">Un elenco di varianti prodotto viene visualizzato, con informazioni sulle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="3e478-123">A list of the product variants is shown, with information about their dimensions.</span></span>  
8. <span data-ttu-id="3e478-124">Nell'elenco, contrassegnare la riga che rappresenta il colore bianco.</span><span class="sxs-lookup"><span data-stu-id="3e478-124">In the list, mark the line representing color White.</span></span>
    * <span data-ttu-id="3e478-125">Si noti che il prezzo del prodotto ora è diverso da quello visualizzato in precedenza quando non era specificato per dimensione.</span><span class="sxs-lookup"><span data-stu-id="3e478-125">Notice, that the product price is now different from the one displayed previously when it was not specified per dimension.</span></span>  
9. <span data-ttu-id="3e478-126">Fare clic su Visualizza prezzi di vendita.</span><span class="sxs-lookup"><span data-stu-id="3e478-126">Click View sales prices.</span></span>
    * <span data-ttu-id="3e478-127">Nella pagina Prezzo (vend.) vengono visualizzati tutti gli accordi commerciali applicabili al prodotto, incluse le varianti.</span><span class="sxs-lookup"><span data-stu-id="3e478-127">The Price (sales) page displays all the trade agreements applicable to the product, including its variants.</span></span>  
10. <span data-ttu-id="3e478-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3e478-128">Close the page.</span></span>

## <a name="find-the-applicable-discount"></a><span data-ttu-id="3e478-129">Individuare lo sconto applicabile</span><span class="sxs-lookup"><span data-stu-id="3e478-129">Find the applicable discount</span></span>
<span data-ttu-id="3e478-130">Verificare che il campo del conto cliente contenga il numero cliente US-001 </span><span class="sxs-lookup"><span data-stu-id="3e478-130">Make sure the Customer account field contains customer number US-001</span></span>   
1. <span data-ttu-id="3e478-131">Nel campo Numero articolo digitare "T0012".</span><span class="sxs-lookup"><span data-stu-id="3e478-131">In the Item number field, type 'T0012'.</span></span>
    * <span data-ttu-id="3e478-132">Assicurarsi che il campo Quantità sia impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="3e478-132">Make sure the Quantity field is set to 1.</span></span>  
    * <span data-ttu-id="3e478-133">I seguenti dettagli di prezzo visualizzati per il prodotto T0012 derivano da uno o più accordi commerciali. Il prezzo unitario è di 1.000 EUR e la percentuale di sconto è 5.</span><span class="sxs-lookup"><span data-stu-id="3e478-133">The following pricing details shown for product T0012 come from one or more trade agreements: The unit price is 1,000 CAD and the discount percentage is 5.</span></span>  
2. <span data-ttu-id="3e478-134">Impostare la quantità su "20".</span><span class="sxs-lookup"><span data-stu-id="3e478-134">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="3e478-135">Le quantità ordine aumentata determina la modifica dello sconto riga che verrà offerto da 5 a 7.</span><span class="sxs-lookup"><span data-stu-id="3e478-135">The increased order quantity causes the line discount that will be offered to the customer to change from 5 to 7 percent.</span></span>  
    * <span data-ttu-id="3e478-136">L'importo netto viene calcolato in base al prezzo unitario, allo sconto e alla quantità totale.</span><span class="sxs-lookup"><span data-stu-id="3e478-136">The Net amount is calculated based on the unit price, discount and the total quantity.</span></span>  
3. <span data-ttu-id="3e478-137">Fare clic su Visualizza sconto riga.</span><span class="sxs-lookup"><span data-stu-id="3e478-137">Click View line discount.</span></span>
    * <span data-ttu-id="3e478-138">Sono disponibili due accordi sugli sconti riga per il prodotto T0012, che specificano uno sconto del 5% per una quantità della riga ordine da 1 a 10 e del 7% per le quantità ordine superiori a 10.</span><span class="sxs-lookup"><span data-stu-id="3e478-138">There are two line discount agreements for product T0012, specifying a 5 percent discount for an order line quantity from 1 to 10, and 7 percent discount for order quantities above 10.</span></span> <span data-ttu-id="3e478-139">Si noti che gli sconti vengono applicati a un gruppo di prodotti, in questo esempio al gruppo con codice 01, a cui il prodotto T0012 appartiene.</span><span class="sxs-lookup"><span data-stu-id="3e478-139">Note that the discounts are applied to a group of products, in this example, Group code 01, of which product T0012 is a member.</span></span>  
4. <span data-ttu-id="3e478-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3e478-140">Close the page.</span></span>

