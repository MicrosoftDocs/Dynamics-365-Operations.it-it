---
title: Programmare un ordine di produzione
description: Questa procedura indica come programmare un ordine di produzione.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b3fe8f6890c7d8ac8835503091642faa773f7f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431108"
---
# <a name="schedule-a-production-order"></a>Programmare un ordine di produzione

[!include [banner](../../includes/banner.md)]

Questa procedura indica come programmare un ordine di produzione. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Si tratta della terza procedura su sette che spiega il ciclo di vita dell'ordine di produzione.


## <a name="schedule-a-production-order"></a>Programmare un ordine di produzione
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
    * Selezionare un ordine di produzione con stato Stimato.  
2. Nel riquadro azioni fare clic su Programmazione.
3. Fare clic su Programma processi.
    * I parametri per la programmazione vengono impostati in questa pagina. È possibile impostare i parametri per utenti specifici o per tutti gli utenti.  
4. Nel campo di direzione di programmazione, selezionare "Avanti da oggi".
5. Immettere una data nel campo Data di programmazione.
6. Selezionare o deselezionare la casella di controllo Capacità limitata.
7. Selezionare o deselezionare la casella di controllo Materiale limitato.
8. Fare clic su OK.

## <a name="view-the-scheduling-results"></a>Visualizzare i risultati della programmazione
1. Nel riquadro azioni fare clic su Ordine di produzione.
2. Fare clic su Tutti i processi.
    * In questa pagina vengono visualizzati i processi programmati appena generati.  
3. Espandere o comprimere la sezione Programmazione.
    * Nella scheda dettaglio Programmazione, è possibile visualizzare la data e l'ora programmate.  
4. Fare clic su Richieste di informazioni.
5. Fare clic su Carico di capacità.
    * Nella pagina Carico di capacità è visualizzata la capacità prenotata tramite la programmazione processi, il numero totale di ore attualmente prenotato per la risorsa e il numero di ore rimanenti e disponibili per la programmazione processi della risorsa.  
6. Chiudere la pagina.
7. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]