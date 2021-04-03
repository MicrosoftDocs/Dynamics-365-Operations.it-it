---
title: Imposta integrata
description: In questo argomento viene descritta l'integrazione dei dati fiscali tra Finance and Operations e Dataverse.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7501ef21492a96c81b971e1d9077beaba9be897b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560339"
---
# <a name="integrated-tax"></a><span data-ttu-id="5a9f1-103">Imposta integrata</span><span class="sxs-lookup"><span data-stu-id="5a9f1-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="5a9f1-104">I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="5a9f1-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="5a9f1-105">Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.</span><span class="sxs-lookup"><span data-stu-id="5a9f1-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="5a9f1-106">Modelli</span><span class="sxs-lookup"><span data-stu-id="5a9f1-106">Templates</span></span>

<span data-ttu-id="5a9f1-107">I dati fiscali includono una raccolta di mappe della tabella che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="5a9f1-107">Tax data includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="5a9f1-108">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5a9f1-108">Finance and Operations apps</span></span> | <span data-ttu-id="5a9f1-109">App basate su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5a9f1-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="5a9f1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a9f1-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="5a9f1-111">Fascia IVA articoli</span><span class="sxs-lookup"><span data-stu-id="5a9f1-111">Item sales tax group</span></span> | <span data-ttu-id="5a9f1-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="5a9f1-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="5a9f1-113">Uffici IVA</span><span class="sxs-lookup"><span data-stu-id="5a9f1-113">Sales tax authorities</span></span> | <span data-ttu-id="5a9f1-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="5a9f1-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="5a9f1-115">Entità codici esenzione IVA CDS</span><span class="sxs-lookup"><span data-stu-id="5a9f1-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="5a9f1-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="5a9f1-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="5a9f1-117">Fasce IVA</span><span class="sxs-lookup"><span data-stu-id="5a9f1-117">Sales tax groups</span></span> | <span data-ttu-id="5a9f1-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="5a9f1-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="5a9f1-119">Gruppi registrazione contabile IVA V2</span><span class="sxs-lookup"><span data-stu-id="5a9f1-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="5a9f1-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="5a9f1-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="5a9f1-121">Codici ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="5a9f1-121">Withholding tax codes</span></span> | <span data-ttu-id="5a9f1-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="5a9f1-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="5a9f1-123">Gruppi ritenute d'acconto</span><span class="sxs-lookup"><span data-stu-id="5a9f1-123">Withholding tax groups</span></span> | <span data-ttu-id="5a9f1-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="5a9f1-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]