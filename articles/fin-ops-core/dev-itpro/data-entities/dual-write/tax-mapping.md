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
ms.openlocfilehash: 0d32a5f7859f0200da823a73d94b9a6b2a9c8e7d
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019856"
---
# <a name="integrated-tax"></a><span data-ttu-id="7290d-103">Imposta integrata</span><span class="sxs-lookup"><span data-stu-id="7290d-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="7290d-104">I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="7290d-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="7290d-105">Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.</span><span class="sxs-lookup"><span data-stu-id="7290d-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="7290d-106">Modelli</span><span class="sxs-lookup"><span data-stu-id="7290d-106">Templates</span></span>

<span data-ttu-id="7290d-107">I dati fiscali includono una raccolta di mappe di entità che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="7290d-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="7290d-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7290d-108">Finance and Operations</span></span>   | <span data-ttu-id="7290d-109">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7290d-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="7290d-110">Codici imposta</span><span class="sxs-lookup"><span data-stu-id="7290d-110">Tax codes</span></span>                  | <span data-ttu-id="7290d-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="7290d-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="7290d-112">Gruppi di imposta</span><span class="sxs-lookup"><span data-stu-id="7290d-112">Tax groups</span></span>               | <span data-ttu-id="7290d-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="7290d-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="7290d-114">Gruppi di articoli imposta</span><span class="sxs-lookup"><span data-stu-id="7290d-114">Tax item groups</span></span>          | <span data-ttu-id="7290d-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="7290d-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="7290d-116">Esenzioni fiscali</span><span class="sxs-lookup"><span data-stu-id="7290d-116">Tax Exemptions</span></span>           | <span data-ttu-id="7290d-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="7290d-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="7290d-118">Uffici tributari</span><span class="sxs-lookup"><span data-stu-id="7290d-118">Tax Authorities</span></span>          | <span data-ttu-id="7290d-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="7290d-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="7290d-120">Codici ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="7290d-120">Withholding tax codes</span></span>      | <span data-ttu-id="7290d-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="7290d-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="7290d-122">Gruppi ritenute d'acconto</span><span class="sxs-lookup"><span data-stu-id="7290d-122">Withholding tax groups</span></span>   | <span data-ttu-id="7290d-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="7290d-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="7290d-124">Gruppo di conti COGE imposta</span><span class="sxs-lookup"><span data-stu-id="7290d-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="7290d-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="7290d-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]
