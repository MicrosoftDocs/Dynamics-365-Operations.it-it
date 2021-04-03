---
title: L'opzione Salva per prossimo pagamento non viene visualizzata
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la casella di controllo Salva per prossimo pagamento non viene visualizzata in Metodo di pagamento nella pagina di pagamento di un sito di e-commerce.
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
ms.openlocfilehash: 3a4fbcd522651ed1b82b72b751ff6ead44c94a71
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585395"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="45716-103">L'opzione "Salva per prossimo pagamento" non viene visualizzata</span><span class="sxs-lookup"><span data-stu-id="45716-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45716-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la casella di controllo **Salva per prossimo pagamento** non viene visualizzata in **Metodo di pagamento** nella pagina di pagamento di un sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="45716-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="45716-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45716-105">Description</span></span>

<span data-ttu-id="45716-106">La casella di controllo **Salva per prossimo pagamento** non viene visualizzata nella sezione **Metodo di pagamento** della pagina di pagamento di un sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="45716-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="45716-107">La figura seguente mostra un esempio di una pagina di pagamento che include la casella di controllo **Salva per prossimo pagamento**.</span><span class="sxs-lookup"><span data-stu-id="45716-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Casella di controllo Salva per prossimo pagamento nel modulo Pagamento](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="45716-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="45716-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="45716-110">Verificare che il Connettore pagamenti di Dynamics 365 per Adyen sia configurato correttamente in Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="45716-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="45716-111">Per verificare che il Connettore pagamenti di Dynamics 365 per Adyen sia configurato correttamente in Commerce Headquarters, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="45716-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="45716-112">Andare a **Retail e Commerce \> Canali \> Punti vendita online**.</span><span class="sxs-lookup"><span data-stu-id="45716-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="45716-113">Selezionare il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="45716-113">Select the online store.</span></span>
1. <span data-ttu-id="45716-114">Nella Scheda dettaglio **Conti pagamento**, assicurarsi che il campo **Consenti salvataggio informazioni di pagamento in e-commerce** sia impostato su **True**.</span><span class="sxs-lookup"><span data-stu-id="45716-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Campo Consenti salvataggio informazioni di pagamento in e-commerce di Commerce Headquarters](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="45716-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="45716-116">Additional resources</span></span>

[<span data-ttu-id="45716-117">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="45716-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="45716-118">Salvare gli strumenti di pagamento online con il connettore Adyen</span><span class="sxs-lookup"><span data-stu-id="45716-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
