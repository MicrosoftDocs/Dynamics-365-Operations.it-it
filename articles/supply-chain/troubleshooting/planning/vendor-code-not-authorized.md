---
title: Il codice fornitore non è autorizzato per un prodotto e una data specifici
description: Quando tenti di stabilizzare un ordine pianificato o di aggiungere una riga a un ordine di acquisto, viene visualizzato un messaggio di errore che indica che il codice fornitore non è autorizzato per un prodotto e una data.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294113"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a>Il codice fornitore non è autorizzato per un prodotto e una data specifici

Codice errore: SYP4881415

## <a name="symptoms"></a>Sintomi

Quando tenti di stabilizzare un ordine pianificato o aggiungere una riga a un ordine fornitore viene visualizzato il seguente messaggio di errore:

> Codice fornitore %1 non autorizzato per %2 in %3.

## <a name="cause"></a>Causa

L'errore si verifica perché il campo **Metodo di controllo fornitore approvato** è impostato su *Solo avviso* o *Non consentito* per il prodotto specificato e il fornitore non è attualmente autorizzato a fornire quel prodotto.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, disabilita il controllo del fornitore per il prodotto in questione o approva il fornitore.

Per disabilitare il controllo del fornitore per un prodotto, attieniti alla seguente procedura.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri il prodotto rilevante.
1. Nella scheda dettaglio **Acquisto** imposta il campo **Metodo di controllo fornitore approvato** su un valore diverso da *Solo avviso* o *Non consentito*.

Per approvare un fornitore per un prodotto, attieniti alla seguente procedura.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri l'articolo rilevante.
1. Nel riquadro azioni, nella scheda **Acquisto**, nel gruppo **Fornitore approvato**, seleziona **Imposta**.
1. Nella pagina elenco **Fornitore approvato** aggiungi una riga alla griglia e imposta i seguenti campi:

    - **Fornitore** – Seleziona il fornitore da approvare per il prodotto corrente.
    - **Data di validità** – Seleziona la data di inizio dell'approvazione del fornitore.
    - **Data di scadenza** – Seleziona la data di fine dell'approvazione del fornitore.

Per informazioni, vedi [Approvare i fornitori per prodotti specifici](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).
