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
# <a name="integrated-tax"></a>Imposta integrata

[!include [banner](../includes/banner.md)]

I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto. Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.

## <a name="templates"></a>Modelli

I dati fiscali includono una raccolta di mappe di entità che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

Finance and Operations   | Altre app Dynamics 365
-------------------------|---------------------------------
Codici imposta                  | msdyn\_taxcodes.md
Gruppi di imposta               | msdyn\_taxgroups.md
Gruppi di articoli imposta          | msdyn\_taxitemgroups.md
Esenzioni fiscali           | msdyn\_taxexemptcodes.md
Uffici tributari          | msdyn\_taxauthorities.md
Codici ritenuta d'acconto      | msdyn\_withholdingtaxcodes.md
Gruppi ritenute d'acconto   | msdyn\_withholdingtaxgroups.md
Gruppo di conti COGE imposta | msdyn\_taxpostinggroups  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

