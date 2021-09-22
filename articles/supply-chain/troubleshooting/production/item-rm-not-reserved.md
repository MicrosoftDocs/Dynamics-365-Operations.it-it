---
title: L'articolo RM non può essere prenotato quando viene rilasciato un ordine di produzione
description: "Quando si rilascia un ordine di produzione, è possibile che venga visualizzato l'errore: \"Impossibile prenotare completamente l'articolo RM\". Assicurarsi che la quantità completa sia disponibile o prenotare manualmente gli articoli."
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 528895252d661bb012f49190c15853989833064d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476795"
---
# <a name="item-rm-cant-be-fully-reserved-when-a-production-order-is-released"></a>L'articolo RM non può essere prenotato completamente quando viene rilasciato un ordine di produzione

## <a name="symptoms"></a>Sintomi

Se non tutte le voci della distinta base sono fisicamente disponibili quando viene rilasciato un ordine di produzione a un magazzino e il criterio **Rilascio in magazzino** è impostato su *Richiedi prenotazione completa*, viene visualizzato il seguente messaggio di errore:

> L'articolo RM non può essere prenotato completamente. Verificare che l'intera quantità sia disponibile o prenotare gli articoli manualmente se il campo Prenotazione nella riga DBA è impostato su Manuale o Avviato. Impossibile rilasciare l'ordine al magazzino perché non è stato possibile prenotare alcuni materiali.

## <a name="resolution"></a>Risoluzione

Questo comportamento è di progettazione e funziona come previsto. Per risolvere questo problema, seguire le indicazioni fornite nel messaggio di errore: "Verificare che l'intera quantità sia disponibile o prenotare gli articoli manualmente se il campo Prenotazione nella riga DBA è impostato su Manuale o Avviato".
