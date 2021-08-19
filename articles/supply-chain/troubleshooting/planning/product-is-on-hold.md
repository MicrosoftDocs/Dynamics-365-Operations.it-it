---
title: Il prodotto è in attesa per le transazioni
description: Dopo aver pianificato gli ordini, viene visualizzato un messaggio di errore che indica che un articolo è in sospeso per le transazioni.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8e012a65041c2f32e21d2631eda18eea488e28e35f6a53bbe9a67c08159765e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752612"
---
# <a name="product-is-on-hold-for-transactions"></a>Il prodotto è in attesa per le transazioni

Codice errore: SYS13295

## <a name="symptoms"></a>Sintomi

Dopo aver stabilizzato gli ordini pianificati, viene visualizzato il seguente messaggio di errore:

> L'articolo %1 è in attesa per le transazioni in %2.

## <a name="cause"></a>Causa

Quando si descrivono gli articoli bloccati, il sistema utilizza i termini *bloccato*, *interrotto*, e *in attesa* in modo intercambiabile. Questo errore significa che l'articolo è impostato come **Interrotto** nelle impostazioni di ordine predefinite.

Se un articolo è bloccato e lo si aggiunge a una riga di un ordine fornitore o di un ordine cliente, viene visualizzato un messaggio di avviso. Quando un articolo è bloccato, le transazioni di magazzino correlate alla riga dell'ordine fornitore o cliente non possono essere modificate, ad esempio durante la registrazione di un documento di trasporto o una fattura. È possibile bloccare un articolo acquistato e contemporaneamente vendere l'articolo. In tal caso, il campo **Interrotto** è selezionato nell'ordine fornitore, ma l'articolo non è bloccato nel magazzino o in un ordine cliente.

Ecco alcune delle condizioni che possono impedire la vendita di un numero di articolo:

- L'articolo è ancora in fase di sviluppo o produzione. Pertanto, non vuoi che venga venduto o prenotato.
- Hai ricevuto molti articoli difettosi e i difetti devono essere corretti prima che l'articolo possa essere venduto.

In casi di questo tipo, è possibile bloccare l'articolo finché il problema non viene risolto.

Se un articolo è bloccato e si crea una riga di ordine di reso, viene visualizzato un messaggio. Non è possibile bloccare una serie o un lotto di un articolo. Se è necessario bloccare parti di un articolo, è possibile spostare le scorte o bloccare le scorte totali dell'articolo per il periodo.

## <a name="resolution"></a>Risoluzione

- Apri la pagina **Impostazioni ordine predefinite** per l'articolo e deseleziona la casella di controllo **Interrotto**.
