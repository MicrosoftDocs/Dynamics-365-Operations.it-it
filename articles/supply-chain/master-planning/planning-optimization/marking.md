---
title: Il contrassegno scorte con l'ottimizzazione della pianificazione
description: Questo argomento fornisce informazioni sulle opzioni disponibili per contrassegnare le scorte in ordini consolidati quando si utilizza l'ottimizzazione della pianificazione.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: dc94ca8b15d626d8ff64f50718d7d2e3e0326144465f3d27787805220842849f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6711907"
---
# <a name="inventory-marking-with-planning-optimization"></a>Il contrassegno scorte con l'ottimizzazione della pianificazione

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce informazioni sulle opzioni disponibili per contrassegnare le scorte in ordini consolidati quando si utilizza l'ottimizzazione della pianificazione.

*Contrassegno* viene utilizzato per collegare domanda e offerta. Assomiglia al *pegging*, che indica come la pianificazione generale prevede di coprire la domanda. Da un punto di vista della pianificazione, la differenza principale è che il contrassegno è più permanente del pegging.

Il contrassegno è stata introdotto per supportare scenari di determinazione dei costi speciali per first in, first out (FIFO) e last in, first out (LIFO). Tuttavia, ora viene utilizzato anche per alcuni scenari senza costi. Il contrassegno tra domanda e offerta è facoltativo e quasi permanente. Il contrassegno può essere rimosso manualmente da un utente oppure può essere rimosso eseguendo un'esplosione di riga dell'ordine cliente in cui l'opzione **Rimuovi contrassegno** è selezionata.

Il pegging è controllato dalla pianificazione generale durante la copertura per collegare la domanda con la fornitura richiesta. Il pegging può essere aggiornato per ogni esecuzione della pianificazione per ottimizzare l'offerta necessaria per coprire la domanda. Quando la pianificazione generale aggiorna le informazioni sul pegging, rispetta qualsiasi contrassegno esistente.

Il pegging inizia includendo il contrassegno pertinente, le prenotazioni disponibili e le prenotazioni su ordine, nella seguente sequenza:

1. Contrassegno tra domanda e offerta
1. Prenotazioni delle scorte disponibili
1. Prenotazione su ordine

Quando si stabilisce un ordine pianificato, la finestra di dialogo **Stabilizzazione** fornisce un campo **Aggiorna contrassegno** che può essere utilizzato per impostare le opzioni di contrassegno per gli ordini creati durante la stabilizzazione. Selezionare uno dei seguenti valori:

- **No** - Non viene applicato alcun contrassegno di inventario.
- **Standard** – Il contrassegno scorte viene aggiornato in base al pegging. Un ordine di richiesta (domanda) viene contrassegnato in base a un ordine di evasione (offerta). Se una certa quantità rimane nell'ordine di evasione, non viene contrassegnata e le informazioni di riferimento vengono lasciate vuote. Ad esempio, se un ordine cliente per 100 pezzi è ancorato a un ordine fornitore per 150 pezzi, le informazioni di riferimento verranno assegnate solo all'ordine cliente.
- **Esteso** – Verranno contrassegnati sia l'ordine di richiesta (domanda) che l'ordine di evasione (offerta), indipendentemente dalla quantità eventualmente rimasta nell'ordine di evasione. Ad esempio, se un ordine cliente per 100 pezzi è ancorato a un ordine fornitore per 150 pezzi, le informazioni di riferimento verranno assegnate all'ordine cliente e all'ordine fornitore.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]