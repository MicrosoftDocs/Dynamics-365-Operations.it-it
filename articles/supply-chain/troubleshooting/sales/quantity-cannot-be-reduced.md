---
title: Impossibile ridurre la quantità quando un ordine cliente viene annullato
description: Impossibile ridurre la quantità quando un ordine cliente viene annullato.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230838"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a>Impossibile ridurre la quantità quando un ordine cliente viene annullato

Codice errore: SYS138831

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> La quantità non può essere ridotta. Il numero di transazioni di inventario nell'ordine è troppo basso perché la quantità o parte di essa sia referenziata da un ordine di output o da un ordine di produzione oppure è contrassegnata a fronte di altre transazioni.

## <a name="cause"></a>Causa

Se il lavoro è associato a un ordine cliente, non è possibile annullare l'ordine cliente finché il lavoro non viene annullato e stornato. Questo requisito si applica anche se il lavoro associato all'ordine cliente viene chiuso.

## <a name="resolution"></a>Risoluzione

Per risolvere il problema, completare le attività seguenti:

1. Annullare il lavoro aperto.
1. Eliminare il carico.
1. Ridurre la quantità prelevata.

### <a name="cancel-open-work"></a>Annullare il lavoro aperto

Per annullare il lavoro aperto, segui questi passaggi.

1. Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.
1. Nel campo **ID lavoro**, specifica l'ID del lavoro che desideri annullare e che attualmente ha valore **Stato lavoro** uguale a *Aperto*, *In corso*, *Annullato*, *Combinato* o *Chiuso*.
1. Selezionare **OK**.
1. Seleziona **Sì** per confermare che desideri annullare il lavoro.

### <a name="delete-the-load"></a>Eliminare il carico

Per eliminare un carico, segui questi passaggi.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Apri l'ordine cliente rilevante.
1. Nella scheda dettaglio **Righe ordine cliente**, seleziona **Magazzino \> Dettagli lavoro**.
1. Nel riquadro delle azioni della pagina **Lavoro**, nella scheda **Lavoro** del gruppo **Lavoro**, seleziona **Annulla lavoro**.
1. Conferma che il campo **Stato lavoro** sia impostato su *Annullato*.
1. Chiudi la pagina **Lavoro**.
1. Nella pagina dei dettagli dell'ordine cliente, scheda dettaglio **Righe ordine cliente**, seleziona **Magazzino \> Dettagli carico**.
1. Nel riquadro delle azioni seleziona **Elimina**.
1. Seleziona **Sì** per confermare che desideri eliminare il carico.
1. Chiudi la pagina **Carico**.

### <a name="reduce-the-picked-quantity"></a>Ridurre la quantità prelevata

Dopo che tutto il lavoro è stato annullato, segui questi passaggi per ridurre la quantità prelevata.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Apri l'ordine cliente rilevante.
1. Nella scheda dettaglio **Righe ordine cliente**, seleziona **Aggiorna riga \> Prelievo** dalla barra degli strumenti.
1. Nella pagina **Prelievo**, sezione **Transazioni**, seleziona la riga in cui il campo **Stato uscita** è impostato su *Prelevato*.
1. Nella sezione **Transazioni**, seleziona **Aggiungi riga di prelievo** dalla barra degli strumenti.
1. Nella sezione **Righe di prelievo**, seleziona **Conferma Preleva tutto** dalla barra degli strumenti.
1. Chiudi la pagina **Prelievo**.
1. Nel riquadro delle azioni della pagina dei dettagli dell'ordine cliente, nella scheda **Ordine cliente**, gruppo **Conserva**, seleziona **Annulla**.
1. Seleziona **Sì** per confermare che desideri annullare l'ordine cliente.
