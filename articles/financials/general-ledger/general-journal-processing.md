---
title: Elaborazione giornale di registrazione generale
description: "Questo articolo descrive le funzionalità di Microsoft Dynamics 365 for Finance and Operations che possono contribuire a rendere l'elaborazione del giornale di registrazione generale più semplice e che possono inoltre garantire che i dati corretti siano acquisiti e il controllo interno non sia compromesso."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: eb46613f805999753c2ab73ffb91a6fdae04c68e
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="general-journal-processing"></a>Elaborazione giornale di registrazione generale

[!INCLUDE [banner](../includes/banner.md)]

Questo articolo descrive le funzionalità di Microsoft Dynamics 365 for Finance and Operations che possono contribuire a rendere l'elaborazione del giornale di registrazione generale più semplice e che possono inoltre garantire che i dati corretti siano acquisiti e il controllo interno non sia compromesso.  

Nomi giornale di registrazione

Una delle aree più importanti da configurare è i nomi di giornale di registrazione. È consigliabile definire nomi di giornali di registrazione specifici per ogni scopo, ad esempio interaziendale, rettifica ratei e correttivo. È possibile personalizzare ciascun nome di giornale di registrazione per rendere semplice e sicura l'immissione dei dati per ogni scopo. 

Nella pagina **Nomi giornale di registrazione** è possibile impostare i seguenti elementi:

-   **Approvazione flusso di lavoro** – Per aumentare il controllo interno, definire flussi di lavoro del giornale di registrazione che stabiliscono i limiti di materialità per i passaggi di revisione e approvazione, in base a criteri quali l'importo totale in Dare. Vengono impostati flussi di lavoro per i giornali di registrazione generali nella pagina **Flussi di lavoro contabilità generale**.
-   **Valori predefiniti** - Selezionare valori predefiniti per i conti di contropartita, la valuta e le dimensioni finanziarie.
-   **Controllo giornale di registrazione** - È possibile impostare restrizioni sul tipo di società e di conto e anche sui valori segmento. 

**Esempi**

Un nome di giornale di registrazione può essere utilizzato solo per le rettifiche. In questo caso, è possibile specificare che solo il tipo di conto **Contabilità generale** è valido per tutte le società. [![Tipi di conto di controllo giornale di registrazione](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Un nome di giornale di registrazione può essere utilizzato solo per un segmento specifico o per un intervallo di conti principali. [![Segmento controllo giornale di registrazione](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

L'opzione **Storno automatico** è disponibile nei giornali di registrazione generali. Ad esempio, si dispone di una rettifica di attribuzione per competenza in cui il documento effettivo non è ancora stato elaborato, come illustrato nella figura seguente.
[![Storno giornale di registrazione generale](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

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

Le strutture di contabilità e delle regole avanzate sono estremamente importanti per garantire che i dati necessari per i report finanziari e il monitoraggio delle prestazioni vengano acquisiti durante l'elaborazione del giornale di registrazione generale e in qualsiasi documentazione. Le strutture di contabilità e delle regole avanzate consentono di personalizzare l'esperienza dell'immissione dati. È possibile consentire l'immissione di dati solo per le dimensioni finanziarie pertinenti in ogni situazione e è inoltre possibile applicare la condizione che vengano sempre acquisiti i dati obbligatori e corretti.

Per ulteriori informazioni, vedere i seguenti argomenti:
- [Pianificazione: piano dei conti](plan-chart-of-accounts.md). 
- [Creare regole avanzate per giornali di registrazione](tasks/create-advanced-rules-journals.md)
- [Creare una scrittura contabile utilizzando un modello](tasks/create-journal-entry-template.md)
- [Creare e convalidare giornali di registrazione](tasks/create-validate-journals.md)
- [Registrare giornali periodici](tasks/post-periodic-journals.md)
- [Elaborare giornale di registrazione allocazioni contabili](tasks/process-ledger-allocation-journal.md)



