---
title: I processi di Warehouse Management sono attualmente in uso
description: Quando si prenota o si rilascia un lavoro, è possibile che venga visualizzato un messaggio che indica che i processi di warehouse management sono attualmente in uso. Risolvi il problema con uno di questi passaggi.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bfda2fae824cdc64d722310d20cf16e6306d766c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476720"
---
# <a name="cant-reserve-or-release-work-because-processes-are-currently-being-used"></a>Impossibile prenotare o rilasciare il lavoro perché i processi sono attualmente in uso

## <a name="symptoms"></a>Sintomi

Quando si lavora con la produzione discreta, si riceve il seguente errore:

> I processi di Warehouse Management sono attualmente in uso. Se le righe di lavoro non sono ancora registrate, è possibile annullare il lavoro creato e qualsiasi riga di carico o spedizione, quindi continuare il processo di prelievo o spedizione.

## <a name="cause"></a>Causa

Questo problema si verifica se si tenta di prenotare o rilasciare il lavoro per una riga, ma la transazione di inventario ha uno stato *Prelevato*, che indica che il materiale è stato prelevato.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, eseguire uno dei passaggi seguenti.

- Modificare di nuovo lo stato dell'ordine di produzione in *Stimato* o *Rilasciato*.
- Aprire la pagina dei dettagli dell'ordine di produzione pertinente. Nel riquadro azioni, nella scheda **Magazzino** nel gruppo **Interrompi**, selezionare **Interrompi e annulla prelievo** per annullare tutte le transazioni prelevate. Quindi selezionare **Rimuovi interruzione** per elaborare l'ordine di produzione.

Ecco una spiegazione delle funzioni *Annulla prelievo* e *Interrompi*:
  
- **Annulla prelievo** - Questa funzione inverte lo stato delle transazioni di inventario per le righe della distinta base (DBA) e le righe della formula che hanno uno stato da *Prelevato* a *In ordine*. Quando il lavoro per il prelievo delle materie prime è completato, lo stato delle righe viene impostato su *Prelevato*. Questo stato impedisce il ripristino dell'ordine di produzione sullo stato *Creato*. In questo caso, è possibile usare la funzione *Annulla prelievo* per ripristinare le transazioni dallo stato *Prelevato* e quindi reimpostare l'ordine di produzione sullo stato *Creato*.
- **Interrompi** - Questa funzione imposta un flah **Interrotto** sull'ordine di produzione per impedire qualsiasi aggiornamento dello stato dell'ordine. Il flag **Interrotto** si trova nella scheda dettaglio **Magazzino** della pagina dei dettagli dell'ordine di produzione.

> [!NOTE]
>
> - I pulsanti sono visibili solo quando viene creato l'ordine di produzione per gli articoli abilitati per i processi di magazzino.
> - Il gruppo **Interrompi** è visibile solo nella scheda **Magazzino** nel riquadro azioni della pagina dei dettagli dell'ordine di produzione. Non è visibile nella Scheda dettaglio **Magazzino** della pagina elenco **Ordini di produzione**.
