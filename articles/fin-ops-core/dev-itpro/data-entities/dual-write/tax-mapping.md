---
title: Imposta integrata
description: In questo argomento viene descritta l'integrazione dei dati fiscali tra Finance and Operations e Dataverse.
author: robinarh
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
ms.openlocfilehash: a7992520b57b4c19b6dc8e13bd8e9ffc87b40f5a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750644"
---
# <a name="integrated-tax"></a>Imposta integrata

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto. Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.

## <a name="templates"></a>Modelli

I dati fiscali includono una raccolta di mappe della tabella che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

App di Finance and Operations | App basate su modello in Dynamics 365 | Descrizione |
-------------------------|---------------------------------|----|
Fascia IVA articoli | msdyn_taxitemgroups |
Uffici IVA | msdyn_taxauthorities |
Entità codici esenzione IVA CDS | msdyn_taxexemptcodes |
Fasce IVA | msdyn_taxgroups |
Gruppi registrazione contabile IVA V2 | msdyn_taxpostinggroups |
Codici ritenuta d'acconto | msdyn_withholdingtaxcodes |
Gruppi ritenute d'acconto | msdyn_withholdingtaxgroups | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]