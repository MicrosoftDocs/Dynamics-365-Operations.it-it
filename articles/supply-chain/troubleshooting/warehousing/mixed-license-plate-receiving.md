---
title: La ricezione di targhe miste non funziona per tutti i codici di smaltimento
description: Quando il campo Azione per un codice smaltimento è impostato su Credito o Scarti, è possibile usare solo la voce di menu Ricevimento targa mista per elaborare gli articoli restituiti.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b762255bc5ef6a1e15688a9c635940e92e67db3c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476793"
---
# <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-but-credit"></a>La ricezione di targhe miste non funziona per nessun codice smaltimento ad eccezione del credito.

## <a name="symptoms"></a>Sintomi

Quando il campo **Azione** per un codice smaltimento è impostato su *Credito* o *Scarti*, è possibile usare solo la voce di menu [Ricevimento targa mista](/dynamics365/supply-chain/warehousing/mixed-license-plate-receiving) per elaborare gli articoli restituiti.

## <a name="resolution"></a>Risoluzione

Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. Attualmente solo i [codici smaltimento](/dynamics365/supply-chain/service-management/set-up-disposition-codes) dove il campo **Azione** è impostato su *Credito* o *Scarti* sono supportati per la ricezione di targhe miste.
