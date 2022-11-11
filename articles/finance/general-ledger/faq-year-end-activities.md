---
title: Domande frequenti sulle attività di fine anno
description: Questo articolo elenca le domande che possono sorgere in relazione alle attività di chiusura di fine anno e le risposte che possono aiutare per eseguire tali attività.
author: moaamer
ms.date: 11/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a75d1e3e68837a437b2369ba369b0063e015b12
ms.sourcegitcommit: 78cbb125f20a33df38bda0546203b8f837cbcd93
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2022
ms.locfileid: "9751959"
---
# <a name="year-end-activities-faq"></a>Domande frequenti sulle attività di fine anno 

[!include [banner](../includes/banner.md)]

Questo articolo elenca le domande che possono sorgere in relazione alle attività di chiusura di fine anno e le risposte che possono aiutare per eseguire tali attività. Le informazioni in questo articolo si concentrano principalmente sulle domande relative alle attività di chiusura di fine anno per la contabilità generale e la contabilità fornitori.

## <a name="general-ledger-year-end-enhancements"></a>Miglioramenti per la chiusura di fine anno della contabilità generale 
Nella versione 10.0.20 è stato introdotto un miglioramento della chiusura di fine anno, abilitato per impostazione predefinita a partire dalla versione 10.0.25. Se l'organizzazione utilizza una versione precedente alla 10.0.25, consigliamo di abilitare questa funzionalità prima di iniziare il processo di chiusura di fine anno. Prima di utilizzare la funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro Gestione funzionalità per controllare lo stato della funzionalità e, se necessario, attivarla. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

 - Modulo: Contabilità generale
 - Nome funzionalità: Miglioramenti per la chiusura di fine anno della contabilità generale

La configurazione dei modelli di chiusura di fine anno è stata spostata nella nuova pagina **Configurazione del modello di chiusura di fine anno**. La pagina di chiusura di fine anno esistente cambierà in modo simile alla pagina Rivalutazione valuta estera per la contabilità generale, in cui viene visualizzato un elenco ogni volta che la chiusura di fine anno viene eseguita o stornata. Un direttore amministrativo può avviare la chiusura di fine anno nella nuova pagina. 

Per stornare la chiusura di fine anno, selezionare l'anno fiscale più recente per la persona giuridica appropriata e scegliere il pulsante **Storna chiusura di fine anno**. Lo storno comporta l'eliminazione delle registrazioni contabili per la chiusura di fine anno precedente, ma non la nuova esecuzione della chiusura di fine anno in modo automatico. 

È possibile eseguire nuovamente la chiusura di fine anno riavviando il processo per l'anno fiscale e la persona giuridica. Il processo continua a utilizzare l'impostazione dei parametri di contabilità generale per determinare se la riesecuzione della chiusura di fine anno tiene conto solo delle transazioni nuove o modificate oppure annulla completamente la chiusura precedente, rieseguendo il processo per tutte le transazioni.  

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Contabilità generale: come si fa a sapere se è in esecuzione la chiusura di fine anno e non l'annullamento della chiusura di fine anno?
Abbiamo notato organizzazioni che cercavano di eseguire la chiusura di fine anno e invece stavano eseguendo un annullamento della chiusura di fine anno. Se la chiusura di fine anno termina molto rapidamente o non produce saldi iniziali, convalidare l'impostazione **Annulla chiusura precedente** in **Chiusura di fine anno** (**Contabilità generale > Periodo chiuso > Chiusura di fine anno > Esegui chiusura fiscale**). 

[![Chiusura di fine anno in corso e chiusura di fine anno annullata.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Se **Annulla chiusura precedente** è impostato su **Sì**, la chiusura di fine anno precedente viene annullata. Quando si esegue un annullamento, il saldo finale e il saldo iniziale vengono completamente eliminati, come se la chiusura di fine anno non fosse mai stata eseguita. I giustificativi vengono eliminati. La chiusura di fine anno non viene ripetuta automaticamente. È necessario rieseguire il processo, questa volta impostando **Annulla chiusura precedente** su **No**. 

> [!NOTE]
> La voce del saldo finale viene facoltativamente creata nell'anno in corso di chiusura. Ciò si verifica solo se il parametro di Contabilità generale **Crea transazioni di chiusura durante il trasferimento** è impostato su **Sì**. La voce del saldo iniziale viene sempre creata, perché è il saldo iniziale per l'anno successivo.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Contabilità generale: qual è la differenza tra i parametri di contabilità generale Annulla ed Elimina per la chiusura di fine anno?
Potrebbe esserci confusione sulla differenza tra il parametro **Annulla chiusura precedente** che si trova nella finestra di dialogo **Chiusura di fine anno** e il parametro **Elimina transazioni di fine anno durante il trasferimento** nella contabilità generale (**Contabilità generale > Periodo chiuso > Chiusura di fine anno > Esegui chiusura fiscale**).  

[![Differenza tra i parametri di contabilità generale Annulla ed Elimina per la chiusura di fine anno.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Selezionare **Annulla chiusura precedente** nel menu a discesa quando si esegue il processo di chiusura di fine anno per eliminare tutte le voci del saldo finale e del saldo iniziale, come se la chiusura di fine anno non fosse mai stata eseguita. I giustificativi verranno eliminati. La chiusura di fine anno non viene ripetuta automaticamente. Per eseguire la chiusura di fine anno, è necessario avviare nuovamente questo processo, questa volta impostando **Annulla chiusura precedente** su **No** (**Contabilità generale > Impostazioni contabilità generale > Parametri di contabilità generale**). 

[![Impostazione dei parametri di contabilità generale.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

Il parametro **Elimina transazioni di fine anno durante il trasferimento** nella contabilità generale viene utilizzato solo quando si esegue (non si annulla) la chiusura di fine anno (**Annulla chiusura precedente** è impostato su **No**). Se quel parametro è impostato su **Sì**, tutte le voci del saldo finale e del saldo iniziale verranno eliminate e la chiusura di fine anno verrà eseguita nuovamente. Questo processo viene utilizzato quando l'organizzazione desidera che tutte le transazioni, comprese le rettifiche dall'ultima chiusura di fine anno, vengano registrate in una singola voce contabile per le voci del saldo finale e del saldo iniziale. 

Se questa opzione è impostata su **No**, tutte le voci del saldo finale e del saldo iniziale rimangono inalterate. Non vengono eliminate. Viene invece creata una nuova voce di saldo finale e di saldo iniziale solo per il delta o per le nuove transazioni registrate dall'ultima chiusura di fine anno per quell'anno fiscale.  

> [!NOTE]
> La voce del saldo finale viene creata nell'anno in corso di chiusura. Ciò si verifica solo se il parametro **Crea transazioni di chiusura durante il trasferimento** nella contabilità generale è impostato su **Sì**. La voce del saldo iniziale viene sempre creata, perché è il saldo iniziale per l'anno successivo. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Contabilità generale: cosa è possibile modificare per migliorare le prestazioni dell'elaborazione di fine anno? 
È possibile apportare una serie di modifiche per migliorare le prestazioni della chiusura di fine anno. Considerare le modifiche suggerite per valutare se sono appropriate per la propria organizzazione.  

### <a name="dimension-sets"></a>Set di dimensioni
Quando si esegue la chiusura di fine anno, il saldo di ogni set di dimensioni viene ricostruito, con un impatto diretto sulle prestazioni. Alcune organizzazioni creano set di dimensioni inutilmente perché sono già stati utilizzati o potrebbero essere utilizzati in futuro.  Questi set di dimensioni non necessari vengono comunque ricostruiti durante la chiusura di fine anno, il che aggiunge tempo al processo. Valutare con attenzione i set di dimensioni ed eliminare quelli non necessari.

I set di dimensioni non necessari influiscono anche sul processo batch **BudgetDimensionFocusInitializeBalance** (**Contabilità generale > Piano dei conti > Dimensioni > Set di dimensioni finanziarie**).

[![Set di dimensioni finanziarie.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configurazione del modello di chiusura di fine anno
Il modello di chiusura di fine anno consente alle organizzazioni di selezionare il livello di dimensione finanziaria da mantenere quando si trasferiscono i saldi di profitti e perdite agli utili non distribuiti. Le impostazioni consentono a un'organizzazione di mantenere le dimensioni finanziarie dettagliate (**Chiudi tutto**) quando si spostano i saldi negli utili non distribuiti o si sceglie di riepilogare gli importi in un singolo valore di dimensione (**Chiudi singolo**). Queste impostazioni possono essere definite per ogni dimensione finanziaria. Per ulteriori informazioni su queste impostazioni, vedere l'articolo [Chiusura di fine anno](year-end-close.md).

Si consiglia di valutare i requisiti dell'organizzazione e, se possibile, chiudere il maggior numero di dimensioni possibile utilizzando l'opzione di fine anno **Chiudi singolo** per migliorare le prestazioni. Se si chiude un valore di dimensione singola (che può anche essere un valore vuoto), il sistema calcola meno dettagli quando determina i saldi per le voci contabili relative a utili non distribuiti.

## <a name="degenerate-dimensions"></a>Dimensioni degenerate

Una dimensione degenerata consente poco o nessun riutilizzo da sola e in combinazione con altre dimensioni. Sono presenti due tipi di dimensioni degenerate. Il primo tipo è una dimensione degenerata individualmente. In genere, questo tipo di dimensione degenerata è presente solo in una singola transazione o in piccoli insiemi di transazioni. Il secondo tipo è una dimensione che diventa degenerata in combinazione con una o più dimensioni aggiuntive che mostrano lo stesso potenziale in base alle possibili permutazioni che possono essere generate. Una dimensione degenerata può avere un impatto significativo sulle prestazioni del processo di chiusura di fine anno. Per ridurre i problemi di prestazioni, definire tutte le dimensioni degenerate come **Chiudi singolo** nella configurazione di chiusura di fine anno, come descritto nella sezione precedente.

## <a name="general-ledger-what-does-the-period-close-year-end-close-do"></a>Contabilità generale: cosa accade quando si seleziona Periodo chiuso - Chiusura di fine anno?
 
[![Periodo chiuso, chiusura di fine anno.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets"></a>Prestazioni migliorate per la ricostruzione dei set di dimensioni finanziarie
Una nuova funzionalità aggiunta nella versione 10.0.16 migliora le prestazioni dei processi di chiusura e consolidamento di fine anno. La funzione si chiama Miglioramenti delle prestazioni per la ricostruzione dei set di dimensioni finanziarie. Questa funzione cambia il modo in cui vengono ricostruiti i set di dimensioni in modo che vengano ricostruiti solo per un periodo di tempo specifico. Nelle versioni precedenti, i set di dimensioni venivano ricostruiti per tutte le date. Ad esempio, se si sta chiudendo l'anno 2020, il sistema ricostruisce solo i saldi per le transazioni entro l'anno fiscale 2020. Se si esegue il consolidamento per un intervallo di date compreso tra il 1° e il 30 novembre 2020, il sistema ricostruisce solo i saldi per quell'intervallo di date.

Prima di utilizzare la funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro Gestione funzionalità per controllare lo stato della funzionalità e, se necessario, attivarla. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:
 
- Modulo: Contabilità generale
- Nome funzionalità: Miglioramenti delle prestazioni per la ricostruzione dei set di dimensioni finanziarie

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2021"></a>Contabilità fornitori: quali modifiche sono state apportate per supportare la creazione di report di fine anno 1099 per il 2021?

Nel 2021, i moduli DIV, NEC e MISC sono stati leggermente modificati e sono state aggiunte alcune caselle aggiuntive.

#### <a name="div-new-box2e-2f"></a>DIV: nuova casella 2e, 2f
 
- Casella 2e. Mostra la parte dell'importo nella casella 1a, ovvero il guadagno della sezione 897 attribuibile alla cessione di interessi immobiliari statunitensi (USRPI).  
- Casella 2f. Mostra la parte dell'importo nella casella 2a, ovvero il guadagno della sezione 897 attribuibile alla cessione USRPI. Si noti che le caselle 2e e 2f si applicano solo a persone ed entità straniere il cui reddito mantiene il proprio carattere quando viene trasferito o distribuito ai relativi proprietari o beneficiari esteri diretti o indiretti. Il valore è generalmente considerato come effettivamente collegato a un'attività commerciale o aziendale negli Stati Uniti. Vedere le istruzioni per la dichiarazione dei redditi. 
 
#### <a name="nec-new-box-2"></a>NEC: nuova casella 2 
 
Se la casella 2 è selezionata, segnala i prodotti di consumo per un totale di 5.000 USD o più che sono stati venduti per la rivendita, in una transazione di compravendita, in una commissione di deposito o su altre basi. In generale, è necessario segnalare qualsiasi reddito derivante dalla vendita di questi prodotti nell'allegato C (modulo 1040). 
 
Nel frattempo, la dimensione del modulo di NEC è cambiata. Durante la stampa, sono presenti tre moduli per pagina. 
 
#### <a name="misc-new-box-11"></a>MISC: nuova casella 11 
 
La casella 11 mostra l'importo pagato per l'acquisto di pesce per la rivendita da parte di qualsiasi persona nel settore ittico. Per dichiarare questo reddito, vedere le istruzioni per la dichiarazione dei redditi. 
 
#### <a name="electronic-filing"></a>Presentazione elettronica 
Per informazioni sulla presentazione elettronica, vedere [Pubblicazione sui requisiti di presentazione elettronica](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

Aggiornare le specifiche del formato e i layout dei record per la dichiarazione elettronica 2021 
- Sez. 2 Record emittente "A". 
- Codici importo - Posizione campo aumentata 28-45, lunghezza portata a 18. 
 
#### <a name="sec-2-issuer-a-record-for-reporting-payments-on-form-1099-div"></a>Sez. 2 Record emittente "A" per la dichiarazione di pagamenti nel modulo 1099-DIV: 
- Tipo di importo - Aggiunta della sezione 897, Dividendi ordinari, e aggiunta del codice importo H. 
- Tipo di importo - Aggiunta della sezione 897, Plusvalenze, e aggiunta del codice importo J. 
 
#### <a name="sec-3-payee-b-record"></a>Sez. 3 Record beneficiario "B" 
- Record informativi generali - Terzo punto aggiornato da 16 a 18 per i campi di importo pagamento. 
- Titolo del campo Pagamento H - Aggiornati posizione del campo 247-258, titolo del campo, lunghezza e descrizione generale del campo. 
- Titolo del campo Pagamento J - Aggiornati posizione del campo 259-270, titolo del campo, lunghezza e descrizione generale del campo. 
- Campo vuoto aggiornato in posizione campo 271-286. 
- Indicatore di paese estero aggiornato in posizione campo 287. 
- Campo riga del nome del primo beneficiario aggiornato in posizione campo 288-327. 
- Campo riga del nome del secondo beneficiario aggiornato in posizione campo 328-367. 
- Posizioni del layout del record, modulo 1099-MISC - Posizione campo 548 e indicatore dei requisiti di presentazione FATCA del titolo del campo eliminati. 
- Posizioni layout record, modulo 1099-NEC - Campo 545-546 aggiornato come vuoti, campo 547 aggiornato all'indicatore di vendita diretta, lunghezza, descrizione e osservazioni, campo 548-722 aggiornato come vuoto. 
 
#### <a name="sec-4-end-of-issuer-c-record"></a>Sez. 4 Fine del record emittente "C" 
- Titolo del campo Pagamento H - Aggiornati posizione del campo 304-321, titolo del campo, lunghezza e descrizione generale del campo. 
- Titolo del campo Pagamento J - Aggiornati posizione del campo 322-339, titolo del campo, lunghezza e descrizione generale del campo. 
- Titolo campo 340-499 - Lunghezza aggiornata a 160. 
 
#### <a name="sec-5-state-totals-k-record"></a>Sez. 5 record totale stato "K" 
- Titolo del campo Pagamento H - Aggiornati posizione del campo 304-321, titolo del campo, lunghezza e descrizione generale del campo. 
- Titolo del campo Pagamento J - Aggiornati posizione del campo 322-339, titolo del campo, lunghezza e descrizione generale del campo. 
- Titolo campo 340-499 - Lunghezza aggiornata a 160.  

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Contabilità fornitori: 1099 - Come si modifica il riquadro 1099 e i valori per un fornitore che non ha tracciato le informazioni 1099 durante l'anno?
Usare la funzionalità Aggiorna modulo 1099 (**Contabilità fornitori > Fornitori > Tutti i fornitori > Seleziona un fornitore > scheda Fornitore nella barra multifunzione > Aggiorna modulo 1099**) per esaminare le transazioni di fatture precedentemente pagate e riassegnare i dati 1099 in modo appropriato in base alle impostazioni nella scheda **Imposta 1099** della pagina **Fornitore**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>È possibile eseguire l'aggiornamento 1099 per tutti i miei fornitori contemporaneamente?
N. La routine Aggiorna modulo 1099 viene eseguita su un singolo fornitore alla volta. Se questo requisito è necessario per l'organizzazione, votare per l'idea intitolata [Processo batch per l'aggiornamento dei dati 1099 del fornitore](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Contabilità fornitori: 1099 - Ricalcola importi 1099 esistenti e Aggiorna tutto nell'utilità Aggiorna modulo 1099
La casella di controllo **Ricalcola importi 1099 esistenti** reimposta l'importo 1099 sui valori totali pagati, se utilizzato insieme alla casella di controllo **Aggiorna tutto**. 

[![Transazioni fiscali 1099: prima di eseguire la routine di aggiornamento.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

La casella di controllo **Ricalcola importi 1099 esistenti** viene considerata solo quando sono presenti valori 1099 parziali sulla fattura o se è stata modificata nel modulo Imposta 1099. Ad esempio, si supponga di avere una fattura con valore $1000,00, ma l'utente digita manualmente un importo 1099 sulla fattura di $500,00.

[![Transazioni IVA 1099: contrassegnare Aggiorna tutto e Ricalcola importi 1099 esistenti.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Quando viene pagato, $ 500,00 sarà l'importo 1099 corrisposto. Se si esegue la routine di ricalcolo, il sistema modifica l'importo 1099 in $1000,00, che è il totale pagato.

[![Transazioni fiscali 1099: dopo aver eseguito la routine 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Contabilità fornitori: 1099 - Creare manualmente transazioni 1099
Un'organizzazione potrebbe dover creare manualmente le transazioni 1099 non associate a una fattura. È possibile aggiungere transazioni 1099 manuali andando in **Contabilità fornitori > Attività periodiche > Imposta 1099 > Liquidazione fornitore per i moduli 1099**. Selezionare il pulsante **Transazioni 1099 manuali**. 

Le transazioni 1099 create manualmente non vengono aggiornate con il processo **Aggiorna tutto** o il processo **Ricalcola importi 1099 esistenti** nell'utilità **Aggiorna modulo 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Contabilità fornitori: 1099 - Il modulo Dynamics 365 Finance supporta il modulo 1096? 

Dynamics 365 Finance non stampa il modulo 1096 Riepilogo annuale e trasmissione delle dichiarazioni negli Stati Uniti.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Contabilità fornitori: 1099 - Esistono nuove funzionalità che supportano la creazione di report 1099 per il settore pubblico? 
È stata aggiunta una nuova funzionalità del settore pubblico, **Aggiorna informazioni 1099 per conto principale**, che è possibile abilitare nell'area di lavoro **Gestione funzionalità**. Questa funzionalità consente di associare i valori dei moduli 1099 per un fornitore dal conto principale nella distribuzione contabile, piuttosto che dal conto predefinito nel record fornitore.

Per ulteriori informazioni, vedere [Configurare i fornitori per la creazione di report 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
