---
title: Errore di sincronizzazione dell'ordine relativo al servizio di pagamento predefinito
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono aiutare a correggere un errore che potrebbe verificarsi quando viene sincronizzato un ordine online.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: fa174bbb257379f6ce906dd21180bbcb19f8bc3f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021129"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="8045e-103">Errore di sincronizzazione dell'ordine relativo al servizio di pagamento predefinito</span><span class="sxs-lookup"><span data-stu-id="8045e-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8045e-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono aiutare a correggere un errore che potrebbe verificarsi quando viene sincronizzato un ordine online.</span><span class="sxs-lookup"><span data-stu-id="8045e-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="8045e-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8045e-105">Description</span></span>

<span data-ttu-id="8045e-106">Quando si sincronizza un ordine online, viene visualizzato il seguente messaggio di errore: "Deve essere presente un servizio di pagamento predefinito per elaborare le transazioni con carta di credito".</span><span class="sxs-lookup"><span data-stu-id="8045e-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Errore dovuto al servizio di pagamento predefinito mancante](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="8045e-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="8045e-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="8045e-109">Confermare o impostare il servizio di pagamento predefinito in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="8045e-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="8045e-110">Per confermare o impostare il servizio di pagamento predefinito in Commerce Headquarters, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="8045e-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8045e-111">Selezionare **Contabilità clienti \> Impostazione pagamenti \> Servizi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="8045e-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="8045e-112">Assicurarsi che l'opzione **Processore predefinito per nuove carte di credito** è impostata su **Sì** per un servizio di pagamento.</span><span class="sxs-lookup"><span data-stu-id="8045e-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8045e-113">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8045e-113">Additional resources</span></span>

[<span data-ttu-id="8045e-114">Impostazione, autorizzazione e acquisizione della carta di credito</span><span class="sxs-lookup"><span data-stu-id="8045e-114">Credit card setup, authorization, and capture</span></span>](../../finance/accounts-receivable/credit-card-authorizations.md)