---
title: Configurare valutazioni e recensioni
description: In questo argomento viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0aac4b680590a95f465d33950f2933c4a4582e54
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002199"
---
# <a name="configure-ratings-and-reviews"></a>Configurare valutazioni e recensioni


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Le valutazioni e le recensioni nei siti Web di e-Commerce consentono ai clienti di informarsi sui prodotti prima di deciderne l'acquisto mediante l'opinione di altri clienti riguardo a quei prodotti. Per i siti Web di e-Commerce, valutazioni e recensioni sono anche un meccanismo di raccolta dei riscontri dei clienti sui prodotti. 

Le valutazioni sono visualizzate nelle pagine elenco di prodotti, le pagine elenco di categorie, le pagine dei risultati delle ricerche e altre pagine del sito. Gli istogrammi delle valutazioni e le recensioni dei prodotti sono visualizzati nelle pagine dettagli prodotto (PDP). Un pulsante **Scrivi una recensione** consente ai clienti di inviare valutazioni e recensioni per un prodotto.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Modulo Valutazioni e recensioni nelle pagine dettagli prodotto 

Tre moduli visualizzano il riepilogo di valutazioni e recensioni nelle pagine dettagli prodotto:

- Modulo Scrivere una recensione
- Modulo Elenco recensioni prodotti
- Modulo Istogramma valutazioni
 
Nella figura seguente sono illustrati i moduli Valutazioni e recensioni in una pagina dettagli prodotto.

![Moduli Valutazioni e recensioni in una pagina dettagli prodotto](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Per informazioni su come ottimizzare i modelli e i layout di pagine dettagli prodotto in modo da condividere le configurazioni per moduli Valutazioni e recensioni tra molteplici pagine dettagli prodotto nel sito di e-Commerce, vedere [Panoramica modelli e layout](templates-layouts-overview.md).

Nella figura seguente viene illustrato come la finestra di dialogo **Aggiungi modulo** presenta i moduli Valutazioni e recensioni in Dynamics 365 Commerce.

![Finestra di dialogo Aggiungi modulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Modulo Scrivere una recensione

Il modulo Scrivere una recensione include un pulsante **Scrivi una recensione** che consente agli utenti di accedere, assegnare una valutazione e scrivere la recensione di un prodotto. Questo modulo consente inoltre agli utenti di modificare una valutazione o una recensione creata precedentemente. Questo modulo viene in genere visualizzato sopra i moduli Istogramma valutazioni ed Elenco recensioni prodotti in una pagina dettagli prodotto.

Nella seguente figura è illustrata la finestra di dialogo **Scrivi una recensione** che viene visualizzata quando un cliente seleziona **Scrivi una recensione**. Il cliente può utilizzare questa finestra di dialogo per inviare una valutazione e una recensione.

![Finestra di dialogo Scrivi una recensione](media/rnr-eCommerce-write-review-module.png)

Nella tabella seguente viene illustrata la proprietà del modulo Scrivere una recensione che deve essere configurata nello strumento di creazione.

| Nome proprietà | Valore        | Descrizione della proprietà                 |
|---------------|--------------|--------------------------------------|
| Nome          | Scrivi recensione | Il nome del modulo Scrivere una recensione. |

### <a name="ratings-histogram-module"></a>Modulo Istogramma valutazioni

Il modulo Istogramma valutazioni visualizza un istogramma delle valutazioni. Questo modulo viene visualizzato in genere tra i moduli Scrivere una recensione e il modulo Elenco recensioni prodotto in una pagina dettagli prodotto.

Il modulo Istogramma valutazioni non richiede alcuna configurazione. È sufficiente aggiungere il modulo nel modello di pagina dettagli prodotto. 

Nelle figure seguenti è illustrato un modello di pagina dettagli prodotto in Dynamics 365 Commerce quando i moduli Valutazioni e recensioni sono configurati per la visualizzazione nelle pagine dettagli prodotto.

![Modello di pagina dettagli prodotto quando valutazioni e recensioni sono configurate per la visualizzazione nelle pagine dettagli prodotto](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Modulo Elenco recensioni prodotti

Il modulo Elenco recensioni prodotti visualizza un elenco di recensioni di prodotti con opzioni di ordinamento, filtro e paginazione. Questo modulo è in genere visualizzato dopo il modulo Istogramma valutazioni in una pagina dettagli prodotto.

Nella tabella seguente sono illustrate le proprietà del modulo Elenco recensioni prodotti che devono essere configurate nello strumento di creazione.

| Nome proprietà              | Valore | Descrizione della proprietà |
|----------------------------|-------| ---------------------|
| Recensioni visualizzate in ogni pagina | 10    | Il numero di recensioni che devono essere visualizzate contemporaneamente in una pagina dettagli prodotto. Sono inclusi i pulsanti **Avanti** e**Indietro** di modo che gli utenti possano passare da una pagina all'altra delle recensioni. |

#### <a name="ratings-histogram--summary-view"></a>Istogramma delle valutazioni - Visualizzazione di riepilogo

Il modulo Elenco recensioni prodotti include uno slot in cui è possibile aggiungere un modulo Istogramma valutazioni. Nella figura seguente viene illustrato come è possibile aggiungere un modulo Istogramma valutazioni nel modulo Elenco recensioni prodotti in Dynamics 365 Commerce.

![Aggiungere un modulo Istogramma valutazioni in un modulo Elenco recensioni prodotti](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configurare un sito per visualizzare valutazioni e recensioni

I valori di configurazione per valutazioni e recensioni, ad esempio l'ID tenant, la lunghezza del testo della recensione e la lunghezza del titolo della recensione sono configurati a livello di sito. 

Per configurare un sito allo scopo di visualizzare valutazioni e recensioni, effettuare le operazioni indicate di seguito. 

1. Andare a **Home \> Siti**.
1. Selezionare il nome del sito. 
1. Andare a **Gestione sito \> Estendibilità**. 
1. Nel campo **Lunghezza massima testo recensione**, immettere il numero massimo di caratteri per il testo della recensione (ad esempio **1000**). 
1. Nel campo **Lunghezza massima titolo recensione**, immettere il numero massimo di caratteri per i titoli delle recensioni (ad esempio **55**). 
1. Selezionare **Salva e pubblica**. 

L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.

![Configurare un sito per visualizzare valutazioni e recensioni](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto

Una valutazione di un prodotto viene visualizzata sotto il titolo del prodotto nella parte superiore della pagina dettagli prodotto. La valutazione di un prodotto può essere configurata di modo che sia collegata alla sezione **Recensioni** della stessa pagina dettagli prodotto. 

Per collegare la valutazione di una prodotto alla sezione **Recensioni** della pagina dettagli prodotto, effettuare le seguenti operazioni.

1. Aprire il modello PDP. 
1. Andare a **Impostazioni modulo contenitore Casella acquisti**.
1. In **Casella acquisti**selezionare **Valutazioni prodotti**, quindi selezionare la casella di controllo **Collega clic a modulo Recensioni completo**.

L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.

![Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche

Per configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, procedere come segue.

1. Andare a **Home \> Siti**.
1. Selezionare il nome del sito. 
1. Andare a **Gestione sito \> Estendibilità**.
1. Nella scheda **Route**, in **Informativa sulla privacy e politica per valutazioni e recensioni**, selezionare **Aggiungi un collegamento**. Se un collegamento è già stato specificato e si desidera sostituirlo, selezionare il collegamento. 
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, quindi selezionare **OK**. 
1. Selezionare **Salva e pubblica**. 

L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.

![Configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e recensioni](ratings-reviews-overview.md)

[Consentire l'utilizzo di valutazioni e recensioni](opt-in-ratings-reviews.md)

[Gestire valutazioni e recensioni](manage-reviews.md)

[Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail](sync-product-ratings.md)
