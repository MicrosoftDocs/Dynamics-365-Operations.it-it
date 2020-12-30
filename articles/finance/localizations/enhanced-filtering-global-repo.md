---
title: Filtro avanzato RCS nel repository globale/RCS
description: Questo argomento descrive le funzionalità di filtro avanzate per il repository globale RCS, che sono state migliorate per includere i filtri aggiuntivi.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444659"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a><span data-ttu-id="f9f24-103">RCS ha migliorato le opzioni del filtro per trovare le configurazioni nel repository globale/RCS</span><span class="sxs-lookup"><span data-stu-id="f9f24-103">RCS enhanced filtering options for finding configurations in the RCS/Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9f24-104">Questo argomento descrive le funzionalità di filtro avanzate per il repository globale Regulatory Configuration Services (RCS), le quali sono state migliorate per includere la possibilità di filtrare con i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="f9f24-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the ability to filter with the following criteria:</span></span> 
- <span data-ttu-id="f9f24-105">**Paese/regione** - Basato sui codici ISO del paese</span><span class="sxs-lookup"><span data-stu-id="f9f24-105">**Country/region** - Based on ISO country codes</span></span>  
- <span data-ttu-id="f9f24-106">Tipi di **tag** per:</span><span class="sxs-lookup"><span data-stu-id="f9f24-106">**Tags** types for:</span></span>
  - <span data-ttu-id="f9f24-107">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="f9f24-107">Functional area</span></span>
  - <span data-ttu-id="f9f24-108">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="f9f24-108">Feature area</span></span>
  - <span data-ttu-id="f9f24-109">Settore</span><span class="sxs-lookup"><span data-stu-id="f9f24-109">Industry</span></span> 
  - <span data-ttu-id="f9f24-110">Documento aziendale</span><span class="sxs-lookup"><span data-stu-id="f9f24-110">Business document</span></span> 

<span data-ttu-id="f9f24-111">Per facilitare l'individuazione di configurazioni specifiche o correlate, è possibile applicare filtri, singolarmente o in gruppo.</span><span class="sxs-lookup"><span data-stu-id="f9f24-111">To make it easier to discover specific or related configurations you can apply filters, either individually or as a group.</span></span> <span data-ttu-id="f9f24-112">Ad esempio, per trovare un singolo tipo di documenti aziendali configurabili correlati alle fatture del fornitore, è possibile fare riferimento al filtro **Tipo di documento aziendale** per cercare il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="f9f24-112">For example, to find a single type of 'configurable business documents that are related to vendor invoices, you could apply a **Business document type** filter to search for that type of document.</span></span> 

<span data-ttu-id="f9f24-113">[![Sezione del filtro per il repository globale](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="f9f24-113">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="f9f24-114">È possibile affinare ulteriormente la ricerca selezionando il tipo di documento, ad esempio "fattura fornitore" e facendo clic sul tasto **Applica filtro**.</span><span class="sxs-lookup"><span data-stu-id="f9f24-114">You can further refine the search by selecting document type, for example 'vendor invoice' and clicking **Apply filter**.</span></span> <span data-ttu-id="f9f24-115">L'esempio seguente mostra i risultati quando il filtro è attivo in **Tipo di documento aziendale** con il tipo di documento aggiunto.</span><span class="sxs-lookup"><span data-stu-id="f9f24-115">The following example shows the results when filtering on **Business document type** with the document type added.</span></span> 

<span data-ttu-id="f9f24-116">[![Filtro applicato e importazione per tipo di documento aziendale](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="f9f24-116">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="f9f24-117">I risultati filtrati possono essere importati in un repository RCS dell'utente o in un ambiente Dynamics 365 Finance, singolarmente o come set.</span><span class="sxs-lookup"><span data-stu-id="f9f24-117">Filtered results can be imported into a users RCS repository or a Dynamics 365 Finance environment, either individually or as a set.</span></span> <span data-ttu-id="f9f24-118">A questo scopo, selezionare il gruppo di configurazioni e fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="f9f24-118">To do this, select the group of configurations, and click **Import**.</span></span>
