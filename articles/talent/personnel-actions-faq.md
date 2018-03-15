---
title: Azioni dipendente [Domande frequenti]
description: "In questo argomento vi sono risposte alle domande che potrebbe essere poste se l'organizzazione utilizza le azioni dipendente. Le azioni dipendente sono passaggi aggiuntivi da completare quando si eseguono attività correlate al personale."
author: ShielaSogge
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: abc52192848649672cbcb8c770d74ba2aef139be
ms.openlocfilehash: e3f0f79df73cce4a54c7e6abbc38381c708af690
ms.contentlocale: it-it
ms.lasthandoff: 02/14/2018

---

# <a name="personnel-actions-faq"></a>Azioni dipendente [Domande frequenti]

[!include[banner](includes/banner.md)]

In questo argomento vi sono risposte alle domande che potrebbe essere poste se l'organizzazione utilizza le azioni dipendente. Le azioni dipendente sono passaggi aggiuntivi da completare quando si eseguono attività correlate al personale. Esempi di attività che potrebbero richiedere azioni dipendente quando si creano nuove posizioni, si modificano valori di posizione esistenti, si assumono nuovi lavoratori, si trasferiscono lavoratori, si modifica la retribuzione lavoratore, si modificano assegnazioni di posizione o si termina un rapporto con i lavoratori.

**Nota:** le azioni dipendente sono disponibili solo se i campi **Attiva azioni lavoratore** e **Attiva azioni posizione** sono stati impostati su **Sì**, nella scheda **Azioni dipendente** della pagina **Parametri condivisi risorse umane**. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Come è possibile indicare se la organizzazione richiede azioni dipendente?
Le azioni dipendente sono richieste dall'organizzazione se viene chiesto di selezionare un'azione dipendente quando si creano nuove posizioni, si modificano posizioni esistenti, si assumono nuovi lavoratori, si trasferiscono lavoratori, si modifica la retribuzione lavoratore, si modificano assegnazioni di posizione, si termina il rapporto con i lavoratori o si inserisce un congedo per i lavoratori. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Qual è la differenza tra un'azione di posizione e un'azione lavoratore?
Sono disponibili due tipi di azioni dipendente:

- Azione di posizione: un'azione di posizione viene eseguita nelle posizioni esistenti o nelle nuove posizioni. Ad esempio, un'azione di posizione può essere obbligatoria se si modifica un valore in una posizione esistente o se si crea una nuova posizione stagionale. Per informazioni dettagliate sull'utilizzo delle azioni di posizione, vedere Attività chiave: posizioni lavoratore esistenti o Attività chiave: nuove posizioni lavoratore.

- Azione lavoratore: un'azione lavoratore viene eseguita per i dipendenti esistenti o i nuovi dipendenti. Ad esempio, un'azione lavoratore potrebbe essere obbligatoria quando un nuovo dipendente viene assunto o un dipendente esistente viene promosso. Per informazioni dettagliate sull'utilizzo delle azioni lavoratore, vedere Assegnare le azioni dipendente ai lavoratori.

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Qual è il significato degli stati delle azioni dipendente?
Le azioni dipendente possono avere i seguenti stati:

- **Bozza**: se il flusso di lavoro viene utilizzato, l'azione non è stata inviata. Se il flusso di lavoro non viene utilizzato, l'azione non è stata completata.
- **In revisione**: l'azione dipendente è stata inviata al flusso di lavoro, ma il flusso di lavoro non viene completato.
- **In attesa di approvazione**: il flusso di lavoro è stato completato, ma le modifiche sono ancora in corso. Annullato: il flusso di lavoro è stato annullato o l'azione dipendente è stata richiamata. Rifiutato: la richiesta di azione è stata rifiutata dall'approvatore.
- **Elaborazione azione**: la richiesta di azione è stata approvata e le modifiche sono in fase di elaborazione.
- **Flusso di lavoro completato**: il flusso di lavoro è stato completato e le modifiche sono state elaborate. Non riuscito: il flusso di lavoro ha avuto esito negativo poiché le informazioni non sono aggiornate. Fare clic su Riattiva per visualizzare le informazioni più recenti e per continuare.
- **Completata**: la posizione è stata creata o modificata correttamente oppure il dipendente è stato correttamente assunto, trasferito o è stato terminato il rapporto con il dipendente oppure ne è stata modificata la retribuzione. Errore: si è verificato un problema diverso dall'assenza di aggiornamento delle informazioni. Aprire il registro messaggi per le azioni dipendente per determinare la causa dell'errore.
- **Negato**: la richiesta di azione è stata negata dall'approvatore.

## <a name="can-i-delete-a-personnel-action"></a>È possibile eliminare un'azione dipendente?
Sì, è possibile eliminare le azioni dipendente con lo stato **Bozza**, **Errore**, **Non riuscito** o **Annullato**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Qual è la modalità più veloce per controllare lo stato di una richiesta di azione dipendente?
Aprire qualsiasi pagina elenco di azioni dipendente e selezionare un'azione dipendente.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Quali azioni eseguire se una richiesta di azione dipendente ha esito negativo?
Se una richiesta di azione dipendente ha esito negativo, eseguire i passaggi indicati di seguito per risolvere l'errore e per inviare di nuovo la richiesta:

> 1. Nel **Riquadro azioni** fare clic sul pulsante **Testo errore** per visualizzare il testo del messaggio che descrive il problema.

> 2. Nel **Riquadro azioni** fare clic su **Riattiva** per caricare le informazioni più recenti e per impostare lo stato dell'azione dipendente di nuovo su **Bozza**.

> 3. Risolvere l'errore e quindi fare clic su **Completo** o **Invia**.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Cosa succede a un'azione dipendente che utilizza il flusso di lavoro quando l'approvazione finale è completata?
Se non sono presenti errori, l'azione dipendente diventa di sola lettura (È possibile visualizzare lo storico della pagina elenco **Tutte le azioni del lavoratore**, ma non è possibile modificare l'azione dipendente). Quando lo stato di un'azione dipendente è **Completato**, la posizione o il record del lavoratore è già stata aggiornata. Per visualizzare le modifiche eseguite, aprire la pagina elenco **Posizioni** o **Lavoratori**.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Per quale motivo viene visualizzato il seguente errore durante l'immissione di un valore diverso da zero nel campo Tariffa retributiva? “Il valore non è incluso nell'intervallo valido. Deve essere compreso tra 0,00 e 0,00”
Verrà visualizzato questo messaggio poiché il campo Livello nel modulo Mansione è vuoto per la mansione associata alla posizione selezionata.

Per risolvere questo errore, effettuare le operazioni seguenti:

> 1. Nel modulo Assegnazioni di posizione lavoratore, fare clic sul campo Posizione.  
> 2. Fare clic sul campo Mansione per aprire la pagina Mansione.
> 3. Nel riquadro Azione, fare clic su Modifica.
> 4. Fare clic sulla scheda Retribuzione.
> 5. Nel campo Livello selezionare un livello.
> 6. Chiudere la pagina Mansione.
> 7. Chiudere la pagina Posizione.
> 8. Tornare alla scheda Retribuzione nella pagina del lavoratore e selezionare Retribuzione fissa.  Selezionare Nuovo e immettere la posizione del dipendente nel campo Posizione.  Immettere un valore nel campo Piano quindi immettere la retribuzione del dipendente nel campo Retribuzione.

## <a name="why-cant-i-change-the-effective-date-in-the-header-of-the-worker-action-form"></a>Per quale motivo non è possibile modificare la data di validità nell'intestazione del modulo Azione lavoratore?
Non è possibile modificare la data di validità poiché nel campo viene inserita automaticamente la data più logica per il tipo di azione.

Esempio

- La data di validità nell'intestazione di un'azione **Termina rapporto con lavoratore** è la data immessa nel campo **Data fine rapporto**.
- La data di validità di un'azione **Assumi lavoratore** è la data immessa nel campo **Data di inizio impiego**.
- La data di validità di un'azione **Trasferisci lavoratore** è la data immessa nel campo **Data di inizio assegnazione** per il lavoratore.


