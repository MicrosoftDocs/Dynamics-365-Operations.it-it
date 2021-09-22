---
title: La quantità non è valida quando si registrano ordini in entrata
description: "Se la quantità allocata per una targa supera la quantità che deve ancora essere ricevuta, viene visualizzato l'errore: \"La quantità non è valida\"."
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5099b320447bf59c72f5017564ea660f19c690a5
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476808"
---
# <a name="license-plate-quantity-is-not-valid-when-registering-inbound-orders"></a>La quantità targa non è valida quando si registrano ordini in entrata

## <a name="symptoms"></a>Sintomi

Quando si registrano ordini in entrata, è possibile che venga visualizzato il seguente messaggio di errore:

> Quantità non valida.

Se il campo **Criteri di raggruppamento delle targhe** è impostato su *Definito dall'utente* per una voce di menu del dispositivo mobile utilizzata per registrare gli ordini in entrata, viene visualizzato questo errore e non è possibile completare la registrazione.

## <a name="cause"></a>Causa

Quando *Definito dall'utente* viene utilizzato come criterio di raggruppamento delle targhe, il sistema suddivide l'inventario in entrata in targhe separate, come indicato dal gruppo di sequenze unità. Se vengono utilizzati numeri di batch o di serie per tenere traccia dell'articolo ricevuto, le quantità di ciascun batch o serie devono essere specificate per targa registrata. Se la quantità specificata per una targa supera la quantità che deve ancora essere ricevuta per le dimensioni correnti, viene visualizzato questo messaggio di errore.

## <a name="resolution"></a>Risoluzione

Quando registri un artciolo utilizzando una voce di menu del dispositivo mobile in cui il campo **Criterio di raggruppamento delle targhe** è impostato su *Definito dall'utente*, il sistema potrebbe richiedere la conferma o l'immissione di numeri di targa, numeri di lotto o numeri di serie.

Nella pagina di conferma della targa, il sistema mostrerà la quantità allocata per la targa corrente. Sulle pagine di conferma del batch o della serie, il sistema mostrerà la quantità che deve ancora essere ricevuta sulla targa corrente. Comprenderà anche un campo in cui è possibile inserire la quantità da registrare per quella combinazione di targa e batch o numero di serie. In questo caso, assicurarsi che la quantità che si sta registrando per la targa non superi la quantità che deve ancora essere ricevuta.

In alternativa, se vengono generate troppe targhe durante la registrazione dell'ordine in entrata, il valore del campo **Criterio di raggruppamento delle targhe** può essere modificato in *Raggruppamento targhe*, è possibile assegnare un nuovo gruppo di sequenze di unità all'articolo o l'opzione **Raggruppamento targhe** per il gruppo di sequenze di unità può essere disattivata.
