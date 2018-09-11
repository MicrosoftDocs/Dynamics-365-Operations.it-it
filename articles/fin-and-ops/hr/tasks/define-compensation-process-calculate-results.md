--- 
title: Definire il processo retributivo e calcolare i risultati
description: I processi di retribuzione vengono utilizzati per determinare nuovi importi e premi di retribuzione per i dipendenti iscritti ai piani di retribuzione variabile e fissa.
author: kherr75
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ba28cf1fa6a8e9a4497d3bac1a2161098ec53db1
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="define-compensation-process-and-calculate-results"></a>Definire il processo retributivo e calcolare i risultati

[!include [task guide banner](../../includes/task-guide-banner.md)]

I processi di retribuzione vengono utilizzati per determinare nuovi importi e premi di retribuzione per i dipendenti iscritti ai piani di retribuzione variabile e fissa. I processi di retribuzione possono essere eseguiti più volte per eseguire l'analisi di simulazione, verificare che le modifiche e le impostazioni siano corrette. Questa procedura consente di creare un processo di retribuzione, eseguire il processo e visualizzare i risultati. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-compensation-process"></a>Creare un processo retributivo
1. Passare a Risorse umane > Compensation > Processo > Processi retributivi.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Processo.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo di processo selezionare un'opzione.
    * Un ciclo specifica il periodo di tempo valutato per determinare la retribuzione. La valutazione considera le posizioni dei dipendenti, le valutazioni delle prestazioni da includere, il calcolo della percentuale di tempo di assunzione del dipendente durante il ciclo e altre informazioni. Un esempio di data di inizio ciclo potrebbe essere il primo giorno dell'anno fiscale precedente.  
6. Nel campo Inizio ciclo immettere una data e un'ora.
    * La data di fine ciclo è importante perché è la data utilizzata per determinare i dipendenti attivamente occupati e iscritti a uno o più piani di retribuzione.  
7. Nel campo Fine ciclo immettere una data.
    * La data di attivazione transazione è la data in cui le nuove tariffe di retribuzione devono essere rese effettive. Molte società includono dei mesi tra la fine di un ciclo e la data in cui le nuove tariffe di retribuzione vengono rese effettive. Il tempo aggiuntivo viene utilizzato per elaborare e verificare la nuova retribuzione.  
8. Nel campo Data di attivazione transazione immettere una data.
    * La data temporizzata viene utilizzata per i piani di retribuzione variabili che determinano l'importo del premio di un dipendente in base alla tariffa retributiva nel determinato momento.  
    * La data di assunzione ripartizione proporzionale retribuzione fissa viene utilizzata con i piani di retribuzione fissa con la regola di assunzione Percentuale.  I dipendenti assunti tra l'inizio del ciclo e la data di assunzione ripartizione proporzionale retribuzione fissa riceveranno il 100% dell'incremento retributivo calcolato, anziché la percentuale proporzionale.  
9. Nel campo Data di assunzione ripartizione proporzionale retribuzione fissa immettere una data.
    * La scadenza della revisione è la data entro cui tutti i risultati del processo devono essere stati esaminati in modo da poter essere caricati in modo un record di retribuzione dipendente prima della data di attivazione della transazione. Questo campo viene visualizzato solo a scopo informativo.  
10. Immettere una data nel campo Scadenza revisione.
11. Fare clic su Salva.

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a>Configurare i piani di retribuzione e le azioni per un processo retributivo.
1. Fare clic su Impostazioni.
    * La pagina Impostazione viene utilizzata per selezionare le pianificazioni da elaborare come parte del processo di retribuzione nonché le azioni che devono essere eseguite in base a ciascun piano.  
2. Nel campo Piano immettere o selezionare un valore.
3. Fare clic su Salva.
4. Scegliere Aggiungi.
5. Nel campo Azione, selezionare un tipo di azione Capitale netto.
6. Scegliere Aggiungi.
7. Nel campo Azione, selezionare un tipo di azione Merito.
    * Le azioni di retribuzione possono essere concatenate tra loro utilizzando il campo Usa risultato precedente per indicare se l'azione selezionata deve utilizzare la retribuzione di base dei dipendenti o il risultato dell'azione precedente come punto di partenza per il calcolo dell'azione.  
8. Selezionare Sì nel campo Usa risultato precedente.
9. Scegliere Aggiungi.
10. Nel campo Azione, selezionare un tipo di azione Generale.
    * I diversi tipi di azione di retribuzione abilitano campi diversi. Per un tipo di azione di retribuzione generale, è possibile specificare una percentuale di incremento o un importo di incremento.  
11. Selezionare l'opzione Seleziona importo incremento.
12. Nel campo Importo incremento immettere un numero.
13. Scegliere Aggiungi.
14. Nel campo Azione, selezionare un tipo di azione Promozione.
    * I tipi di azione Promozione e Altra modifica livello consentono agli utenti di effettuare rettifiche manuali alla retribuzione del dipendente. I suggerimenti possono essere abilitati per questi tipi di azione nonché per altri tipi di azione al fine di poter immettere un nuovo valore di retribuzione consigliato per un dipendente.  
15. Scegliere Aggiungi.
16. Selezionare un'opzione nel campo Tipo.
    * I piani di retribuzione variabile e fissa possono essere eseguiti nello stesso processo di retribuzione.  
17. Nel campo Piano immettere o selezionare un valore.
    * Utilizzare la casella di controllo Abilita retribuzione basata sulla produttività per determinare se gli importi di retribuzione variabile e fissa devono essere rettificati in base alla valutazione delle prestazioni del dipendente.  
    * Il fattore può essere ignorato nei piani di retribuzione variabile.  
18. Fare clic su Salva.
19. Scegliere Aggiungi.
20. Chiudere la pagina.

## <a name="run-the-compensation-process"></a>Eseguire il processo retributivo
1. Fare clic su Esegui processo.
    * Il controllo Mostra risultati di elaborazione consente di visualizzare i messaggi di elaborazione del processo di retribuzione completo quando l'elaborazione è terminata.  
2. Selezionare Sì nel campo Mostra risultati di elaborazione.
3. Fare clic su OK.

## <a name="view-the-results"></a>Visualizzare i risultati
1. Fare clic su Risultati processo.
2. Fare clic su Risultati dei dipendenti.
3. Nell'elenco trovare e selezionare il record desiderato.
4. Espandere la sezione Retribuzione fissa.
    * Espandere la scheda dettaglio per visualizzare i risultati del processo. Se l'opzione per abilitare i suggerimenti è stata contrassegnata per un'azione di retribuzione, i campi Suggerimento verranno abilitati per tale azione.  
5. Nell'elenco trovare e selezionare il record desiderato.
    * I risultati per un singolo dipendente possono essere visualizzati facendo clic sul pulsante Visualizza risultati.  
    * È possibile sovrascrivere l'importo di retribuzione calcolato modificando la percentuale o l'importo dell'aumento nei campi Suggerimento.  
6. Nel campo della percentuale suggerita immettere un numero.
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nel campo della percentuale suggerita immettere un numero.
    * Ricalcola può essere utilizzato per ignorare le modifiche apportate al record esistente e generare un nuovo risultato di retribuzione per il dipendente selezionato.  
    * Quando tutte le modifiche sono complete per un dipendente, modificare lo stato su Approvato.  
9. Fare clic su Cambia stato.
10. Fare clic su Approvato.
    * Dopo che il record è stato approvato può essere caricato nel record ufficiale di retribuzione del dipendente. La nuova retribuzione sarà valida a partire dalla data di transazione specificata nel processo di retribuzione.  


