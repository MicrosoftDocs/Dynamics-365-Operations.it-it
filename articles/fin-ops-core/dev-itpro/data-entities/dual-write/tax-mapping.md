---
title: Imposta integrata
description: In questo argomento viene descritta l'integrazione dei dati fiscali tra Finance and Operations e Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: rhaertle
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: c7e76294944196670ed4b02ebf785c1bed7b5106f73d4b66a15a19c9a4235cbf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738554"
---
# <a name="integrated-tax"></a>Imposta integrata

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto. Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.

## <a name="templates"></a>Modelli

I dati fiscali includono una raccolta di mappe della tabella che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

| App di Finance and Operations | App di interazione con i clienti | descrizione |
|-----------------------------|-----------------------------------|-------------|
[Fascia IVA articoli](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Uffici IVA](mapping-reference.md#193) | msdyn_taxauthorities | |
[Entità codici esenzione IVA CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Fasce IVA](mapping-reference.md#195) | msdyn_taxgroups | |
[Gruppi registrazione contabile IVA V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Codici ritenuta d'acconto](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Gruppi ritenute d'acconto](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
