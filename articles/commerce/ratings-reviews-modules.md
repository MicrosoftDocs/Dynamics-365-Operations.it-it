---
title: Moduli Valutazioni e recensioni
description: Questo articolo tratta i moduli di valutazione e recensione utilizzati nelle pagine dei dettagli del prodotto in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: ede42caac78dc48fa6315a2d3c22f1e0f12f0810
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283589"
---
# <a name="ratings-and-reviews-modules"></a>Moduli Valutazioni e recensioni

[!include [banner](includes/banner.md)]

Questo articolo tratta i moduli di valutazione e recensione utilizzati nelle pagine dei dettagli del prodotto in Microsoft Dynamics 365 Commerce.

Le valutazioni e le recensioni nei siti Web di e-Commerce consentono ai clienti di informarsi sui prodotti prima di deciderne l'acquisto e costituiscono anche un meccanismo di raccolta dell'opinione dei clienti riguardo ai prodotti. 

Le valutazioni sono visualizzate nelle pagine elenco di prodotti, le pagine elenco di categorie, le pagine dei risultati delle ricerche e altre pagine del sito. 

Gli istogrammi delle valutazioni e le recensioni dei prodotti sono visualizzati nelle pagine dettagli prodotto. Un pulsante **Scrivi una recensione** consente ai clienti di inviare valutazioni e recensioni per un prodotto. Le funzionalità di queste pagine dettagli prodotto sono controllate dai moduli di valutazione e recensione.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Modulo Valutazioni e recensioni nelle pagine dettagli prodotto 

Tre moduli visualizzano il riepilogo di valutazioni e recensioni nelle pagine dettagli prodotto:
- Modulo Scrivere una recensione
- Modulo Elenco recensioni prodotti
- Modulo Istogramma valutazioni
 
Nella figura seguente sono illustrati i moduli Valutazioni e recensioni in una pagina dettagli prodotto.

![Moduli Valutazioni e recensioni in una pagina dettagli prodotto.](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Per informazioni su come ottimizzare i modelli e i layout di pagine dettagli prodotto in modo da condividere le configurazioni per moduli Valutazioni e recensioni tra molteplici pagine dettagli prodotto nel sito di e-Commerce, vedere [Panoramica modelli e layout](templates-layouts-overview.md).

Nella figura seguente viene illustrato come la finestra di dialogo **Aggiungi modulo** presenta i moduli Valutazioni e recensioni in Dynamics 365 Commerce.
![Finestra di dialogo Aggiungi modulo.](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Modulo Scrivere una recensione

Il modulo Scrivere una recensione include un pulsante **Scrivi una recensione** che consente agli utenti di accedere, assegnare una valutazione e scrivere la recensione di un prodotto. Questo modulo consente inoltre agli utenti di modificare una valutazione o una recensione creata precedentemente. Questo modulo viene in genere visualizzato sopra i moduli Istogramma valutazioni ed Elenco recensioni prodotti in una pagina dettagli prodotto.
Nella seguente figura è illustrata la finestra di dialogo **Scrivi una recensione** che viene visualizzata quando un cliente seleziona **Scrivi una recensione**. Il cliente può utilizzare questa finestra di dialogo per inviare una valutazione e una recensione.

![Finestra di dialogo Scrivi una recensione.](media/rnr-eCommerce-write-review-module.png)

Nella tabella seguente viene illustrata la proprietà del modulo Scrivere una recensione che deve essere configurata nello strumento di creazione.

| Nome proprietà | Valore        | Descrizione della proprietà                 |
|---------------|--------------|--------------------------------------|
| Nome          | Scrivi recensione | Il nome del modulo Scrivere una recensione. |

### <a name="ratings-histogram-module"></a>Modulo Istogramma valutazioni

Il modulo Istogramma valutazioni visualizza un istogramma delle valutazioni. Questo modulo viene visualizzato in genere tra i moduli Scrivere una recensione e il modulo Elenco recensioni prodotto in una pagina dettagli prodotto.
Il modulo Istogramma valutazioni non richiede alcuna configurazione. È sufficiente aggiungere il modulo nel modello di pagina dettagli prodotto. Nelle figure seguenti è illustrato un modello di pagina dettagli prodotto in Dynamics 365 Commerce quando i moduli Valutazioni e recensioni sono configurati per la visualizzazione nelle pagine dettagli prodotto.
![Modello di pagina dettagli prodotto quando valutazioni e recensioni sono configurate per la visualizzazione nelle pagine dettagli prodotto.](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Modulo Elenco recensioni prodotti

Il modulo Elenco recensioni prodotti visualizza un elenco di recensioni di prodotti con opzioni di ordinamento, filtro e paginazione. Questo modulo è in genere visualizzato dopo il modulo Istogramma valutazioni in una pagina dettagli prodotto.
Nella tabella seguente sono illustrate le proprietà del modulo Elenco recensioni prodotti che devono essere configurate nello strumento di creazione.

| Nome proprietà              | Valore | Descrizione della proprietà |
|----------------------------|-------| ---------------------|
| Recensioni visualizzate in ogni pagina | 10    | Il numero di recensioni che devono essere visualizzate contemporaneamente in una pagina dettagli prodotto. Sono inclusi i pulsanti **Avanti** e **Indietro** di modo che gli utenti possano passare da una pagina all'altra delle recensioni. |

#### <a name="ratings-histogram--summary-view"></a>Istogramma delle valutazioni - Visualizzazione di riepilogo

Il modulo Elenco recensioni prodotti include uno slot in cui è possibile aggiungere un modulo Istogramma valutazioni. Nella figura seguente viene illustrato come è possibile aggiungere un modulo Istogramma valutazioni nel modulo Elenco recensioni prodotti in Dynamics 365 Commerce.

![Aggiungere un modulo Istogramma valutazioni in un modulo Elenco recensioni prodotti.](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo carrello](add-cart-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
