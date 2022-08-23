---
title: Modulo indirizzo di spedizione
description: In questo articolo viene descritto il modulo di indirizzo di spedizione e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 48e6909b4dac9722830a83ec3a63a58876768d7e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275007"
---
# <a name="shipping-address-module"></a>Modulo indirizzo di spedizione

[!include [banner](includes/banner.md)]

In questo articolo viene descritto il modulo di indirizzo di spedizione e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.

Il modulo dell'indirizzo di spedizione consente ai clienti di aggiungere o selezionare l'indirizzo di spedizione per un ordine durante il flusso di check out. Se un cliente è connesso, sono visualizzati tutti gli indirizzi salvati in precedenza per tale cliente e il cliente può scegliere tra di essi. Il cliente può anche aggiungere un nuovo indirizzo. Il modulo dell'indirizzo di spedizione viene utilizzato per tutti gli articoli in un ordine che devono essere spediti.

I formati degli indirizzi di spedizione possono essere definiti in Commerce headquarters per ogni paese o regione e il modulo dell'indirizzo di spedizione applica le regole specifiche del paese.

Quando i clienti immettono un indirizzo di spedizione durante il flusso di check out, hanno la possibilità di salvare l'indirizzo come indirizzo principale. Questa opzione viene visualizzata solo se un cliente ha effettuato l'accesso.

Sebbene il modulo dell'indirizzo di spedizione non fornisca la convalida dell'indirizzo, questa funzionalità può essere implementata mediante la personalizzazione.

L'immagine seguente mostra un esempio di un nuovo modulo Indirizzo di spedizione in una pagina checkout.

![Esempio di un modulo dell'indirizzo di spedizione su una pagina Checkout.](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Proprietà del modulo

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione | Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un'intestazione facoltativa per il modulo dell'indirizzo di spedizione. |
| Mostra tipo di indirizzo | **True** o **False** | Se questa proprietà facoltativa è impostata su **True** verrà visualizzato un tipo di indirizzo, ad esempio **Casa** o **Attività commerciale**. Se non viene specificato alcun tipo di indirizzo, l'indirizzo verrà automaticamente salvato come **Tipo**=**Altro**. |
| Abilita suggerimento automatico| **True** o **False** | Se questa proprietà facoltativa è impostata su **True**, verranno forniti suggerimenti di indirizzo automatici. Questi suggerimenti sono forniti da Bing Maps. Per informazioni su come configurare l'integrazione di Bing Maps per il proprio sito, vedere [Modulo Selettore punto vendita](store-selector.md). Questa funzionalità è disponibile a partire da Commerce versione 10.0.15.|
|Opzioni di suggerimento automatico| Un numero| Se i suggerimenti di indirizzo automatici sono abilitati, è possibile specificare opzioni aggiuntive, come il numero massimo di suggerimenti da fornire.|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Aggiungere un modulo di indirizzi di spedizione a una pagina Checkout e impostare le proprietà necessarie

Un modulo di indirizzi di spedizione può essere aggiunto solo a un modulo checkout. Per ulteriori informazioni su come configurare il modulo di indirizzi di spedizione e aggiungerlo a una pagina di checkout, vedere [Modulo Checkout](add-checkout-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)

[Memorizzare il modulo di selezione](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
