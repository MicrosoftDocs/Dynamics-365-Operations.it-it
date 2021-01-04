---
title: Risolvere i problemi relativi alle offerte di vendita
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431103"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="45f88-103">Risolvere i problemi relativi alle offerte di vendita</span><span class="sxs-lookup"><span data-stu-id="45f88-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="45f88-104">Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.</span><span class="sxs-lookup"><span data-stu-id="45f88-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="45f88-105">Non riesco a modificare la quantità di vendita di un'offerta di vendita per un articolo di tipo Assistenza.</span><span class="sxs-lookup"><span data-stu-id="45f88-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="45f88-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="45f88-106">Issue description</span></span>

<span data-ttu-id="45f88-107">Se provi a impostare una quantità di vendita (campo **SalesQty**) per un elemento di tipo *Servizio*, in una riga dell'offerta di vendita, verrà visualizzato il seguente messaggio: "Aggiornamento non consentito per il campo Quantità".</span><span class="sxs-lookup"><span data-stu-id="45f88-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="45f88-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="45f88-108">Issue resolution</span></span>

<span data-ttu-id="45f88-109">Non è possibile impostare una quantità di vendita per i prodotti che sono articoli di tipo Assistenza.</span><span class="sxs-lookup"><span data-stu-id="45f88-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="45f88-110">Ad esempio, se offri un servizio per installare un articolo, non ha senso registrare una quantità, perché non esiste un articolo fisico.</span><span class="sxs-lookup"><span data-stu-id="45f88-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="45f88-111">Esiste solo un servizio.</span><span class="sxs-lookup"><span data-stu-id="45f88-111">There is only a service.</span></span>

