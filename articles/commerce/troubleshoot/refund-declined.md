---
title: Il rimborso di un ordine di reso viene rifiutato
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.
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
ms.openlocfilehash: 99fd4b816b1a3a1fe3c2d1579be45b43fdc3d385
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020758"
---
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="24c52-103">Il rimborso di un ordine di reso viene rifiutato</span><span class="sxs-lookup"><span data-stu-id="24c52-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="24c52-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.</span><span class="sxs-lookup"><span data-stu-id="24c52-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="24c52-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24c52-105">Description</span></span>

<span data-ttu-id="24c52-106">Un rimborso viene rifiutato quando la carta di credito utilizzata per fatturare un ordine di reso è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.</span><span class="sxs-lookup"><span data-stu-id="24c52-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="24c52-107">Viene visualizzato il messaggio di errore seguente: "Lo stato di alcuni pagamenti non è corretto per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="24c52-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="24c52-108">Riconvalidare lo stato di tutti i pagamenti prima della fatturazione.".</span><span class="sxs-lookup"><span data-stu-id="24c52-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="24c52-109">I dettagli dell'autorizzazione di pagamento includeranno il seguente messaggio di errore: "SendRequest() gateway Adyen non riuscito con stato 'InternalServerError'.22144; risposta vuota restituita da Adyen. (22001);"</span><span class="sxs-lookup"><span data-stu-id="24c52-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Rimborso di un ordine di reso rifiutato](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="24c52-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="24c52-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="24c52-112">Abilitare resi senza ricevuta in Adyen</span><span class="sxs-lookup"><span data-stu-id="24c52-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="24c52-113">Per abilitare i resi senza ricevuta, seguire i passaggi in [Risoluzione dei problemi relativi al Connettore pagamenti di Dynamics 365 per Adyen](adyen-support.md) per contattare il team di supporto Adyen e richiedere che i resi senza ricevuta siano abilitati nell'account esercente Adyen.</span><span class="sxs-lookup"><span data-stu-id="24c52-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="24c52-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="24c52-114">Additional resources</span></span>

[<span data-ttu-id="24c52-115">Connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="24c52-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="24c52-116">Impostare il connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="24c52-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
