---
title: Aggiungere o copiare leasing (anteprima)
description: In questo argomento viene descritto come creare un nuovo leasing inserendo le relative informazioni in Leasing cespite o copiando le informazioni da un leasing esistente.
author: moaamer
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ee4803c4653b8c2df2cb731652456b1ce2796cd0
ms.sourcegitcommit: e77d72fde17a43bd1780c265702254011af7407c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2021
ms.locfileid: "7893647"
---
# <a name="add-or-copy-leases-preview"></a>Aggiungere o copiare leasing (anteprima)

[!include [banner](../includes/banner.md)]

Questo argomento spiega come creare un leasing da zero in Leasing cespite e anche come creare un leasing copiando un leasing esistente. Il processo per creare un leasing da zero prevede l'immissione delle informazioni per il nuovo leasing e quindi la creazione di una pianificazione del leasing. Dopo che è stato configurato almeno un leasing, potrebbe essere più semplice copiare le informazioni da un leasing esistente e quindi modificare tali informazioni come richiesto per creare un nuovo leasing.

## <a name="create-a-lease"></a>Creare un leasing

Segui questi passaggi per creare un leasing in Leasing cespite.

1. Nella pagina **Riepilogo leasing**, nel riquadro azioni, seleziona **Nuovo**.
2. Immetti le informazioni sul leasing. I campi obbligatori hanno bordi rossi.

> La data di inizio del canone di leasing non può essere anteriore alla data di inizio del leasing. Se inserisci una data di inizio per il canone di leasing precedente alla data di inizio del leasing, riceverai un messaggio di errore.
  
## <a name="create-a-lease-schedule"></a>Creare un programma di leasing

Dopo aver immesso le informazioni per il leasing, segui questi passaggi per creare una pianificazione del leasing.

> [!NOTE]
> Le dimensioni finanziarie potrebbero cambiare in base a qualsiasi dimensione finanziaria personalizzata.

1. Seleziona **Crea scadenziari** per generare i libri di leasing. I libri di leasing includono lo scadenziario di pagamento, ammortamento e spese.
2. Per accedere ai libri di leasing e visualizzare lo scadenziario appena creato, seleziona la scheda **Libri**.

    La pagina **Dettagli libro** mostra come il leasing viene contabilizzato dai libri che gli sono stati assegnati. Da qui è possibile visualizzare i programmi di leasing.

    Lo scadenzario pagamenti contiene gli input dalla scheda **Righe scadenzario pagamenti** nella pagina **Aggiungi leasing**. Puoi comunque modificare ogni importo di pagamento e pagamento variabile. L'obbligazione sul leasing viene calcolata in base allo scadenziario pagamenti modificato.

4. Dopo aver finito di esaminare lo scadenziario pagamenti, seleziona **Conferma scadenziario**. Dopo la conferma dello scadenziario, il leasing non è più disponibile per la modifica.

    > [!NOTE]
    > Il sistema calcola automaticamente il termine del leasing dalle righe dello scadenzario pagamenti nella pagina **Aggiungi leasing**.
    >
    > Per calcolare il termine del leasing in mesi, il sistema trova la differenza tra la data di inizio e la data di fine per una specifica riga dello scadenziario pagamenti. Quindi si sposta alla riga di scadenziario pagamenti successiva e trova di nuovo la differenza. Infine, il sistema somma tutti gli importi per determinare il termine del leasing in mesi.

5. Per visualizzare gli interessi passivi del periodo calcolato, apri la pagina **Piano di ammortamento dell'obbligazione**. Per visualizzare l'ammortamento a quote costanti calcolato, apri la pagina **Piano di ammortamento cespite**.
6. Dopo aver terminato la revisione dell'importo calcolato, è possibile creare la scrittura contabile di riconoscimento iniziale nella pagina **Riconoscimento iniziale**. Ricevi un messaggio che informa che il giornale di registrazione è stato creato.

    > [!NOTE]
    > La scrittura contabile non viene registrata nella contabilità generale fino a quando non registri manualmente la voce.

7. Per rivedere la voce di riconoscimento iniziale proposta prima di registrarla, seleziona **Giornale di registrazione leasing di cespite**.

    > [!NOTE]
    > Il giornale di registrazione leasing cespite non può essere creato manualmente. Viene creato automaticamente quando vengono creati i programmi di leasing.

8. Una volta terminata la revisione della scrittura contabile di riconoscimento iniziale e quando sei pronto per registrarla, seleziona **Registra** per riconoscere l'Asset ROU e l'obbligazione sul leasing nella contabilità generale.

## <a name="copy-a-lease"></a>Copiare un leasing

Il leasing di cespiti consente di copiare i dettagli di un leasing per creare un nuovo leasing con le stesse informazioni. È quindi possibile modificare i campi del leasing prima di creare i programmi per il leasing copiato.

1. Nella pagina **Riepilogo leasing**, seleziona il leasing da copiare, quindi, nel riquadro azioni, seleziona **Copia leasing**.

    > [!NOTE]
    > Se il parametro **Manuale** è disattivato per la sequenza numerica degli ID leasing, il numero successivo nella sequenza viene automaticamente generato come ID leasing del leasing copiato. Se il parametro **Manuale** è attivato, viene visualizzato un messaggio che richiede di inserire l'ID leasing prima di procedere alla copia del leasing.

2. Seleziona **Copia**. I dettagli del leasing vengono copiati dal leasing selezionato in un nuovo leasing. È quindi possibile modificare i dettagli del nuovo leasing prima di salvarlo e creare i programmi di leasing.

## <a name="asset-leasing-journal"></a>Giornale di registrazione leasing cespite

Tutte le scritture contabili create in Leasing cespite sono contenute nel giornale di registrazione Leasing cespiti. Nella pagina **Giornale di registrazione leasing cespite** (**Leasing cespite \> Scritture contabili \> Giornale di registrazione leasing cespiti**), è possibile filtrare in base allo stato di registrazione, visualizzare scritture contabili specifiche e giustificativi e registrare scritture contabili non registrate.

> [!NOTE]
> Il giornale di registrazione leasing cespite non può essere creato manualmente. Viene creato automaticamente quando vengono creati i programmi di leasing.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
