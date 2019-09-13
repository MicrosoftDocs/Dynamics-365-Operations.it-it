---
title: Introduzione agli ordini di lavoro
description: Questo argomento fornisce una panoramica degli ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9483c50a15fca566b1f5e089297795bbbe09c042
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875743"
---
# <a name="introduction-to-work-orders"></a>Introduzione agli ordini di lavoro

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Gli ordini di lavoro sono utilizzati per gestire i processi di manutenzione, fornire le informazioni necessarie sugli stessi e registrarne il consumo. Un ordine di lavoro può contenere uno o più processi di ordine di lavoro e uno o più cespiti possono essere collegati a un ordine di lavoro. Ogni riga di ordine di lavoro definisce un processo di manutenzione programmato per il cespite.

Gli ordini di lavoro possono essere creati manualmente o automaticamente:

- Automaticamente utilizzando il modulo **Programma piani di manutenzione** per i piani di manutenzione basati su calendario impostati su "Crea automaticamente".  

- Automaticamente utilizzando il modulo **Programma cicli di manutenzione**, per i piani di manutenzione impostati su "Crea automaticamente".  

- Creazione da un programma di manutenzione, che può consistere di processi di manutenzione preventiva o richieste di intervento di manutenzione.  

- Creazione di un ordine di lavoro manualmente.  

- Creazione di un ordine di lavoro da **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**.

>[!NOTE]
>I processi di ordine di lavoro correlati allo stesso cespite sono associati allo stesso ID di progetto.

## <a name="all-work-orders"></a>Tutti gli ordini di lavoro

Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** per aprire l'elenco. **Tutti gli ordini di lavoro** contiene un elenco di tutti gli ordini di lavoro e visualizza alcune delle informazioni relative a un ordine di lavoro.

![Figura 1](media/01-work-orders.png)

- Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** per visualizzare un elenco di ordini di lavoro attivi.

- Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Processi di manutenzione di ordine di lavoro personali in unità funzionali** per visualizzare un elenco di processi di ordine di lavoro contenenti cespiti installati in unità funzionali a cui si è associati come lavoratore (impostazione in [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md)).

- Nell'elenco **Tutti gli ordini di lavoro** (visualizzazione griglia), fare clic su un collegamento nella colonna **Ordine di lavoro** per visualizzare la visualizzazione dettagli del record selezionato. Fare clic sul pulsante **Modifica** per apportare modifiche.  

- La visualizzazione dettagli contiene informazioni dettagliate relative all'ordine di lavoro.  

- Nella visualizzazione dettagli, selezionare il collegamento **Righe** per visualizzare i dettagli del processo di ordine di lavoro oppure selezionare il collegamento **Intestazione** per visualizzare i dettagli dell'ordine di lavoro.  

- Il riquadro verticale **Informazioni correlate** nella parte destra della schermata contiene ulteriori informazioni relative all'ordine di lavoro. Espandere il riquadro per visualizzare le informazioni correlate per l'ordine di lavoro selezionato.  


![Figura 2](media/02-work-orders.png)


I pulsanti dei riquadri azioni sono organizzati in schede. Di seguito è riportata una breve descrizione dei pulsanti relativi a Gestione cespiti aziendali:



| Nome del pulsante                     | Descrizione                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifica                            | Modifica l'ordine di lavoro selezionato.                                                                                                                                                                                                                                           |
| Nuovi                             | Crea un nuovo ordine di lavoro.                                                                                                                                                                                                                                                  |
| CANC                          | Elimina l'ordine di lavoro selezionato.                                                                                                                                                                                                                                         |
| Pool di ordini di lavoro                 | Aggiunge l'ordine di lavoro selezionato a un pool di ordini di lavoro o lo rimuove dal pool di ordini di lavoro.                                                                                                                                                                                           |
| Rettifica                          | Modifica le informazioni su data di inizio e di fine previste, livello di servizio, addetto alla manutenzione responsabile o gruppo di addetti alla manutenzione responsabile negli ordini di lavoro selezionati.                                                                                                                                     |
| Ordine di lavoro correlato              | Crea un nuovo ordine di lavoro correlato al processo di ordine di lavoro selezionato. È utile se si desidera registrare ordini di lavoro principali e secondari.                                                                                                                              |
| Copia ordine di lavoro                 | Crea un nuovo ordine di lavoro basato su un ordine di lavoro esistente.                                                                                                                                                                                                                |
| Storico eventi                   | Visualizza lo storico registrazioni dell'ordine di lavoro.                                                                                                                                                                                                                |
| Note dei processi di manutenzione di ordine di lavoro                           | Crea una descrizione o inserisce note o commenti in un ordine di lavoro. Iniziare facendo clic sul pulsante **Aggiungere timbro data/ora** per aggiungere il nome utente e un timbro data/ora alla nota. Le note sono visualizzate nel modulo **Ordine di lavoro** > Scheda dettaglio **Dettagli riga** > scheda **Descrizione**. |
| Strumenti                           | Crea un elenco degli strumenti necessari in un ordine di lavoro. Gli strumenti sono impostati come risorse in **Amministrazione organizzazione** > **Comune** > **Risorse** > **Risorse**.                                                                                                      |
| Elenco di controllo di manutenzione           | Visualizza l'elenco di controllo per il cespite collegato all'ordine di lavoro.                                                                                                                                                                                                              |
| Errore di cespite                     | Visualizza o registra le informazioni sugli errori di un cespite da utilizzare per la gestione degli errori.                                                                                                                                                                                        |
| Tempi di fermo per la manutenzione            | Specifica i tempi di fermo per la manutenzione per un ordine di lavoro.                                                                                                                                                                                                                               |
| Valutazione delle condizioni            | Registra le misure di valutazione delle condizioni in ordine di lavoro.                                                                                                                                                                                                             |
| Contatori cespiti                 | Crea o visualizza le registrazioni contatore nel cespite.                                                                                                                                                                                                                     |
| Prevista                        | Visualizza o crea le previsioni in un ordine di lavoro.                                                                                                                                                                                                                               |
| Giornali di registrazione                        | Visualizza o crea giornali di registrazione di ordine di lavoro. Le righe dei giornali di registrazione possono essere copiate da previsioni.                                                                                                                                                                                         |
| Transazioni progetto            | Visualizza tutte le transazioni registrate correlate agli ordini di lavoro creati per il cespite.                                                                                                                                                                                             |
| Aggiorna stato ordine di lavoro                | Aggiorna lo stati del ciclo di vita dell'ordine di lavoro.                                                                                                                                                                                                                                                |
| Registro dello stato del ciclo di vita                       | Registro che visualizza gli stati del ciclo di vita dell'ordine di lavoro selezionato.                                                                                                                                                                                                                   |
| Documenti cespiti                | Visualizza l'elenco dei documenti associati ai cespiti correlati a un ordine di lavoro. Tali documenti vengono impostati in **Gestione cespiti** > **Impostazione** > **Documenti cespiti**.                                                                                                 |
| Programma                        | Programma gli ordini di lavoro selezionati.                                                                                                                                                                                                                                      |
| Spedisci            | Programma l'ordine di lavoro selezionato per un lavoratore.                                                                                                                                                                                                                        |
| Elimina programmazione                 | Elimina la programmazione dell'ordine di lavoro selezionato.                                                                                                                                                                                                                          |
| Processi di manutenzione ordine di lavoro programmati             | Apre la pagina elenco **Processi di manutenzione ordine di lavoro programmati**.                                                                                                                                                                                                                             |
| Richiesta di acquisto ordine di lavoro | Apre la pagina elenco **Richiesta di acquisto ordine di lavoro**.                                                                                                                                                                                                                 |
| Acquisto ordine di lavoro             | Apre la pagina elenco **Acquisto ordine di lavoro**.                                                                                                                                                                                                                             |
| Controllo costi                    | Confronta i costi in budget e i costi effettivi nell'ordine di lavoro.                                                                                                                                                                                                                |
| Controllo ore                    | Confronta le ore previste e le ore effettive nell'ordine di lavoro.                                                                                                                                                                                                                |
| Report di ordine di lavoro               | Stampa il report di ordine di lavoro.                                                                                                                                                                                                                                                |
| Consumo ordine di lavoro          | Stampa il report del consumo.                                                                                                                                                                                                                                               |


I pulsanti nella scheda **Ordine di lavoro** > gruppo **Progetto** sono associati alle funzionalità nel modulo **Gestione progetti e contabilità** relativo a previsioni, giornali di registrazione e fatturazione.

>[!NOTE]
>Le previsioni create in un ordine di lavoro possono essere incluse quando si esegue la programmazione generale utilizzando il modello previsionale selezionato nel modulo **Parametri di gestione cespiti**.

