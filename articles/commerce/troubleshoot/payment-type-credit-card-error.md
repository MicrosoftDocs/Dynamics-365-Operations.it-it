---
title: Errore "Il tipo di pagamento deve essere una carta di credito" nella pagina dell'ordine cliente
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando viene visualizzato un messaggio di errore nella pagina dell'ordine cliente dopo la sincronizzazione di un ordine.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585394"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a><span data-ttu-id="cc6e8-103">Errore "Il tipo di pagamento deve essere una carta di credito" nella pagina dell'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="cc6e8-103">"Payment type must be credit card" error on the sales order page</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cc6e8-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando viene visualizzato un messaggio di errore nella pagina dell'ordine cliente dopo la sincronizzazione di un ordine.</span><span class="sxs-lookup"><span data-stu-id="cc6e8-104">This topic provides troubleshooting guidance that can help when an error message is shown on the sales order page after an order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="cc6e8-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc6e8-105">Description</span></span>

<span data-ttu-id="cc6e8-106">Quando si apre la pagina dell'ordine cliente dopo aver sincronizzato un ordine, viene visualizzato il seguente messaggio di errore: "Il tipo di pagamento deve essere una carta di credito poiché è stato specificato il numero di carta di credito".</span><span class="sxs-lookup"><span data-stu-id="cc6e8-106">When you open the sales order page after you sync an order, you receive the following error message: "The payment type must be credit card, since the credit card number has been specified."</span></span>

![Errore "Il tipo di pagamento deve essere una carta di credito"](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a><span data-ttu-id="cc6e8-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="cc6e8-108">Resolution</span></span>

### <a name="set-the-payment-type-in-commerce-headquarters"></a><span data-ttu-id="cc6e8-109">Impostare il tipo di pagamento in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="cc6e8-109">Set the payment type in Commerce headquarters</span></span>

1. <span data-ttu-id="cc6e8-110">Andare a **Contabilità clienti \> Impostazione pagamenti \> Condizioni di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="cc6e8-110">Go to **Accounts receivable \> Payment setup \> Terms of payment**.</span></span>
1. <span data-ttu-id="cc6e8-111">Nella barra di navigazione a sinistra, selezionare i termini di pagamento.</span><span class="sxs-lookup"><span data-stu-id="cc6e8-111">In the left navigation, select your terms of payment.</span></span>
1. <span data-ttu-id="cc6e8-112">Nel campo **Tipo di pagamento**, assicurarsi che **Carta di credito** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="cc6e8-112">In the **Payment type** field, make sure that **Credit card** is selected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cc6e8-113">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="cc6e8-113">Additional resources</span></span>

[<span data-ttu-id="cc6e8-114">Registrazione di vendite e pagamenti online</span><span class="sxs-lookup"><span data-stu-id="cc6e8-114">Posting of online sales and payments</span></span>](../tasks/posting-online-sales-payments.md)
