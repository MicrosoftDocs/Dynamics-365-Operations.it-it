---
title: Aggiungere suggerimenti sul prodotto su POS
description: In questo articolo viene descritto l'utilizzo dei suggerimenti sul prodotto in un dispositivo POS.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 170e2bf18aefc79a796620818c7100ff8e6e689a
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460058"
---
# <a name="add-product-recommendations-on-pos"></a>Aggiungere suggerimenti sul prodotto su POS

[!include [banner](includes/banner.md)]

Fondamentalmente, i suggerimenti sul prodotto sono un'applicazione aziendale trasformativa che si estende su tutte le aree commerciali per creare esperienze di scoperta di prodotti ricchi, coinvolgenti e personalizzati. Per implementare questa funzionalità sul POS, seguire i passaggi in [come aggiungere i suggerimenti si dispositivi POS.](add-recommendations-control-pos-screen.md) 

Per ulteriori informazioni sulle funzionalità di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scenari

I suggerimenti sul prodotto sono abilitati per i seguenti scenari di POS. Sono disponibili in Cloud POS o Modern POS (MPOS).

1. Nella pagina **Dettagli prodotto**:

    - Se un associato del punto vendita visita una pagina **Dettagli prodotto** quando visualizza le transazioni precedenti su più canali diversi, il servizio dei suggerimenti suggerisce articoli aggiuntivi che è probabile vengano acquistati insieme. A seconda dei componenti aggiuntivi per il servizio, i rivenditori possono mostrare i suggerimenti **Guarda articoli simili** e **Acquista descrizioni simili** per i prodotti, oltre ai suggerimenti personalizzati per gli utenti che hanno una precedente cronologia degli acquisti.

    [![Suggerimenti sulla pagina Dettagli prodotto.](./media/proddetails.png)](./media/proddetails.png)

2. Nella pagina **Transazione**:

    - Il motore dei suggerimenti suggerisce gli articoli in base all'intero elenco di articoli nel carrello che vengono acquistati insieme di frequente.

    > [!NOTE]
    > Per visualizzare i suggerimenti nella pagina **Transazione**, il rivenditore deve aggiornare il layout dello schermo in Dynamics 365 Commerce. Il controllo **Suggerimenti** deve essere rilasciato nella pagina **Transazione**.

    [![Suggerimenti nella pagina Transazione.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Configurare Commerce per abilitare i suggerimenti POS 

Per impostare i suggerimenti dei prodotti, conferma di aver completato il processo di provisioning per i suggerimenti dei prodotti di Commerce seguendo i passaggi descritti in [Abilitare i suggerimenti dei prodotti](../commerce/enable-product-recommendations.md). Per impostazione predefinita, i suggerimenti vengono visualizzati su entrambe le pagine **Dettagli prodotto** e **Dettagli cliente** dopo aver completato i passaggi di provisioning e i dati sono stati cucinati correttamente. 

## <a name="add-recommendations-to-the-transaction-screen"></a>Aggiungere suggerimenti alla schermata della transazione

1. Per aggiungere suggerimenti alla schermata della transazione, segui i passaggi in [Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md).
1. Per riflettere le modifiche apportate nella finestra di progettazione del layout dello schermo POS, esegui il processo di configurazione del canale **1070** in Commerce headquarters.

> [!NOTE] 
> Se vuoi abilitare i suggerimenti POS utilizzando il file CSV (valori separati da virgole) RecoMock, è necessario distribuire il file CSV alla libreria di risorse Microsoft Dynamics Lifecycle Services (LCS) prima di configurare il gestore layout. Se utilizzi il file CSV RecoMock, non devi abilitare i suggerimenti. Il file CSV è disponibile solo a scopo dimostrativo. È consigliato per i clienti o gli architetti di soluzioni che desiderano imitare l'aspetto degli elenchi di suggerimenti a scopo dimostrativo senza dover acquistare un'unità di stockkeeping (SKU) aggiuntiva.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
