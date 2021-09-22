---
title: Le prenotazioni non possono essere rimosse quando si annulla un ordine
description: Non è possibile annullare un ordine cliente finché il lavoro associato a tale ordine non viene annullato e stornato. Per effettuare questa operazione, effettuare i tre passaggi illustrati di seguito.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8d947e64568246dba5eff3c21fd3920b6494b73
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476779"
---
# <a name="reservations-cannot-be-removed-when-canceling-an-order"></a>Le prenotazioni non possono essere rimosse quando si annulla un ordine

## <a name="symptoms"></a>Sintomi

Se il lavoro è associato a un ordine cliente e si tenta di annullare tale ordine, viene visualizzato il seguente messaggio di errore:

> Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni.

Non è possibile annullare l'ordine cliente finché il lavoro non viene annullato e stornato. Questo requisito si applica anche se il lavoro associato all'ordine cliente viene chiuso.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, procedere come segue:

1. Annulla il lavoro e inserisci nuovamente l'inventario nell'ubicazione desiderata. Vai al carico rilevante dell'ordine cliente e seleziona **Riduci quantità prelevata** sulla riga di carico o **Storna lavoro** nel riquadro azioni.

    Il lavoro ora ha uno stato di *Annullato* e viene creato ed elaborato automaticamente un nuovo lavoro di movimento scorte per reinserire le scorte nell'ubicazione descritta al momento dello storno.

2. Elimina il carico. Anche la spedizione viene eliminata.

3. Ora dovresti essere in grado di accedere all'ordine cliente e annullarlo.
