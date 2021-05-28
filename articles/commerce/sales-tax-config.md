---
title: Configurare l'IVA per gli ordini online
description: Questo argomento fornisce una panoramica della selezione della fascia IVA per diversi tipi di ordine online in Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fff4f39703a146412b460dacc3805fde097ab756
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021442"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurare l'IVA per gli ordini online

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica della selezione della fascia IVA per diversi tipi di ordine online utilizzando le impostazioni fiscali basate sulla destinazione o sull'account cliente. 

Un canale di e-commerce può supportare opzioni come la consegna o il ritiro degli ordini online. L'applicabilità dell'IVA si basa sull'opzione selezionata dai clienti online. 

## <a name="destination-based-taxes-for-online-orders"></a>Imposte basate sulla destinazione per ordini online

In generale, le imposte per gli ordini online spediti agli indirizzi dei clienti sono definite dalla destinazione. Ogni fascia IVA ha una configurazione fiscale basata sulla destinazione della vendita al dettaglio in cui l'azienda può definire i dettagli della destinazione come provincia/regione, stato, contea e città in una forma gerarchica.

### <a name="orders-delivered-to-customer-address"></a>Ordini consegnati all'indirizzo del cliente

Quando viene effettuato un ordine online, il motore fiscale di Commerce utilizza l'indirizzo di consegna di ogni voce dell'ordine e trova le fasce IVA con criteri fiscali basati sulla destinazione corrispondenti. Ad esempio, per un ordine online con un indirizzo di consegna di una voce a San Francisco, California, il motore fiscale troverà la fascia IVA e il codice IVA per la California, quindi calcolerà di conseguenza l'imposta per ogni articolo di riga.

### <a name="order-pick-up-in-store"></a>Ritiro dell'ordine nel punto vendita

Per le righe ordine con ritiro nel punto vendita o al piano strada specificato, verrà applicato il gruppo fiscale del punto vendita selezionato. Per dettagli su come configurare l'IVA per un determinato punto vendita, vedere [Impostare altre opzioni fiscali per i punti vendita](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

## <a name="customer-account-based-taxes-for-online-orders"></a>Imposte basate sull'account del cliente per ordini online

Potrebbe esserci uno scenario aziendale in cui si desidera configurare una fascia IVA su un conto cliente specifico in Commerce Headquarters. Ci sono due aree in Commerce Headquarters in cui è possibile configurare l'IVA su un account cliente. Per accedervi, è necessario dapprima accedere a una pagina dei dettagli del cliente selezionando **Retail e Commerce \> Clienti \> Tutti i clienti** e quindi selezionare un cliente.

Le due aree in cui è possibile configurare l'IVA per un account cliente sono:

- **Fascia IVA** nella Scheda dettaglio **Fattura e consegna** della pagina dei dettagli del cliente. 
- **IVA** nella Scheda dettaglio **Generale** della pagina **Gestisci indirizzi**. Per accedervi dalla pagina dei dettagli del cliente, selezionare un indirizzo specifico sotto la Scheda dettaglio **Indirizzi** e quindi selezionare **Avanzate**.

> [!TIP]
> Per gli ordini cliente online, se desideri applicare solo le imposte basate sulla destinazione ed evitare quelle basate sull'account del cliente, assicurarsi che il campo **Fascia IVA** sia vuoto nella Scheda dettaglio **Fattura e consegna** della pagina dei dettagli del cliente. Per garantire che i nuovi clienti che si registrano utilizzando il canale online non ereditino le impostazioni della fascia IVA predefinite del cliente o del gruppo di clienti, assicurarsi che il campo **Fascia IVA** sia vuoto anche per le impostazioni del cliente e per le impostazioni del gruppo di clienti predefinite del canale online (**Retail e Commerce \> Clienti \> Gruppi di clienti**).

## <a name="determine-destination-based-tax-or-customer-account-based-tax-applicability"></a>Determinare l'applicabilità dell'imposta basata sulla destinazione o dell'imposta basata sull'account cliente 

La tabella seguente spiega se per gli ordini online vengono applicate imposte basate sulla destinazione o imposte basate sull'account cliente. 

| Tipo di cliente | Indirizzo di spedizione                   | Cliente > Fattura e consegna > Fascia IVA? | Indirizzo sul conto del cliente in Commercial Headquarters? | Indirizzo cliente > Avanzate > Generale> Fascia IVA?                                              | Fascia IVA applicata      |
|---------------|------------------------------------|-----------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------|
| Guest         | Manhattan, NY                      | No (vuoto)                                                | No (vuoto)                              | No (vuoto)                                                                                                   | NY (imposte basate su destinazione) |
| Accesso eseguito     | Austin, TX                          | No (vuoto)                                             | Sì                               | Nessuna priorità<br/><br/>Nuovo indirizzo aggiunto tramite canale online.                                                            | TX (imposte basate su destinazione) |
| Accesso eseguito     | San Francisco, CA (ritiro presso punto vendita) | Sì (NY)                                            | Non applicabile                              | Non applicabile                                                                                                    | CA (imposte basate su destinazione) |
| Accesso eseguito     | Houston, TX                         | Sì (NY)                                            | Sì                               | Sì (NY)<br/><br/>Nuovo indirizzo aggiunto tramite canale online e fascia IVA ereditata dall'account cliente. | NY (imposte basate sull'account del cliente)  |
| Accesso eseguito     | Austin, TX                          | Sì (NY)                                            | Sì                               | Sì (NY)<br/><br/>Nuovo indirizzo aggiunto tramite canale online e fascia IVA ereditata dall'account cliente. | NY (imposte basate sull'account del cliente)  |
| Accesso eseguito     | Sarasota, FL                       | Sì (NY)                                            | Sì                               | Sì (WA)<br/><br/>Impostato manualmente su WA.                                                                          | WA (imposte basate sull'account del cliente)  |
| Accesso eseguito     | Sarasota, FL                       | No (vuoto)                                                | Sì                               | Sì (WA)<br/><br/>Impostato manualmente su WA.                                                                          | WA (imposte basate sull'account del cliente)  |

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare le imposte per i punti vendita online in base alla destinazione](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination)

[Panoramica dell'IVA](../finance/general-ledger/indirect-taxes-overview.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Metodi di calcolo IVA nel campo Origine](../finance/general-ledger/sales-tax-calculation-methods-origin-field.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Assegnazione e sostituzioni IVA](../supply-chain/procurement/tasks/sales-tax-assignment-overrides.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Opzioni importo totale e intervallo per i codici IVA](../finance/general-ledger/whole-amount-interval-options-sales-tax-codes.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Calcolo dell'esenzione fiscale](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]