---
title: La pagina di immissione della carta di credito visualizza un errore al momento del pagamento
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la sezione Metodo di pagamento non viene caricata e viene visualizzato un messaggio di errore.
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
ms.openlocfilehash: f0751fc76e6eb4320f766886b4c1efcb1042e996
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585388"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a><span data-ttu-id="12fc4-103">La pagina di immissione della carta di credito visualizza un errore al momento del pagamento</span><span class="sxs-lookup"><span data-stu-id="12fc4-103">Credit card entry page shows an error at checkout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12fc4-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la sezione **Metodo di pagamento** non viene caricata e viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="12fc4-104">This topic provides troubleshooting guidance that can help when the **Payment method** section isn't loaded and shows an error message.</span></span>

## <a name="description"></a><span data-ttu-id="12fc4-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12fc4-105">Description</span></span>

<span data-ttu-id="12fc4-106">Quando si apre la pagina di pagamento di un punto vendita online, la sezione **Metodo di pagamento** non viene caricata e viene visualizzato il seguente messaggio di errore: "Si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="12fc4-106">When you open the checkout page of an online store, the **Payment method** section isn't loaded, and the following error message is shown: "Something went wrong.</span></span> <span data-ttu-id="12fc4-107">Riprova più tardi."</span><span class="sxs-lookup"><span data-stu-id="12fc4-107">Please try again later."</span></span>

![Errore nel modulo di pagamento](media/payment-module-error.jpg)

## <a name="resolution"></a><span data-ttu-id="12fc4-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="12fc4-109">Resolution</span></span>

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a><span data-ttu-id="12fc4-110">Attendere che la cache di Commerce Scale Unit scada</span><span class="sxs-lookup"><span data-stu-id="12fc4-110">Wait for the Commerce Scale Unit cache to expire</span></span>

<span data-ttu-id="12fc4-111">Le impostazioni del servizio di pagamento nella pagina di pagamento del punto vendita online vengono memorizzate nella cache in Commerce Scale Unit e la loro visualizzazione sul sito di e-commerce può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="12fc4-111">The payment service settings on the online store's checkout page are cached on the Commerce Scale Unit and can take up to 15 minutes to appear on the e-commerce site.</span></span> <span data-ttu-id="12fc4-112">Queste impostazioni del servizio di pagamento includono modifiche all'ID account esercente, chiave API cloud e varie impostazioni di configurazione relative al metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="12fc4-112">These payment service settings include changes to the merchant account ID, cloud API key, and various configuration settings that are related to the payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="12fc4-113">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="12fc4-113">Additional resources</span></span>

[<span data-ttu-id="12fc4-114">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="12fc4-114">Set up an online channel</span></span>](../channel-setup-online.md)
