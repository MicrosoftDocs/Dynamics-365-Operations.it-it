---
title: Configurare l'IVA per gli ordini online
description: Questo argomento fornisce una panoramica della selezione della fascia IVA per diversi tipi di ordine online in Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 36dd3e8a3d47f02eed5b9c8bb79d773d98069376
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254843"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurare l'IVA per gli ordini online

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica della selezione della fascia IVA per diversi tipi di ordine online. 

Il canale di e-commerce potrebbe voler supportare opzioni come la consegna o il ritiro per gli ordini online. L'applicabilità dell'IVA si basa sull'opzione selezionata dagli utenti online. Quando un cliente del sito sceglie di acquistare un articolo online e lo fa spedire a un indirizzo, l'IVA viene determinata in base all'impostazione del gruppo fiscale dell'indirizzo di spedizione del cliente. Quando un cliente sceglie di ritirare un articolo acquistato in un negozio, l'IVA viene determinata in base all'impostazione del gruppo fiscale del negozio di ritiro. 

## <a name="orders-shipped-to-a-customer-address"></a>Ordini spediti a un indirizzo del cliente 

In generale, le tasse per gli ordini online spediti agli indirizzi dei clienti sono definite dalla destinazione. Ogni fascia IVA ha una configurazione fiscale basata sulla destinazione di vendita al dettaglio in cui l'azienda può definire i dettagli della destinazione come provincia/regione, stato, contea e città in una forma gerarchica. Quando viene effettuato un ordine online, il motore fiscale di Commerce utilizza l'indirizzo di consegna di ogni voce dell'ordine e trova le fasce IVA con criteri fiscali basati sulla destinazione corrispondenti. Ad esempio, per un ordine online con un indirizzo di consegna di una voce a San Francisco, California, il motore fiscale troverà la fascia IVA e il codice IVA per la California, quindi calcolerà di conseguenza l'imposta per ogni articolo di riga.  

## <a name="customer-based-tax-groups"></a>Gruppi fiscali basati sul cliente

In Commerce headquarters, ci sono due posizioni in cui sono configurate i gruppi fiscali dei clienti:

- **Profilo del cliente**
- **Indirizzo di spedizione del cliente**

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a>Se il profilo di un cliente ha un gruppo fiscale configurato

Il record del profilo di un cliente in headquarters può avere un gruppo fiscale configurato, tuttavia per gli ordini online il gruppo fiscale configurato nel profilo di un cliente non verrà utilizzato dal motore fiscale. 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a>Se l'indirizzo di spedizione di un cliente ha un gruppo fiscale configurato

Se il record dell'indirizzo di spedizione di un cliente ha un gruppo fiscale configurato e un ordine online (o una voce) viene spedito all'indirizzo di spedizione del cliente, il gruppo fiscale configurato nel record dell'indirizzo del cliente verrà utilizzato dal motore fiscale per i calcoli fiscali.

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a>Configurare un gruppo fiscale per un record di indirizzo di spedizione di un cliente

Per configurare un gruppo fiscale per il record dell'indirizzo di spedizione di un cliente in Commerce headquarters seguire questi passaggi.

1. Andare a **Tutti i clienti**, quindi selezionare il cliente desiderato. 
1. Nella Scheda dettaglio **Indirizzi**, selezionare l'indirizzo desiderato, quindi selezionare **Altre opzioni \> Avanzate**. 
1. Nella scheda **Generale** della pagina **Gestisci indirizzi** impostare il valore dell'IVA secondo necessità.

> [!NOTE]
> Il gruppo fiscale viene definito utilizzando l'indirizzo di consegna della riga dell'ordine e le imposte basate sulla destinazione vengono configurate nel gruppo fiscale stesso. Per ulteriori informazioni, vedere [Impostare le imposte per i punti vendita online in base alla destinazione](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="order-pickup-in-store"></a>Ritiro dell'ordine nel punto vendita

Per le righe ordine con ritiro nel punto vendita o al piano strada specificato, verrà applicato il gruppo fiscale del punto vendita selezionato. Per dettagli su come configurare il gruppo fiscale per un determinato punto vendita, vedere [Impostare altre opzioni fiscali per i punti vendita](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

> [!NOTE]
> Quando una riga ordine viene ritirata presso un negozio, le impostazioni fiscali dell'indirizzo del cliente (se configurate) verranno ignorate dal motore fiscale e verrà applicata la configurazione fiscale del punto vendita. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'IVA](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Metodi di calcolo IVA nel campo Origine](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[Assegnazione e sostituzioni IVA](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Opzioni importo totale e intervallo per i codici IVA](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Calcolo dell'esenzione fiscale](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]