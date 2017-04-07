---
title: Panoramica personale di suggerimenti del prodotto
description: "In Dynamics 365 per le operazioni, i suggerimenti prodotto possono essere visualizzata nell&quot;unità di (POS) del POS. I premi produttività vengono articoli che il cliente potrebbe essere interessato in base al storico acquisti, gli articoli nell&quot;elenco di obiettivi e gli articoli che altri clienti essi acquistati in linea e le quantità richieste di mattone-e- mortaio. Per i rivenditori ai cataloghi grandi dimensioni, i suggerimenti per semplificare il cliente con l&quot;importo rilevamento del prodotto. Montrando i prodotti mirati agli interessi di un cliente e alle di acquisto, i suggerimenti del prodotto sono disponibili i rivenditori alla vendita e la vendita e grado della ritenuta cliente. In Dynamics 365 per le operazioni, i suggerimenti dei prodotti sono alimentate dai servizi eapprendimento automatico conoscitivi di Microsoft Azure."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: af1f4ba1ed5efe0e35d08d37d09e7ada4a4c1b7a
ms.lasthandoff: 03/31/2017


---

# <a name="personalized-product-recommendations-overview"></a>Panoramica personale di suggerimenti del prodotto

In Dynamics 365 per le operazioni, i suggerimenti prodotto possono essere visualizzata nell'unità di (POS) del POS. I premi produttività vengono articoli che il cliente potrebbe essere interessato in base al storico acquisti, gli articoli nell'elenco di obiettivi e gli articoli che altri clienti essi acquistati in linea e le quantità richieste di mattone-e- mortaio. Per i rivenditori ai cataloghi grandi dimensioni, i suggerimenti per semplificare il cliente con l'importo rilevamento del prodotto. Montrando i prodotti mirati agli interessi di un cliente e alle di acquisto, i suggerimenti del prodotto sono disponibili i rivenditori alla vendita e la vendita e grado della ritenuta cliente. In Dynamics 365 per le operazioni, i suggerimenti dei prodotti sono alimentate dai servizi eapprendimento automatico conoscitivi di Microsoft Azure.

<a name="scenarios"></a>Scenari
---------

I suggerimenti dei prodotti sono abilitate per gli scenari di Retail POS. Sono disponibili in Retail POS su cloud o in Retail moderno (MPOS).

1.  ** Dettagli prodotto ** nella pagina:

-   Se un livello del punto vendita visitare alla ** dettagli del prodotto ** pagina per controllare le transazioni precedenti tra i canali diversi, il motore di suggerimento suggerisce gli articoli aggiuntivi che possono essere acquistati set.
-   Se il livello del punto vendita viene aggiunto un cliente alla transazione e quindi visualizza la quale ** dettagli del prodotto ** pagina, il motore di suggerimento vengono forniti suggerimenti personali utilizzando lo storico transazioni cliente.

[proddetails![(]. /media/proddetails.png)](. /media/proddetails.png)

2.  ** Transazione ** nella pagina:

-   Il motore di suggerimento suggerisce gli articoli in base all'intero elenco di articoli nel carrello.
-   Se il livello del punto vendita viene aggiunto un cliente alla transazione, il motore di suggerimento vengono forniti suggerimenti personali utilizzando lo storico transazioni cliente ed Elenco di articoli nel carrello.

** Nota ** visualizzare i suggerimenti su ** transazione ** la pagina, il rivenditore deve aggiornare il layout dello schermo in Dynamics 365 per le operazioni. ** Suggerimenti ** il controllo deve essere depositato su ** transazione ** nella pagina. ![[] (transactionscreenmultipleproductslargemessengersbag-5. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  ** Dettagli cliente ** nella pagina:
    -   Il motore di suggerimento suggerisce gli articoli in base all'ID utente e gli articoli nell'elenco di obiettivi del cliente.

[customerdetailsrecommendations![(]. /media/customerdetailsrecommendations.png)](. /media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Configurazione di Dynamics 365 per le operazioni successivo per consentire alle istruzioni di Retail POS
Per impostare i suggerimenti del prodotto, è necessario effettuare le seguenti operazioni.

1.  Assicurarsi di aver selezionato il corretto ** persona giuridica **.
2.  Spostamento ** il punto vendita dell'entità **, selezionare ** vendita al dettaglio ** quindi fare clic su ** aggiornare **. ** ** Il si basa sui dati dimostrativi o i dati dal database operativo e lo muoverà nel punto vendita dell'entità.
3.  Facoltativo: Per visualizzare i suggerimenti sulla transazione le schermate, passare ** layout dello schermo, scelgono ** il layout dello schermo, lanciano ** Progettazione layout dello schermo, ** ** ** quindi cadono ** controllo di suggerimenti ** in cui necessario.
4.  ** Parametri Passare al dettaglio, selezionare ** ** apprendimento automatico **, scegliere Sì ** ** in ** abilitare suggerimenti di Retail POS **.
5.  Per visualizzare i suggerimenti sul POS, globale processo di configurazione di esecuzione ** ** 1110. Per riflettere le modifiche eseguite a Progettazione layout dello schermo di Retail POS, eseguire il processo di configurazione dei canali ** ** 1070.

## <a name="how-does-it-work"></a>[] () funzionale?
Quando si aggiorna ** il record di entità ** l'entità, verranno effettuate le azioni seguenti.

-   I dati nel formato richiesto da servizi conoscitivi vengono estratti da Dynamics 365 per il database operativo le operazioni e vengono inviati al punto vendita dell'entità.
-   I dati vengono utilizzati da azzurrata floor (ADF) di dati per eseguire la pulitura dei dati tramite gli script dell'hive come parte delle attività di ADF. I dati vengono archiviati puliti di immagazzinamento di chiazza.
-   I dati di archiviazione di chiazza vengono utilizzati dall'API conoscitivo di servizi per preparare un modello di suggerimento.

Quando viene attivata ** abilitare suggerimenti ** e vengono effettuati i processi di configurazione, verranno effettuate le azioni seguenti.

-   Le credenziali di modello e l'ID vengono recuperate tramite API e vengono archiviate in Dynamics 365 per il database operativo operazioni, nel web.config per l'AOS nonché nel server al dettaglio.
-   Le credenziali di modello e l'ID vengono rese disponibili di CRT in modo da poter soddisfare requisiti per i suggerimenti del prodotto dal POS e di cloud MPOS in modalità in linea.


<a name="see-also"></a>Vedere anche
--------

[Aggiungere un controllo di suggerimenti alla pagina delle transazioni per un'unità di Retail POS] () add-recommendations-control-pos-screen.md


