---
title: Configurare valutazioni e revisioni
description: In questo articolo viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 27b1beddd474a2ca4db73f8e344b2d85934c43b1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276867"
---
# <a name="configure-ratings-and-reviews"></a>Configurare valutazioni e revisioni

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.

Le valutazioni e le recensioni nei siti Web di e-Commerce consentono ai clienti di informarsi sui prodotti prima di deciderne l'acquisto mediante l'opinione di altri clienti riguardo a quei prodotti. Per i siti Web di e-Commerce, valutazioni e recensioni sono anche un meccanismo di raccolta dei riscontri dei clienti sui prodotti. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configurare un sito per visualizzare valutazioni e recensioni

I valori di configurazione per valutazioni e recensioni, ad esempio l'ID tenant, la lunghezza del testo della recensione e la lunghezza del titolo della recensione sono configurati a livello di sito. 

Per configurare un sito allo scopo di visualizzare valutazioni e recensioni, effettuare le operazioni indicate di seguito. 

1. Andare a **Home \> Siti**.
1. Selezionare il nome del sito. 
1. Andare a **Impostazioni del sito \> Estensioni**. 
1. Nel campo **Lunghezza massima testo recensione**, immettere il numero massimo di caratteri per il testo della recensione (ad esempio **1000**). 
1. Nel campo **Lunghezza massima titolo recensione**, immettere il numero massimo di caratteri per i titoli delle recensioni (ad esempio **55**). 
1. Selezionare **Salva e pubblica**. 

L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.

![Configurare un sito per visualizzare valutazioni e recensioni.](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto

Una valutazione di un prodotto viene visualizzata sotto il titolo del prodotto nella parte superiore della pagina dettagli prodotto. La valutazione di un prodotto può essere configurata di modo che sia collegata alla sezione **Recensioni** della stessa pagina dettagli prodotto. 

Per collegare la valutazione di una prodotto alla sezione **Recensioni** della pagina dettagli prodotto, effettuare le seguenti operazioni.

1. Aprire il modello PDP. 
1. Andare a **Impostazioni modulo contenitore Casella acquisti**.
1. In **Casella acquisti** selezionare **Valutazioni prodotti**, quindi selezionare la casella di controllo **Collega clic a modulo Recensioni completo**.

L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.

![Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto.](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche

Per configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, procedere come segue.

1. Andare a **Home \> Siti**.
1. Selezionare il nome del sito. 
1. Andare a **Impostazioni del sito \> Estensioni**.
1. Nella scheda **Route**, in **Informativa sulla privacy e politica per valutazioni e recensioni**, selezionare **Aggiungi un collegamento**. Se un collegamento è già stato specificato e si desidera sostituirlo, selezionare il collegamento. 
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, quindi selezionare **OK**. 
1. Selezionare **Salva e pubblica**. 

L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.

![Configurare il collegamento per la pagina dell'informativa sulla privacy e dei criteri.](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>Configurare i moduli di valutazione e recensione nelle pagine dei dettagli del prodotto

Per informazioni sulla configurazione dei moduli di valutazione e recensione nelle pagine dei dettagli del prodotto, vedere [Moduli Valutazioni e recensioni](ratings-reviews-modules.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e revisioni](ratings-reviews-overview.md)

[Consentire utilizzo di valutazioni e sulle revisioni](opt-in-ratings-reviews.md)

[Gestire valutazioni e revisioni](manage-reviews.md)

[Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail](sync-product-ratings.md)

[Abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore](manual-publish-rating-reviews.md)

[Importare ed esportare valutazioni e recensioni](import-export-reviews.md)

[Configurare l'autenticazione da servizio a servizio](service-to-service-auth.md)

[Recensioni e valutazioni - Domande frequenti](ratings-reviews-faq.md)

[Moduli Valutazioni e recensioni](ratings-reviews-modules.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
