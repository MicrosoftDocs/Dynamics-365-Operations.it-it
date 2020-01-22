---
title: Imposta integrata
description: In questo argomento viene descritta l'integrazione dei dati fiscali tra Finance and Operations e Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 86e74086a5a74c7af5f2572d1a653a1658d729c0
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853861"
---
# <a name="integrated-tax"></a><span data-ttu-id="fb15b-103">Imposta integrata</span><span class="sxs-lookup"><span data-stu-id="fb15b-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb15b-104">I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="fb15b-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="fb15b-105">Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.</span><span class="sxs-lookup"><span data-stu-id="fb15b-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="fb15b-106">Modelli</span><span class="sxs-lookup"><span data-stu-id="fb15b-106">Templates</span></span>

<span data-ttu-id="fb15b-107">I dati fiscali includono una raccolta di mappe di entità che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="fb15b-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="fb15b-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fb15b-108">Finance and Operations</span></span>   | <span data-ttu-id="fb15b-109">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="fb15b-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="fb15b-110">Codici imposta</span><span class="sxs-lookup"><span data-stu-id="fb15b-110">Tax codes</span></span>                  | <span data-ttu-id="fb15b-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="fb15b-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="fb15b-112">Gruppi di imposta</span><span class="sxs-lookup"><span data-stu-id="fb15b-112">Tax groups</span></span>               | <span data-ttu-id="fb15b-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="fb15b-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="fb15b-114">Gruppi di articoli imposta</span><span class="sxs-lookup"><span data-stu-id="fb15b-114">Tax item groups</span></span>          | <span data-ttu-id="fb15b-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="fb15b-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="fb15b-116">Esenzioni fiscali</span><span class="sxs-lookup"><span data-stu-id="fb15b-116">Tax Exemptions</span></span>           | <span data-ttu-id="fb15b-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="fb15b-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="fb15b-118">Uffici tributari</span><span class="sxs-lookup"><span data-stu-id="fb15b-118">Tax Authorities</span></span>          | <span data-ttu-id="fb15b-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="fb15b-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="fb15b-120">Codici ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="fb15b-120">Withholding tax codes</span></span>      | <span data-ttu-id="fb15b-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="fb15b-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="fb15b-122">Gruppi ritenute d'acconto</span><span class="sxs-lookup"><span data-stu-id="fb15b-122">Withholding tax groups</span></span>   | <span data-ttu-id="fb15b-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="fb15b-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="fb15b-124">Gruppo di conti COGE imposta</span><span class="sxs-lookup"><span data-stu-id="fb15b-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="fb15b-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="fb15b-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

