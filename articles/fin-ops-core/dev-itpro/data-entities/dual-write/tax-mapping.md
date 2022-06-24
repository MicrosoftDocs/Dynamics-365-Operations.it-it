---
title: Imposta integrata
description: In questo articolo viene descritta l'integrazione dei dati fiscali tra Finanza e operazioni e Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 8864a9567d57739aa72fa1859f5cfce6df33e8f7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864545"
---
# <a name="integrated-tax"></a>Imposta integrata

[!include [banner](../../includes/banner.md)]



I dati di impostazione fiscale definiscono la configurazione delle imposte indirette (IVA, GST) sia per la ritenuta d'acconto. Descrive la regola del calcolo fiscale, l'aliquota fiscale, la contabilità fiscale, la liquidazione e altri concetti.

## <a name="templates"></a>Modelli

I dati fiscali includono una raccolta di mappe della tabella che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

| App Finanza e operazioni | App di interazione con i clienti | Description |
|-----------------------------|-----------------------------------|-------------|
[Fascia IVA articoli](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Uffici IVA](mapping-reference.md#193) | msdyn_taxauthorities | |
[Entità codici esenzione IVA CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Fasce IVA](mapping-reference.md#195) | msdyn_taxgroups | |
[Gruppi registrazione contabile IVA V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Codici ritenuta d'acconto](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Gruppi ritenute d'acconto](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
