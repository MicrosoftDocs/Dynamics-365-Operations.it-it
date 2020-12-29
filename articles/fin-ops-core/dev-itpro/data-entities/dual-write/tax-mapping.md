---
title: Imposta integrata
description: In questo argomento viene descritta l'integrazione dei dati fiscali tra Finance and Operations e Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 14c22dd6602b5fbf866c8dc6b057f6c8acb1f48f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679298"
---
# <a name="integrated-tax"></a><span data-ttu-id="d0dd1-103">Imposta integrata</span><span class="sxs-lookup"><span data-stu-id="d0dd1-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="d0dd1-104">I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="d0dd1-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="d0dd1-105">Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.</span><span class="sxs-lookup"><span data-stu-id="d0dd1-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="d0dd1-106">Modelli</span><span class="sxs-lookup"><span data-stu-id="d0dd1-106">Templates</span></span>

<span data-ttu-id="d0dd1-107">I dati fiscali includono una raccolta di mappe della tabella che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="d0dd1-107">Tax data includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="d0dd1-108">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d0dd1-108">Finance and Operations apps</span></span> | <span data-ttu-id="d0dd1-109">App basate su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d0dd1-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="d0dd1-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="d0dd1-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="d0dd1-111">Fascia IVA articoli</span><span class="sxs-lookup"><span data-stu-id="d0dd1-111">Item sales tax group</span></span> | <span data-ttu-id="d0dd1-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="d0dd1-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="d0dd1-113">Uffici IVA</span><span class="sxs-lookup"><span data-stu-id="d0dd1-113">Sales tax authorities</span></span> | <span data-ttu-id="d0dd1-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="d0dd1-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="d0dd1-115">Entità codici esenzione IVA CDS</span><span class="sxs-lookup"><span data-stu-id="d0dd1-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="d0dd1-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="d0dd1-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="d0dd1-117">Fasce IVA</span><span class="sxs-lookup"><span data-stu-id="d0dd1-117">Sales tax groups</span></span> | <span data-ttu-id="d0dd1-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="d0dd1-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="d0dd1-119">Gruppi registrazione contabile IVA V2</span><span class="sxs-lookup"><span data-stu-id="d0dd1-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="d0dd1-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="d0dd1-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="d0dd1-121">Codici ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="d0dd1-121">Withholding tax codes</span></span> | <span data-ttu-id="d0dd1-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="d0dd1-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="d0dd1-123">Gruppi ritenute d'acconto</span><span class="sxs-lookup"><span data-stu-id="d0dd1-123">Withholding tax groups</span></span> | <span data-ttu-id="d0dd1-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="d0dd1-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

