---
title: L'opzione Ritira non appare nella pagina del carrello o nelle pagine dei dettagli del prodotto
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'opzione per il ritiro presso il punto vendita non viene visualizzata nella pagina del carrello o nelle pagine dei dettagli del prodotto.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 88367e13b4d079edb0816e301901828b65c437ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900310"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a>L'opzione "Ritira" non appare nella pagina del carrello o in quelle dei dettagli del prodotto

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'opzione per il ritiro presso il punto vendita non viene visualizzata nella pagina del carrello o nelle pagine dei dettagli del prodotto.

## <a name="description"></a>Descrizione

Il pulsante **Ritira** non appare nella pagina del carrello o nelle pagine dei dettagli del prodotto.

La figura seguente mostra un esempio di una pagina che include il pulsante **Ritira**.

![Pulsante Ritira.](media/pickup-button-missing.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a>Abilitare l'estensione BOPIS in Creazione di siti di Commerce

Per abilitare l'estensione "acquisto online, ritiro in negozio" (BOPIS) in Creazione di siti di Commerce, seguire questi passaggi.

1. Selezionare il sito.
1. Selezionare **Impostazioni sito**, quindi selezionare **Estensioni**.
1. Assicurarsi che l'opzione **Disabilita BOPIS** sia deselezionata.

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a>Configurare le modalità di consegna in Commerce Headquarters

Per configurare modalità di consegna in Commerce Headquarters, procedere come segue.

1. Selezionare **Approvvigionamento \> Impostazione \> Modalità di consegna**.
1. Assicurarsi che una modalità di consegna **Ritiro del cliente** sia stata creata e che alla stessa siano assegnati prodotti e indirizzi.
1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri**.
1. Nel riquadro di spostamento sinistro, selezionare **Ordini cliente**.
1. Assicurarsi che l'opzione **Modalità di consegna ritiro** sia configurata correttamente.

### <a name="configure-customer-orders-payments"></a>Configurare i pagamenti di ordini cliente

Per configurare i pagamenti di ordini cliente in Commerce Headquarters, seguire questi passaggi.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri**.
1. Nel riquadro di spostamento sinistro, selezionare **Ordini cliente**.
1. Nella Scheda dettaglio **Pagamenti**, assicurarsi che i campi **Termini di pagamento** e **Metodo di pagamento** siano impostati correttamente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare l'estensione BOPIS](../cpe-bopis.md)

[Abilitare più modalità di consegna ritiro per gli ordini cliente](../multiple-pickup-modes.md)

[Pagamenti ordini Commerce multicanale](../dev-itpro/commerce-payments.md)

[Memorizzare il modulo di selezione](../store-selector.md)
