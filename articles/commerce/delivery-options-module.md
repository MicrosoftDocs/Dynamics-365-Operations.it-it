---
title: Modulo Opzioni di consegna
description: In questo argomento vengono descritte le opzioni di consegna e la procedura per configurarle in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f9e8df576efd1e58fde235828823f31e87ed58bf
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2020
ms.locfileid: "4413622"
---
# <a name="delivery-options-module"></a>Modulo Opzioni di consegna

[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le opzioni di consegna e la procedura per configurarle in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I moduli delle opzioni di consegna consentono ai clienti di selezionare una modalità di consegna come la spedizione o il ritiro per il proprio ordine online. È necessario un indirizzo di spedizione per determinare la modalità di consegna. Se l'indirizzo di spedizione viene modificato, le opzioni di consegna devono essere recuperate di nuovo. Se un ordine include solo articoli che verranno prelevati in un punto vendita, questo modulo viene automaticamente nascosto.

Per informazioni su come configurare le modalità di consegna, vedere [Configurazione del canale online](channel-setup-online.md)e [Imposta la modalità di consegna](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Ciascuna modalità di consegna può avere un addebito associato. Per ulteriori informazioni su come attivare configurare le spese di consegna per un punto vendita online, vedere [Addebiti automatici avanzati omnicanale](omni-auto-charges.md).

Nella versione 10.0.13 di Commerce, il modulo delle opzioni di consegna è stato aggiornato per supportare le funzioni **Spese di intestazione senza ripartizione proporzionale** e **Spedizione come spese riga**. Se la ripartizione è disattivata, l'aspettativa è che il flusso di lavoro dell'e-commerce non consentirà una modalità di consegna mista per gli articoli nel carrello (ovvero, alcuni articoli sono selezionati per la spedizione, ma altri sono selezionati per il ritiro). La funzione **Spese di intestazione senza ripartizione proporzionale** richiede che il flag **Abilita la gestione della modalità di consegna coerente nel canale** sia abilitato in Commerce headquarters. Quando questo flag è abilitato, le spese di spedizione verranno applicate a livello di intestazione o a livello di riga, a seconda della configurazione in Commerce headquarters.

Il tema Fabrikam supporta una modalità di consegna mista, in cui alcuni articoli vengono selezionati per la spedizione ma altri vengono selezionati per il ritiro. In questa modalità, le spese di spedizione verranno ripartite proporzionalmente per tutti gli articoli selezionati per la modalità di consegna. Affinché una modalità di consegna mista funzioni, è necessario prima configurare la funzione **Spese di intestazione senza ripartizione proporzionale** in Commerce headquarters. Per ulteriori informazioni su questa configurazione, vedere [Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti](pro-rate-charges-matching-lines.md).

Se le spese di spedizione si applicano agli articoli, possono essere visualizzate nella riga del carrello per ogni articolo. Questa funzionalità richiede che la proprietà **Mostra le spese di spedizione su una voce** sia abilitata sia per il modulo carrello che per il modulo checkout. Per ulteriori informazioni, vedere [Modulo Carrello](add-cart-module.md) e [Modulo Checkout](add-checkout-module.md).

L'immagine seguente mostra un esempio di modulo Opzioni di consegna in una pagina checkout.

![Esempio di un modulo Opzioni di consegna su una pagina Checkout](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Proprietà del modulo Opzioni di consegna

| Proprietà | Valori | descrizione |
|----------|--------|-------------|
| Intestazione | Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un'intestazione facoltativa per il modulo delle opzioni di consegna. |
| Nome classe CSS personalizzato | Testo | Un nome della classe Cascading Style Sheets ( CSS) che verrà utilizzato per eseguire il rendering di questo modulo, se applicabile. |
| Filtra opzione modalità di consegna | **Non filtrare** o **Modalità non di spedizione** | Un valore che specifica se il modulo Opzioni di consegna deve filtrare tutte le modalità di consegna non di spedizione. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Aggiungere un modulo Opzioni di consegna a una pagina Checkout e impostare le proprietà necessarie

Un modulo delle opzioni di consegna può essere aggiunto solo a un modulo checkout. Per ulteriori informazioni su come configurare il modulo delle opzioni di consegna e aggiungerlo a una pagina di checkout, vedere [Modulo Checkout](add-checkout-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)

[Configurazione del canale online](channel-setup-online.md)

[Addebiti automatici avanzati omnicanale](omni-auto-charges.md)

[Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti](pro-rate-charges-matching-lines.md)

[Imposta la modalità di consegna](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
