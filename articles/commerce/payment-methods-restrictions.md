---
title: Limitare i metodi di pagamento per i resi senza una ricevuta
description: In questo argomento viene descritto come determinati tipi di pagamento possono essere limitati per il rimborso se i resi vengono eseguiti senza una ricevuta.
author: rapraj
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: dfc49e3c3132fe2687ea71e5da75fe31753d57f9
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023098"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="7ccc1-103">Limitare i metodi di pagamento per i resi senza una ricevuta</span><span class="sxs-lookup"><span data-stu-id="7ccc1-103">Restrict payment methods for returns without a receipt</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7ccc1-104">Ogni tipo di pagamento accettato dal rivenditore deve essere configurato quando si imposta il sistema.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="7ccc1-105">In questo argomento viene descritto come determinati tipi di pagamento possono essere limitati per il rimborso se i resi vengono eseguiti senza una ricevuta.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="7ccc1-106">Impostare i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="7ccc1-106">Set up payment methods</span></span>

<span data-ttu-id="7ccc1-107">Per impostare i metodi di pagamento, è necessario completare le attività indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="7ccc1-108">Creare i metodi di pagamento accettati da tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="7ccc1-109">Creare tipi e numeri di carta a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="7ccc1-110">Se le carte di credito o di debito sono accettate, è necessario creare un metodo di pagamento per carte, quindi creare i tipi e i numeri di carta a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="7ccc1-111">Impostare metodi di pagamento per punti vendita.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-111">Set up store payment methods.</span></span> <span data-ttu-id="7ccc1-112">Associare i metodi di pagamento a ogni punto vendita, quindi immettere le impostazioni specifiche del punto vendita per ogni metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="7ccc1-113">Impostare metodi di pagamento con carta per punti vendita.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="7ccc1-114">Per qualsiasi metodo di pagamento con carta accettato dal punto vendita, è necessario completare l'impostazione della carta.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="7ccc1-115">![Impostazione archivio](media/NoReceiptReturns1.png "Impostazione punto vendita al dettaglio")</span><span class="sxs-lookup"><span data-stu-id="7ccc1-115">![Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="7ccc1-116">Limitare i metodi di pagamento per i resi senza una ricevuta</span><span class="sxs-lookup"><span data-stu-id="7ccc1-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="7ccc1-117">Per ogni metodo di pagamento per punto vendita, nella pagina **Gestione punto vendita**, in **Resi senza ricevuta**, impostare **Limitare per rimborsi senza ricevuta** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-117">For each store payment method, on the **Store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="7ccc1-118">Il valore predefinito è **No**, a indicare che il metodo di pagamento è consentito per i rimborsi.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="7ccc1-119">Quando l'opzione **Limitare per i rimborsi senza ricevuta** è impostata su **Sì**, il metodo di pagamento selezionato non sarà consentito per i rimborsi.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="7ccc1-120">![Metodo di pagamento punto vendita](media/NoReceiptReturns3.png "Metodo di pagamento punto vendita al dettaglio")</span><span class="sxs-lookup"><span data-stu-id="7ccc1-120">![Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="7ccc1-121">Quando un cassiere seleziona un metodo di pagamento che è limitato per il rimborso senza ricevuta, viene visualizzato un messaggio per verificare i metodi di pagamento accettabili.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="7ccc1-122">![Metodi di pagamento accettabili](media/NoReceiptReturns4.png "Metodi di pagamento accettabili")</span><span class="sxs-lookup"><span data-stu-id="7ccc1-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="7ccc1-123">Se una transazione ha un reso con ricevuta e un reso senza ricevuta, le condizioni di restrizione non verranno applicate perché la transazione sarà un flusso di lavoro di reso con una ricevuta.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 

