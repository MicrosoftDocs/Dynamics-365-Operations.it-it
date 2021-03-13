---
title: Attività dei tempi di fermo per la manutenzione
description: Questo argomento spiega i tempi di fermo per la manutenzione sono utilizzati per ottenere una panoramica della capacità necessaria per eseguire processi di manutenzione di determinati cespiti durante un periodo specifico.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenanceStopCopy, EntAssetMaintenanceStopObject, EntAssetObjectProductionStop, EntAssetProductionStopType, EntAssetMaintenanceStop
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 986b2ae4cf7f7819caaf35e009fd4735f35e6928
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017957"
---
# <a name="maintenance-downtime-activities"></a>Attività dei tempi di fermo per la manutenzione

[!include [banner](../../includes/banner.md)]

I tempi di fermo per la manutenzione sono utilizzati per ottenere una panoramica della capacità necessaria per eseguire processi di manutenzione di determinati cespiti durante un periodo specifico. Ad esempio, è possibile creare una registrazione di tempi di fermo per la manutenzione per la Linea di produzione 10 nel Reparto di produzione 29-A del sito di produzione 02. La registrazione di tempi di fermo per la manutenzione comporta una data di inizio e una di fine che indicano il periodo in cui i cespiti associati all'interruzione per manutenzione non sono disponibili per la produzione.

**Attività tempi di fermo per manutenzione** è una panoramica delle righe di programma di manutenzione e dei processi di manutenzione di ordine di lavoro relativi ai cespiti associati durante il periodo specificato. Tutte le righe relative ai processi di manutenzione di ordine di lavoro hanno una data di inizio entro il periodo di interruzione per manutenzione. È possibile acquisire informazioni utili e apportare rettifiche ai processi di manutenzione pianificati:

- Ottenere una panoramica dei periodi di interruzione delle attrezzature di produzione (cespiti) necessari.  
- Ottenere una panoramica delle ore di manutenzione pianificata, raggruppate per competenze (gruppi di addetti alla manutenzione o addetti alla manutenzione responsabili), ad esempio carico di capacità di elettricisti, meccanici o altri gruppi di addetti alla manutenzione necessari per eseguire i processi di manutenzione pianificati.  
- Apportare modifiche alle righe di programma di manutenzione o ai processi di manutenzione di ordine di lavoro associati ai cespiti, ad esempio cambiare la data e l'ora di inizio e quelle di fine in una riga oppure selezionare altri addetti alla manutenzione per ottimizzare il flusso di lavoro degli addetti alla manutenzione e dei gruppi di addetti alla manutenzione.

Dopo la selezione dei cespiti in una registrazione di tempi di fermo per la manutenzione, tutte le righe di programma di manutenzione aperte e i processi di manutenzione di ordine di lavoro relativi agli ordini di lavoro attivi vengono inclusi nella registrazione dei tempi di fermo per la manutenzione.

## <a name="maintenance-downtime-activities"></a>Attività dei tempi di fermo per la manutenzione

Fare clic su **Gestione cespiti** > **Comune** > **Attività tempi di fermo per manutenzione** > **Tutte le attività tempi di fermo per manutenzione** per visualizzare un elenco di tutte le attività dei tempi di fermo per la manutenzione e alcune delle informazioni relative alle attività. Fare clic su un collegamento nella colonna **Attività tempi di fermo per manutenzione** per visualizzare i dettagli. Nella figura seguente è illustrato un esempio dell'elenco **Attività dei tempi di fermo per la manutenzione**.

![Figura 1](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>Creare un'attività di tempi di fermo per la manutenzione

1. Fare clic su **Gestione cespiti** > **Comune** > **Attività tempi di fermo per manutenzione** > **Tutte le attività tempi di fermo per manutenzione** o **Attività tempi di fermo per manutenzione attive**.

2. Fare clic su **Nuovo**.

3. Immettere un ID nel campo **Attività tempi di fermo per manutenzione** e un nome nel campo **Nome**.

4. Immettere il periodo dell'interruzione per manutenzione nei campi **Data/ora di inizio** e **Data/ora di fine**.

5. Nella Scheda dettaglio **Cespiti attività tempi di fermo per manutenzione** > fare clic su **Aggiungi riga** per aggiungere i cespiti, uno alla volta, all'attività dei tempi di fermo per la manutenzione.

6. Fare clic su **Salva** dopo che tutti i cespiti sono stati aggiunti. Nella figura seguente è illustrato un esempio di un'attività dei tempi di fermo per la manutenzione con i cespiti e i processi di manutenzione correlati.

7. I processi di manutenzione di ordine di lavoro e le righe di programma di manutenzione aperte associati ai cespiti selezionati sono visualizzati nelle Schede dettaglio **Processi di manutenzione ordine di lavoro risultanti** e **Righe programma di manutenzione**. Nella Scheda dettaglio **Generale** > gruppo **Ordini di lavoro** > campo **Ore previsioni di manutenzione** e nella Scheda dettaglio **Generale** > gruppo **Programma di manutenzione** > campo **Ore previsioni di manutenzione**, viene visualizzato il numero totale di ore previste per i processi di manutenzione di ordine di lavoro e le righe di programma di manutenzione.

Nella figura seguente è illustrato un esempio della visualizzazione dettagliata **Attività dei tempi di fermo per la manutenzione**.

![Figura 2](media/20-preventive-maintenance.png)

>[!NOTE]
>I processi di manutenzione di ordine di lavoro e le righe di programma di manutenzione relativi ai cespiti selezionati vengono aggiornati automaticamente se nuovi ordini di lavoro o righe di programma di manutenzione vengono creati dopo la creazione dell'attività dei tempi di fermo per la manutenzione. Ad esempio, se si programmano piani di manutenzione o cicli di manutenzione nei cespiti due giorni dopo la creazione dell'attività dei tempi di fermo per la manutenzione, nuove righe di programma di manutenzione vengono aggiunte all'attività dei tempi di fermo per la manutenzione.

8. In **Tutte le attività tempi di fermo per manutenzione** > **Attività tempi di fermo per manutenzione** > selezionare un'attività dei tempi di fermo per la manutenzione nell'elenco e fare clic su **Carico di capacità** per aprire la finestra di dialogo **Calcola carico di capacità**. Utilizzare questa finestra di dialogo per ottenere una panoramica del carico di capacità su, ad esempio, date, cespiti, tipi di cespite e tipi di processo di manutenzione. Da notare che le date visualizzate nella finestra di dialogo sono le date di inizio e fine selezionati **Attività tempi di fermo per manutenzione**. Questo calcolo sono inclusi i cespiti relativi all'attività dei tempi di fermo per la manutenzione.

9. Nella finestra di dialogo **Calcolare carico di capacità**, modificare la data di inizio e di fine se necessario e scegliere se includere o meno gli ordini di lavoro e i programmi di manutenzione nel calcolo. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli del calcolo del carico di capacità in relazione alle unità funzionali. Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutti i cespiti di un'unità funzionale, selezionati nell'attività dei tempi di fermo per la manutenzione verranno visualizzati nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore. Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del carico di capacità in tutti i livelli di unità funzionali a cui sono correlate.

10. Fare clic su **OK** per avviare il calcolo. Il numero totale di ore viene visualizzato nella panoramica. **Carico di capacità**. Nella scheda **Carico di capacità** > gruppi di riquadri azioni **Raggruppa per**, fai clic sui pulsanti appropriati per ottenere una panoramica più dettagliata dell'allocazione delle ore previste. Nella figura seguente vengono illustrati i risultati di un calcolo **Carico di capacità**.

![Figura 3](media/21-preventive-maintenance.png)

11. Dopo aver ottenuto una panoramica del carico di capacità, se si desidera modificare i processi di manutenzione di ordine di lavoro o le righe di programma di manutenzione, ritornare alla visualizzazione dettagli **Attività dei tempi di fermo per la manutenzione** e selezionare le righe da modificare nelle Schede dettaglio **Processi di manutenzione ordine di lavoro risultanti** e **Righe programma di manutenzione**.

12. Fare clic sul pulsante **Rettifica** e aggiornare le date di inizio e di fine previste, il livello di servizio o gli addetti alla manutenzione responsabili per i processi di manutenzione di ordine di lavoro o le righe di programma di manutenzione selezionati.

13. Fare clic su **OK** dopo aver apportato le modifiche. 

>[!NOTE]
>I processi di manutenzione di ordine di lavoro e le righe di programma di manutenzione non inclusi nel periodo di tempi di fermo per la manutenzione dopo aver apportato le modifiche, vengono rimossi automaticamente da **Attività tempi di fermo per manutenzione**.

14. In **Tutte le attività tempi di fermo per manutenzione** > **Attività tempi di fermo per manutenzione** > selezionare un'attività dei tempi di fermo per la manutenzione nell'elenco e fare clic su **Previsione articolo** per aprire la finestra di dialogo **Calcolare previsioni articolo**. Utilizzare questa finestra di dialogo per calcolare le previsioni relative agli articoli (pezzi di ricambio e altri articoli necessari) e per raggrupparli allo scopo di ottenere una panoramica, ad esempio, per data, cespite, tipo di cespite e tipo di processo di manutenzione. Da notare che le date visualizzate nella finestra di dialogo sono le date di inizio e fine selezionati **Attività tempi di fermo per manutenzione**. Questo calcolo include pezzi di ricambio e articoli relativi ai cespiti selezionati nell'attività dei tempi di fermo per la manutenzione.

15. Nella finestra di dialogo **Calcolare previsioni articolo**, modificare la data di inizio e di fine se necessario e scegliere se includere o meno gli ordini di lavoro e i programmi di manutenzione nel calcolo. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli del calcolo del carico di capacità in relazione alle unità funzionali. Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutti i cespiti di un'unità funzionale, selezionati nell'attività dei tempi di fermo per la manutenzione verranno visualizzati nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore. Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del carico di capacità in tutti i livelli di unità funzionali a cui sono correlate.

16. Fare clic su **OK** per avviare il calcolo. Il numero totale di previsioni articolo è visualizzato nella panoramica **Previsione articolo**. Nella scheda **Previsione articolo** > gruppi di riquadri azioni **Raggruppa per**, fai clic sui pulsanti appropriati per ottenere una panoramica più dettagliata dell'allocazione degli articoli previsti. Nella figura seguente vengono illustrati i risultati di un calcolo **Previsione articolo**.

![Figura 4](media/22-preventive-maintenance.png)

- È possibile copiare i cespiti da un'attività dei tempi di fermo per la manutenzione a un'altra. In **Tutte le attività tempi di fermo per manutenzione**, selezionare il pulsante **Copia attività tempi di fermo per manutenzione** e apportare le selezioni nei campi **Da attività tempi di fermo per manutenzione** e **A attività tempi di fermo per manutenzione** e fare clic su **OK**.
- In **Tutte le attività tempi di fermo per manutenzione**, fare clic sul pulsante **Righe programma di manutenzione** o **Ordini di lavoro attivi** per aprire i relativi elenchi e visualizzare le righe associate all'attività dei tempi di fermo per la manutenzione selezionata.

