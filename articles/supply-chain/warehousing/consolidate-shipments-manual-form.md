---
title: Consolidare le spedizioni manualmente utilizzando la pagina Consolida spedizioni
description: Questo articolo presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente utilizzando la pagina Consolida spedizioni.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 05f094b82b3d9bf9c095bc43f404aa7159bcafba
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427906"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>Consolidare le spedizioni manualmente utilizzando la pagina Consolida spedizioni

[!include [banner](../includes/banner.md)]

Questo articolo presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente utilizzando la pagina **Consolida spedizioni**.

## <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Lo scenario in questo articolo fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti

Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti. Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crea gli ordini cliente per questo scenario

Inizia creando una raccolta di ordini cliente con cui puoi lavorare. Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS). A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.

Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.

### <a name="create-sales-orders-1-and-2"></a>Crea ordini cliente 1 e 2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-007*
    - **Pool:** *ShipCons*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

### <a name="create-sales-orders-3-and-4"></a>Crea ordini cliente 3 e 4

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-007*
    - **Pool:** lasciare vuoto questo campo.

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

## <a name="release-the-orders-to-the-warehouse"></a>Rilascia gli ordini al magazzino

Segui questi passaggi per rilasciare ciascun ordine cliente creato per questo scenario nel magazzino.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente**.
1. Trova e seleziona l'ordine cliente da rilasciare.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Azioni \> Rilascia in magazzino** per rilasciare l'ordine cliente selezionato.
1. Ripeti questa procedura per ogni altro ordine cliente creato per questo scenario.

## <a name="consolidate-shipments"></a>Consolida spedizioni

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Trova e seleziona una spedizione creata quando l'ordine cliente 1 è stato rilasciato al magazzino. Il campo **Criteri di consolidamento spedizioni** deve essere impostato su *Pool di ordini*.
1. Nel riquadro azioni, nella scheda **Spedizioni**, seleziona **Spedizioni \> Consolida spedizioni**.
1. Verifica le spedizioni consigliate per il consolidamento. Solo una spedizione con gli stessi criteri deve essere suggerita per il consolidamento.
1. Chiudi la pagina **Consolidamento spedizioni**.
1. Trova e seleziona una spedizione creata quando l'ordine cliente 3 è stato rilasciato al magazzino. Il campo **Criteri di consolidamento spedizioni** deve essere impostato su *Predefinito*.
1. Nel riquadro azioni, nella scheda **Spedizioni**, seleziona **Spedizioni \> Consolida spedizioni**.
1. Verifica che le spedizioni siano consigliate per il consolidamento.
1. Seleziona **Mostra filtri**.
1. Nel riquadro **Filtri**, rimuovere il filtro **Numero ordine** e seleziona **Applica**.
1. Verifica le spedizioni consigliate per il consolidamento. Solo una spedizione con gli stessi criteri deve essere suggerita per il consolidamento.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei criteri di consolidamento delle spedizioni](about-shipment-consolidation-policies.md)
- [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]