---
title: Risolvere i problemi relativi alle offerte di vendita
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 09529ba729170be7281e2ae04008d3ba4a58e060
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824752"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="85d76-103">Risolvere i problemi relativi alle offerte di vendita</span><span class="sxs-lookup"><span data-stu-id="85d76-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="85d76-104">Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.</span><span class="sxs-lookup"><span data-stu-id="85d76-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="85d76-105">Non riesco a modificare la quantità di vendita di un'offerta di vendita per un articolo di tipo Assistenza.</span><span class="sxs-lookup"><span data-stu-id="85d76-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="85d76-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="85d76-106">Issue description</span></span>

<span data-ttu-id="85d76-107">Se provi a impostare una quantità di vendita (campo **SalesQty**) per un elemento di tipo *Servizio*, in una riga dell'offerta di vendita, verrà visualizzato il seguente messaggio: "Aggiornamento non consentito per il campo Quantità".</span><span class="sxs-lookup"><span data-stu-id="85d76-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85d76-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="85d76-108">Issue resolution</span></span>

<span data-ttu-id="85d76-109">Non è possibile impostare una quantità di vendita per i prodotti che sono articoli di tipo Assistenza.</span><span class="sxs-lookup"><span data-stu-id="85d76-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="85d76-110">Ad esempio, se offri un servizio per installare un articolo, non ha senso registrare una quantità, perché non esiste un articolo fisico.</span><span class="sxs-lookup"><span data-stu-id="85d76-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="85d76-111">Esiste solo un servizio.</span><span class="sxs-lookup"><span data-stu-id="85d76-111">There is only a service.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]