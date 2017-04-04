---
title: "Aggiungere un controllo di suggerimenti alla pagina delle transazioni per un&quot;unità di Retail POS"
description: "In questo argomento viene descritto come aggiungere un controllo di suggerimenti su schermo delle transazioni per un&quot;unità di (POS) del POS mediante Progettazione layout dello schermo in Microsoft Dynamics 365 per le operazioni."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Aggiungere un controllo di suggerimenti alla pagina delle transazioni per un'unità di Retail POS

In questo argomento viene descritto come aggiungere un controllo di suggerimenti su schermo delle transazioni per un'unità di (POS) del POS mediante Progettazione layout dello schermo in Microsoft Dynamics 365 per le operazioni.

È possibile visualizzare i suggerimenti del prodotto nell'unità di Retail POS quando si utilizza Microsoft Dynamics 365 per le operazioni. il *Recommendations* è articoli che il cliente potrebbe essere interessato in base al storico acquisti, gli articoli nell'elenco di obiettivi e gli articoli che altri clienti essi acquistati in linea e le quantità richieste di mattone-e- mortaio. Per visualizzare i suggerimenti del prodotto, è necessario aggiungere un controllo della stampa transazione mediante Progettazione layout dello schermo.

## <a name="open-layout-designer"></a>Aprire Progettazione layout
1.  ** Va al dettaglio e il commercio ** &gt; ** il Manica impostato ** &gt; ** POS configurato ** &gt; ** POS ** &gt; ** layout dello schermo **.
2.  Utilizzare il filtro rapido per individuare lo schermo che si desidera aggiungere al controllo. Ad esempio, filtrare il ** ID layout dello schermo ** il campo utilizzando un valore pari a F2CP16: 9M".
3.  Nell'elenco trovare e selezionare il record desiderato. Ad esempio, selezionare il nome ": F2CP16: ID layout dello schermo di 9M: F2CP16: 9M".
4.  ** Fare clic su Progettazione layout **.
5.  Utilizzare le richieste per aprire Progettazione layout. Quando richiesto per le credenziali, immettere le stesse credenziali cui è utilizzata quando Progettazione layout è stato avviato ** layout dello schermo ** dalla pagina.
6.  Quando si apre la sessione, una pagina simile a quella di seguito viene publicata. Il layout verrà diverso a seconda delle personalizzazioni effettuate per il punto vendita.

![[] (screenlayout-pic-1. /media/screenlayout-pic-1.png)](. /media/screenlayout-pic-1.png) Scelgono un'opzione di visualizzazione
-----------------------

Sono disponibili due opzioni di configurazioni disponibili. Scegliere l'opzione che funziona in modo ottimale per la memoria e seguire le istruzioni rimanenti il completamento di impostare il controllo. Le due opzioni sono:
-   I premi produttività vengono sempre disponibili.
-   A ** suggerimenti ** scheda viene visualizzata la griglia sul lato destro dello schermo.

#### <a name="to-make-recommendations-always-visible"></a>Per rendere i suggerimenti sempre visibili

1.  Ridurre l'altezza dell'area dei dettagli delle righe di transazione in modo che sia la stessa quella del pannello del cliente relativa a sinistra. [] (. /media/pic-2.png![) [] (screenlayout-pic-2. /media/screenlayout-pic-2.png)](. /media/screenlayout-pic-2.png)
2.  Dal menu a sinistra, la la chiusura e il controllo di suggerimenti tra all'area dettagli riga di transazione e la griglia dei pulsanti nella parte inferiore dello schermo centrale di transazione. Ridimensiona il controllo in modo che va bene per quello spazio. [] (. /media/pic-3.png![) [] (screenlayout-pic-3. /media/screenlayout-pic-3.png)](. /media/screenlayout-pic-3.png)
3.  ** Cliccano X ** per salvare le modifiche e chiudere la finestra di progettazione del layout.
4.  In Dynamics 365 per le operazioni, spostarsi ** al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazioni di distribuzione **.
5.  Nell'elenco selezionare, immettere 1090 ** **.
6.  Fare clic su ** esecuzione ora **.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Per aggiungere una scheda di suggerimenti alla griglia dei pulsanti a destra dello schermo

1.  Fare clic con il pulsante destro del mouse sullo spazio vuoto sotto l'ultima scheda nella griglia dei pulsanti presente sul lato destro della pagina.
2.  Per personalizzare ** **.![[] (pic-5. /media/pic-5.png)](. /media/pic-5.png)
3.  Fare clic su ** nuova scheda **.
4.  Individuare la nuova scheda aggiunti appena. Può essere necessario necessario scorrere l'elenco.
5.  ** Contenuto ** in a discesa, selezionare ** prodotti consigliati **. ![[] (pic-6. /media/pic-6.png)](. /media/pic-6.png)
6.  ** Etichetta ** nel campo, digitare un nome per il foglio di suggerimenti. Ad esempio, digitare "i prodotti consigliati".
7.  In ** immagine ** sistemi, selezionare l'immagine da visualizzare nella scheda.
8.  Click **OK**. La nuova scheda viene visualizzata nella griglia.
9.  ** Cliccano X ** per salvare le modifiche e chiudere la finestra di progettazione del layout.
10. In Dynamics 365 per le operazioni, spostarsi ** al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazioni di distribuzione **.
11. Nell'elenco selezionare, immettere 1090 ** **.
12. Fare clic su ** esecuzione ora **.


<a name="see-also"></a>Vedere anche
--------

[] Panoramica personale di suggerimenti prodotto (personalized-product-recommendations.md)


