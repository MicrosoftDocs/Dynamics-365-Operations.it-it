---
title: Consolidare le spedizioni quando i criteri di consolidamento delle spedizioni vengono ignorati dalla pagina Rilascia in magazzino
description: Questo argomento presenta uno scenario in cui una o più righe di vendita devono essere rilasciate manualmente al magazzino dalla pagina Rilascia in magazzino e i criteri di consolidamento della spedizione definiti dal sistema devono essere ignorati prima del rilascio.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 4aaaa7949d988607b38dd6e38a3c3497f227b8af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963338"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a>Consolidare le spedizioni quando i criteri di consolidamento delle spedizioni vengono ignorati dalla pagina Rilascia in magazzino

[!include [banner](../includes/banner.md)]

Questo argomento presenta uno scenario in cui una o più righe di vendita devono essere rilasciate manualmente al magazzino dalla pagina **Rilascia in magazzino** e i criteri di consolidamento della spedizione definiti dal sistema devono essere ignorati prima del rilascio. Potrebbe essere necessario sostituire i criteri di consolidamento della spedizione se, ad esempio, un ordine che di solito non è consolidato con spedizioni aperte deve essere consolidato con spedizioni aperte.

Durante lo scenario, creerai un insieme di ordini cliente e quindi sovrascriverai i criteri di consolidamento della spedizione predefinita prima di rilasciare gli ordini al magazzino.

## <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti

Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti. Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crea gli ordini cliente per questo scenario

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini clienti** e crea tre ordini clienti identici con le seguenti impostazioni:

    - **Conto cliente:** *US-002*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>Rilascia gli ordini cliente dalla pagina Rilascia in magazzino

Segui questi passaggi per sovrascrivere i criteri di consolidamento della spedizione durante il rilascio al magazzino.

1. Vai a **Gestione magazzino \> Rilascia in magazzino \> Rilascia in magazzino**.
1. Nel riquadro superiore, seleziona il primo ordine cliente creato per questo scenario.
1. Seleziona **Aggiungi** per aggiungere la riga al rilascio al magazzino. Tieni presente che il criterio di consolidamento della spedizione *Predefinito* viene applicato nel riquadro inferiore.
1. Nel riquadro inferiore, seleziona **Seleziona nuovi criteri di consolidamento spedizioni**.
1. Seleziona un criterio che consenta il consolidamento con altre spedizioni aperte dello stesso criterio. Ad esempio, seleziona il criterio *CustomerOrderNo*.
1. Seleziona **Rilascia in magazzino**.
1. Seleziona il secondo e terzo ordine cliente creato per questo scenario.
1. Seleziona **Aggiungi** per aggiungere righe al rilascio al magazzino. Tieni presente che il criterio *Predefinito* viene applicato nel riquadro inferiore.
1. Seleziona la seconda riga, quindi nel campo **Seleziona nuovi criteri di consolidamento spedizioni**, seleziona il criterio *CustomerOrderNo*.
1. Seleziona **Rilascia in magazzino** per entrambe le righe.

## <a name="verify-the-shipments"></a>Verifica le spedizioni

Dovrebbero essere state create due spedizioni:

- La prima spedizione contiene due righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerOrderNo*.
- La seconda spedizione contiene una riga ed è stata creata utilizzando il criterio di consolidamento della spedizione *Predefinito*.

Segui questi passaggi per rivedere le spedizioni che sono state create.

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Trova e seleziona la spedizione richiesta.
1. Nel campo **Criteri di consolidamento spedizioni**, rivedi il criterio di consolidamento usato al momento della creazione della spedizione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Criteri consolidamento spedizione](about-shipment-consolidation-policies.md)
- [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md)
