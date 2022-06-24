---
title: Applicare le impostazioni di visualizzazione per le dimensioni del prodotto
description: Questo articolo illustra le impostazioni di visualizzazione per le dimensioni del prodotto e descrive come applicarle in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d7575e205a9732259b00e424f66eeadfe8c659ee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899177"
---
# <a name="apply-display-settings-for-product-dimensions"></a>Applicare le impostazioni di visualizzazione per le dimensioni del prodotto

[!include [banner](includes/banner.md)]


Questo articolo illustra le impostazioni di visualizzazione per le dimensioni del prodotto e descrive come applicarle in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce supporta dimensioni, stile e colore per distinguere le varianti del prodotto. Le dimensioni vengono generalmente visualizzate come valori di testo, ad esempio "Piccolo", "Medio" e "Grande" per le dimensioni e "Nero" e "Marrone" per i colori. Tuttavia, se un prodotto supporta molte varianti potrebbe essere difficile esplorare le varianti di prodotto, poiché sono necessarie più selezioni per visualizzare l'immagine per ciascuna variante di prodotto. Per semplificare la ricerca delle varianti di prodotto, la versione 10.0.20 di Commerce può utilizzare immagini e codici esadecimali (esadecimali) per mostrare le dimensioni come campioni.

In Commerce Site Builder, le impostazioni di dimensione sono definite in **Impostazioni sito \> Estensioni \> Impostazioni dimensione**. La figura seguente mostra un esempio di impostazioni delle dimensioni in Site Builder.

![Esempio di impostazioni del sito in Creazione di siti Web Commerce.](./dev-itpro/media/swatch_site_settings.PNG)

Sono disponibili due impostazioni di dimensione:

- **Dimensioni da visualizzare come immagine**: specifica le dimensioni da visualizzare come campioni nelle pagine del sito di e-commerce come le pagine dei dettagli del prodotto (PDP) e le pagine dell'elenco dei risultati di ricerca. Qualsiasi combinazione di colore, dimensione e dimensioni dello stile può essere visualizzata come campione. Se una dimensione viene selezionata per la visualizzazione come campione, il rendering del modulo Commerce cercherà una configurazione disponibile di un campione di codice esadecimale. Se non è configurato alcun codice esadecimale, la logica di sistema cercherà una configurazione di un campione di URL immagine. Se non è configurato né un codice esadecimale né un URL immagine, verrà visualizzato il testo.

    La seguente illustrazione mostra un esempio in cui i colori vengono visualizzati come campioni su un PDP o un sito di e-commerce. In questo esempio, un codice esadecimale è configurato per la dimensione del colore. Pertanto, i campioni vengono visualizzati come colori. Tuttavia, per la dimensione non sono configurati né un codice esadecimale né un URL immagine. Pertanto, viene visualizzato il testo.

    ![Esempio della dimensione del colore mostrata come campioni nella pagina dei dettagli di un prodotto e-commerce.](./dev-itpro/media/swatch_pdp.png)

- **Dimensioni da visualizzare nella scheda prodotto**: specifica quali dimensioni devono apparire sulle schede prodotto che vengono mostrate negli elenchi e nelle pagine degli elenchi. Prima che una dimensione possa essere visualizzata su una scheda prodotto, questa impostazione deve essere abilitata per quella dimensione. Anche l'impostazione **Dimensioni da visualizzare come immagine** dovrebbe essere abilitata. Il comportamento di selezione dei campioni sulle schede prodotto è ottimizzato per la dimensione del colore. Per altre dimensioni, potrebbe essere necessaria un'estensione della visualizzazione per personalizzare il comportamento di selezione dei campioni.

    La figura seguente mostra un esempio in cui una pagina di elenco su un sito di e-commerce contiene schede prodotto che includono campioni di colore.

    ![Esempio della dimensione del colore mostrata come campioni nella pagina elenco e-commerce.](./dev-itpro/media/swatch_searchresults.PNG)

Per informazioni su come configurare le dimensioni del prodotto in modo che vengano visualizzate come campioni nelle pagine del sito, vedi [Configurare i valori delle dimensioni del prodotto in modo che appaiano come campioni](./dev-itpro/dimensions-swatch.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo dei risultati di ricerca](search-result-module.md)

[Modulo casella acquisti](add-buy-box.md)

[Configurare i valori di dimensione prodotto in modo che appaiano come campioni](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
