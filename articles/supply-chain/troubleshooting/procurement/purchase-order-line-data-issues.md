---
title: Discrepanze nei dati delle righe ordine fornitore
description: Si notano discrepanze nei dati o dati corrotti nelle righe ordine fornitore.
author: SmithaNataraj
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: PurchLineManualCorrection, PurchTable, PurchLine, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ee2cb9a07c8a00a92c71e3e99d8ec20aa27fb20e
ms.sourcegitcommit: b9799a58d6ec221df86788bc37c4fbd28b435e89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2022
ms.locfileid: "8100803"
---
# <a name="purchase-order-line-data-discrepancies"></a>Discrepanze nei dati delle righe ordine fornitore

## <a name="symptoms"></a>Sintomi

Quando si ispezionano le righe di un ordine di acquisto, si nota uno o più dei seguenti problemi:

- È presente una discrepanza nei dati o dati corrotti nelle rimanenze delle righe ordine fornitore (consegna o fattura).
- Sono presenti dati corrotti in una riga ordine fornitore o nello stato dell'intestazione.
- Non puoi fatturare un ordine di acquisto perché, ad esempio, ricevi uno o più dei seguenti messaggi di errore:

    - "Arrestato (errore): la transazione è già stata registrata."
    - "Impossibile fatturare la quantità perché non è presente un numero sufficiente di operazioni di magazzino con stato Ricevuto."
    - "Transazioni di inventario insufficienti con stato "Acquistato" per l'articolo %0 quantità %1."

- Non è possibile finalizzare o chiudere un ordine fornitore a causa, ad esempio, di uno dei seguenti problemi:

    - Il pulsante **Finalizza** non è disponibile.
    - Non è possibile annullare la quantità ordinata di una riga ordine fornitore per un ordine fornitore il cui stato è Confermato e Ricevuto.

## <a name="cause"></a>Causa

Questi problemi sono in genere causati da dati corrotti o da una discrepanza nelle quantità rimanenti per una o più righe ordine fornitore.

## <a name="resolution"></a>Risoluzione

In genere è possibile risolvere questi problemi aggiornando lo stato dell'acquisto, le rimanenze di consegne e/o di fatture per le righe ordine fornitore pertinenti, come descritto nella procedura seguente.

1. Vai a **Approvvigionamento \> Attività periodiche \> Pulizia \> Correggi manualmente righe ordine di acquisto**.
1. Nel campo **Ordine fornitore**, trova e seleziona l'ordine di acquisto all'origine del problema.
1. Nella sezione **Righe ordine fornitore**, seleziona una riga in cui hai riscontrato una discrepanza.
1. Nella sezione **Transazioni di magazzino**, esaminare i dati visualizzati. Se si notano incoerenze tra una riga ordine fornitore e le relative transazioni di magazzino, selezionare uno dei seguenti comandi nel riquadro azioni, a seconda di dove si trovano le incoerenze:

    - **Ricalcola \> Ricalcola rimanenza consegna** – Aggiorna automaticamente la riga ordine fornitore e gli stati dell'intestazione. Questa funzione funziona solo per le righe ordine fornitore in stock (ovvero le righe in cui l'articolo è un articolo in stock). Gli articoli non in stock e gli articoli a peso variabile non sono attualmente supportati.
    - **Ricalcola \> Ricalcola rimanenza fattura** – Aggiorna automaticamente la riga ordine fornitore e gli stati dell'intestazione. Questa funzione funziona solo per le righe ordine fornitore in stock (ovvero le righe in cui l'articolo è un articolo in stock). Gli articoli non in stock e gli articoli a peso variabile non sono attualmente supportati.
    - **Ricalcola \> Ricalcola stato** – Ricalcola lo stato della riga selezionata. Questo calcolo si basa sulla logica esistente. Pertanto, lo stato dell'intestazione dell'ordine fornitore verrà aggiornato come richiesto, in base allo stato della nuova riga ordine fornitore.

1. Se vedi ancora incoerenze nelle quantità rimanenti, puoi utilizzare i seguenti campi per modificarle direttamente come richiesto:

    - Rimanenza consegna
    - Rimanenza consegna inventario
    - Rimanenza fattura
    - Rimanenza fattura magazzino
