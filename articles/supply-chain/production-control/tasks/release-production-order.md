---
title: Rilasciare un ordine di produzione
description: Questa procedura indica come rilasciare un ordine di produzione.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6d0db7f93e113d8f41effd68ce19aa065b031fd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573659"
---
# <a name="release-a-production-order"></a>Rilasciare un ordine di produzione

[!include [banner](../../includes/banner.md)]

Questa procedura indica come rilasciare un ordine di produzione. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Si tratta della quarta procedura su sette che spiega il ciclo di vita dell'ordine di produzione.

1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
    * Nella griglia selezionare un ordine di produzione con lo stato Programmato.  
2. Nel riquadro azioni fare clic su Ordine di produzione.
3. Fare clic su Rilascia.
    * In questa pagina, è possibile confermare il rilascio dell'intervallo selezionato di ordini di produzione. Fare clic su Seleziona se si desidera aggiungere ordini.  
    * Il passaggio di rilascio indica quando l'ordine di produzione viene rilasciato allo shop floor di produzione in modo che gli operatori dello shop floor possano indicare lo stato di avanzamento nei processi di produzione. I documenti di produzione che contengono le informazioni rilevanti sull'elaborazione dei processi possono essere emessi. Il lavoro del magazzino per il prelievo delle materie prime viene generato per gli articoli impostati per il processo di magazzino.  
4. Fare clic sulla scheda Generale.
    * Selezionare i report di produzione da stampare. Il report della scheda processi stampa una pagina per ciascun processo programmato e richiede che l'ordine di produzione venga programmato a livello di processo. Il report contiene informazioni sull'ora di inizio e di fine programmata, la quantità da produrre e la risorsa che elabora il processo. Il report del processo del ciclo di lavorazione raccoglie le stesse informazioni nella stessa pagina, ma non stampa una pagina per ciascun processo. Nel report Scheda del ciclo di lavorazione vengono visualizzate solo le operazioni ma non i processi. Di conseguenza, il report non richiede la programmazione dei processi, ma può essere utilizzato quando gli ordini di produzione vengono programmati a livello di operazione.  
5. Fare clic sulla casella di controllo Stampa scheda ciclo di lav.
6. Fare clic su OK.
7. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]