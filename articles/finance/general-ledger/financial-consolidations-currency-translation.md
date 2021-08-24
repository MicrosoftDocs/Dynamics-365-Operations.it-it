---
title: Panoramica dei consolidamenti finanziari e delle conversioni di valuta
description: In questo argomento vengono descritti i consolidamenti finanziari e le conversioni di valuta nella contabilità generale.
author: aprilolson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 0df16db842c159b4db469139a0b5463a82e3fe07b4e23f8f7cf0272caaf23602
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748982"
---
# <a name="financial-consolidations-and-currency-translation-overview"></a>Panoramica consolidamenti finanziari e conversione valuta

[!include [banner](../includes/banner.md)]

Questo argomento descrive l'approccio utilizzato da Microsoft Dynamics 365 Finance e la funzionalità di creazione di report finanziari per i consolidamenti. Descrive scenari che implicano la creazione di report per più società, l'aggregazione, l'eliminazione e gli interessi di minoranza. Descrive inoltre come gestire le situazioni speciali, ad esempio gli scenari in cui le persone giuridiche hanno periodi fiscali diversi o piani dei conti diversi.

In questo argomento sono state inserite informazioni relative a utenti e consulenti funzionali e si presuppone che i lettori abbiano una conoscenza generale di Finance e della funzionalità di creazione di report finanziari. L'impostazione di base non viene trattata.

> [!NOTE]
> Il termine *persona giuridica* viene utilizzato in Finance e il termine *società* viene utilizzato nella creazione di report finanziari. Entrambi questi termini vengono utilizzati in questo argomento. Tuttavia, per lo scopo per cui sono utilizzati in questo argomento, i significati coincidono.

## <a name="audience"></a>Destinatari
Questo argomento è destinato a utenti di contabilità e ai consulenti dell'applicazione che desiderano utilizzare Finance and Operations e la funzionalità di creazione di report finanziari per consolidare i dati di più società e di più valute.

## <a name="approach"></a>Approccio
Finance utilizza una persona giuridica separata per elaborare un consolidamento. Consente il consolidamento di istanza singola ma offre l'opzione per importare i dati da altre origini. Il processo di consolidamento deve essere eseguito ogni volta che vengono apportate modifiche alle persone giuridiche di origine.

La funzionalità di creazione di report finanziari può consolidare più società durante la generazione dei report. Sebbene i dati vengano archiviati in un data mart, abbiano versione e possano essere esportati, ogni società di origine è il proprietario e il contenitore dei dati. Il report può essere eseguito in qualsiasi momento, anche ogni minuto, ad esempio. Offre molti vantaggi aggiuntivi, ad esempio la possibilità di eseguire il drill-down a tutte le società e le dimensioni.

Gli utenti possono utilizzare Consolidato [online], la creazione di report finanziari o una combinazione di queste due funzionalità. Nella scelta dipende dalle esigenze della società e dalle preferenze dei revisori.

## <a name="consolidations"></a>Consolidamenti
Il modulo **Consolidamenti** include opzioni per il consolidamento di più persone giuridiche durante il processo di consolidamento e per l'importazione o l'esportazione del saldo di una società. È inoltre possibile impostare le eliminazioni e registrarle nei giornali di registrazione eliminazioni.

## <a name="benefits-of-using-consolidate-online"></a>Vantaggi dell'utilizzo di Consolidato online
I clienti che utilizzano il modulo **Consolidamenti** beneficiano di vari vantaggi:

- **Profondità di dati** - È possibile creare report consolidati che riuniscono i dati effettivi e di budget sia a livello contabile che a livello di dimensioni.
- **Consolidamenti dinamici** - I consolidamenti possono essere elaborati più volte.
- **Capacità di controllo** - Le dimensioni e i conti vengono gestiti per l'analisi e il controllo e i saldi vengono creati in base alla data.
- **Conversione valuta** - È possibile impostare intervalli di conti e tassi per convertire la valuta di contabilizzazione della società di origine nella valuta di contabilizzazione della società di consolidamento.
- **Elaborare le eliminazioni in una società consolidata o di eliminazione** - È possibile elaborare e registrare le eliminazioni come singolo processo durante il consolidamento. In alternativa, è possibile eseguire una proposta separatamente.

## <a name="supported-consolidation-scenarios"></a>Scenari di consolidamento supportati
Di seguito sono riportati alcuni degli scenari di consolidamento supportati da Consolidato online:

- Consolidamenti a singolo livello tra persone giuridiche
- Consolidamenti che implicano eliminazioni
- Interessi di minoranza (per questo scenario, è necessario utilizzare il calcolo manuale e l'immissione manuale nella società).
- Più piani dei conti tra persone giuridiche
- Calendari fiscali diversi tra più persone giuridiche
- Consolidamenti che includono più valute di dichiarazione

## <a name="legal-entity-setup"></a>Impostazione della persona giuridica
Prima di elaborare un consolidamento, è necessario impostare la persona giuridica. È possibile eseguire il consolidamento quante volte è necessario e tutti i dati verranno convertiti dalla valuta di contabilizzazione della società di origine nella valuta definita per la società consolidata. Pertanto, per la seguente struttura organizzativa, se è necessario convertire tutte le società nordamericane prima in dollari USA (USD) e poi in euro (EUR), la valuta della società padre, è necessario disporre di almeno due società di consolidamento.

![Struttura organizzativa.](./media/organizational-structure.png "Struttura organizzativa")

Nella struttura organizzativa precedente, è necessario disporre di una persona giuridica per il consolidamento nordamericano, poiché i consolidamenti consolidano sempre dalla valuta di contabilizzazione della società di origine nella valuta della società di consolidamento. In questo esempio, se tutte le società vengono incluse in un unico consolidamento, la società affiliata messicana verrà convertita dai pesos messicani (MXN) in EUR, non da MXN a USD a EUR.

Quando si crea la persona giuridica, è possibile specificare se la società viene utilizzata sia per il processo di consolidamento che per il processo di eliminazione o solo per uno di questi processi. Nella figura seguente la società viene utilizzata per entrambi i processi. Tenere presente che non è possibile registrare i giornali di registrazione giornalieri in una società consolidata, ma è possibile registrarli in una società di eliminazione. Di conseguenza, può essere opportuno disporre di una società di eliminazione separata.

![Persona giuridica che viene utilizzata sia per il consolidamento che per l'eliminazione.](./media/sep-elimination-company.png "Persona giuridica che viene utilizzata sia per il consolidamento che per l'eliminazione")

## <a name="main-accounts-and-consolidation-account-groups"></a>Conti principali e gruppi di conti di consolidamento
Una scelta da affrontare riguarda come consolidare il piano dei conti. Durante il processo di consolidamento, sono disponibili tre opzioni per il consolidamento dei conti principali.

La prima opzione consiste nell'utilizzare i conti principali dalle società di origine. In questo caso, verrà consolidato ogni conto di tutte le società. Ad esempio, se la Cassa corrisponde al conto 100000 nella società USMF e al conto 1100 nella società DEMF, la società consolidata includerà entrambi i conti. Ciascun conto avrà il proprio saldo.

La seconda opzione consiste nello specificare un conto di consolidamento predefinito nella pagina **Conti principali**. Il conto verrà mappato al conto di consolidamento. Questa opzione può essere utile quando sono presenti più piani dei conti diversi o è necessario mappare a un grafico definito dalla sede centrale.

![Conto di consolidamento predefinito specificato nella pagina Conti principali.](./media/main-accounts.png "Conto di consolidamento predefinito specificato nella pagina Conti principali")

La terza opzione consiste nell'utilizzare i gruppi di conti di consolidamento. È possibile definire tutti i gruppi di conti di consolidamento necessari. Quindi, nella pagina **Conti di consolidamento aggiuntivi** si esegue il mapping del conto principale dal piano dei conti al conto desiderato per il gruppo.

![Mapping nella pagina dei conti di consolidamento aggiuntivi.](./media/additional-consolidation-accounts.png "Mapping nella pagina dei conti di consolidamento aggiuntivi")

## <a name="consolidating-online"></a>Consolidamento online
Per ulteriori informazioni su come immettere i dettagli dei consolidamenti online, vedere [Consolidamenti finanziari online](./consolidate-online.md).

## <a name="managing-consolidation-transactions"></a>Gestione delle transazioni di consolidamento
Per visualizzare i risultati del consolidamento, sono disponibili più opzioni:

- Generare un report finanziario per la società di consolidamento.
- Esaminare la pagina di elenco **Bilancio di verifica** nella società di consolidamento.
- Nell'elenco delle transazioni di consolidamento nella pagina **Consolidamenti** visualizzare i saldi che sono stati creati in base alla data per ogni società di origine per ogni periodo.

    ![Transazioni di consolidamento nella pagina Consolidamenti.](./media/managing-consolidation-transactions.png "Transazioni di consolidamento nella pagina Consolidamenti")

Per eseguire nuovamente il consolidamento, è possibile elaborare semplicemente il consolidamento. In alternativa, è possibile prima selezionare **Rimuovi transazioni** nella pagina **Consolidamenti**.
Nel caso in cui i saldi sul tuo conto consolidato non siano accurati, questi saldi possono essere corretti utilizzando la pagina **Rettifiche periodo di chiusura**.

## <a name="consolidate-with-import"></a>Consolida con importazione
Il consolidamento con funzionalità di importazione funge dalla funzionalità di consolidamento in linea. Quando si selezionano le persone giuridiche, verrà visualizzato il percorso al fine di origine che contiene i dati.

## <a name="export-company-balances"></a>Esporta saldi società
La funzionalità di esportazione dei saldi della società opera come la funzionalità di consolidamento online. Quando si selezionano le persone giuridiche, si imposta un percorso file per l'output.

## <a name="elimination-rules"></a>Regole di eliminazione
Per eliminare le transazioni interaziendali, è possibile creare una regola di eliminazione. In alternativa, è possibile creare un inserimento manuale di eliminazione nella società designata come una società di eliminazione. Se si crea una regola di eliminazione, sono disponibili due opzioni per il metodo di eliminazione: **Modifica netto** e **Fisso**.

### <a name="set-up-elimination-rules"></a>Impostare regole di eliminazione
Quando si impostano le regole di eliminazione in Finance, è possibile creare una dimensione finanziaria che viene utilizzata specificatamente per l'eliminazione. La maggior parte dei clienti definisce questa dimensione finanziaria **Partner commerciale** o un'espressione simile. Se si decide di non utilizzare una dimensione finanziaria, assicurarsi di avere conti principali che vengono utilizzati solo per le transazioni interaziendali.

L'impostazione delle eliminazioni è disponibile nell'area **Impostazioni** del modulo **Consolidamenti**. Dopo aver immesso una descrizione per la regola, è necessario selezionare la società in cui verrà registrato il giornale di registrazione eliminazioni. La società che si seleziona deve avere l'opzione **Utilizza per processo di eliminazione finanziario** selezionate nell'impostazione della persona giuridica.

È possibile impostare la data in cui la regola di eliminazione diventa effettiva e la data in cui scade, in base alle esigenze. Se si vuole che la regola di eliminazione sia disponibile nel processo di proposta di eliminazione, è necessario impostare l'opzione **Attiva** su **Sì**. Selezionare un nome di giornale di registrazione di tipo **Eliminazione**.

![Proprietà di base di una regola di eliminazione.](./media/ledger-elimination-rule-journal.png "Proprietà di base di una regola di eliminazione")

Dopo avere definito le proprietà di base, selezionare **Righe** per definire le regole di elaborazione effettive. Sono disponibili due opzioni per le eliminazioni: è possibile eliminare l'importo netto della modifica o definire un importo fisso.

Selezionare i conti di origine. È possibile utilizzare un asterisco (\*) come carattere jolly. Ad esempio **1\**_seleziona tutti i conti che iniziano con_* 1** come origine dei dati per l'allocazione.

Dopo aver selezionato i conti di origine, utilizzare il campo **Specifica conto** per specificare il conto che viene utilizzato dalla società di destinazione. Selezionare **Origine** per utilizzare lo stesso conto principale che viene definito nel conto principale. Se si seleziona **Definito dall'utente**, è necessario specificare un conto di destinazione.

![Pagina Riga regola di eliminazione contabile.](./media/ledger-elimination-rule-line.png "Pagina Riga regola di eliminazione contabile")

Il campo **Specifica dimensioni** funziona come il campo **Specifica conto**. Selezionare **Origine** per utilizzare le stesse dimensioni nella società di origine e in quella di destinazione. Se si seleziona **Definito dall'utente**, è necessario specificare le dimensioni nella società di destinazione selezionando **Dimensioni di destinazione**. Selezionare quindi le dimensioni di origine e i valori e le dimensioni finanziarie utilizzati come origine dell'eliminazione.

### <a name="process-elimination-transactions"></a>Elaborare transazioni di eliminazione
Sono disponibili due modi per elaborare le transazioni di eliminazione. La transazione può essere eliminata durante il processo di consolidamento online oppure è possibile creare un giornale di registrazione eliminazioni per eseguire il processo di proposta di eliminazione. Questa sezione si concentra sulla seconda opzione.

In una società che viene definita come società di eliminazione, selezionare **Giornale di registrazione eliminazioni** nel modulo **Consolidamenti**. Dopo aver selezionato il nome del giornale di registrazione, selezionare **Righe**. Per eseguire la proposta, selezionare **Proposte** \> **Proposta di eliminazione**.

Selezionare la società che rappresenta l'origine dei dati consolidati, quindi selezionare la regola da elaborare. Immettere l'ora di inizio e di fine per definire l'intervallo di date in cui cercare gli importi di eliminazione. Il campo **Data registrazione CoGe** specifica la data che viene utilizzata per registra il giornale di registrazione nella contabilità generale. Dopo avere selezionato **OK**, è possibile esaminare gli importi e registrare il giornale di registrazione.

> [!NOTE]
> Il giornale di registrazione eliminazioni mostra gli importi dei valori dei conti nella valuta delle transazioni di origine, non nella valuta di contabilizzazione. Quando si esaminano gli importi del giornale di registrazione eliminazioni, questo comportamento potrebbe apparire confusionario.

Per ulteriori informazioni ed esempi, vedere [Regole di eliminazione](./elimination-rules.md).

## <a name="currency-revaluation-in-a-consolidation-company"></a>Rivalutazione della valuta in una società di consolidamento
Quando si consolidano i dati da una valuta di contabilizzazione a un'altra, è necessario eseguire la rivalutazione della valuta in presenza di una variazione nei tassi di cambio, affinché i saldi dei conti vengano rivalutati correttamente. Quando si consolidano i dati originariamente, utilizzare la scheda **Conversione valuta** per selezionare i tassi di cambio iniziali da utilizzare per la conversione durante il processo di consolidamento. Dopo che si è inserito un nuovo tasso di cambio (ad esempio nel mese successivo), è necessario rivalutare i saldi dei conti. I profitti non realizzati o le perdite non realizzate vengono aggiornati in base al nuovo tasso di cambio e alla data.

Per ulteriori informazioni sulla rivalutazione della valuta in una società di consolidamento, vedere [Rivalutazione della valute nella società di consolidamento](currency-revaluation-consolidation-company.md).

Per ulteriori informazioni sul funzionamento della rivalutazione della valuta nel modulo **Contabilità generale**, vedere [Rivalutazione valuta estera per la contabilità generale](./foreign-currency-revaluation-general-ledger.md).

### <a name="additional-information"></a>Informazioni aggiuntive
- Tutti i livelli di registrazione vengono consolidati con il processo di consolidamento.
- I giornali di registrazione eliminazioni possono essere registrati solo al livello corrente.
- Solo i saldi operativi vengono consolidati. Pertanto, per visualizzare i saldi iniziali, è necessario eseguire una chiusura di fine anno nella società di consolidamento.
- È possibile registrare un giornale di registrazione giornaliero in una società di eliminazione, ma non in una società di eliminazione.
- Le rettifiche ai saldi in una società di consolidamento possono essere effettuate solo utilizzando la pagina **Rettifiche periodo di chiusura**. 

## <a name="benefits-of-using-financial-reporting-for-financial-consolidations-and-currency-translation-or-to-complement-consolidate-online-for-consolidated-reporting"></a>Vantaggi dell'utilizzo della funzionalità di creazione di report finanziari per i consolidamenti finanziari e la conversione delle valute o per completare il consolidamento online per la creazione di report consolidati
I clienti che utilizzano la funzionalità di creazione di report finanziari per i consolidamenti finanziari e la conversione delle valute o per completare il consolidamento online per la creazione di report consolidati usufruiranno di vari vantaggi:

- **Profondità di dati** - È possibile creare report consolidati che riuniscono i dati effettivi e di budget sia a livello contabile che a livello di dimensioni. Per Finance questi dati includono i dati sia del controllo del budget che della pianificazione del budget.
- **Consolidamenti dinamici** - I consolidamenti possono essere creati in qualsiasi momento e a qualsiasi livello della gerarchia organizzativa.
- **Capacità di controllo complete** - Tutte le dimensioni, i conti e i dettagli delle transazioni vengono gestiti per l'analisi e il controllo. Inoltre, la funzionalità di creazione di report finanziari offre la funzionalità di drill-back completa in qualsiasi delle persone giuridiche consolidate.
- **Conversione della valuta semplificata** - Dopo l'impostazione minima in Finance, è possibile convertire qualsiasi report finanziario in qualsiasi valuta di dichiarazione impostata. È inoltre possibile impostare un numero illimitato di valute di dichiarazione.
- **Registrare le eliminazioni all'origine** - È possibile creare e stampare un report di eliminazione per verificare le transazioni di eliminazione. È quindi possibile registrare qualsiasi nuova eliminazione come transazione interaziendale standard. È inoltre possibile utilizzare una persona giuridica di eliminazione per qualsiasi transazione che non si desidera nelle persone giuridiche.

## <a name="supported-consolidation-scenarios-for-financial-reporting"></a>Scenari di consolidamento supportati per la creazione di report finanziari

Di seguito sono riportati alcuni degli scenari di consolidamento supportati dalla funzionalità di creazione di report finanziari:

- Consolidamenti a singolo livello e multilivello tra persone giuridiche
- Consolidamenti che utilizzano strutture organizzative create da persone giuridiche
- Consolidamenti che implicano eliminazioni
- Interessi di minoranza
- Più piani dei conti tra persone giuridiche
- Calendari fiscali diversi tra più persone giuridiche
- Consolidamenti che includono più valute di dichiarazione
- Consolidamenti di Business Unit

## <a name="generating-consolidated-financial-statements"></a>Generazione di rendiconti finanziari consolidati
Per informazioni sugli scenari in cui si potrebbero generare rendiconti finanziari consolidati, vedere [Generare rendiconti finanziari consolidati](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]