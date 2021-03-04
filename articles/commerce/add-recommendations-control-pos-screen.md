---
title: Aggiungere suggerimenti alla schermata della transazione
description: In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: af2450b27106325a86f6db68f9791637694cda63
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413340"
---
# <a name="add-recommendations-to-the-transaction-screen"></a>Aggiungere suggerimenti alla schermata della transazione

[!include [banner](includes/banner.md)]


In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 Commerce. Per ulteriori informazioni sulle funzionalità di suggerimenti sul prodotto, leggere i [suggerimenti sul prodotto nella documentazione POS](product.md).


È possibile visualizzare i suggerimenti sul prodotto sul proprio dispositivo POS quando si utilizza Commerce. Per visualizzare i suggerimenti di prodotti, è necessario aggiungere un controllo alla schermata della transazione mediante la funzionalità di progettazione del layout dello schermo. 

## <a name="open-layout-designer"></a>Aprire Progettazione layout

1. Passare a **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **POS** &gt; **Layout schermo**.
2. Utilizzare il filtro rapido per individuare la schermata a cui si desidera aggiungere il controllo. Ad esempio, filtrare il campo **ID layout schermo** utilizzando il valore **F2CP16:9M**.
3. Nell'elenco trovare e selezionare il record desiderato. Ad esempio, selezionare **Nome: F2CP16:9M ID layout schermo: F2CP16:9M**.
4. Fare clic su **Progettazione layout**.
5. Seguire i prompt per avviare Progettazione layout. Quando vengono richieste le credenziali, immettere le stesse credenziali utilizzate quando la funzionalità Progettazione layout è stata avviata dalla pagina **Layout schermo**.
6. Quando si effettua l'accesso, viene visualizzata una pagina simile a quella riportata di seguito. Il layout sarà diverso a seconda delle personalizzazioni effettuate per il punto vendita.


    [![Progettazione layout](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Scelta di un'opzione visualizzata

Sono disponibili due opzioni di configurazioni. Scegliere l'opzione che funziona in modo ottimale per il punto vendita e seguire le istruzioni rimanenti per completare l'impostazione del controllo. Le due opzioni sono le seguenti:

- I suggerimenti sono sempre visibili.
- Una scheda **Suggerimenti** viene visualizzata nella griglia sul lato destro della schermata.

### <a name="make-recommendations-always-visible"></a>Rendere i suggerimenti sempre visibili


1. Ridurre l'altezza dell'area dei dettagli delle righe di transazione in modo che sia la stessa di quella del pannello del cliente alla sua sinistra.


    [![Altezza ridotta dell'area dei dettagli delle righe di transazione](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. Dal menu a sinistra, trascinare il controllo dei suggerimenti tra l'area dei dettagli delle righe di transazione e la griglia dei pulsanti in basso al centro della schermata della transazione. Ridimensionare il controllo in modo da adattarlo a tale spazio.

    [![Controllo per suggerimenti aggiunto al layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.
4. In Commerce, passare a **Retail e Commerce** &gt; **Vendita al dettaglio e commercio IT** &gt; **Programmazione della distribuzione**.
5. Nell'elenco, selezionare **1090 Registri**.
6. Fare clic su **Esegui adesso**.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Aggiunta di una scheda Suggerimenti alla griglia dei pulsanti sul lato destro della schermata

1. Fare clic con il pulsante destro del mouse sullo spazio vuoto sotto l'ultima scheda nella griglia dei pulsanti presente sul lato destro della pagina.

2. Fare clic su **Personalizza**.

    [![Finestra di dialogo Personalizzazione - Controllo scheda](./media/pic-5.png)](./media/pic-5.png)

3. Fare clic su **Nuova scheda**.
4. Individuare la nuova scheda appena aggiunta. Potrebbe essere necessario scorrere verso il basso.
5. Nell'elenco a discesa **Contenuti**, selezionare **Prodotti consigliati**.

    [![Selezione di Prodotti consigliati nel campo Contenuto](./media/pic-6.png)](./media/pic-6.png)

6. Nel campo **Etichetta**, digitare un nome per la scheda dei suggerimenti. Ad esempio, digitare "Prodotti consigliati".
7. Nel campo **Immagine**, selezionare l'immagine che verrà visualizzata sulla scheda.
8. Fare clic su **OK**. La nuova scheda viene visualizzata nella griglia dei pulsanti.
9. Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.
10. In Commerce, passare a **Retail e Commerce** &gt; **Vendita al dettaglio e commercio IT** &gt; **Programmazione della distribuzione**.
11. Nell'elenco, selezionare **1090 Registri**.
12. Fare clic su **Esegui adesso**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti sul prodotto nel POS](product.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]