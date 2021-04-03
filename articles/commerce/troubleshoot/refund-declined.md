---
title: Il rimborso di un ordine di reso viene rifiutato
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.
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
ms.openlocfilehash: e202c6b4b9e025d5af1cd5eb6235884aab6444e6
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585399"
---
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="dbc80-103">Il rimborso di un ordine di reso viene rifiutato</span><span class="sxs-lookup"><span data-stu-id="dbc80-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dbc80-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.</span><span class="sxs-lookup"><span data-stu-id="dbc80-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="dbc80-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbc80-105">Description</span></span>

<span data-ttu-id="dbc80-106">Un rimborso viene rifiutato quando la carta di credito utilizzata per fatturare un ordine di reso è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.</span><span class="sxs-lookup"><span data-stu-id="dbc80-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="dbc80-107">Viene visualizzato il messaggio di errore seguente: "Lo stato di alcuni pagamenti non è corretto per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="dbc80-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="dbc80-108">Riconvalidare lo stato di tutti i pagamenti prima della fatturazione.".</span><span class="sxs-lookup"><span data-stu-id="dbc80-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="dbc80-109">I dettagli dell'autorizzazione di pagamento includeranno il seguente messaggio di errore: "SendRequest() gateway Adyen non riuscito con stato 'InternalServerError'.22144; risposta vuota restituita da Adyen. (22001);"</span><span class="sxs-lookup"><span data-stu-id="dbc80-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Rimborso di un ordine di reso rifiutato](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="dbc80-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="dbc80-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="dbc80-112">Abilitare resi senza ricevuta in Adyen</span><span class="sxs-lookup"><span data-stu-id="dbc80-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="dbc80-113">Per abilitare i resi senza ricevuta, seguire i passaggi in [Risoluzione dei problemi relativi al Connettore pagamenti di Dynamics 365 per Adyen](adyen-support.md) per contattare il team di supporto Adyen e richiedere che i resi senza ricevuta siano abilitati nell'account esercente Adyen.</span><span class="sxs-lookup"><span data-stu-id="dbc80-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dbc80-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dbc80-114">Additional resources</span></span>

[<span data-ttu-id="dbc80-115">Connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="dbc80-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="dbc80-116">Impostare il connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="dbc80-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
