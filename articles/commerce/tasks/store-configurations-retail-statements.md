---
title: " Configurazioni dei punti vendita per rendiconti di vendita al dettaglio"
description: In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di commercio.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e255c58997ed1c0ad5614b15867f14714a8bcfc8
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "4413609"
---
# <a name="store-configurations-for-retail-statements"></a> Configurazioni dei punti vendita per rendiconti di vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di commercio. Le dimensioni finanziarie dei punti vendita sono analizzate in un'altra procedura. Questa procedura utilizza la società dimostrativa USRT.

1. Nel **pannello di navigazione**, andare a **Moduli > Retail e Commerce > Canali > Punti vendita > Tutti i punti vendita**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su **Modifica**.
5. Le impostazioni nella Scheda dettaglio **Rendiconto/Chiusura** interessano la creazione, la convalida e la registrazione del rendiconto per l'archivio. Espandere la Scheda dettaglio **Rendiconto/Chiusura**.  
6. Nel campo **Metodo rendiconto**, selezionare il metodo in base al quale raggruppare le linee del rendiconto.  
7. Selezionare "Sì" in **Un rendiconto al giorno** se si deve creare un solo rendiconto al giorno quando si creano i rendiconti tramite il processo batch di creazione dei rendiconti.  
8. Il campo **Calcolo riepilogo incassi** definisce se si devono aggiungere tutti i riepiloghi incassi o solo l'ultimo.  
9. Nel campo **Arrotondamento**, selezionare il conto CoGe per la registrazione delle differenze di arrotondamento.  
10. Nel campo **Importo arrotondamento massimo**, immettere la differenza di arrotondamento massima consentita.
11. Nel campo **Registrazione**, immettere la differenza di registrazione totale massima consentita per un rendiconto.
12. Nel campo **Turno**, immettere la differenza totale massima in un turno di un rendiconto.  
13. Nel campo **Transazione**, immettere la differenza totale massima in una riga del rendiconto.  
14. Nel campo **Metodo di chiusura**, definire se le transazioni da includere nel rendiconto devono fanno parte di turno chiuso o se possono essere transazioni che rientrano nell'intervallo di data/ora definito.  
15. Nel campo **Fine giorno lavorativo**, immettere un'ora se le transazioni che si verificano dopo la mezzanotte devono essere registrate per il giorno precedente.  
16. Selezionare "Sì" in **Registra come giorno lavorativo** se le transazioni che si verificano dopo la mezzanotte devono essere registrate come parte del giorno precedente.  
17. Selezionare "Sì" in **Dividi per metodo rendiconto** per ottenere i rendiconti creati per ciascun metodo di rendiconto definito. Questa azione può essere utile se le prestazioni di registrazione devono essere migliorate per gli archivi con alti volumi di transazioni perché creano molti piccoli rendiconti che possono essere elaborati in parallelo.  
18. Nella Scheda dettaglio **Generale**, nel campo **Cliente predefinito**, è possibile selezionare il conto cliente da utilizzare per le vendite ai clienti che entrano.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]