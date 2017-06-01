---
title: Panoramica dei suggerimenti sul prodotto personalizzati
description: In Dynamics 365 for Operations, i suggerimenti d prodotti possono essere visualizzati nel dispositivo POS. I suggerimenti sono articoli a cui il cliente potrebbe essere interessato in base al relativo storico acquisti, articoli nell&quot;elenco preferenze e che altri clienti hanno acquistato online e in punti vendita fisici. Per i rivenditori con cataloghi di grandi dimensioni, i suggerimenti aiutano il cliente a individuare i prodotti. Mostrando i prodotti mirati agli interessi e alle abitudini di acquisto di un cliente, i suggerimenti sul prodotto possono aiutare i rivenditori con l&quot;upselling e il cross-selling e possono aumentare la ritenuta cliente. In Dynamics 365 for Operations, i suggerimenti sul prodotto sono generati da servizi cognitivi e da Microsoft Azure Machine Learning.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: edacd4cc9f9db59617bc579cb106e8e1017b8957
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="personalized-product-recommendations-overview"></a>Panoramica dei suggerimenti sul prodotto personalizzati

[!include[banner](includes/banner.md)]


In Dynamics 365 for Operations, i suggerimenti d prodotti possono essere visualizzati nel dispositivo POS. I suggerimenti sono articoli a cui il cliente potrebbe essere interessato in base al relativo storico acquisti, articoli nell'elenco preferenze e che altri clienti hanno acquistato online e in punti vendita fisici. Per i rivenditori con cataloghi di grandi dimensioni, i suggerimenti aiutano il cliente a individuare i prodotti. Mostrando i prodotti mirati agli interessi e alle abitudini di acquisto di un cliente, i suggerimenti sul prodotto possono aiutare i rivenditori con l'upselling e il cross-selling e possono aumentare la ritenuta cliente. In Dynamics 365 for Operations, i suggerimenti sul prodotto sono generati da servizi cognitivi e da Microsoft Azure Machine Learning.

<a name="scenarios"></a>Scenari
---------

I suggerimenti sul prodotto sono abilitati per i seguenti scenari di POS. Sono disponibili in Cloud POS o Modern POS (MPOS).

1.  Nella pagina **Dettagli prodotto**:

-   Se un associato del punto vendita visita una pagina **Dettagli prodotto** quando visualizza le transazioni precedenti su più canali diversi, il motore dei suggerimenti suggerisce articoli aggiuntivi che è probabile vengano acquistati insieme.
-   Se l'associato del punto vendita aggiunge un cliente alla transazione e quindi visita una pagina **Dettagli prodotto**, il motore dei suggerimenti fornisce suggerimenti personalizzati utilizzando lo storico transazioni del cliente.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  Nella pagina **Transazione**:

-   Il motore dei suggerimenti suggerisce articoli in base all'intero elenco di articoli nel carrello.
-   Se l'associato del punto vendita aggiunge un cliente alla transazione, il motore dei suggerimenti fornisce suggerimenti personalizzati utilizzando lo storico transazioni del cliente e l'elenco di articoli nel carrello.

**Nota**: per visualizzare i suggerimenti nella pagina **Transazione**, il rivenditore deve aggiornare il layout dello schermo in Dynamics 365 for Operations. Il controllo **Suggerimenti** deve essere rilasciato nella pagina **Transazione**. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  Nella pagina **Dettagli cliente**:
    -   Il motore dei suggerimenti suggerisce articoli in base all'ID utente e articoli nell'elenco preferenze del cliente.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Configurare Dynamics 365 for Operations per abilitare i suggerimenti POS
Per impostare i suggerimenti sul prodotto, è necessario effettuare le seguenti operazioni.

1.  Assicurarsi di aver selezionato la **Persona giuridica** corretta.
2.  Accedere ad **Archivio entità**, selezionare **Vendite al dettaglio**, quindi fare clic su **Aggiorna**.** ** In tal modo verranno utilizzati i dati dimostrativi (o i dati dell'utente) provenienti dal database operativo che verranno spostati nell'Archivio entità.
3.  Facoltativo: per visualizzare i suggerimenti sulla schermata della transazione, passare a **Layout schermo, **scegliere il layout dello schermo, avviare **Progettazione layout schermo**,** **quindi rilasciare il **controllo di suggerimenti** dove necessario.
4.  Passare a **Parametri di vendita al dettaglio**, selezionare **Machine-learning**, quindi scegliere **Sì **in **Abilita suggerimenti POS**.
5.  Per visualizzare i suggerimenti sul POS, eseguire il processo di configurazione globale **1110**. Per riflettere le modifiche apportate a Progettazione layout schermo POS, eseguire il processo di configurazione dei canali **1070**.

## <a name="how-does-it-work"></a>[]()Come funziona?
Quando si aggiorna l'entità **Archivio entità**, verranno effettuate le azioni seguenti.

-   I dati nel formato richiesto dai servizi cognitivi vengono estratti dal database operativo Dynamics 365 for Operations e vengono inviati all'Archivio entità.
-   I dati vengono utilizzati da Azure Data Factory (ADF) per eseguire la pulitura dei dati tramite gli script Hive come parte delle attività ADF. I dati puliti vengono archiviati nell'archiviazione BLOB.
-   I dati nell'archiviazione BLOB vengono utilizzati dall'API dei servizi cognitivi per preparare un modello di suggerimento.

Quando si attiva **Abilita suggerimenti** e si eseguono i processi di configurazione, verranno effettuate le azioni seguenti.

-   L'ID e le credenziali di modello vengono recuperate dall'API e archiviate nel database operativo di Dynamics 365 for Operations, nel file web.config per AOS e nel server vendita al dettaglio.
-   L'ID e le credenziali del modello vengono rese disponibili a CRT in modo da poter soddisfare le richieste di suggerimenti sul prodotto da Cloud POS e MPOS in modalità online.


<a name="see-also"></a>Vedere anche
--------

[Aggiungere un controllo di suggerimenti alla pagina della transazione su un dispositivo POS](add-recommendations-control-pos-screen.md)




