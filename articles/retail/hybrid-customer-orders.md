---
title: Ordini cliente ibridi
description: "Un ordine cliente ibrido è un ordine singolo che contiene prodotti che possono essere ritirati nel punto vendita dal cliente e prodotti che verranno ritirati o spediti in un secondo momento."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: a00e69a589ffe744f88edb6a8b3709c4029fc1ec
ms.contentlocale: it-it
ms.lasthandoff: 01/04/2019

---

# <a name="hybrid-customer-orders"></a><span data-ttu-id="f4b6b-103">Ordini cliente ibridi</span><span class="sxs-lookup"><span data-stu-id="f4b6b-103">Hybrid customer orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f4b6b-104">Un ordine cliente ibrido è un ordine singolo che contiene prodotti che possono essere ritirati nel punto vendita dal cliente e prodotti che verranno ritirati o spediti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-104">A hybrid customer order is a single order, which contains products that can be carried out of the store by the customer, as well as products that will be picked up or shipped later.</span></span>

<span data-ttu-id="f4b6b-105">In Microsoft Dynamics 365 for Retail, è possibile selezionare o trasportare tutti i prodotti o trasportare prodotti selezionati per un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-105">In Microsoft Dynamics 365 for Retail, you can select either carry out all products or carry out selected products for a customer order.</span></span> <span data-ttu-id="f4b6b-106">Le righe di prodotti contrassegnate come trasporto vengono fatturate automaticamente dopo la creazione dell'ordine, in modo analogo è lo stesso per un ordine che deve essere selezionato dopo che l'ordine è stato creato.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-106">The product lines that are marked as carry out are automatically invoiced after the order is created, similarly this is the same for an order that is to be picked-up after the order is created.</span></span> <span data-ttu-id="f4b6b-107">L'importo dovuto sugli ordini ibridi viene determinato sommando la percentuale di deposito nelle righe prelievo e spedizione di prodotti con l'importo totale delle righe di trasporto.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-107">The amount due on hybrid orders is determined by adding the deposit percentage on pick and ship product lines with the full amount of the carry out lines.</span></span> <span data-ttu-id="f4b6b-108">Per gli ordini ibridi, il sistema passa tra la modalità ordine cliente e la modalità cash-and-carry nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="f4b6b-108">For hybrid orders, the system switches between customer order mode and cash and carry mode as follows:</span></span>

- <span data-ttu-id="f4b6b-109">Se tutti i prodotti nel carrello vengono impostati sull'**esecuzione consegna**, l'ordine verrà trattato come transazione cash-and-carry.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-109">If all products in the cart are set to **Carry out delivery**, the order will be handled as a Cash and Carry transaction.</span></span>
- <span data-ttu-id="f4b6b-110">Se una o tutte le righe nel carrello vengono impostate su **Prelievo** o **spedizione consegna**, l'ordine verrà gestito come transazione ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-110">If any or all lines in the cart are set to either **Pick** or **ship delivery**, the order will be handled as a Customer order transaction.</span></span>

<span data-ttu-id="f4b6b-111">Se è selezionata una riga del carrello ed è selezionata l'opzione **Preleva selezionati**, **Spedizione selezionata** o **Esecuzione selezionata**, solo la riga del carrello specifica verrà impostata con quel metodo di consegna.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-111">If a cart line is selected and **Pick selected**, **Ship selected**, or **Carry out selected** is selected, only the specific cart line is set with that delivery method.</span></span> <span data-ttu-id="f4b6b-112">In tal caso, il flusso downstream dell'operazione continua normalmente.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-112">In that case, the downstream flow of the operation continues as usual.</span></span> <span data-ttu-id="f4b6b-113">Se invece l'opzione **Preleva selezionati**, **Spedizione selezionata** o **Esecuzione selezionata** è selezionata ma non è selezionata alcune riga del carrello, verrà visualizzata una nuova pagina con l'elenco di tutte le righe del carrello.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-113">However, if **Pick selected**, **Ship selected**, or **Carry out selected** is selected without a cart line being selected, a new page opens that lists all the cart lines.</span></span> <span data-ttu-id="f4b6b-114">In questa schermata è possibile selezionare più righe contemporaneamente per l'impostazione del metodo di consegna.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-114">On that screen, you can select multiple lines at once for setting the delivery method.</span></span> <span data-ttu-id="f4b6b-115">Quando si utilizza tale metodo per selezionare le righe, qualsiasi metodo di consegna precedente assegnato alla riga verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="f4b6b-115">When you use that method for selecting lines, any previous delivery method that has been assigned to the line will be overridden.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f4b6b-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f4b6b-116">Additional resources</span></span>

[<span data-ttu-id="f4b6b-117">Panoramica degli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="f4b6b-117">Customer orders overview</span></span>](customer-orders-overview.md)

