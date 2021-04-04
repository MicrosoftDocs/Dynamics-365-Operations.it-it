---
title: I pagamenti vengono saldati automaticamente prima che gli ordini vengano fatturati o spediti
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un pagamento viene liquidato nel portale Adyen subito dopo che è stato effettuato un ordine, anche se l'ordine cliente non è stato fatturato o spedito.
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
ms.openlocfilehash: 788854a3119eb9ffaf839beb93a5bc15cdcd6387
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585393"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="ffa83-103">I pagamenti vengono saldati automaticamente prima che gli ordini vengano fatturati o spediti</span><span class="sxs-lookup"><span data-stu-id="ffa83-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ffa83-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un pagamento viene liquidato nel portale Adyen subito dopo che è stato effettuato un ordine, anche se l'ordine cliente non è stato fatturato o spedito.</span><span class="sxs-lookup"><span data-stu-id="ffa83-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="ffa83-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffa83-105">Description</span></span>

<span data-ttu-id="ffa83-106">Dopo l'esecuzione di un ordine, il pagamento viene liquidato immediatamente nel portale Adyen, anche se l'ordine cliente non è stato fatturato o spedito.</span><span class="sxs-lookup"><span data-stu-id="ffa83-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="ffa83-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="ffa83-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="ffa83-108">Configurare l'acquisizione manuale dei pagamenti e-commerce nel portale Adyen</span><span class="sxs-lookup"><span data-stu-id="ffa83-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="ffa83-109">Per configurare l'acquisizione manuale dei pagamenti e-commerce nel portale Adyen, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="ffa83-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="ffa83-110">Accedere al portale Adyen.</span><span class="sxs-lookup"><span data-stu-id="ffa83-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="ffa83-111">Nell'angolo in alto a destra, selezionare l'account esercente per il canale di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="ffa83-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="ffa83-112">Nella barra di spostamento superiore, selezionare **Account** e quindi seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="ffa83-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="ffa83-113">Nel campo **Ritardo acquisizione**, selezionare **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="ffa83-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Impostazione Ritardo acquisizione nel portale Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="ffa83-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ffa83-115">Additional resources</span></span>

[<span data-ttu-id="ffa83-116">Acquisizione di pagamenti Adyen</span><span class="sxs-lookup"><span data-stu-id="ffa83-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="ffa83-117">Connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="ffa83-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="ffa83-118">Impostare il connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="ffa83-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
