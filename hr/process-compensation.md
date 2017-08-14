---
title: Processo retributivo
description: Il processo retributivo consente di calcolare i nuovi importi relativi alla retribuzione di base per i dipendenti in base a rettifiche di capitale netto, obiettivi di incentivo per merito e prestazioni.
author: kherr
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 822c4581db76923c564bde34f8402b333a035f0b
ms.openlocfilehash: 28b825ba685b5a05764b25602ae32f1370c82e07
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="process-compensation"></a>Processo retributivo
Il processo retributivo consente di calcolare i nuovi importi relativi alla retribuzione di base per i dipendenti in base a rettifiche di capitale netto, obiettivi di incentivo per merito e prestazioni. Questo argomento descrive il flusso di base dell'elaborazione delle retribuzioni per i piani di retribuzione fissa senza factoring delle prestazioni di un dipendente.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Pianificare i nuovi budget e importi retributivi
Per concedere ai dipendenti un incentivo per merito, è necessario impostare un budget per incentivi fissi per ciascun reparto: Gestione retribuzioni > Collegamenti > Obiettivi incentivo per merito. In alternativa, è possibile aprire questo modulo dal reparto: Organizzazione > Reparti. In questo campo è possibile specificare ulteriormente se i dipendenti in un determinato sindacato o una determinata ubicazione devono ottenere una percentuale di incentivo diversa. I campi **Budget** e **Valuta** sono informativi e possono essere utilizzati per prendere nota un importo in valuta per il budget.

## <a name="set-up-the-compensation-process"></a>Impostare il processo retributivo
Un evento di processo consente di specificare i parametri per il processo retributivo. Sono inclusi il periodo di date da valutare per la determinazione degli importi retribuzione e la data di inizio validità dei nuovi importi di retribuzione.

Facoltativamente, è possibile includere una data di assunzione ripartizione proporzionale retribuzione fissa se uno dei piani di retribuzione fissa utilizza una regola di assunzione in percentuale. Per tali piani, qualsiasi utente assunto dopo la data di inizio del ciclo e prima della data di assunzione ripartizione proporzionale retribuzione fissa riceverà il 100% dell'incentivo generale o per merito calcolato. Qualsiasi persona assunta dopo la data di assunzione ripartizione proporzionale retribuzione fissa e prima della data di fine del ciclo riceverà una parte dell'incentivo calcolato in base al numero di giorni rispetto ai giorni totali del ciclo in cui è stato impiegato. Ad esempio, se il ciclo riguarda il periodo dal 1° gennaio al 31 dicembre e la data di assunzione ripartizione proporzionale retribuzione fissa è il 1° aprile, un dipendente assunto a marzo riceverà l'incentivo completo calcolato mentre un dipendente assunto il 1° luglio riceverà circa la metà dell'incentivo calcolato.

La data di **temporizzazione** dell'evento processo viene utilizzata solo per elaborare alcuni piani di retribuzione variabile e non viene trattata in questo argomento. **Scadenza revisione** è la data finale per applicare tutti i suggerimenti in modo da poter caricare nuovi importi di retribuzione nel record dipendente. La data di revisione è solo informativa.

Una volta che i parametri dell'evento processo sono stati salvati, è possibile fare clic sul pulsante **Imposta** per indicare i piani da includere nell'esecuzione del processo e le azioni di retribuzione fissa da intraprendere per ciascun piano.

Fare clic sul pulsante **Aggiunti** nella scheda **Piani** per aggiungere un piano di retribuzione all'evento processo. Le colonne **Usa altro fattore**, **Fattore** e **Descrizione fattore** vengono utilizzate solo per i piani di retribuzione variabile e non vengono descritte in questo argomento.

Salvare il record, quindi fare clic sul pulsante **Aggiungi** nella scheda **Azioni** per aggiungere le azioni di retribuzione fissa per il piano selezionato. Utilizzare l'opzione **Abilita suggerimento** se si desidera immettere un importo diverso dall'incentivo produttività calcolato per l'azione. Per calcolare un'azione in base al risultato dell'azione precedente per collegare più azioni di retribuzione, contrassegnare l'opzione **Usa risultato precedente**. Le azioni di retribuzione fissa sono tipi di logica retributiva a cui è possibile assegnare nomi descrittivi. Per i piani Scala e Fascia, è possibile aggiungere solo le azioni di retribuzione fissa dei seguenti tipi:

| Tipo di azione di retribuzione fissa. | Funzionalità                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Capitale netto                        | Le azioni di capitale netto metteranno a confronto il livello retributivo del dipendente alla data di fine del ciclo con il punto di riferimento minimo per il livello indicato sulla mansione del dipendente. Se il livello di retribuzione di un dipendente è inferiore al punto di riferimento minimo, verrà calcolato l'incentivo necessario per portare il dipendente sul punto minimo dell'intervallo.                                                                                |
| Merito                         | Le azioni di merito calcoleranno un incentivo in base al livello di retribuzione del dipendente alla data di fine del ciclo e la percentuale di incentivo trovata nel budget per incentivi fissi per il reparto, il sindacato e l'ubicazione del dipendente.                                                                                                                                                                                         |
| Generale                       | Le azioni generali calcoleranno un incentivo in base alla percentuale o concederanno ai dipendenti un importo forfettario. Ciò viene determinato in base alle impostazioni di **Retribuzione fissa** della scheda **Generale**.                                                                                                                                                                                                                        |
| Promozione                     | Le azioni di promozione forniscono un percorso con nome in cui è possibile assegnare un incentivo, pertanto è necessario contrassegnare l'opzione  **Abilita suggerimento** in modo che sia possibile immettere un suggerimento per i dipendenti che riceveranno le promozioni.  Per i dipendenti senza un incentivo suggerito non verrà aggiunta l'azione **Promozione** ai record di retribuzione fissa.                                                                       |
| Altra modifica livello            | Nell'esempio precedente, **Declassamento** è il nome dell'azione di **Retribuzione fissa** con un tipo di **Altra modifica livello**. Ciò genera un incentivo produttività pari a 0 (zero modifiche) in modo che sia possibile immettere un importo di suggerimento per rettificare la retribuzione del dipendente. Accertarsi di contrassegnare l'opzione **Abilita suggerimento**. I dipendenti senza un suggerimento non avranno questa azione aggiunta ai loro record di retribuzione fissa. |

È possibile aggiungere solo le azioni di **Retribuzione fissa** di tipo piano da passo a passo.

| Tipo di azione di retribuzione fissa. | Funzionalità                                                                                                                                                                                           |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Graduale                           | Nella scheda Generale, indicare se questa azione passaggio deve spostare i dipendenti in avanti di 0 passi, 1 passo  o due passi.                                                                                  |
|                                | **0 passi**: il dipendente riceverrà la retribuzione per il passo corrente che hanno superato.                                                                                                                      |
|                                | **1 passo**: il sistema controllerà se il dipendente è già all'ultimo punto di riferimento per il livello.                                                                                             |
|                                | **2 passi**: il sistema sposterà il dipendente in avanti di due passi sul livello corrente. Il sistema può spostare solo il dipendente di uno o zero passi se raggiunge l'ultimo punto di riferimento per il livello. |

## <a name="run-the-compensation-process"></a>Eseguire il processo retributivo
Dopo che l'evento processo è stato impostato con i campi data, i piani e le azioni necessari, è possibile fare clic su **Esegui processo** nella pagina **Evento processo**. In tal modo viene visualizzata la finestra di dialogo per **eseguire eventi processo di retribuzione**. All'interno di questa finestra di dialogo, è possibile fare clic sull'opzione **Mostra risultati di elaborazione** per vedere come gli importi di retribuzione sono stati calcolati per ciascun dipendente. Facendo clic su **OK** verrà eseguito il processo retributivo per tutti i dipendenti inclusi nei piani di retribuzione selezionati a partire dalla data di fine del ciclo.

## <a name="view-the-process-results"></a>Visualizzare i risultati del processo
Per visualizzare i risultati di processo, aprire la pagina **Risultati processo**. Ogni volta che viene eseguito un evento processo, viene creato un evento retribuzione. In questo modo, è possibile effettuare collaudi, apportare rettifiche ed eseguire più volte l'evento retributivo per vedere in che modo le varie modifiche influenzano la retribuzione del dipendente.

La pagina **Risultati processo** contiene informazioni sul processo eseguito tra cui quando il processo è stato eseguito, l'utente che ha eseguito il processo e se si sono verificati errori quando il processo è stato eseguito. È inoltre possibile contrassegnare l'opzione **Bloccato** per disattivare il pulsante **Carica retribuzione** e impedire a chiunque di caricare gli eventi di retribuzione nei record del dipendente. Se si fa clic sul pulsante **Risultati dei dipendenti**, viene visualizzato l'elenco dei dipendenti inclusi nell'esecuzione.

L'opzione **Risultati dei dipendenti** mostra le informazioni sul processo stesso, nonché le azioni di retribuzione eseguite nel processo. La sezione **Retribuzione fissa** contiene un record per ogni azione inclusa nell'evento processo per il piano di retribuzione. Nelle colonne **Linee guida correnti** e **Suggerimento** vengono visualizzate ulteriori informazioni per l'azione selezionata nella sezione **Retribuzione fissa**. Se l'opzione **Abilita suggerimenti** è stata contrassegnata per l'azione, i campi Suggerimenti saranno modificabili. Questo consentirà di rettificare manualmente gli importi per il dipendente. Notare che se si è selezionato **Usa risultato precedente** per l'azione sull'evento processo, sarà necessario aggiornare manualmente gli importi per tutte le azioni dipendenti.

Dopo che gli importi di retribuzione sono stati controllati per un dipendente e tutte le rettifiche ai valori suggeriti sono state apportate, è possibile modificare lo **Stato** nella riga **Evento dipendente** per indicare se l'evento è stato approvato o deve essere ignorato. Facoltativamente, è possibile annullare tutte le modifiche apportate al suggerimento del dipendente facendo clic sul pulsante **Ricalcola**. In questo modo l'evento corrente di un dipendente verrà contrassegnato con lo stato Ignora e verrà creato un nuovo evento dipendente con valori ricalcolati.

## <a name="loading-approved-compensation-changes"></a>Caricamento delle modifiche retributive approvate
Una volta che uno o più eventi del dipendente presentano lo stato aggiornato in Approvato, possono essere caricati nei record di retribuzione fissa del dipendente. Questa operazione può essere effettuata scegliendo un evento dipendente alla volta e facendo clic sul pulsante **Carica retribuzione dipendente** nella pagina **Risultati dei dipendenti** oppure facendo clic su **Carica retribuzione** nella pagina **Risultati processo** per caricare tutti gli eventi dipendente approvati contemporaneamente.

Facendo clic su **OK** nella finestra di dialogo  **Carica retribuzione** verranno aggiunte le righe d'azione retributiva diverse da zero nella pagina **Retribuzione fissa dipendente**.

