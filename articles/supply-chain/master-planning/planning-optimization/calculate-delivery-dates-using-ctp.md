---
title: Calcolare le date di consegna di ordini cliente utilizzando CTP
description: La funzionalità Capable-to-promise (CTP) ti consente di fornire ai clienti date realistiche alle quali puoi promettere merci specifiche. Questo articolo descrive come impostare e utilizzare CTP per ogni motore di pianificazione (Ottimizzazione pianificazione e il motore di pianificazione generale deprecato).
author: t-benebo
ms.date: 07/20/2022
ms.topic: article
ms.search.form: SalesAvailableDlvDates, SalesTable, CustParameters, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-20
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 4a3b8ba89d9fb224026cf32cad89d7f28321ee79
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741205"
---
# <a name="calculate-sales-order-delivery-dates-using-ctp"></a>Calcolare le date di consegna di ordini cliente utilizzando CTP

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->
<!-- KFN: Split into two topics, one for PO and one for classic. -->

La funzionalità Capable-to-promise (CTP) ti consente di fornire ai clienti date realistiche alle quali puoi promettere merci specifiche. Per ogni riga di vendita, puoi fornire una data che tenga conto delle scorte disponibili, della capacità di produzione e dei tempi di trasporto esistenti.

CTP estende la funzionalità [available-to-promise](../../sales-marketing/delivery-dates-available-promise-calculations.md) (ATP) prendendo in considerazione le informazioni sulla capacità. Mentre ATP prende in considerazione solo la disponibilità dei materiali e presuppone risorse di capacità infinite, CTP prende in considerazione la disponibilità di materiali e capacità. Pertanto, fornisce un quadro più realistico della possibilità di soddisfare la domanda entro un determinato intervallo di tempo.

CTP funziona in modo leggermente differente, a seconda del motore di pianificazione generale in uso (Ottimizzazione pianificazione o il motore di pianificazione generale deprecato). In questo articolo viene descritto come configurare CTP per ogni motore. CTP per Ottimizzazione pianificazione supporta attualmente solo un sottoinsieme degli scenari CTP supportati dal motore di pianificazione generale deprecato.

## <a name="turn-on-ctp-for-planning-optimization"></a>Attivare CTP per Ottimizzazione pianificazione

CTP per il motore di pianificazione generale deprecato è sempre disponibile. Tuttavia, se vuoi utilizzare la funzionalità CTP per Ottimizzazione pianificazione, devi attivarla per il tuo sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Pianificazione generale*
- **Nome funzionalità:** *(Anteprima) CTP per Ottimizzazione pianificazione*

## <a name="how-ctp-compares-to-atp"></a>Raffronto tra CTP e ATP

CTP e ATP sono simili, ma spesso CTP può fornire un risultato più accurato, come mostra l'esempio seguente.

L'articolo A è un articolo composto dagli articoli B e C e la quantità disponibile dell'articolo A è 0 (zero). Se esegui un controllo ATP che prende in considerazione solo i materiali, anche la quantità di ATP sarà 0 (zero). Tuttavia, se esegui un controllo CTP, il sistema verificherà la disponibilità degli articoli B e C, verificherà le risorse necessarie per trasformarli nell'articolo A e calcolerà quanti articoli A possono essere prodotti. Inoltre, il calcolo CTP può verificare le risorse e i materiali necessari per creare più articoli B e C e per utilizzare tali articoli per creare più articoli A.

Un calcolo CTP che prende in considerazione sia i materiali che le risorse potrebbe mostrare una quantità maggiore rispetto a un calcolo che controlla solo i materiali, in particolare quando l'articolo che viene controllato è un articolo assemblato su ordinazione. In altre parole, la funzionalità CTP si basa sulla funzione di esplosione e può essere eseguita per una riga di ordine cliente selezionata per calcolare la data di consegna prevista.

## <a name="how-ctp-differs-depending-on-the-master-planning-engine-that-you-use"></a>Differenze in CTP a seconda del motore di pianificazione generale utilizzato

La tabella seguente riassume le differenze tra CTP per Ottimizzazione pianificazione e CTP per il motore di pianificazione generale deprecato.

| Elemento | Ottimizzazione pianificazione | Motore di pianificazione generale deprecato |
|---|---|---|
| L'impostazione **Controllo della data di consegna** per ordini, righe ordine e prodotti | *CTP per Ottimizzazione pianificazione* | *CTP* |
| Ora di calcolo | Il calcolo viene attivato eseguendo un piano dinamico come attività pianificata. | Il calcolo viene attivato immediatamente ogni volta che immetti o aggiorni una riga di ordine cliente. |
| Valore del campo **CTP per Ottimizzazione pianificazione** | <p>Un valore *Non pronto* viene visualizzato per gli ordini e le righe ordine in cui il piano dinamico non è stato eseguito dalla creazione o dall'ultimo aggiornamento di ordini e righe.</p><p>Un valore *Pronto* viene visualizzato per gli ordini e le righe in cui è stato utilizzato CTP per calcolare le date di consegna confermate eseguendo il piano dinamico.</p> | Un valore *Pronto* è sempre visualizzato. |

## <a name="set-default-delivery-date-control-methods"></a><a name="default-methods"></a>Impostare i metodi di controllo predefiniti della data di consegna

Il sistema può utilizzare vari metodi disponibili per calcolare le stime della data di consegna per ogni ordine e riga ordine. Devi impostare il metodo di controllo della data di consegna che vuoi utilizzare più spesso come metodo predefinito globale. Puoi inoltre impostare singole sostituzioni per ogni prodotto. Successivamente, sarai in grado di ignorare i metodi predefiniti per ogni ordine e/o riga ordine come necessario.

### <a name="set-the-global-default-delivery-date-control"></a><a name="global-default"></a>Impostare il controllo globale della data di consegna predefinita

Il metodo di controllo della data di consegna predefinita verrà applicato a tutte le nuove righe ordine in cui non si applica una sostituzione. Per selezionarne un metodo, procedi come segue.

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
1. Nella scheda **Spedizioni**, nella Scheda dettaglio **Controllo consegna**, nel campo **Controllo data di consegna**, seleziona il metodo che vuoi utilizzare come metodo predefinito per la tua azienda:

    - *Nessuno*: le date di consegna non vengono calcolate.
    - *Lead time di vendita*: è il tempo che trascorre tra la creazione di un ordine cliente e la spedizione degli articoli. Il calcolo della data di consegna è basato su un numero predefinito di giorni e non prende in considerazione la disponibilità delle scorte, la domanda nota e l'offerta pianificata.
    - *ATP*: è la quantità di un articolo disponibile e che può essere promessa a un cliente in una data specifica. Il calcolo della quantità ATP include magazzino non impegnato, lead time, entrate e uscite pianificate.
    - *ATP + margine su uscita magazzino*: la data di spedizione è uguale alla data ATP più il margine su uscita da magazzino per l'articolo. Il margine su uscita da magazzino consiste nel tempo richiesto per preparare gli articoli per la spedizione.
    - *CTP*: utilizza il calcolo CTP fornito dal motore di pianificazione generale deprecato. Se utilizzi Ottimizzazione pianificazione, il metodo di controllo della data di consegna *CTP* non è consentito e se è selezionato, causerà un errore durante l'esecuzione del calcolo.
    - *CTP per Ottimizzazione pianificazione*: utilizza il calcolo CTP fornito da Ottimizzazione pianificazione. Questa opzione non ha effetto se stai utilizzando il motore di pianificazione generale deprecato.

### <a name="set-delivery-date-control-overrides-for-individual-products"></a>Impostare le sostituzioni del controllo della data di consegna per singoli prodotti

Puoi assegnare sostituzioni per prodotti specifici in cui vuoi utilizzare un metodo di controllo della data di consegna diverso da quello impostato come metodo predefinito globale.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Seleziona il prodotto che vuoi impostare.
1. Nella scheda **Gestione articoli** del riquadro azioni, nel gruppo **Impostazioni ordine**, seleziona **Impostazioni ordine predefinite**.
1. Nella pagina **Impostazioni ordine predefinite**, nella Scheda dettaglio **Ordine cliente**, imposta l'opzione **Ignora controllo consegna** su *Sì*.
1. Nel campo **Controllo data di consegna**, seleziona il metodo da utilizzare per il prodotto selezionato. Sono disponibili le stesse opzioni descritte nella sezione [Impostare il controllo globale della data di consegna predefinita](#global-default).

## <a name="schedule-ctp-for-planning-optimization-calculations"></a><a name="batch-job"></a>Pianificare CTP per i calcoli di Ottimizzazione pianificazione

Quando usi CTP per Ottimizzazione pianificazione, devi eseguire un piano dinamico per far sì che il sistema esegua i calcoli CTP e quindi impostare le date di spedizione e ricevimento confermate per tutti gli ordini pertinenti. Il piano deve includere tutti gli articoli per i quali sono richieste date di spedizione e ricevimento confermate (quando utilizzi CTP per il motore di pianificazione generale deprecato, i calcoli CTP vengono eseguiti immediatamente in locale, pertanto non devi eseguire un piano dinamico per visualizzare i risultati CTP).

Per assicurarti che le date siano disponibili in tempo utile per tutti gli utenti, ti consigliamo di configurare processi batch per eseguire i piani pertinenti su base ricorrente. Ad esempio, un processo batch configurato per eseguire un piano dinamico ogni 30 minuti imposterà le date di spedizione e ricevimento confermate ogni 30 minuti. Pertanto, gli utenti che inseriscono e importano ordini dovranno attendere al massimo 30 minuti per ottenere le date di spedizione e ricevimento confermate.

Per configurare un processo batch allo scopo di eseguire un piano dinamico regolarmente, procedi come segue.

1. Vai a **Pianificazione generale \> Pianificazione generale \> Esegui \> Pianificazione generale**.
1. Nella finestra di dialogo **Pianificazione generale**, nella Scheda dettaglio **Parametri**, imposta il campo **Piano generale** sul piano dinamico che vuoi eseguire.
1. Nella Scheda dettaglio **Esecuzione in background**, imposta l'opzione **Elaborazione batch** su *Sì*.
1. Seleziona **Ricorrenza** e configura la pianificazione come necessario.
1. Seleziona **OK** per salvare la pianificazione.
1. Seleziona **OK** per creare il processo batch e chiudere la finestra di dialogo.

## <a name="use-ctp-for-the-deprecated-master-planning-engine"></a>Utilizza CTP per il motore di pianificazione generale deprecato

### <a name="create-a-new-order-by-using-ctp-for-the-deprecated-master-planning-engine"></a>Creare un nuovo ordine utilizzando CTP per il motore di pianificazione generale deprecato

Ogni volta che aggiungi un nuovo ordine cliente o riga ordine, il sistema gli assegna un metodo di controllo della data di consegna predefinito. L'intestazione dell'ordine inizia sempre con il metodo predefinito globale. Se viene assegnata una sostituzione a un articolo ordinato, la nuova riga ordine utilizzerà tale sostituzione. In caso contrario, anche la nuova riga ordine utilizzerà il metodo predefinito globale. Pertanto, devi impostare i tuoi metodi predefiniti di modo che corrispondano al metodo di controllo della data di consegna che vuoi utilizzare più spesso. Dopo aver creato un ordine, puoi ignorare il metodo predefinito a livello di intestazione dell'ordine e/o di riga dell'ordine come necessario. Per ulteriori informazioni, vedi [Impostare i metodi di controllo predefiniti della data di consegna](#default-methods) e [Modificare gli ordini cliente esistenti per utilizzare CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-you-use-ctp-for-the-deprecated-master-planning-engine"></a>Visualizzare le date di consegna confermate quando si utilizza CTP per il motore di pianificazione generale deprecato

Se utilizzi il motore di pianificazione generale deprecato, i calcoli CTP vengono applicati agli ordini e/o alle righe ordine in cui il campo **Controllo data di consegna** è impostato su *CTP*.

Per le righe di vendita che utilizzano CTP per il motore di pianificazione generale deprecato, il sistema imposta automaticamente i campi **Data di spedizione confermata** e **Data di ricevimento confermata** ogni volta che salvi una riga di vendita. Se in seguito apporti una modifica pertinente a una riga di vendita (ad esempio, ne modifichi la quantità o il sito), le date verranno immediatamente ricalcolate.

- Per visualizzare le date di consegna confermate per una riga di ordine cliente, apri l'ordine cliente e seleziona la riga di vendita. Quindi, nella Scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, esamina i valori **Data di spedizione confermata** e **Data di ricevimento confermata**.
- Per visualizzare le date di consegna confermate per un intero ordine, apri l'ordine cliente e seleziona la visualizzazione **Intestazione**. Quindi, nella Scheda dettaglio **Consegna**, esamina i valori **Data di spedizione confermata** e **Data di ricevimento confermata**.

## <a name="use-ctp-for-planning-optimization"></a>Usare CTP per Ottimizzazione pianificazione

### <a name="create-a-new-order-by-using-ctp-for-planning-optimization"></a>Creare un nuovo ordine utilizzando CTP per Ottimizzazione pianificazione

Ogni volta che aggiungi un nuovo ordine cliente o riga ordine, il sistema gli assegna un metodo di controllo della data di consegna predefinito. L'intestazione dell'ordine inizia sempre con il metodo predefinito globale. Se viene assegnata una sostituzione a un articolo ordinato, la nuova riga ordine utilizzerà tale sostituzione. In caso contrario, anche la nuova riga ordine utilizzerà il metodo predefinito globale. Pertanto, devi impostare i tuoi metodi predefiniti di modo che corrispondano al metodo di controllo della data di consegna che vuoi utilizzare più spesso. Dopo aver creato un ordine, puoi ignorare il metodo predefinito a livello di intestazione dell'ordine e/o di riga dell'ordine come necessario. Per ulteriori informazioni, vedi [Impostare i metodi di controllo predefiniti della data di consegna](#default-methods) e [Modificare gli ordini cliente esistenti per utilizzare CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-using-ctp-for-planning-optimization"></a>Visualizzare le date di consegna confermate quando si utilizza CTP per Ottimizzazione pianificazione

Se utilizzi Ottimizzazione pianificazione, i calcoli CTP vengono applicati agli ordini e/o alle righe ordine in cui il campo **Controllo data di consegna** è impostato su *CTP per Ottimizzazione pianificazione*.

Per le righe di vendita che utilizzano CTP per Ottimizzazione pianificazione, i campi **Data di spedizione confermata** e **Data di ricevimento confermata** rimarranno vuoti finché non esegui il piano dinamico appropriato (in genere utilizzando un processo batch periodico). Dopo l'esecuzione, i campi vengono impostati automaticamente. Per ulteriori informazioni, vedi [Pianificare CTP per i calcoli di Ottimizzazione pianificazione](#batch-job).

Il campo **Stato CTP per Ottimizzazione pianificazione** indica se le date confermate sono state calcolate per ogni riga che utilizza CTP per Ottimizzazione pianificazione. Il campo mostra un valore *Non pronto* per righe e ordini in cui le date di consegna confermate non sono state ancora calcolate o non sono più valide a causa di altre modifiche. Mostra un valore *Pronto* per righe e ordini che sono stati calcolati. Puoi visualizzare lo stato di ogni riga e dell'intero ordine.

- Per visualizzare lo stato di una riga di ordine cliente, apri l'ordine cliente e seleziona la riga di vendita. Quindi, nella Scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, esamina il valore **Stato CTP per Ottimizzazione pianificazione**. I campi **Data di spedizione confermata** e **Data di ricevimento confermata** per la riga sono visualizzati anche in questa scheda dopo che sono stati calcolati.
- Per visualizzare lo stato per un intero ordine, apri l'ordine cliente e seleziona la visualizzazione **Intestazione**. Quindi, nella Scheda dettaglio **Consegna**, esamina il valore di **Stato CTP per Ottimizzazione pianificazione**. I campi **Data di spedizione confermata** e **Data di ricevimento confermata** per l'ordine sono visualizzati anche in questa scheda dopo che sono stati calcolati.

<!-- KFM: The following text may be untrue and needs to be reviewed with the PM for next revision:

The sales orders that are *Ready* or *Not ready* are shown in the **All sales orders** list page. You can check the sales order that are *Ready* or *Not ready* from the sales order list page by filtering on this new status field.

-->

> [!NOTE]
> - Se aggiorni una riga di ordine cliente dopo che CTP per Ottimizzazione pianificazione ne ha calcolato le date confermate, il sistema cancellerà tali date fino alla successiva esecuzione del piano dinamico appropriato.
> - Se modifichi un'impostazione correlata che potrebbe influire sulle date confermate esistenti (ad esempio, modificando lead time, prenotazioni o contrassegni), devi cancellare le date confermate per gli ordini esistenti pertinenti. Questa azione farà sì che lo stato di ogni riga pertinente venga modificato in *Non pronto*. Questa modifica, a sua volta, farà sì che il sistema ricalcoli le date confermate alla successiva esecuzione del piano dinamico.

## <a name="change-existing-sales-orders-so-that-they-use-ctp"></a><a name="change-orders"></a>Modificare gli ordini cliente esistenti in modo che utilizzino CTP

Puoi modificare il valore **Controllo data di consegna** per qualsiasi ordine aperto in qualsiasi momento. Puoi modificare il valore a livello di intestazione e/o per ciascuna riga come necessario.

### <a name="change-to-ctp-at-the-order-header-level"></a>Passare a CTP a livello di intestazione dell'ordine

<!-- KFM: Would be nice to mention how changing this setting on the header affects the individual lines. -->

Per modificare un ordine in modo che utilizzi CTP a livello di intestazione dell'ordine, procedi come segue.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente**.
1. Apri l'ordine cliente che vuoi impostare o creane uno.
1. Seleziona **Intestazione** per visualizzare le informazioni sull'intestazione nella pagina **Dettagli ordini cliente**.
1. Nella Scheda dettaglio **Consegna**, imposta il campo **Controllo data di consegna** su uno dei seguenti valori, a seconda del motore di pianificazione in uso:

    - *CTP*: utilizza il calcolo CTP fornito dal motore di pianificazione generale deprecato. Se usi Ottimizzazione pianificazione, il metodo di controllo della data di consegna *CTP* non è consentito. Pertanto, se selezioni questo valore, si verificherà un errore durante l'esecuzione del calcolo.
    - *CTP per Ottimizzazione pianificazione*: utilizza il calcolo CTP fornito da Ottimizzazione pianificazione. Questa impostazione non ha effetto se stai utilizzando il motore di pianificazione generale deprecato.

<!-- KFM: Additional dialogs are shown here. Review these with the PM and expand this procedure at next revision. -->
1. Seleziona **OK** per applicare le modifiche.

### <a name="change-to-ctp-at-the-order-line-level"></a>Passare a CTP a livello di riga ordine

Se hai creato una riga ordine utilizzando un differente metodo di controllo della data di consegna, puoi passare a CTP in qualsiasi momento. Le modifiche che apporti a livello di riga non hanno effetto su altre righe. Tuttavia, potrebbero spostare le date di consegna globali dell'ordine in avanti o indietro, a seconda di come cambia ogni calcolo di riga aggiornato. <!-- KFM: Confirm this intro at next revision -->

Per modificare un ordine di modo che utilizzi CTP per il motore di pianificazione generale deprecato a livello di riga, procedi come segue.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente**.
1. Apri l'ordine cliente che vuoi impostare o creane uno.
1. Nella pagina **Dettagli ordine cliente**, nella Scheda dettaglio **Riga ordine cliente**, seleziona la riga di ordine cliente che intendi impostare.
1. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, imposta il campo **Controllo data di consegna** su uno dei seguenti valori, a seconda del motore di pianificazione in uso:

    - *CTP*: utilizza il calcolo CTP fornito dal motore di pianificazione generale deprecato. Se usi Ottimizzazione pianificazione, il metodo di controllo della data di consegna *CTP* non è consentito. Pertanto, se selezioni questo valore, si verificherà un errore durante l'esecuzione del calcolo.
    - *CTP per Ottimizzazione pianificazione*: utilizza il calcolo CTP fornito da Ottimizzazione pianificazione. Questa impostazione non ha effetto se stai utilizzando il motore di pianificazione generale deprecato.

    Viene visualizzata la finestra di dialogo **Date di spedizione e di ricevimento disponibili** che mostra le date di spedizione e ricevimento disponibili. Questa finestra di dialogo funziona allo stesso modo per le righe dell'ordine e per l'intestazione dell'ordine, come descritto nella sezione precedente.

1. Nel riquadro azioni selezionare **Salva**.
