---
title: Aggiungere un controllo di suggerimenti alla pagina della transazione su un dispositivo POS
description: "In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: eac70614770189d1e45f347b282c94e645e95b00
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Aggiungere un controllo di suggerimenti alla pagina della transazione su un dispositivo POS

[!include [banner](includes/banner.md)]

> [!NOTE]
> Durante la nuova progettazione della funzionalità del servizio di suggerimenti prodotto con un algoritmo migliore e nuove funzionalità orientate alla vendita al dettaglio, verrà rimossa la versione corrente di tale servizio. Per ulteriori informazioni vedere [Funzionalità rimosse o deprecate](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features). 

In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 for Retail.

È possibile visualizzare i suggerimenti di prodotti sul proprio dispositivo POS quando si utilizza Microsoft Dynamics 365 for Retail. *Suggerimenti* sono articoli a cui il cliente potrebbe essere interessato in base al relativo storico acquisti, articoli nell'elenco preferenze e che altri clienti hanno acquistato online e in punti vendita fisici. Per visualizzare i suggerimenti di prodotti, è necessario aggiungere un controllo alla schermata della transazione mediante la funzionalità di progettazione del layout dello schermo.

## <a name="open-layout-designer"></a>Aprire Progettazione layout
1.  Passare a **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **POS** &gt; **Layout schermo**.
2.  Utilizzare il filtro rapido per individuare la schermata a cui si desidera aggiungere il controllo. Ad esempio, filtrare il campo **ID layout schermo** utilizzando un valore pari a "F2CP16: 9M".
3.  Nell'elenco trovare e selezionare il record desiderato. Ad esempio, selezionare "Nome: F2CP16:9M ID layout schermo: F2CP16:9M".
4.  Fare clic su **Progettazione layout**.
5.  Seguire i prompt per avviare Progettazione layout. Quando vengono richieste le credenziali, immettere le stesse credenziali utilizzate quando la funzionalità Progettazione layout è stata avviata dalla pagina **Layout schermo**.
6.  Quando si effettua l'accesso, viene visualizzata una pagina simile a quella riportata di seguito. Il layout sarà diverso a seconda delle personalizzazioni effettuate per il punto vendita.

[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Scegliere un'opzione di visualizzazione
-----------------------

Sono disponibili due opzioni di configurazioni. Scegliere l'opzione che funziona in modo ottimale per il punto vendita e seguire le istruzioni rimanenti per completare l'impostazione del controllo. Le due opzioni sono le seguenti:
-   I suggerimenti sono sempre visibili.
-   Una scheda **Suggerimenti** viene visualizzata nella griglia sul lato destro della schermata.

#### <a name="to-make-recommendations-always-visible"></a>Per rendere i suggerimenti sempre visibili

1.  Ridurre l'altezza dell'area dei dettagli delle righe di transazione in modo che sia la stessa di quella del pannello del cliente alla sua sinistra.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  Dal menu a sinistra, trascinare il controllo dei suggerimenti tra l'area dei dettagli delle righe di transazione e la griglia dei pulsanti in basso al centro della schermata della transazione. Ridimensionare il controllo in modo da adattarlo a tale spazio.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.
4.  In Dynamics 365 for Retail, passare a **Vendita al dettaglio** &gt; **Vendita al dettaglio IT** &gt; **Programmazioni della distribuzione**.
5.  Nell'elenco, selezionare **1090 Registri**.
6.  Fare clic su **Esegui adesso**.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Per aggiungere una scheda Suggerimenti alla griglia dei pulsanti sul lato destro della schermata

1.  Fare clic con il pulsante destro del mouse sullo spazio vuoto sotto l'ultima scheda nella griglia dei pulsanti presente sul lato destro della pagina.
2.  Fare clic **Personalizza**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)
3.  Fare clic su **Nuova scheda**.
4.  Individuare la nuova scheda appena aggiunta. Potrebbe essere necessario scorrere verso il basso.
5.  Nell'elenco a discesa **Contenuti**, selezionare **Prodotti consigliati**. [![pic-6](./media/pic-6.png)](./media/pic-6.png)
6.  Nel campo **Etichetta**, digitare un nome per la scheda dei suggerimenti. Ad esempio, digitare "Prodotti consigliati".
7.  Nel campo **Immagine**, selezionare l'immagine che verrà visualizzata sulla scheda.
8.  Fare clic su **OK**. La nuova scheda viene visualizzata nella griglia dei pulsanti.
9.  Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.
10. In Dynamics 365 for Retail, passare a **Vendita al dettaglio** &gt; **Vendita al dettaglio IT** &gt; **Programmazioni della distribuzione**.
11. Nell'elenco, selezionare **1090 Registri**.
12. Fare clic su **Esegui adesso**.


<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica dei suggerimenti sul prodotto personalizzati](personalized-product-recommendations.md)




