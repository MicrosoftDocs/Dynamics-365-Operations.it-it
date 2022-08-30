---
title: Stabilizzare ordini pianificati
description: Questo articolo spiega come stabilizzare gli ordini pianificati. Quando gli ordini pianificati vengono stabilizzati, diventano ordini fornitore, di trasferimento o di produzione effettivi.
author: t-benebo
ms.date: 08/09/2022
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7c8d5b7992c7955b9c5b1c7e773fdd467ccba6f9
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335347"
---
# <a name="firm-planned-orders"></a>Stabilizza ordini pianificati

[!include [banner](../../includes/banner.md)]

Gli ordini pianificati devono essere *stabilizzati* (ovvero, rilasciati) come parte del processo di pianificazione generale. Quando gli ordini pianificati vengono stabilizzati, diventano ordini fornitore, di trasferimento o di produzione effettivi. Questi ordini sono inoltre noti come *ordini rilasciati* o *aperti*.

Esistono tre metodi per stabilizzare gli ordini pianificati:

- **Stabilizzazione manuale** - Seleziona ordini pianificati specifici in un elenco, quindi avvia manualmente il processo.
- **Stabilizzazione automatica** - Definire un intervallo temporale di stabilizzazione predefinito per gruppi di copertura, singoli articoli e combinazioni di articoli e piani generali. Quindi, durante le esecuzioni della pianificazione generale, gli ordini pianificati verranno automaticamente stabilizzati se la data dell'ordine rientra nell'intervallo di tempo specificato per la stabilizzazione.
- **Stabilizzazione basata su query** - Definire una query per selezionare gli ordini pianificati in base alle loro proprietà. È possibile impostare un processo batch per eseguire la query e stabilizzare gli ordini corrispondenti in base a una pianificazione regolare.

Questo articolo descrive ogni metodo in dettaglio.

## <a name="enable-the-features-that-are-described-in-this-article"></a><a name="enable-features"></a>Abilita le funzionalità descritte in questo articolo

La maggior parte delle funzionalità degli ordini pianificati sono disponibili in tutte le installazioni standard di Microsoft Dynamics 365 Supply Chain Management che utilizzano l'ottimizzazione della pianificazione. Tuttavia, alcune delle funzionalità descritte in questo articolo devono essere attivate in Gestione funzionalità prima di poterle utilizzare.

### <a name="turn-parallelized-firming-of-planned-orders-on-or-off"></a>Attivare o disattivare la stabilizzazione parallela degli ordini pianificati

La stabilizzazione parallela aiuta ad accelerare il processo di stabilizzazione parallelizzandolo su più thread. Questo approccio può essere utile quando molti ordini pianificati vengono stabilizzati. Per utilizzare questa funzionalità, la funzionalità *Stabilizzazione parallela degli ordini pianificati* deve essere attivata per il sistema. 

A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, è possibile attivare o disattivare questa funzionalità cercando la funzionalità *Stabilizzazione parallela degli ordini pianificati* nell'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="turn-planned-order-firming-with-filtering-on-or-off"></a>Attivare o disattivare la funzionalità Stabilizzazione di ordini pianificati con filtri

La stabilizzazione di ordini pianificati con filtri consente di definire criteri logici per la selezione degli ordini pianificati da stabilizzare. È inoltre possibile visualizzare in anteprima quali ordini pianificati sono stati selezionati, eseguire il processo in background e / o pianificarlo come processo batch.

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.25 di Supply Chain Management, la funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Stabilizzazione di ordini pianificati con filtri* nell'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="turn-auto-firming-for-planning-optimization-on-or-off"></a>Attivare o disattivare la funzionalità Stabilizzazione automatica per Ottimizzazione pianificazione

La stabilizzazione automatica consente di stabilizzare gli ordini pianificati nel processo di pianificazione generale durante il intervallo temporale stabilito. La stabilizzazione automatica è sempre supportata per il motore di pianificazione integrato in Supply Chain Management. Tuttavia, per utilizzarlo anche con l'ottimizzazione della pianificazione, è necessario attivare la funzionalità.

A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.29 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, è possibile attivare o disattivare questa funzionalità cercando la funzionalità *Stabilizzazione automatica per Ottimizzazione pianificazione* nell'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="manually-firm-planned-orders"></a>Stabilizzare manualmente ordini pianificati

Per stabilizzare manualmente gli ordini pianificati, individuare e selezionare gli ordini pianificati che si desidera stabilizzare, quindi avviare manualmente il processo di stabilizzazione.

1. [Apri una pagina elenco di ordini pianificati](approved-planned-order.md#view-planned-orders).
1. Usa il campo **Filtra**, il campo **Piano** e le intestazioni di colonna per filtrare e ordinare l'elenco in modo da poter trovare gli ordini pianificati che stai cercando.
1. Selezionare la casella di controllo per ogni ordine pianificato che si desidera stabilizzare. Se desideri stabilizzare tutti gli ordini pianificati attualmente elencati nella pagina (in base ai filtri applicati), ignora questo passaggio.
1. Nel riquadro azioni seleziona uno degli pulsanti riportati di seguito:

    - **Stabilizza** - Stabilizza solo gli ordini pianificati selezionati.
    - **Stabilizza tutto** - Stabilizza tutti gli ordini pianificati attualmente elencati nella pagina (in base ai filtri applicati), indipendentemente dalle caselle di controllo selezionate. Questa opzione può essere utile se stai stabilizzando un numero elevato di ordini pianificati.

1. Nella finestra di dialogo **Stabilizzazione**, nella scheda dettaglio **Parametri**, impostare i seguenti campi: (Molti di questi campi prendono i valori predefiniti dalla scheda **Aggiornamento standard** nella pagina **Parametri di pianificazione generale**.)

    - **Aggiorna contrassegno** – Selezionare i criteri di contrassegno scorte da utilizzare durante la stabilizzazione degli ordini pianificati.
    - **Interrompi stabilizzazione in caso di errore** - Imposta questa opzione su *Sì* per interrompere la stabilizzazione di tutti gli ordini pianificati selezionati se si verifica un errore in uno di essi. Questa opzione deve essere impostata su *No* se **Stabilizzazione parallela** è impostata su *Sì*.
    - **Stabilizzazione parallela** - Questa opzione è disponibile solo se la funzionalità [*Stabilizzazione parallela degli ordini pianificati*](#enable-features) è attivata per il tuo sistema e se hai selezionato due o più ordini pianificati per la stabilizzazione. Impostala su *Sì* eseguire i processi di stabilizzazione in parallelo. La stabilizzazione parallelo può aiutare a migliorare le prestazioni.
    - **Numero di thread** - Questa opzione è disponibile solo se la funzionalità [*Stabilizzazione parallela degli ordini pianificati*](#enable-features) è attivata per il tuo sistema e se hai impostato l'opzione **Stabilizzazione parallela** su *Sì*. Immettere il numero di thread da utilizzare per parallelizzare il processo di stabilizzazione. Per consigli su come utilizzare questa opzione nella pianificazione generale, vedere [Migliorare le prestazioni della pianificazione generale](../master-planning-performance.md#number-of-threads).

        > [!NOTE]
        > Un valore di *0* (zero) per il campo **Numero di thread** aumenta il tempo di esecuzione della pianificazione generale. Di conseguenza, è consigliabile impostare il campo sempre su un valore maggiore di 0.

    - **Raggruppa per fornitore** - Imposta questa opzione su *Sì* per raggruppare gli ordini fornitore pianificati e creare un unico ordine fornitore per fornitore durante la stabilizzazione. In alternativa, è possibile creare un unico ordine fornitore con una riga per ciascun ordine pianificato.
    - **Raggruppa per gruppo di acquirenti** –Impostare questa opzione su *Sì* per raggruppare gli ordini fornitore pianificati in modo da creare un unico ordine fornitore che unisca il fornitore e il gruppo di acquirenti. Per utilizzare questa opzione, è necessario anche impostare l'opzione **Raggruppa per fornitore** su *Sì*.
    - **Raggruppa per contratto di acquisto**: imposta questa opzione su *Sì* per raggruppare ordini di acquisto pianificati che hanno lo stesso fornitore dei contratti di acquisto esistenti e creare un ordine di acquisto per contratto di acquisto. Questa opzione viene abilitata automaticamente quando **Raggruppa per fornitore** è abilitata. Per utilizzare **Raggruppa per contratto di acquisto**, **Trova contratto di acquisto** deve essere impostato su *Sì* nella pagina **Parametri di pianificazione generale**.
    - **Raggruppa per periodo** (nella sezione **Ordini fornitore**): selezionare il periodo per cui raggruppare gli ordini fornitore pianificati. Per utilizzare questa opzione, è necessario selezionare anche l'opzione **Raggruppa per fornitore**.
    - **Raggruppa per periodo** (nella sezione **Trasferimenti**): selezionare il periodo per cui raggruppare gli ordini di trasferimento pianificati. Gli ordini verranno raggruppati in base ai valori di **Magazzino origine** e **Magazzino destinazione**.

    > [!NOTE]
    > Ciascuna delle opzioni "Raggruppa per" fa sì che il sistema converta ogni ordine pianificato in una riga nel singolo ordine di acquisto risultante dal raggruppamento.

    ![Scheda dettaglio Parametri nella finestra di dialogo Stabilizzazione.](./media/manual-firming.png "Scheda dettaglio Parametri nella finestra di dialogo Stabilizzazione")

1. Nella scheda dettaglio **Esegui in background**, impostare il processo in modo che venga eseguito in modalità batch. Tuttavia, non ha senso impostare una pianificazione ricorrente quando esegui la stabilizzazione. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management. Tuttavia, per la stabilizzazione manuale, il processo batch elaborerà solo gli ordini pianificati attualmente selezionati. Non elaborerà gli ordini che corrispondono ai filtri attualmente applicati alla pagina.
1. Seleziona **OK** per applicare le impostazioni e generare gli ordini stabilizzati.

## <a name="auto-firm-planned-orders"></a>Stabilizzare automaticamente gli ordini pianificati

La stabilizzazione automatica consente di stabilizzare gli ordini pianificati nel processo di pianificazione generale. Puoi Definire un intervallo temporale di stabilizzazione per gruppi di copertura, singoli articoli e combinazioni di articoli e piani generali. Quindi, durante le esecuzioni della pianificazione generale, gli ordini pianificati verranno automaticamente stabilizzati se la data dell'ordine rientra nell'intervallo di tempo specificato per la stabilizzazione. Gli ordini pianificati generati dall'ottimizzazione della pianificazione e l'operazione di pianificazione generale incorporata gestiscono la data dell'ordine (ovvero la data di inizio) in modo diverso.

> [!NOTE]
> La stabilizzazione automatica degli ordini fornitore pianificati può avvenire solo per gli articoli associati a un fornitore.
> 
> Gli ordini derivati (cioè ordini fornitore in conto lavoro) che sono stabilizzati mostreranno uno stato di *In revisione* quando è abilitato il rilevamento delle modifiche.

> [!IMPORTANT]
> Prima che la funzionalità descritta in questa sezione possa essere utilizzata con l'ottimizzazione della pianificazione, la [funzionalità *Stabilizzazione automatica per l'ottimizzazione della pianificazione*](#enable-features) deve essere attivato per il sistema, come descritto all'inizio di questo articolo. La stabilizzazione automatica può sempre essere utilizzato con il motore di pianificazione generale integrato.

### <a name="auto-firming-with-planning-optimization-vs-the-built-in-planning-engine"></a>Stabilizzazione automatica con l'ottimizzazione della pianificazione e motore di pianificazione integrato

Sia l'ottimizzazione di pianificazione che il motore di pianificazione integrato possono essere utilizzati per stabilizzare automaticamente gli ordini pianificati. Tuttavia, esistono delle differenze importanti. Ad esempio, l'ottimizzazione di pianificazione utilizza la data dell'ordine (ovvero la data di inizio) per determinare quali ordini pianificati devono essere stabilizzati, mentre il motore di pianificazione integrato utilizza la data del fabbisogno (ovvero la data di fine). Nella seguente tabella vengono riepilogate le differenze.

| Funzionalità | Ottimizzazione pianificazione | Motore di pianificazione integrato |
|---|---|---|
| **Base data** | La stabilizzazione automatica si basa sulla data dell'ordine (data di inizio). | La stabilizzazione automatica si basa sulla data del fabbisogno (data di fine). |
| **Lead time** | Poiché la data dell'ordine (data di inizio) attiva la stabilizzazione, non è necessario considerare i lead time come parte dell'intervallo temporale per la stabilizzazione. | Per garantire che gli ordini vengano stabilizzati in modo tempestivo, l'intervallo temporale per la stabilizzazione deve essere più lungo del lead time. |
| **Ordini per la settimana in corso** | Per stabilizzare tutti gli ordini che devono iniziare nella settimana corrente, l'intervallo temporale per la stabilizzazione deve essere di una settimana. | Se si desidera stabilizzare tutti gli ordini che devono iniziare nella settimana corrente, l'intervallo temporale per la stabilizzazione deve essere il lead time più una settimana. |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>Impostare la stabilizzazione automatica e l'intervallo temporale di stabilizzazione

Si attiva il stabilizzazione automatica assegnando un intevallo temporale di stabilizzazione automatica all'impostazione di copertura pertinente, come descritto più avanti in questa sezione. Se la stabilizzazione automatica non è attivata per nessuna configurazione di copertura o se la pianificazione viene avviata da una pagina specifica, come la pagina **Fabbisogno netto** per un prodotto rilasciato, il processo di stabilizzazione automatica viene saltata.

Le opzioni di raggruppamento e contrassegno per il Stabilizzazione automatica prendono i valori dalla scheda **Aggiornamento standard** nella pagina **Parametri di pianificazione generale**.

L'intervallo temporale di stabilizzazione automatica è definito dal numero di giorni immessi per l'impostazione della copertura pertinente. È possibile attivare la stabilizzazione automatica e controllare l'intervallo temporale nei seguenti modi:

- Per definire l'intervallo temporale predefinito per la stabilizzazione di un gruppo di copertura, andare a **Pianificazione generale \> Impostazioni \> Copertura \> Gruppi di copertura** e selezionare un gruppo di copertura. Quindi, nella Scheda dettaglio **Altro**, nel campo **Intervallo temporale di stabilizzazione automatica (giorni)**, immettere il numero di giorni.
- Per sovrascrivere l'intervallo temporale di stabilizzazione definito per il gruppo di copertura per un articolo specifico, andare a **Gestione informazioni sul prodotto \> Prodotti rilasciati**. Nel riquadro azioni, selezionare **Piano**, quindi selezionare **Copertura articoli**. Nella scheda **Generale**, selezionare **Ignora intervalli temporali** e nel campo **Intervallo temporale di stabilizzazione automatico (giorni)**, immettere il numero di giorni.
- Per sovrascrivere l'intervallo temporale per la stabilizzazione definito per il gruppo di copertura e la copertura articoli per un piano generale specifico, andare a **Pianificazione generale \> Impostazioni \> Piani generali** e selezionare un piano generale. Quindi, nella Scheda dettaglio **Intervallo temporale in giorni**, impostare **Stabilizzazione** su *Sì* e immettere il numero di giorni.

Se imposti tutti i intervalli temporali menzionati in precedenza su *0* (zero), la stabilizzazione automatica è effettivamente disabilitata per i relativi articoli coperti.

## <a name="firm-planned-orders-by-using-a-query"></a>Stabilizzare gli ordini pianificati utilizzando una query

La stabilizzazione basata su query consente di pianificare la stabilizzazione in base a criteri definiti in anticipo. A differenza del stabilizzazione automatica, la stabilizzazione basata su query consente il stabilizzazione automatica di diversi sottoinsiemi di ordini in diversi momenti. Inoltre, è possibile utilizzare operazioni manuali o automatizzate per stabilizzare diversi tipi di ordini pianificati. Puoi anche visualizzare in anteprima quali ordini stabilizzati vengono selezionati in base alle tue impostazioni. Pertanto, puoi confermare che la selezione soddisfa le tue aspettative.

Puoi combinare la stabilizzazione automatica con ia stabilizzazione basata su query. Ad esempio, un processo di stabilizzazione basato su query ha un intervallo temporale in avanti più lungo di quello di una configurazione di copertura di stabilizzazione automatica corrispondente. Pertanto, il processo di stabilizzazione basato su query elaborerà gli ordini pianificati prima che venga attivata la stabilizzazione automatica. È possibile sfruttare questo comportamento per pianificare gli ordini per fornitori specifici in modo diverso rispetto agli ordini per prodotti simili di altri fornitori.

> [!IMPORTANT]
> Prima che la funzionalità descritta in questa sezione possa essere utilizzata, la [funzionalità *Stabilizzazione degli ordini pianificati con il filtraggio*](#enable-features) deve essere attivato per il sistema, come descritto all'inizio di questo articolo.

Per stabilizzare un ordine pianificato utilizzando il processo di stabilizzazione basato su query, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale \> Pianificazione generale \> Esegui \> Stabilizzazione ordini pianificati**.
1. Nella finestra di dialogo **Stabilizzazione ordini pianificati**, nella scheda dettaglio **Parametri** impostare le opzioni di elaborazione, contrassegno e raggruppamento di base. Queste opzioni funzionano esattamente come nella finestra di dialogo **Stabilizzazione**. (Vedere la sezione precedente per le descrizioni.) Quindi, nella sezione **Piano**, imposta i seguenti campi che sono univoci per la finestra di dialogo **Stabilizzazione ordini pianificati**:

    - **Piano** - Selezionare il piano generale da applicare durante il stabilizzazione degli ordini pianificati trovati da questa query.
    - **Giorni futuri intervallo temporale di stabilizzazione** – selezionare fino a quando i vari fabbisogni e altre considerazioni devono essere calcolati mediante la pianificazione generale.
    - **Giorni passati intervallo temporale di stabilizzazione** – selezionare fino a quando nel passato i vari fabbisogni e altre considerazioni devono essere calcolati mediante la pianificazione generale.

    ![Scheda dettaglio Parametri nella finestra di dialogo Stabilizzazione ordini pianificati.](./media/planned-order-firming-main-1.png "Scheda dettaglio Parametri nella finestra di dialogo Stabilizzazione ordini pinificati")

1. Per specificare quali record devono essere inclusi nell'ordine, selezionare il pulsante **Filtro** nella scheda dettaglio **Record da includere**. Viene visualizzata una finestra di dialogo di query standard, in cui è possibile definire criteri di selezione, criteri di ordinamento e join. I campi funzionano esattamente come funzionano per altri tipi di query in Supply Chain Management. I campi qui sono di sola lettura e mostrano i valori correlati alla tua query.

    ![Scheda dettaglio Record da includere nella finestra di dialogo Stabilizzazione ordini pianificati.](./media/planned-order-firming-main-2.png "Scheda dettaglio Record da includere nella finestra di dialogo Stabilizzazione ordini pianificati")

1. Selezionare **Anteprima** per visualizzare in anteprima il contenuto del tuo ordine consolidato, in base alle tue impostazioni fino a quel momento. L'elenco degli ordini pianificati che verranno stabilizzati viene visualizzato come messaggio. È quindi possibile rettificare le impostazioni come richiesto fino a quando l'anteprima non mostra l'ordine stabilizzato come lo si desidera.

    ![Esempio di anteprima di un ordine stabilizzato.](./media/planned-order-firming-preview.png "Esempio di anteprima di un ordine stabilizzato")

    > [!WARNING]
    > Questa funzionalità stabilizzerà tutti gli ordini pianificati che corrispondono ai criteri di filtro. La stabilizzazione acritica degli ordini pianificati può causare la creazione di un numero enorme di ordini fornitore, di trasferimento e di produzione indesiderati. Prima di continuare, usa sempre il pulsante **Anteprima** per convalidare i record che verranno inclusi.

1. Nella scheda dettaglio **Esegui in background**, impostare il processo in modo che venga eseguito in modalità batch e/o impostare una pianificazione ricorrente. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Seleziona **OK** per applicare le impostazioni e generare gli ordini stabilizzati.

## <a name="track-firmed-orders"></a>Tenere traccia degli ordini stabilizzati

Per tenere traccia di un ordine pianificato che è stato stabilizzato, segui questi passaggi.

1. [Apri una pagina elenco di ordini pianificati](approved-planned-order.md#view-planned-orders).
1. Aprire o selezionare l'ordine pianificato che si desidera tracciare.
1. Nella scheda **Visualizza** del riquadro azioni, nel gruppo **Visualizza**, selezionare **Cronologia stabilizzazione**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
