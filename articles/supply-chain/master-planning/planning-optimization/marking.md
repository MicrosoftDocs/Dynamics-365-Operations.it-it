---
title: Contrassegno inventario con Ottimizzazione pianificazione
description: Questo articolo fornisce informazioni sulle opzioni disponibili per contrassegnare le scorte in ordini consolidati quando si utilizza l'ottimizzazione della pianificazione.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 55c83cdbc144f194fe80e8281a35ec7ff43d551e
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219939"
---
# <a name="inventory-marking-with-planning-optimization"></a>Contrassegno inventario con Ottimizzazione pianificazione

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce informazioni sulle opzioni disponibili per contrassegnare le scorte in ordini consolidati quando si utilizza l'ottimizzazione della pianificazione.

*Contrassegno* viene utilizzato per collegare domanda e offerta. Assomiglia al *pegging*, che indica come la pianificazione generale prevede di coprire la domanda. Da un punto di vista della pianificazione, la differenza principale è che il contrassegno è più permanente del pegging.

Il contrassegno è stata introdotto per supportare scenari di determinazione dei costi speciali per first in, first out (FIFO) e last in, first out (LIFO). Tuttavia, ora viene utilizzato anche per alcuni scenari senza costi. Il contrassegno tra domanda e offerta è facoltativo e quasi permanente. Il contrassegno può essere rimosso manualmente da un utente oppure può essere rimosso eseguendo un'esplosione di riga dell'ordine cliente in cui l'opzione **Rimuovi contrassegno** è selezionata.

Il pegging è controllato dalla pianificazione generale durante la copertura per collegare la domanda con la fornitura richiesta. Il pegging può essere aggiornato per ogni esecuzione della pianificazione per ottimizzare l'offerta necessaria per coprire la domanda. Quando la pianificazione generale aggiorna le informazioni sul pegging, rispetta qualsiasi contrassegno esistente.

Il pegging inizia includendo il contrassegno pertinente, le prenotazioni disponibili e le prenotazioni su ordine, nella seguente sequenza:

1. Contrassegno tra domanda e offerta
1. Prenotazioni delle scorte disponibili
1. Prenotazione su ordine

Quando si stabilisce un ordine pianificato, la finestra di dialogo **Stabilizzazione** fornisce un campo **Aggiorna contrassegno** che può essere utilizzato per impostare le opzioni di contrassegno per gli ordini creati durante la stabilizzazione. Selezionare uno dei seguenti valori:

- *No* - Non viene applicato alcun contrassegno di inventario.
- *Standard* – Il contrassegno scorte viene aggiornato in base al pegging. Un ordine di richiesta (domanda) viene contrassegnato in base a un ordine di evasione (offerta). Se una certa quantità rimane nell'ordine di evasione, non viene contrassegnata e le informazioni di riferimento vengono lasciate vuote. Ad esempio, se un ordine cliente per 100 pezzi è ancorato a un ordine fornitore per 150 pezzi, le informazioni di riferimento verranno assegnate solo all'ordine cliente.
- *Esteso* – Verranno contrassegnati sia l'ordine di richiesta (domanda) che l'ordine di evasione (offerta), indipendentemente dalla quantità eventualmente rimasta nell'ordine di evasione. Ad esempio, se un ordine cliente per 100 pezzi è ancorato a un ordine fornitore per 150 pezzi, le informazioni di riferimento verranno assegnate all'ordine cliente e all'ordine fornitore.
- *Livello singolo standard*: viene utilizzato il contrassegno a livello singolo. Il contrassegno a livello singolo contrassegna solo l'articolo principale, non i componenti della distinta base (DBA). Pertanto, puoi mantenere flessibile l'assegnazione dei componenti per gli ordini di produzione dopo la stabilizzazione. Il contrassegno a livello singolo consente al sistema di eseguire l'ottimizzazione per le modifiche della domanda dell'ultimo minuto. Nel contrassegno a livello singolo *standard*, gli ordini di fabbisogno vengono contrassegnati rispetto ai relativi ordini di evasione, ma gli ordini di evasione non vengono contrassegnati se hanno quantità rimanenti.
- *Livello singolo esteso*: viene utilizzato il contrassegno a livello singolo. Nel contrassegno a livello singolo *esteso*, gli ordini di fabbisogno vengono contrassegnati rispetto ai relativi ordini di evasione e gli ordini di evasione vengono sempre contrassegnati indipendentemente dalla quantità rimanente.

Per impostare l'opzione di contrassegno predefinita per il sistema, andare a **Pianificazione generale \> Impostazioni \> Parametri di pianificazione generale**. Quindi, nella scheda **Aggiornamento standard**, impostare il campo **Aggiorna contrassegno** sull'opzione preferita.

> [!NOTE]
> Le opzioni *Livello singolo standard* e *Livello singolo esteso* sono disponibili solo se la funzionalità *Automazione dell'offerta Produzione su ordine* è abilitata nel sistema. Per ulteriori informazioni su questa funzionalità e su come abilitarla, vedere [Automazione dell'offerta Produzione su ordine](../make-to-order-supply-automation.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
