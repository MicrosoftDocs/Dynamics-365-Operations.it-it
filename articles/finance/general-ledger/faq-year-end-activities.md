---
title: Domande frequenti sulle attività di fine anno
description: Questo articolo elenca le domande che possono sorgere in relazione alle attività di chiusura di fine anno e le risposte che possono aiutare per eseguire tali attività.
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853042"
---
# <a name="year-end-activities-faq"></a>Domande frequenti sulle attività di fine anno 

[!include [banner](../includes/banner.md)]

Questo articolo elenca le domande che possono sorgere in relazione alle attività di chiusura di fine anno e le risposte che possono aiutare per eseguire tali attività. Le informazioni in questo articolo si concentrano principalmente sulle domande relative alle attività di chiusura di fine anno per la contabilità generale e la contabilità fornitori.

## <a name="general-ledger-year-end-enhancements"></a>Miglioramenti per la chiusura di fine anno della contabilità generale

Microsoft Dynamics 365 Finance versione 10.0.20 ha introdotto un miglioramento per la chiusura di fine anno. Questo miglioramento è abilitato per impostazione predefinita a partire dalla versione 10.0.25 e diventa obbligatorio a partire dalla versione 10.0.29. Se l'organizzazione utilizza una versione precedente alla 10.0.25, consigliamo di abilitare questa funzionalità prima di iniziare il processo di chiusura di fine anno. Prima di utilizzare la funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro **Gestione funzionalità** per controllare lo stato della funzionalità e, se necessario, attivarla. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo**: Contabilità generale
- **Nome funzionalità**: Miglioramenti per la chiusura di fine anno della contabilità generale

La configurazione dei modelli di chiusura di fine anno è stata spostata nella nuova pagina **Configurazione del modello di chiusura di fine anno**. La pagina di chiusura di fine anno esistente diventa come la pagina **Rivalutazione valuta estera per la contabilità generale**, in cui viene visualizzato un elenco ogni volta che la chiusura di fine anno viene eseguita o stornata. La pagina non mostra le informazioni storiche sulle chiusure di fine anno effettuate prima dell'abilitazione della funzionalità. Un direttore amministrativo può avviare la chiusura di fine anno nella nuova pagina.

Per stornare la chiusura di fine anno, selezionare l'anno fiscale più recente per la persona giuridica appropriata e scegliere **Storna chiusura di fine anno**. Lo storno comporta l'eliminazione delle registrazioni contabili per la chiusura di fine anno precedente, ma non la nuova esecuzione della chiusura di fine anno in modo automatico. Se si abilita la funzionalità **Miglioramenti per la chiusura di fine anno della contabilità generale** dopo aver completato una chiusura di fine anno e si desidera annullare i risultati storici di fine anno, eseguire il chiusura storica di fine anno nuovamente dopo aver abilitato il parametro di Contabilità generale **Elimina voci di chiusura di fine anno esistenti alla nuova chiusura dell'anno**.

È possibile eseguire nuovamente la chiusura di fine anno riavviando il processo per l'anno fiscale e la persona giuridica. Il processo continua a utilizzare l'impostazione dei parametri di contabilità generale per determinare se la nuova esecuzione della chiusura di fine anno tiene conto solo delle transazioni nuove o modificate oppure il processo viene rieseguito per tutte le transazioni e annulla completamente la chiusura precedente.

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>Contabilità generale: la funzionalità Miglioramenti per la chiusura di fine anno della contabilità generale è abilitata. Perché non è possibile visualizzare le chiusure dell'anno precedente nella sezione Cronologia della pagina Chiusura di fine anno?

Prima di abilitare la funzionalità **Miglioramenti per la chiusura di fine anno della contabilità generale**, vengono tracciate la data e l'ora in cui è stato eseguito l'ultimo processo di chiusura di fine anno. Non si è tenuto traccia della cronologia per ogni volta che è stata eseguita la chiusura di fine anno. Pertanto, i dettagli di ogni esecuzione di chiusura di fine anno non sono disponibili per la visualizzazione. Dopo aver abilitato la funzionalità, vengono mantenute le successive informazioni sul processo di chiusura di fine anno. I giustificativi di tutti i processi di chiusura di fine anno, anche quelli eseguiti prima dell'abilitazione della funzionalità, possono essere visualizzati nella pagina **Transazioni giustificativo**. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>Contabilità generale: il processo di chiusura di fine anno non riesce a causa del seguente errore: "Impossibile eseguire la chiusura di fine anno perché una o più transazioni contabili registrate nell'anno fiscale che si sta chiudendo sono state liquidate in una transazione contabile in un anno fiscale diverso". Cosa significa questo errore?

Poiché la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** è abilitata, solo le transazioni contabili liquidate dell'anno fiscale in chiusura sono escluse dal saldo iniziale. Questo comportamento fa sì che debiti e crediti siano sbilanciati. Per ulteriori informazioni, vedere [Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno](awareness-between-ledger-settlement-year-end-close.md).

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>Contabilità generale: lo storno del processo di chiusura di fine anno non riesce a causa del seguente errore: "La chiusura di fine anno per 1/1/2022 non può essere stornata perché la transazione del saldo iniziale è stata liquidata in contabilità generale nell'anno fiscale 1/1/2023." Cosa significa questo errore?

Poiché la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** è abilitata, gli storni dell'elaborazione di fine anno non sono consentiti se le transazioni di apertura sono state liquidate nel nuovo anno fiscale. Stornare la liquidazione contabile nel nuovo anno fiscale 2023 prima di stornare la chiusura di fine anno per il 1° gennaio 2022. In alternativa, richiudere l'anno per il 1° gennaio 2022, ma solo per le nuove voci di rettifica. Per richiudere l'anno solo per le rettifiche, disabilitare il parametro di Contabilità generale **Elimina voci di fine anno esistenti alla nuova chiusura dell'anno**.

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>Contabilità generale: perché l'automazione di compensazioni dei saldi contabili non elabora le transazioni di compensazioni dei saldi contabili di dicembre?

La funzionalità **Automatizza compensazioni dei saldi contabili** esegue l'automazione per le transazioni con data dal primo giorno dell'anno fiscale alla data corrente in cui viene eseguita l'occorrenza. Per gli anni fiscali che terminano il 31 dicembre, potrebbe essere necessario modificare la data di esecuzione dell'occorrenza per garantire che venga eseguita a dicembre. Ad esempio, l'automazione è configurata per essere eseguita il primo giorno di ogni mese. Questa automazione viene eseguita il 1° dicembre 2022 ed è programmata per il 1° gennaio 2023. Si consiglia di modificare l'occorrenza per il 1° gennaio 2023, in modo che venga eseguita il 31 dicembre 2022. Questa modifica garantisce che le transazioni con data dal 2 al 31 dicembre sono prese in considerazione per la liquidazione automatica.

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>Contabilità generale: qual è la differenza tra l'azione Storna chiusura di fine anno e il parametro Elimina voci di fine anno esistenti alla nuova chiusura dell'anno?

Potrebbe esserci confusione sulla differenza tra l'azione **Storna chiusura di fine anno** e il parametro di Contabilità generale **Elimina voci di fine anno esistenti alla nuova chiusura dell'anno** (**Contabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale**).

Selezionare l'azione **Storna chiusura di fine anno** quando si esegue il processo di chiusura di fine anno per eliminare tutte le voci del saldo finale e del saldo iniziale, come se la chiusura di fine anno non fosse mai stata eseguita. In tal caso, i giustificativi vengono eliminati. La chiusura di fine anno non viene ripetuta automaticamente. Per eseguire la chiusura di fine anno, selezionare l'azione **Esegui chiusura di fine anno**.

Il parametro **Elimina voci di fine anno esistenti alla nuova chiusura dell'anno** in Contabilità generale viene utilizzato solo quando si esegue (non si storna) la chiusura di fine anno. Se il parametro è impostato su **Sì**, tutte le voci del saldo finale e del saldo iniziale vengono eliminate e la chiusura di fine anno viene eseguita nuovamente. Questa opzione viene utilizzata quando l'organizzazione desidera che tutte le transazioni, comprese le rettifiche dall'ultima chiusura di fine anno, vengano registrate in una singola voce contabile per le voci del saldo finale e del saldo iniziale. Se il parametro è impostato su **No**, tutte le voci del saldo finale e del saldo iniziale rimangono inalterate. Non vengono eliminate. Viene invece creata una nuova voce di saldo finale e di saldo iniziale solo per il delta o per le nuove transazioni registrate dall'ultima chiusura di fine anno per quell'anno fiscale.

> [!NOTE]
> La voce del saldo finale viene creata nell'anno in corso di chiusura. Ciò si verifica solo se il parametro **Crea transazioni di chiusura durante il trasferimento** nella contabilità generale è impostato su **Sì**. La voce del saldo iniziale viene sempre creata, perché è il saldo iniziale per l'anno successivo.

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>Contabilità generale: qual è la differenza tra le opzioni "Chiudi tutto" e "Chiudi singolo" nella sezione Trasferisci dimensioni di profitti e perdite del processo di chiusura di fine anno?

**Chiudi tutto** mantiene i valori di dimensione finanziaria originali delle transazioni registrate e li utilizza per creare i saldi iniziali per il conto utili non distribuiti. I saldi iniziali distinti per gli utili distribuiti vengono creati per ogni combinazione specifica di valori di dimensione finanziaria. Se l'opzione **Chiudi singolo** è selezionata, tutte le transazioni registrate con quella dimensione finanziaria vengono riepilogate in un saldo iniziale utili non distribuiti per il valore di dimensione immesso nel campo dopo **Chiudi singolo**. 

Ad esempio, si supponga che tutte le transazioni per l'anno fiscale siano state registrate con la struttura dei conti del conto principale - Reparto. Nella dimensione finanziaria Reparto del modello, l'opzione **Chiudi singolo** è selezionata e 100 è il valore di dimensione immesso. Se il ricavo totale di tutte le transazioni registrate per i reparti 200, 300 e 400 è $ 100.000, un saldo iniziale viene creato per gli utili non distribuiti - 100. Se si seleziona **Chiudi singolo** ma si lascia vuoto il valore della dimensione finanziaria, tutte le transazioni vengono registrate come utili non distribuiti con tale valore di dimensione vuoto.

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>Contabilità generale: quando si seleziona l'opzione "Chiudi singolo" nella sezione Trasferisci dimensioni di profitti e perdite del processo di chiusura di fine anno, le informazioni dettagliate sulle transazioni vanno perse?

Le opzioni **Chiudi tutto** e **Chiudi singolo** vengono utilizzate per specificare quali dimensioni finanziarie nelle transazioni registrate nei conti profitti e perdite vengono trasferite nel conto principale degli utili non distribuiti. La registrazione storica e dettagliata dei conti profitti e perdite non è influenzata e rimarrà dettagliata. L'opzione influisce sul livello di dettaglio che viene trasferito ai conti degli utili non distribuiti come saldo iniziale del nuovo anno. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>Contabilità generale: il processo di chiusura di fine anno non riesce perché la valuta di dichiarazione per l'anno non è bilanciata. Cosa significa?

Questo errore può verificarsi dopo aver abilitato la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** (la funzionalità Riconoscimento). Quando la funzionalità è abilitata, le transazioni contabili che sono state liquidate non saranno più incluse nel saldo iniziale dell'anno fiscale successivo per l'esecuzione della chiusura di fine anno della contabilità generale. L'esclusione delle transazioni contabili liquidate può rappresentare una sfida per i clienti alla chiusura di fine anno se la contabilità generale è definita con la valuta di dichiarazione.   
La compensazione dei saldi contabili viene eseguita solo per la valuta di contabilizzazione.  Quando le transazioni contabili vengono liquidate, la convalida garantisce solo che i debiti nella valuta di contabilizzazione siano uguali ai crediti nella valuta di contabilizzazione. Gli importi in valuta di dichiarazione per tali transazioni contabili non sono convalidati e potrebbero non avere debiti pari ai crediti.  Inoltre, la compensazione dei saldi contabili non calcola né registra automaticamente un profitto o una perdita nella valuta di dichiarazione.  A causa di queste limitazioni, una transazione di profitto/perdita deve essere nella valuta di dichiarazione per l'esecuzione della compensazione dei saldi contabili.  Se la transazione profitto/perdita non è inclusa nella compensazione dei saldi contabili, la chiusura di fine anno restituisce un messaggio di sbilanciamento.  Per ulteriori informazioni, vedere [Funzionalità Riconoscimento tra liquidazione saldi contabili e valuta di dichiarazione sbilanciata](reporting-currency-yec.md).

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>Contabilità generale: cosa è possibile modificare per migliorare le prestazioni dell'elaborazione di fine anno?

È possibile apportare una serie di modifiche per migliorare le prestazioni della chiusura di fine anno. Considerare le modifiche suggerite per determinare se sono appropriate per la propria organizzazione.

### <a name="optimize-year-end-close-service"></a>Servizio Ottimizzazione della chiusura di fine anno

Il servizio **Ottimizzazione della chiusura di fine anno** consente ai clienti Microsoft Dynamics 365 Finance di accelerare la chiusura di fine anno spostando la pesante elaborazione di fine anno in un microservizio. Il tempo risparmiato grazie a un'efficiente chiusura di fine anno consente a ciascun team di Finance di reagire in modo tempestivo alle rettifiche richieste, fino alla generazione dei report finanziari. Elaborando la chiusura di fine anno in un microservizio, vengono liberate risorse preziose. L'elevazione dell'elaborazione riduce al minimo il carico su SQL Server e offre ai clienti l'opportunità di accelerare l'elaborazione della chiusura di fine anno.

Il servizio **Ottimizzazione della chiusura di fine anno** è disponibile nella versione 10.0.31, per permettere a più clienti di utilizzare il nuovo servizio per la chiusura di fine anno 2022. Inoltre, il servizio è stato riportato nelle versioni 10.0.30 e 10.0.29. Per ulteriori informazioni, vedere [Ottimizzazione della chiusura di fine anno](optimize-year-end-close.md).

### <a name="dimension-sets"></a>Set di dimensioni

Quando si esegue la chiusura di fine anno, il saldo di ogni set di dimensioni viene ricreato. Questo comportamento ha un impatto diretto sulle prestazioni. Alcune organizzazioni creano set di dimensioni inutilmente perché sono già stati utilizzati o potrebbero essere utilizzati in futuro. Dal momento che questi set di dimensioni non necessari vengono ricostruiti durante la chiusura di fine anno, aumenta il tempo necessario al processo. Valutare con attenzione i set di dimensioni ed eliminare quelli che non sono necessari.

I set di dimensioni non necessari influiscono anche sul processo batch **BudgetDimensionFocusInitializeBalance** (**Contabilità generale \> Piano dei conti \> Dimensioni \> Set di dimensioni finanziarie**).

[![Set di dimensioni finanziarie.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configurazione del modello di chiusura di fine anno

Il modello di chiusura di fine anno consente alle organizzazioni di selezionare il livello di dimensione finanziaria da mantenere quando si trasferiscono i saldi di profitti e perdite agli utili non distribuiti. Le impostazioni consentono a un'organizzazione di mantenere le dimensioni finanziarie dettagliate (**Chiudi tutto**) quando si spostano i saldi negli utili non distribuiti o si sceglie di riepilogare gli importi in un singolo valore di dimensione (**Chiudi singolo**). Queste impostazioni possono essere definite per ogni dimensione finanziaria. Per ulteriori informazioni su queste impostazioni, vedere l'articolo [Chiusura di fine anno](year-end-close.md).

Si consiglia di valutare i requisiti dell'organizzazione e, se possibile, chiudere il maggior numero di dimensioni possibile utilizzando l'opzione di fine anno **Chiudi singolo** per migliorare le prestazioni. Se si chiude un valore di dimensione singola (che può anche essere un valore vuoto), il sistema calcola meno dettagli quando determina i saldi per le voci contabili relative a utili non distribuiti.

### <a name="degenerate-dimensions"></a>Dimensioni degenerate

Una dimensione degenerata consente poco o nessun riutilizzo da sola e in combinazione con altre dimensioni. Sono presenti due tipi di dimensioni degenerate. Il primo tipo è una dimensione degenerata individualmente. In genere, questo tipo di dimensione degenerata è presente solo in una singola transazione o in piccoli insiemi di transazioni. Il secondo tipo è una dimensione che diventa degenerata in combinazione con una o più dimensioni aggiuntive che mostrano lo stesso potenziale in base alle possibili permutazioni che possono essere generate. Una dimensione degenerata può avere un impatto significativo sulle prestazioni del processo di chiusura di fine anno. Per ridurre i problemi di prestazioni, definire tutte le dimensioni degenerate come **Chiudi singolo** nella configurazione di chiusura di fine anno, come descritto nella sezione precedente.

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>Contabilità fornitori: quali modifiche sono state apportate per supportare la creazione di report di fine anno 1099 per il 2022?

#### <a name="update-to-all-1099-forms"></a>Aggiornamento a tutti i moduli 1099

Le seguenti modifiche sono state apportate a tutti i moduli 1099 per l'anno fiscale 2022:

- Nel 2021 l'anno era fisso sui moduli 1099. A partire dal 2022, l'anno viene compilato dal report.

#### <a name="1099-misc"></a>1099-MISC

I seguenti aggiornamenti sono stati effettuati sul modulo 1099-MISC per l'anno fiscale 2022:

- Casella 13: ora indica il requisito di compilazione del Foreign Account Tax Compliance Act (FATCA).
- Casella 14: utilizzata ora per segnalare i pagamenti in eccesso del paracadute d'oro.
- Casella 15: utilizzata ora per segnalare il pagamento nell'ambito dei piani di compensazione differita non qualificata (NQDC).
- Casella 16: utilizzata ora per segnalare le ritenute statali.
- Casella 17: utilizzata ora per segnalare il numero di stato del pagatore.
- Casella 18: utilizzata ora per segnalare il reddito statale.

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Contabilità fornitori: 1099 - Come si modifica il riquadro 1099 e i valori per un fornitore che non ha tracciato le informazioni 1099 durante l'anno?

Utilizzare la funzionalità **Aggiorna modulo 1099** per esaminare le transazioni di fatture pagate in precedenza e riassegnare i dati del modulo 1099 in modo appropriato, secondo le impostazioni della scheda **Imposta 1099** della pagina **Fornitore**. Per utilizzare la funzionalità **Aggiorna modulo 1099**, andare a **Contabilità fornitori \> Fornitori \> Tutti i fornitori**, selezionare un fornitore, quindi, nel riquadro Azioni della scheda **Fornitore** scegliere **Aggiorna modulo 1099**.

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>È possibile eseguire la funzionalità Aggiorna modulo 1099 per tutti i fornitori contemporaneamente?

È possibile utilizzare la pagina **Aggiorna informazioni nel modulo 1099 per più fornitori** per aggiornare la casella 1099 in un record fornitore e per aggiornare le transazioni con le informazioni dalla casella 1099. Per aprire questa pagina, andare a **Contabilità fornitori \> Attività periodica \> Imposta 1099**. Per accedere alla pagina, è necessario disporre del privilegio di sicurezza **Aggiorna casella e transazioni 1099 per più fornitori**.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Contabilità fornitori: 1099 - Ricalcola importi 1099 esistenti e Aggiorna tutto nell'utilità Aggiorna modulo 1099

La casella di controllo **Ricalcola importi 1099 esistenti** reimposta l'importo 1099 sui valori totali pagati, se utilizzato insieme alla casella di controllo **Aggiorna tutto**.

[![Transazioni fiscali 1099: prima di eseguire la routine di aggiornamento.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

La casella di controllo **Ricalcola importi 1099 esistenti** viene considerata solo quando sono presenti valori 1099 parziali sulla fattura o se la fattura è stata modificata nel modulo Imposta 1099. Ad esempio, si supponga di avere una fattura con valore $1000,00, ma l'utente digita manualmente un importo 1099 sulla fattura di $ 500,00.

[![Transazioni IVA 1099: contrassegnare Aggiorna tutto e Ricalcola importi 1099 esistenti.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Quando la fattura viene pagata, $ 500,00 sarà l'importo 1099 corrisposto. Se si esegue la routine di ricalcolo, l'importo 1099 viene modificato in $1000,00, che è il totale corrisposto.

[![Transazioni fiscali 1099: dopo aver eseguito la routine 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Contabilità fornitori: 1099 - Creare manualmente transazioni 1099

Un'organizzazione potrebbe dover creare manualmente le transazioni 1099 non associate a una fattura. È possibile aggiungere transazioni 1099 manuali andando in **Contabilità fornitori \> Attività periodiche \> Imposta 1099 \> Liquidazione fornitore per i moduli 1099**. Selezionare il pulsante **Transazioni 1099 manuali**.

Le transazioni 1099 create manualmente non vengono aggiornate con il processo **Aggiorna tutto** o il processo **Ricalcola importi 1099 esistenti** nell'utilità **Aggiorna modulo 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Contabilità fornitori: 1099 - Il modulo Dynamics 365 Finance supporta il modulo 1096?

Dynamics 365 Finance non stampa il modulo 1096 Riepilogo annuale e trasmissione delle dichiarazioni negli Stati Uniti.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Contabilità fornitori: 1099 - Esistono nuove funzionalità che supportano la creazione di report 1099 per il settore pubblico?

È stata aggiunta una nuova funzionalità del settore pubblico, **Aggiorna informazioni 1099 per conto principale**, che è possibile abilitare nell'area di lavoro **Gestione funzionalità**. Questa funzionalità consente di associare i valori dei moduli 1099 per un fornitore dal conto principale nella distribuzione contabile, piuttosto che dal conto predefinito nel record fornitore.

Per ulteriori informazioni, vedere [Configurare i fornitori per la creazione di report 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
