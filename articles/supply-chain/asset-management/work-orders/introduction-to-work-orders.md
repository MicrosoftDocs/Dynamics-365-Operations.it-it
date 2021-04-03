---
title: Introduzione agli ordini di lavoro
description: Questo argomento fornisce una panoramica degli ordini di lavoro in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e9890057ab852a7fb0d60056bb102ce15ac124e2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263736"
---
# <a name="introduction-to-work-orders"></a>Introduzione agli ordini di lavoro

[!include [banner](../../includes/banner.md)]



Gli ordini di lavoro sono utilizzati per gestire i processi di manutenzione, fornire le informazioni necessarie e registrarne il consumo. Ogni ordine di lavoro può contenere uno o più processi di ordine di lavoro e uno o più cespiti possono essere collegati a un ordine di lavoro. Ogni processo di ordine di lavoro definisce un processo di manutenzione programmato per il cespite.

Gli ordini di lavoro possono essere creati nei seguenti modi:

- Per i piani di manutenzione basati su calendario in cui è attivata l'impostazione "Crea automaticamente", automaticamente tramite [Piani di manutenzione programmata](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md).

- Per i cicli di manutenzione in cui è attivata l'impostazione "Crea automaticamente", automaticamente tramite [Programma cicli di manutenzione](../preventive-and-reactive-maintenance/maintenance-rounds.md).

- Per processi di manutenzione preventiva o richieste di manutenzione, da [Programma di manutenzione](../preventive-and-reactive-maintenance/maintenance-schedule.md).

- Manualmente

- Dalla pagina **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**.

>[!NOTE]
>I processi di ordine di lavoro correlati allo stesso cespite sono associati allo stesso ID di progetto.

## <a name="all-work-orders"></a>Tutti gli ordini di lavoro

Selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** per aprire la pagina elenco **Tutti gli ordini di lavoro**. In questa pagina vengono visualizzati tutti gli ordini di lavoro e alcune informazioni correlate.

Nella figura seguente è illustrato un esempio della pagina di elenco **Tutti gli ordini di lavoro**.

![Figura 1](media/01-work-orders.png)

Per visualizzare un elenco di ordini di lavoro attivi, selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro**. 

Per visualizzare un elenco di processi di ordini di lavoro contenenti cespiti installati in unità funzionali a cui si è collegati come lavoratore, selezionare **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Processi di manutenzione di ordine di lavoro personali in unità funzionali**. La relazione tra i lavoratori e le unità funzionali viene impostata nella pagina **Lavoratori**. Per ulteriori informazioni, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).

Di seguito sono riportati alcuni metodi di utilizzo della pagina **Tutti gli ordini di lavoro**:

- Nella visualizzazione griglia, selezionare un collegamento nella colonna **Ordine di lavoro** per visualizzare i dettagli relativi al record selezionato. È possibile selezionare **Modifica** per aprire il record da modificare.

- La visualizzazione dettagli contiene informazioni dettagliate relative all'ordine di lavoro.  

- Nella visualizzazione dettagli, selezionare la scheda **Righe** per visualizzare i dettagli del processo di ordine di lavoro oppure selezionare la scheda **Intestazione** per visualizzare i dettagli dell'ordine di lavoro.  

- Espandere il riquadro **Informazioni correlate** sul lato destro della pagina per visualizzare ulteriori informazioni correlate all'ordine di lavoro selezionato.

Nella figura seguente è illustrato un esempio della visualizzazione dettagli **Tutti gli ordini di lavoro**.

![Figura 2](media/02-work-orders.png)


I pulsanti del riquadro azioni sono organizzati in schede. Nella tabella seguente vengono brevemente descritte i pulsanti correlati a Gestione cespiti:



| Nome del pulsante                     | Descrizione                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifica                            | Modifica l'ordine di lavoro selezionato.                                                                                                                                                                                                                                           |
| Nuovi                             | Crea un nuovo ordine di lavoro.                                                                                                                                                                                                                                                  |
| Elimina                          | Elimina l'ordine di lavoro selezionato.                                                                                                                                                                                                                                         |
| Pool di ordini di lavoro                 | Aggiunge l'ordine di lavoro selezionato a un pool di ordini di lavoro o lo rimuove dal pool di ordini di lavoro.                                                                                                                                                                                           |
| Rettifica                          | Modifica le informazioni su data di inizio e di fine previste, livello di servizio, addetto alla manutenzione responsabile o gruppo di addetti alla manutenzione responsabile negli ordini di lavoro selezionati.                                                                                                                                     |
| Ordine di lavoro correlato              | Crea un nuovo ordine di lavoro correlato al processo di ordine di lavoro selezionato. È utile se si desidera registrare ordini di lavoro principali e secondari.                                                                                                                              |
| Copia ordine di lavoro                 | Crea un nuovo ordine di lavoro basato su un ordine di lavoro esistente.                                                                                                                                                                                                               |
| Storico eventi                   | Visualizza lo storico registrazioni per l'ordine di lavoro.                                                                                                                                                                                                                |
| Note del processo di manutenzione degli ordini di lavoro                           | Crea una descrizione dell'ordine di lavoro o inserisce note o commenti. Iniziare selezionando **Aggiungere timbro data/ora** per aggiungere il nome utente e un timbro data/ora alla nota. Le note vengono visualizzate nella scheda **Descrizione** della scheda dettaglio **Dettagli riga** della pagina **Ordine di lavoro**.         |
| Strumenti                           | Crea un elenco degli strumenti necessari in un ordine di lavoro. Gli strumenti sono impostati come risorse in **Amministrazione organizzazione** > **Risorse** > **Risorse**.                                                                                                      |
| Elenco di controllo di manutenzione           | Visualizza l'elenco di controllo per il cespite collegato all'ordine di lavoro.                                                                                                                                                                                                              |
| Errore del cespite                     | Visualizza o registra le informazioni dell'errore di un cespite. Queste informazioni vengono utilizzate per la gestione degli errori.                                                                                                                                                                                      |
| Tempi di fermo per la manutenzione            | Specifica i tempi di fermo per la manutenzione per un ordine di lavoro.                                                                                                                                                                                                                               |
| Valutazione delle condizioni            | Registra le misure di valutazione delle condizioni in ordine di lavoro.                                                                                                                                                                                                             |
| Contatori cespiti                 | Crea o visualizza le registrazioni contatore nel cespite.                                                                                                                                                                                                                     |
| Prevista                        | Visualizza o crea le previsioni in un ordine di lavoro.                                                                                                                                                                                                                               |
| Giornali di registrazione                        | Visualizza o crea giornali di registrazione di ordine di lavoro. Le righe dei giornali di registrazione possono essere copiate da previsioni.                                                                                                                                                                                         |
| Transazioni progetto            | Visualizza tutte le transazioni registrate correlate agli ordini di lavoro creati per il cespite.                                                                                                                                                                                             |
| Aggiorna stato ordine di lavoro           | Aggiorna lo stato del ciclo di vita dell'ordine di lavoro.                                                                                                                                                                                                                                                |
| Registro dello stato del ciclo di vita                      | Visualizza un registro contenente gli stati del ciclo di vita dell'ordine di lavoro selezionato.                                                                                                                                                                                                                   |
| Documenti cespiti                | Visualizza l'elenco dei documenti associati ai cespiti correlati a un ordine di lavoro. Tali documenti vengono impostati in **Gestione cespiti** > **Impostazione** > **Documenti cespiti**.                                                                                                 |
| Programma                        | Programma gli ordini di lavoro selezionati.                                                                                                                                                                                                                                      |
| Spedisci            | Programma l'ordine di lavoro selezionato per un lavoratore.                                                                                                                                                                                                                        |
| Elimina programmazione                 | Elimina la programmazione dell'ordine di lavoro selezionato.                                                                                                                                                                                                                          |
| Processi di manutenzione degli ordini di lavoro programmati             | Apre la pagina elenco **Processi di manutenzione ordine di lavoro programmati**.                                                                                                                                                                                                                             |
| Richiesta di acquisto ordine di lavoro | Apre la pagina elenco **Richiesta di acquisto ordine di lavoro**.                                                                                                                                                                                                                 |
| Acquisto ordine di lavoro             | Apre la pagina elenco **Acquisto ordine di lavoro**.                                                                                                                                                                                                                             |
| Controllo costi                    | Confronta i costi in budget e i costi effettivi nell'ordine di lavoro.                                                                                                                                                                                                                |
| Controllo ore                    | Confronta le ore previste e le ore effettive nell'ordine di lavoro.                                                                                                                                                                                                                |
| Report di ordine di lavoro               | Stampa un report di ordine di lavoro.                                                                                                                                                                                                                                                |
| Consumo ordine di lavoro          | Stampa un report del consumo.                                                                                                                                                                                                                                               |


I pulsanti della scheda **Ordine di lavoro** del gruppo **Progetto** del riquadro azioni sono correlati alle funzionalità nel modulo **Gestione progetti e contabilità** relativo a previsioni, giornali di registrazione e fatturazione.

>[!NOTE]
>Per includere le previsioni create in un ordine di lavoro quando si esegue la programmazione generale, utilizzare il modello previsionale selezionato nel modulo **Parametri di gestione cespiti**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]