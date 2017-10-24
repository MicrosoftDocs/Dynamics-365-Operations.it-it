--- 
title: " Configurazioni dei punti vendita per rendiconti di vendita al dettaglio"
description: "In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cac676c9c6ebb6769fe7e30ac08a2c8334befc24
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="store-configurations-for-retail-statements"></a> Configurazioni dei punti vendita per rendiconti di vendita al dettaglio

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio. Le dimensioni finanziarie dei punti vendita al dettaglio sono analizzate in un'altra procedura. Questa procedura utilizza la società dimostrativa USRT.

1. Passare a Vendita al dettaglio e commercio > Canali > Punti vendita al dettaglio > Tutti i punti vendita al dettaglio.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Le impostazioni nella sezione Rendiconto/Chiusura interessa la creazione, la convalida e la registrazione del rendiconto per l'archivio.  Aprire la sezione Rendiconto/Chiusura.  
    * Selezionare il metodo da utilizzare per raggruppare le linee del rendiconto.  
    * Selezionare "Sì" se si deve creare un solo rendiconto al giorno quando si creano i rendiconti tramite il processo batch di creazione dei rendiconti.  
    * Il campo Calcolo riepilogo incassi definisce se si devono aggiungere tutti i riepiloghi incassi o solo l'ultimo.  
    * Selezionare il conto CoGe per la registrazione delle differenze di arrotondamento.  
    * Nel campo Importo arrotondamento massimo, è possibile immettere la differenza di arrotondamento massima consentita.  
    * Nel campo Registrazione, è possibile immettere la differenza di registrazione totale massima consentita per un rendiconto.  
    * Nel campo Turno, è possibile immettere la differenza totale massima in un turno di un rendiconto.  
    * Nel campo Transazione, è possibile immettere la differenza totale massima in una riga del rendiconto.  
    * Nel campo Metodo di chiusura, è possibile definire se le transazioni da includere nel rendiconto devono fanno parte di turno chiuso o se possono essere transazioni che rientrano nell'intervallo di data/ora definito.  
    * Nel campo Fine giorno lavorativo, è possibile immettere un'ora se le transazioni che si verificano dopo la mezzanotte devono essere registrate per il giorno precedente.  
    * Selezionare "Sì" se le transazioni che si verificano dopo la mezzanotte devono essere registrate come parte del giorno precedente.  
    * Selezionare "Sì" per ottenere i rendiconti creati per ciascun metodo di rendiconto definito. Ciò può essere utile se le prestazioni di registrazione devono essere migliorate per gli archivi con alti volumi di transazioni perché creano molti piccoli rendiconti che possono essere elaborati in parallelo.  
    * Nel campo Cliente predefinito, è possibile selezionare il conto cliente da utilizzare per le vendite ai clienti che entrano.  


