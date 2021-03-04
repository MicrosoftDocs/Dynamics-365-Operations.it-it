---
title: Domande frequenti sulle attività di fine anno
description: In questo argomento sono riportate informazioni utili per le attività di chiusura di fine anno.
author: kweekley
manager: tfehr
ms.date: 01/25/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6d10f54913ca8dff56a59ea597a9bd7c3e69d4bc
ms.sourcegitcommit: bd4763cc6088e114818e80bb1c27c6521b039743
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5107697"
---
# <a name="year-end-activities-faq"></a>Domande frequenti sulle attività di fine anno 

In questo argomento sono riportate informazioni utili per le attività di chiusura di fine anno. Le informazioni in questo argomento si concentrano principalmente sulle domande relative alle attività di chiusura di fine anno per la contabilità generale e la contabilità fornitori.

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Contabilità generale: come si fa a sapere se è in esecuzione la chiusura di fine anno e non l'annullamento della chiusura di fine anno?
Abbiamo notato organizzazioni che cercavano di eseguire la chiusura di fine anno e invece stavano eseguendo un annullamento della chiusura di fine anno. Se la chiusura di fine anno termina molto rapidamente o non produce saldi iniziali, convalidare l'impostazione **Annulla chiusura precedente** in **Chiusura di fine anno** (**Contabilità generale > Periodo chiuso > Chiusura di fine anno > Esegui chiusura fiscale**). 

[![Chiusura di fine anno in corso e chiusura di fine anno annullata](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Se **Annulla chiusura precedente** è impostato su **Sì**, la chiusura di fine anno precedente viene annullata. Quando si esegue un annullamento, il saldo finale e il saldo iniziale vengono completamente eliminati, come se la chiusura di fine anno non fosse mai stata eseguita. I giustificativi vengono eliminati. La chiusura di fine anno non viene ripetuta automaticamente. È necessario rieseguire il processo, questa volta impostando **Annulla chiusura precedente** su **No**. 

> [!NOTE]
> La voce del saldo finale viene facoltativamente creata nell'anno in corso di chiusura. Ciò si verifica solo se il parametro di Contabilità generale **Crea transazioni di chiusura durante il trasferimento** è impostato su **Sì**. La voce del saldo iniziale viene sempre creata, perché è il saldo iniziale per l'anno successivo.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Contabilità generale: qual è la differenza tra i parametri di contabilità generale Annulla ed Elimina per la chiusura di fine anno?
Potrebbe esserci confusione sulla differenza tra il parametro **Annulla chiusura precedente** che si trova nella finestra di dialogo **Chiusura di fine anno** e il parametro **Elimina transazioni di fine anno durante il trasferimento** nella contabilità generale (**Contabilità generale > Periodo chiuso > Chiusura di fine anno > Esegui chiusura fiscale**).  

[![Differenza tra i parametri di contabilità generale Annulla ed Elimina per la chiusura di fine anno](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Selezionare **Annulla chiusura precedente** nel menu a discesa quando si esegue il processo di chiusura di fine anno per eliminare tutte le voci del saldo finale e del saldo iniziale, come se la chiusura di fine anno non fosse mai stata eseguita. I giustificativi verranno eliminati. La chiusura di fine anno non viene ripetuta automaticamente. Per eseguire la chiusura di fine anno, è necessario avviare nuovamente questo processo, questa volta impostando **Annulla chiusura precedente** su **No** (**Contabilità generale > Impostazioni contabilità generale > Parametri di contabilità generale**). 

[![Impostazione dei parametri di contabilità generale](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

Il parametro **Elimina transazioni di fine anno durante il trasferimento** nella contabilità generale viene utilizzato solo quando si esegue (non si annulla) la chiusura di fine anno (**Annulla chiusura precedente** è impostato su **No**). Se quel parametro è impostato su **Sì**, tutte le voci del saldo finale e del saldo iniziale verranno eliminate e la chiusura di fine anno verrà eseguita nuovamente. Questo processo viene utilizzato quando l'organizzazione desidera che tutte le transazioni, comprese le rettifiche dall'ultima chiusura di fine anno, vengano registrate in una singola voce contabile per le voci del saldo finale e del saldo iniziale. 

Se questa opzione è impostata su **No**, tutte le voci del saldo finale e del saldo iniziale rimangono inalterate. Non vengono eliminate. Viene invece creata una nuova voce di saldo finale e di saldo iniziale solo per il delta o per le nuove transazioni registrate dall'ultima chiusura di fine anno per quell'anno fiscale.  

> [!NOTE]
> La voce del saldo finale viene creata nell'anno in corso di chiusura. Ciò si verifica solo se il parametro **Crea transazioni di chiusura durante il trasferimento** nella contabilità generale è impostato su **Sì**. La voce del saldo iniziale viene sempre creata, perché è il saldo iniziale per l'anno successivo. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Contabilità generale: cosa è possibile modificare per migliorare le prestazioni dell'elaborazione di fine anno? 
È possibile apportare una serie di modifiche per migliorare le prestazioni della chiusura di fine anno. Considerare le modifiche suggerite per valutare se sono appropriate per la propria organizzazione.  

### <a name="dimension-sets"></a>Set di dimensioni
Quando si esegue la chiusura di fine anno, il saldo di ogni set di dimensioni viene ricostruito, con un impatto diretto sulle prestazioni. Alcune organizzazioni creano set di dimensioni inutilmente perché sono già stati utilizzati o potrebbero essere utilizzati in futuro.  Questi set di dimensioni non necessari vengono comunque ricostruiti durante la chiusura di fine anno, il che aggiunge tempo al processo. Valutare con attenzione i set di dimensioni ed eliminare quelli non necessari.

I set di dimensioni non necessari influiscono anche sul processo batch **BudgetDimensionFocusInitializeBalance** (**Contabilità generale > Piano dei conti > Dimensioni > Set di dimensioni finanziarie**).

[![Set di dimensioni finanziarie](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configurazione del modello di chiusura di fine anno
Il modello di chiusura di fine anno consente alle organizzazioni di selezionare il livello di dimensione finanziaria da mantenere quando si trasferiscono i saldi di profitti e perdite agli utili non distribuiti. Le impostazioni consentono a un'organizzazione di mantenere le dimensioni finanziarie dettagliate (**Chiudi tutto**) quando si spostano i saldi negli utili non distribuiti o si sceglie di riepilogare gli importi in un singolo valore di dimensione (**Chiudi singolo**). Queste impostazioni possono essere definite per ogni dimensione finanziaria. Per ulteriori informazioni su queste impostazioni, vedere l'argomento [Chiusura di fine anno](year-end-close.md).

Si consiglia di valutare i requisiti dell'organizzazione e, se possibile, chiudere il maggior numero di dimensioni possibile utilizzando l'opzione di fine anno **Chiudi singolo** per migliorare le prestazioni. Chiudendo un valore di dimensione singola (che può anche essere un valore vuoto), il sistema calcola meno dettagli quando determina i saldi per le voci del conto utili non distribuiti.

### <a name="10013-update-or-later"></a>Aggiornamento 10.0.13 o successivo
Se è stato eseguito l'aggiornamento alla versione 10.0.13 o successiva dopo l'ultima chiusura di fine anno dell'organizzazione, il processo di chiusura di fine anno potrebbe richiedere più tempo a causa dell'[implementazione della funzionalità HashV2](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/verify-hash-function-changes-after-update-to-dynamics-365-finance-2020-release-wave-2). (Il termine *hash* si riferisce a un campo calcolato da altri campi stringa. L'API per calcolare il valore GUID dell'hash è stata aggiornata per migliorare la sicurezza. Per accelerare il processo di chiusura di fine anno, si consiglia di ricostruire i saldi dei set di dimensioni prima di eseguire la chiusura di fine anno. Se i saldi del set di dimensioni sono stati già ricostruiti dopo aver eseguito l'aggiornamento 10.0.13, non è necessario eseguire nuovamente il processo di ricostruzione.
 
## <a name="general-ledger--what-does-the-period-close--year-end-close-do"></a>Contabilità generale: cosa accade quando si seleziona Periodo chiuso - Chiusura di fine anno?
 
[![Periodo chiuso, chiusura di fine anno](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets-new-feature"></a>Miglioramenti delle prestazioni per la ricostruzione dei set di dimensioni finanziarie (nuova funzionalità)
Una nuova funzionalità aggiunta nella versione 10.0.16 migliora le prestazioni dei processi di chiusura e consolidamento di fine anno. La funzione si chiama Miglioramenti delle prestazioni per la ricostruzione dei set di dimensioni finanziarie. Questa funzione cambia il modo in cui vengono ricostruiti i set di dimensioni in modo che vengano ricostruiti solo per un periodo di tempo specifico. Nelle versioni precedenti, i set di dimensioni venivano ricostruiti per tutte le date. Ad esempio, se si sta chiudendo l'anno 2020, il sistema ricostruisce solo i saldi per le transazioni entro l'anno fiscale 2020. Se si esegue il consolidamento per un intervallo di date compreso tra il 1° e il 30 novembre 2020, il sistema ricostruisce solo i saldi per quell'intervallo di date.

Poiché questa funzione è considerata una modifica sostanziale, è necessario abilitarla utilizzando l'area di lavoro **Gestione funzionalità**.
 
[![Chiusura di fine anno](./media/faq-2020-yr-end-06.png)](./media/faq-2020-yr-end-06.png)

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2020"></a>Contabilità fornitori: quali modifiche sono state apportate per supportare la creazione di report di fine anno 1099 per il 2020?

Sono state aggiunte due nuove funzionalità normative per le modifiche di fine anno 1099 nel 2020. La prima funzionalità, **Applica le modifiche ai moduli 1099-NEC e 1099-MISC per il 2020**, è stata rilasciata a metà anno come funzionalità obbligatoria. Il suo scopo è garantire che i dati transazionali 1099 per l'anno 2020 possano essere tracciati per il nuovo modulo 1099-NEC. Questa funzionalità ha aggiunto i campi 1099 necessari per supportare il nuovo 1099-NEC e ha aggiornato i campi 1099-MISC. Sono stati aggiornati anche i dati del record fornitore per le informazioni sul riquadro 1099. 

La seconda funzionalità normativa, **Dichiarazioni 1099 aggiornate per la normativa fiscale 2020**, contiene le seguenti modifiche.

- 1099-OID - L'IRS ha convertito il modulo per l'utilizzo continuativo.
   - La terza e la quarta cifra dell'anno di riferimento devono essere compilate al momento della stampa. Usa la terza e la quarta cifra del campo **Anno di riferimento** da **Opzioni di stampa imposta 1099**. 

- 1099-NEC - Un nuovo modulo per il 2020. Viene registrata la retribuzione dei non dipendenti. 

-   1099-MISC - A causa della creazione del modulo 1099-NEC, l'IRS ha rivisto il modulo 1099-MISC e ha riorganizzato i numeri di riquadro per la dichiarazione di determinati redditi.
Di seguito sono elencate le modifiche alla dichiarazione del reddito e ai numeri di riquadro del modulo.
   - Il contribuente ha effettuato vendite dirette per almeno $5.000 (casella di controllo) nel riquadro 7.
   - I proventi dell'assicurazione sui raccolti sono riportati nel riquadro 9.
   - I proventi lordi di un avvocato sono riportati nel riquadro 10.
   - I differimenti della sezione 409A sono riportati nel riquadro 12.
   - Il reddito da indennità differita non qualificata è riportato nel riquadro 14.
   - I riquadri 15, 16 e 17 riportano rispettivamente la trattenuta delle tasse statali, il numero di identificazione statale e l'ammontare del reddito guadagnato nello stato.

- Nessuna modifica a 1099-DIV o 1099-INT nel 2020.

- Presentazione elettronica: il formato è cambiato per adattarsi alle nuove modifiche al modulo NEC e al riquadro MISC sopra descritte. Per informazioni specifiche sui requisiti di presentazione elettronica, vedere [Pubblicazione IRS 1220](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Contabilità fornitori: 1099 - Come si modifica il riquadro 1099 e i valori per un fornitore che non ha tracciato le informazioni 1099 durante l'anno?
Usare la funzionalità Aggiorna modulo 1099 (**Contabilità fornitori > Fornitori > Tutti i fornitori > Seleziona un fornitore > scheda Fornitore nella barra multifunzione > Aggiorna modulo 1099**) per esaminare le transazioni di fatture precedentemente pagate e riassegnare i dati 1099 in modo appropriato in base alle impostazioni nella scheda **Imposta 1099** della pagina **Fornitore**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>È possibile eseguire l'aggiornamento 1099 per tutti i miei fornitori contemporaneamente?
N. La routine Aggiorna modulo 1099 viene eseguita su un singolo fornitore alla volta. Se questo requisito è necessario per l'organizzazione, votare per l'idea intitolata [Processo batch per l'aggiornamento dei dati 1099 del fornitore](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-vs-update-all-in-the-update-1099-utility"></a>Contabilità fornitori: 1099 - "Ricalcola importi 1099 esistenti" e "Aggiorna tutto" nell'utilità Aggiorna modulo 1099.
La casella di controllo **Ricalcola importi 1099 esistenti** reimposta l'importo 1099 sui valori totali pagati, se utilizzato insieme alla casella di controllo **Aggiorna tutto**. 

[![Transazioni fiscali 1099: prima di eseguire la routine di aggiornamento](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

La casella di controllo **Ricalcola importi 1099 esistenti** viene considerata solo quando sono presenti valori 1099 parziali sulla fattura o se è stata modificata nel modulo Imposta 1099. Ad esempio, si supponga di avere una fattura con valore $1000,00, ma l'utente digita manualmente un importo 1099 sulla fattura di $500,00.

[![Transazioni IVA 1099: contrassegnare Aggiorna tutto e Ricalcola importi 1099 esistenti](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Quando viene pagato, $500,00 sarà l'importo 1099 corrisposto. Se si esegue la routine di ricalcolo, il sistema modifica l'importo 1099 in $1000,00, che è il totale pagato.

[![Transazioni fiscali 1099: dopo aver eseguito la routine 1099](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Contabilità fornitori: 1099 - Creare manualmente transazioni 1099
Un'organizzazione potrebbe dover creare manualmente le transazioni 1099 non associate a una fattura. È possibile aggiungere transazioni 1099 manuali andando in **Contabilità fornitori > Attività periodiche > Imposta 1099 > Liquidazione fornitore per i moduli 1099**. Selezionare il pulsante **Transazioni 1099 manuali**. 

Le transazioni 1099 create manualmente non vengono aggiornate con il processo **Aggiorna tutto** o il processo **Ricalcola importi 1099 esistenti** nell'utilità **Aggiorna modulo 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Contabilità fornitori: 1099 - Dynamics 365 Finance supporta il modulo 1096? 

Dynamics 365 Finance non stampa il modulo 1096 Riepilogo annuale e trasmissione delle dichiarazioni negli Stati Uniti.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Contabilità fornitori: 1099 - Esistono nuove funzionalità che supportano la creazione di report 1099 per il settore pubblico? 
È stata aggiunta una nuova funzionalità del settore pubblico, **Aggiorna informazioni 1099 per conto principale**, che è possibile abilitare nell'area di lavoro **Gestione funzionalità**. Questa funzionalità consente di associare i valori dei moduli 1099 per un fornitore dal conto principale nella distribuzione contabile, piuttosto che dal conto predefinito nel record fornitore.

Per ulteriori informazioni, vedere [Configurare i fornitori per la creazione di report 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]