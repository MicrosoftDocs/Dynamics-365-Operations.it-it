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
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173087"
---
# <a name="integrated-tax"></a><span data-ttu-id="d2510-103">Imposta integrata</span><span class="sxs-lookup"><span data-stu-id="d2510-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d2510-104">I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="d2510-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="d2510-105">Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.</span><span class="sxs-lookup"><span data-stu-id="d2510-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="d2510-106">Modelli</span><span class="sxs-lookup"><span data-stu-id="d2510-106">Templates</span></span>

<span data-ttu-id="d2510-107">I dati fiscali includono una raccolta di mappe di entità che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="d2510-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="d2510-108">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d2510-108">Finance and Operations apps</span></span> | <span data-ttu-id="d2510-109">App basate su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d2510-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="d2510-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="d2510-110">Description</span></span> |
-------------------------|---------------------------------
<span data-ttu-id="d2510-111">Codici imposta</span><span class="sxs-lookup"><span data-stu-id="d2510-111">Tax codes</span></span>                   | <span data-ttu-id="d2510-112">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="d2510-112">msdyn\_taxcodes.md</span></span> | 
<span data-ttu-id="d2510-113">Gruppi di imposta</span><span class="sxs-lookup"><span data-stu-id="d2510-113">Tax groups</span></span>                 | <span data-ttu-id="d2510-114">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="d2510-114">msdyn\_taxgroups.md</span></span> | 
<span data-ttu-id="d2510-115">Gruppi di articoli imposta</span><span class="sxs-lookup"><span data-stu-id="d2510-115">Tax item groups</span></span>             | <span data-ttu-id="d2510-116">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="d2510-116">msdyn\_taxitemgroups.md</span></span> | 
<span data-ttu-id="d2510-117">Esenzioni fiscali</span><span class="sxs-lookup"><span data-stu-id="d2510-117">Tax Exemptions</span></span>             | <span data-ttu-id="d2510-118">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="d2510-118">msdyn\_taxexemptcodes.md</span></span> | 
<span data-ttu-id="d2510-119">Uffici tributari</span><span class="sxs-lookup"><span data-stu-id="d2510-119">Tax Authorities</span></span>             | <span data-ttu-id="d2510-120">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="d2510-120">msdyn\_taxauthorities.md</span></span> | 
<span data-ttu-id="d2510-121">Codici ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="d2510-121">Withholding tax codes</span></span>       | <span data-ttu-id="d2510-122">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="d2510-122">msdyn\_withholdingtaxcodes.md</span></span> | 
<span data-ttu-id="d2510-123">Gruppi ritenute d'acconto</span><span class="sxs-lookup"><span data-stu-id="d2510-123">Withholding tax groups</span></span>     | <span data-ttu-id="d2510-124">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="d2510-124">msdyn\_withholdingtaxgroups.md</span></span> | 
<span data-ttu-id="d2510-125">Gruppo di conti COGE imposta</span><span class="sxs-lookup"><span data-stu-id="d2510-125">Tax Ledger Account Group</span></span> | <span data-ttu-id="d2510-126">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="d2510-126">msdyn\_taxpostinggroups</span></span>     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

