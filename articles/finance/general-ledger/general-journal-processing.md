---
title: Elaborazione giornale di registrazione generale
description: Questo articolo descrive le funzionalità di Microsoft Dynamics 365 Finance che possono contribuire a rendere l'elaborazione del giornale di registrazione generale più semplice e che possono inoltre garantire che i dati corretti siano acquisiti e che il controllo interno non sia compromesso.
author: kweekley
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2055c028f7bfe8edc9faec8f791fff2fbfe08bfa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896378"
---
# <a name="general-journal-processing"></a>Elaborazione giornale di registrazione generale

[!include [banner](../includes/banner.md)]

Questo articolo descrive le funzionalità che possono contribuire a rendere l'elaborazione del giornale di registrazione generale più semplice e che possono inoltre garantire che i dati corretti siano acquisiti e che il controllo interno non sia compromesso.  

## <a name="journal-names"></a>Nomi giornale di registrazione

Una delle aree più importanti da configurare è i nomi di giornale di registrazione. È consigliabile definire nomi di giornali di registrazione specifici per ogni scopo, ad esempio interaziendale, rettifica ratei e correttivo. È possibile personalizzare ciascun nome di giornale di registrazione per rendere semplice e sicura l'immissione dei dati per ogni scopo. 

Nella pagina **Nomi giornale di registrazione** è possibile impostare i seguenti elementi:

-   **Approvazione flusso di lavoro** – Per aumentare il controllo interno, definire flussi di lavoro del giornale di registrazione che stabiliscono i limiti di materialità per i passaggi di revisione e approvazione, in base a criteri quali l'importo totale in Dare. Vengono impostati flussi di lavoro per i giornali di registrazione generali nella pagina **Flussi di lavoro contabilità generale**.
-   **Valori predefiniti** - Selezionare valori predefiniti per i conti di contropartita, la valuta e le dimensioni finanziarie.
-   **Controllo giornale di registrazione** - È possibile impostare restrizioni sul tipo di società e di conto e anche sui valori segmento. 

**Esempi**

Un nome di giornale di registrazione può essere utilizzato solo per le rettifiche. In questo caso, è possibile specificare che solo il tipo di conto **Contabilità generale** è valido per tutte le società. 

[![Tipi di account di controllo giornale di registrazione.](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Un nome di giornale di registrazione può essere utilizzato solo per un segmento specifico o per un intervallo di conti principali. 

[![Segmento controllo giornale di registrazione.](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

L'opzione **Storno automatico** è disponibile nei giornali di registrazione generali. Ad esempio, si dispone di una rettifica di attribuzione per competenza in cui il documento effettivo non è ancora stato elaborato, come illustrato nella figura seguente.
[![Storno giornale di registrazione generale.](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

Il componente aggiuntivo di Microsoft Excel per le scritture contabili fornisce un ulteriore livello di automazione e rende l'immissione di dati più semplice. L'azione **Apri righe in Excel** è disponibile nelle pagine **Giornale di registrazione generale** e **Giustificativo giornale di registrazione**. 

Nella pagina **Giornali di registrazione periodici** è possibile impostare i giornali ricorrenti per automatizzare l'elaborazione del giornale di registrazione. 

È possibile utilizzare in qualsiasi momento modelli di giustificativo. Nella pagina **Giornali di registrazione generali** le azioni **Salva** e **Seleziona modello giustificativo** si trovano nella pagina **Giustificativo giornale di registrazione**, sotto **Funzioni** per le righe del giustificativo.

## <a name="related-setup"></a>Impostazione correlata
La seguente impostazione non è specifica dei giornali di registrazione generali, ma contribuirà a garantire che l'immissione di dati sia semplice e corretta.

### <a name="main-account"></a>Conto principale

L'impostazione del conto principale offre numerose opzioni per l'elaborazione dei giornali di registrazione generali:

-   **Fabbisogno di DB/CR** - Utilizzare questa opzione se un conto principale è limitato alle transazioni in dare o in avere. L'impostazione è verificata quando un giornale di registrazione viene convalidato o registrato.

-   **Conto di contropartita predefinito**
-   **Sospeso** - Consente di sospendere un conto principale per l'immissione di dati per tutte le società o per una società/persona giuridica specifica.
-   **Non consentire immissione manuale** - Impedisce agli utenti di immettere manualmente un valore per il conto nei giornali di registrazione.
-   **Valuta predefinita/Convalida valuta**
-   **Sostituzioni persona giuridica** - Questa impostazione è specifica per la società/persona giuridica definita:
    -   **IVA predefinita/Convalida IVA**
    -   **Dimensione predefinita** – **Non fissa** o **Valore fisso**. **Valore fisso** contribuirà a garantire che tutte le registrazioni per il conto principale utilizzano sempre qualsiasi valore di dimensione impostato come **Fisso**.
-   **Convalida di registrazione**
    -   **Convalida utente** - Questa opzione consente di controllare a quali utenti è consentito registrare in un conto principale.
    -   **Convalida tipo di registrazione** - Questa opzione consente di controllare quali tipi di registrazione sono consentiti in un conto principale.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Strutture di contabilità e delle regole avanzate

Le strutture di contabilità e delle regole avanzate sono estremamente importanti per garantire che i dati necessari per i report finanziari e il monitoraggio delle prestazioni vengano acquisiti durante l'elaborazione del giornale di registrazione generale e in qualsiasi documentazione. Le strutture di contabilità e delle regole avanzate consentono di personalizzare l'esperienza dell'immissione dati. È possibile consentire l'immissione di dati solo per le dimensioni finanziarie pertinenti in ogni situazione ed è inoltre possibile applicare la condizione che vengano sempre acquisiti i dati richiesti e precisi.

Per ulteriori informazioni, vedere gli argomenti seguenti:
- [Definire il piano dei conti](plan-chart-of-accounts.md) 
- [Creare regole avanzate per giornali di registrazione](tasks/create-advanced-rules-journals.md)
- [Creare una scrittura contabile utilizzando un modello](tasks/create-journal-entry-template.md)
- [Creare e convalidare giornali di registrazione](tasks/create-validate-journals.md)
- [Registrare giornali di registrazione periodici](tasks/post-periodic-journals.md)
- [Elaborare giornale di registrazione allocazioni contabili](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>Simula registrazione
**Simula registrazione** è disponibile nel menu **Convalida** della maggior parte dei giornali di registrazione. Quando si convalida un giornale di registrazione utilizzando la funzione **Convalida**, il sistema testa il giornale di registrazione alla ricerca di condizioni di errore specifiche. Se si utilizza la funzione **Simula registrazione**, il sistema esegue tutto degli stessi processi che vengono eseguiti durante la registrazione senza registrare effettivamente il giornale di registrazione. È quindi possibile esaminare i messaggi di registrazione visualizzati, correggere gli errori riscontrati e quindi aprire il menu **Registra** per registrare il giornale di registrazione. 

**Simula registrazione** non è disponibile per l'elaborazione batch. È tuttavia disponibile codice per simulare la registrazione in batch e gli sviluppatori possono estendere il codice per aggiungere tale funzionalità.  

## <a name="journal-unlock"></a>Sblocco del giornale di registrazione
Un pulsante è disponibile nella pagina del giornale di registrazione per sbloccare un giornale di registrazione il cui stato "Bloccato dal sistema" è impostato su Sì. Questo sblocco può essere eseguito da un amministratore del sistema che ha analizzato tutti i processi batch di esecuzione e confermato che tale giornale di registrazione non è più elaborato attivamente da un processo batch. Questo pulsante viene abilitato mediante la funzionalità denominata **Pulsante di sblocco del giornale di registrazione** nella pagina **Gestione funzionalità**. 

## <a name="workflow-recall"></a>Richiamo in un flusso di lavoro 
La capacità di richiamare un giornale di registrazione in un flusso di lavoro il cui stato è "Irreversibile" viene abilitata utilizzando il pulsante **Flusso di lavoro** in un giornale di registrazione e nella pagina **Storico flusso di lavoro**. Questo pulsante viene abilitato mediante la funzionalità denominata **Ripristino stato del flusso di lavoro per giornali di registrazione** nella pagina **Gestione funzionalità**.

## <a name="delete-journal-lines"></a>Eliminare le righe di un giornale di registrazione
La capacità di eliminare tutte le righe di un giornale di registrazione viene abilitata in un giornale di registrazione in **Funzioni** > **Elimina righe giornale di registrazione**. Per abilitare questa funzionalità, in **Gestione funzionalità**, selezionare **Elimina ottimizzazioni prestazioni del giornale di registrazione**. Questa funzionalità influisce sulle estensioni della tabella **LedgerJournalTrans** ed è il metodo **Elimina**, poiché l'insieme di righe viene rimosso senza chiamare il metodo **Elimina** di ciascuna riga. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
