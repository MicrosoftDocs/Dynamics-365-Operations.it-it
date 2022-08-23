---
title: Automazione dell'offerta Produzione su ordine
description: In questo articolo viene descritto come impostare e utilizzare i vari miglioramenti aggiunti dalla funzionalità Automazione dell'offerta Produzione su ordine.
author: t-benebo
ms.date: 07/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-27
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9044acb472548a797ed387b08ca6892459785793
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220607"
---
# <a name="make-to-order-supply-automation"></a>Automazione dell'offerta Produzione su ordine

[!include [banner](../includes/banner.md)]

La funzionalità *Automazione dell'offerta Produzione su ordine* aggiunge vari miglioramenti a Microsoft Dynamics 365 Supply Chain Management. Questi miglioramenti ti consentono di effettuare le seguenti operazioni:

- Visualizzare il carico di capacità della risorsa per un periodo definito dall'utente e quindi abilitare la valutazione a lungo termine del carico di capacità.
- Migliorare la flessibilità controllando la tolleranza di ritardo (giorni negativi) per ogni piano generale.
- Mantenere i prodotti disponibili per gli ordini dell'ultimo minuto e ottimizzare l'utilizzo dell'offerta esistente eseguendo il pegging dell'ultima offerta possibile per una domanda anziché usare la prima offerta possibile.
- Mantenere flessibile l'assegnazione dei componenti per gli ordini di produzione dopo la stabilizzazione, di modo che il sistema sia in grado di eseguire l'ottimizzazione per modifiche della domanda dell'ultimo minuto. In altre parole, limitare il contrassegno a un livello.
- Controllare i criteri di evasione per ogni ordine cliente. Le impostazioni predefinite sono quelle della configurazione del cliente.
- Ottimizzare il flusso di informazioni interaziendale. Gli ordini fornitore vengono aggiornati in modo da includere i campi per la modalità di consegna, i termini di consegna e il numero articolo esterno. Questa modifica garantisce che le informazioni dettagliate sulla domanda possano fluire alla società fornitrice.

In questo articolo viene descritto come configurare e utilizzare ogni miglioramento.

> [!NOTE]
> Tutti i miglioramenti descritti in questo articolo si applicano ai sistemi che utilizzano la pianificazione generale integrata. I due miglioramenti seguenti sono supportati anche dal componente aggiuntivo Ottimizzazione pianificazione per Microsoft Dynamics 365 Supply Chain Management:
>
> - Tolleranza di ritardo nei piani generali
> - Controllo sulla sequenza di pegging utilizzata durante la pianificazione generale

## <a name="turn-on-the-make-to-order-supply-automation-feature"></a>Attivare la funzionalità Automazione dell'offerta Produzione su ordine

Prima di poter utilizzare la funzionalità descritta in questo articolo, devi attivarla per il sistema. Gli amministratori possono usare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), dove la funzionalità è elencata nel modo seguente:

- **Modulo:** *Pianificazione generale*
- **Nome funzionalità**: *Automazione dell'offerta Produzione su ordine*

## <a name="set-the-number-of-days-to-show-on-capacity-load-page"></a>Impostare il numero di giorni da visualizzare nella pagina Carico di capacità

La pagina **Carico di capacità** ti consente di esaminare la capacità disponibile di una risorsa. La funzionalità *Automazione dell'offerta Produzione su ordine* migliora la pagina **Carico di capacità** aggiungendo il campo **Numero di giorni**. È possibile utilizzare questo campo per limitare il numero di giorni visualizzati nella griglia **Panoramica**. Il valore che imposti viene salvato in memoria. Pertanto, se esci dalla pagina e vi accedi di nuovo in seguito, la griglia **Panoramica** mostrerà ancora il numero di giorni che hai specificato per l'ultima volta.

Per aprire la pagina **Carico di capacità** in modo da poter esaminare la capacità disponibile per una singola risorsa, procedi come segue.

1. Vai a **Amministrazione organizzazione \> Risorse \> Risorse**.
1. Seleziona una risorsa da esaminare.
1. Nel riquadro Azioni, nella scheda **Risorsa**, nel gruppo **Visualizza**, seleziona **Carico di capacità**.
1. Usa il filtro **Numero di giorni** per limitare il numero di giorni visualizzati nella griglia **Panoramica**.

Per aprire la pagina **Carico di capacità** in modo da poter esaminare la capacità disponibile per un gruppo di risorse, procedi come segue.

1. Passare a **Amministrazione organizzazione \> Risorse \> Gruppi di risorse**.
1. Seleziona un gruppo di risorse da esaminare.
1. Nel riquadro Azioni, nella scheda **Gruppo di risorse**, nel gruppo **Visualizza**, seleziona **Carico di capacità**.
1. Usa il filtro **Numero di giorni** per limitare il numero di giorni visualizzati nella griglia **Panoramica**.

## <a name="apply-a-single-level-of-marking-when-you-firm-planned-orders"></a>Applicare un unico livello di contrassegno quando si stabilizzano ordini pianificati

*Contrassegno* viene utilizzato per collegare domanda e offerta. Assomiglia al *pegging*, che indica come la pianificazione generale prevede di coprire la domanda. Tuttavia, il contrassegno è più permanente del pegging. La funzionalità *Automazione dell'offerta Produzione su ordine* aggiunge la possibilità di limitare il contrassegno delle scorte a un unico livello quando gli ordini pianificati vengono stabilizzati. Aggiunge le seguenti nuove opzioni al campo **Aggiorna contrassegno** nella finestra di dialogo **Stabilizzazione** durante la stabilizzazione di un ordine pianificato:

- *Livello singolo standard*: viene utilizzato il contrassegno a livello singolo. Il contrassegno a livello singolo contrassegna solo l'articolo principale, non i componenti della distinta base (DBA). Pertanto, puoi mantenere flessibile l'assegnazione dei componenti per gli ordini di produzione dopo la stabilizzazione. Il contrassegno a livello singolo consente al sistema di eseguire l'ottimizzazione per le modifiche della domanda dell'ultimo minuto. Nel contrassegno a livello singolo *standard*, gli ordini di fabbisogno vengono contrassegnati rispetto ai relativi ordini di evasione, ma gli ordini di evasione non vengono contrassegnati se hanno quantità rimanenti.
- *Livello singolo esteso*: viene utilizzato il contrassegno a livello singolo. Nel contrassegno a livello singolo *esteso*, gli ordini di fabbisogno vengono contrassegnati rispetto ai relativi ordini di evasione e gli ordini di evasione vengono sempre contrassegnati indipendentemente dalla quantità rimanente.

Queste opzioni sono disponibili nel campo **Aggiorna contrassegno** nella scheda **Aggiornamento standard** della pagina **Parametri di pianificazione generale**, in cui definisci la selezione predefinita per la finestra di dialogo **Stabilizzazione**.

Per ulteriori informazioni, vedi [Contrassegno scorte con Ottimizzazione pianificazione](planning-optimization/marking.md).

## <a name="set-delay-tolerance-negative-days-at-the-master-plan-level"></a>Impostare la tolleranza di ritardo (giorni negativi) a livello di piano generale

La funzionalità *Automazione dell'offerta Produzione su ordine* aggiunge la possibilità di configurare la tolleranza di ritardo (giorni negativi) a livello di piano generale. L'impostazione è disponibile anche a livello di copertura articoli e di gruppo di copertura. Se i giorni negativi vengono assegnati a più livelli, il sistema applica la seguente gerarchia per decidere quale impostazione utilizzare:

- Se i giorni negativi sono configurati nella pagina **Piani generali**, tale impostazione ha la precedenza su tutte le altre impostazioni dei giorni negativi quando viene eseguito il piano.
- Se i giorni negativi sono configurati nella pagina **Copertura articoli**, tale impostazione ha la precedenza sull'impostazione del gruppo di copertura.
- I giorni negativi configurati nella pagina **Gruppi di copertura** si applicano solo se non sono stati configurati giorni negativi per un articolo o un piano generale pertinente.

Per impostare giorni negativi per un piano generale, procedi come segue.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Seleziona un piano generale nel riquadro elenco o creane uno.
1. Nella Scheda dettaglio **Intervalli temporali in giorni**, imposta l'opzione **Giorni negativi** su *Sì*.
1. Nel campo vicino, immetti il numero di giorni negativi da consentire.

Per ulteriori informazioni su come utilizzare i giorni negativi, vedi [Tolleranza di ritardo (giorni negativi)](planning-optimization/delay-tolerance.md).

## <a name="control-the-pegging-sequence-used-during-master-planning"></a>Controllare la sequenza di pegging utilizzata durante la pianificazione generale

La pianificazione generale utilizza una *sequenza di pegging* per determinare quale offerta coprirà quale domanda. La funzionalità *Automazione dell'offerta Produzione su ordine* aggiunge una nuova opzione **Usa ultima offerta possibile** che fornisce un maggiore controllo sulla sequenza di pegging. La nuova opzione ti consente di mantenere i prodotti disponibili per gli ordini dell'ultimo minuto e di ottimizzare l'utilizzo dell'offerta esistente eseguendo il pegging dell'ultima offerta possibile per una domanda anziché usare la prima offerta possibile.

Puoi impostare la sequenza di pegging a livello di piano generale, copertura articoli o gruppo di copertura. Se una sequenza di pegging viene impostata a più livelli, il sistema applica la seguente gerarchia per decidere quale impostazione utilizzare:

- Se una sequenza di pegging viene impostata nella pagina **Piani generali**, tale impostazione ha la precedenza su tutte le altre impostazioni della sequenza di pegging quando viene eseguito il piano.
- Se una sequenza di pegging viene impostata nella pagina **Copertura articoli**, tale impostazione ha la precedenza sull'impostazione del gruppo di copertura.
- La sequenza di pegging impostata nella pagina **Gruppi di copertura** si applica solo se le impostazioni della sequenza di pegging non sono state configurate per un articolo o un piano generale pertinente.

Per impostare il pegging a livello di gruppo di copertura, procedi come segue.

1. Andare a **Pianificazione generale \> Impostazioni \> Copertura \> Gruppi di copertura**.
1. Seleziona un gruppo nel riquadro elenco o creane uno.
1. Nella Scheda dettaglio **Generale**, nella sezione **Sequenza di pegging**, utilizza i campi **Consuma scorte disponibili** e **Usa ultima offerta** per configurare la sequenza di pegging. La tabella più avanti in questa sezione mostra come queste impostazioni vengono combinate per definire la sequenza di pegging.

Per impostare il pegging a livello di copertura articoli, procedi come segue.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Seleziona un prodotto nella griglia o creane uno.
1. Nella scheda **Piano** del riquadro Azioni seleziona **Copertura articoli**.
1. La pagina **Copertura articoli** fornisce righe che ti consentono di definire le regole di copertura che si applicano all'articolo in ogni magazzino. Seleziona una riga esistente nella griglia o creane una.
1. Nella scheda **Generale**, seleziona la casella di controllo **Sostituisci sequenza di pegging**.
1. Utilizza i campi **Consuma scorte disponibili** e **Usa ultima fornitura** per configurare la sequenza di pegging. La tabella più avanti in questa sezione mostra come queste impostazioni vengono combinate per definire la sequenza di pegging.

Per impostare il pegging a livello di piano generale, procedi come segue.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Seleziona un piano generale nel riquadro elenco o creane uno.
1. Nella Scheda dettaglio **Generale**, imposta l'opzione **Sostituisci sequenza di pegging** su *Sì*.
1. Utilizza i campi **Consuma scorte disponibili** e **Usa ultima fornitura** per configurare la sequenza di pegging. La tabella più avanti in questa sezione mostra come queste impostazioni vengono combinate per definire la sequenza di pegging.

La tabella seguente mostra come le impostazioni **Consuma scorte disponibili** e **Usa ultima offerta** vengono combinate per stabilire la sequenza di pegging.

| | Usa ultima offerta = Sì | Usa ultima offerta = No |
|---|---|---|
| **Consuma scorte disponibili** = *Prima di tutte le offerte* | <ol><li>Disponibilità</li><li>Offerta esistente che può rispettare la data della domanda</li><li>Offerta esistente che non può soddisfare la data della domanda, ma rispetta il limite di giorni negativi</li><li>Creare una nuova offerta (ordine pianificato)</li></ol> | <ol><li>Disponibilità</li><li>Offerta esistente che può rispettare la data della domanda</li><li>Offerta esistente che non può soddisfare la data della domanda, ma rispetta il limite di giorni negativi</li><li>Creare una nuova offerta (ordine pianificato)</li></ol> |
| **Consuma scorte disponibili** = *Dopo tutte le offerte* | <ol><li>Offerta esistente che può rispettare la data della domanda</li><li>Disponibilità</li><li>Offerta esistente che non può soddisfare la data della domanda, ma rispetta il limite di giorni negativi</li><li>Creare una nuova offerta (ordine pianificato)</li></ol> | <ol><li>Offerta esistente che può rispettare la data della domanda</li><li>Offerta esistente che non può soddisfare la data della domanda, ma rispetta il limite di giorni negativi</li><li>Disponibilità</li><li>Creare una nuova offerta (ordine pianificato)</li></ol> |

## <a name="review-and-set-the-fulfillment-policy-that-applies-to-each-sales-order"></a>Esaminare e impostare i criteri di adempimento che si applicano a ogni ordine cliente

I criteri di adempimento controllano la percentuale del prezzo o della quantità ordine totale che deve essere fisicamente prenotata affinché sia possibile rilasciare un ordine cliente al magazzino. Puoi impostare criteri di adempimento predefiniti globali e quindi sostituirli per clienti specifici come necessario. La funzionalità *Automazione dell'offerta Produzione su ordine* aggiunge la possibilità di visualizzare quali criteri predefiniti si applicano effettivamente a qualsiasi ordine e di applicare una sostituzione specifica dell'ordine come necessario.

- Per impostare i criteri di adempimento predefiniti globali per gli ordini cliente, vai a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**. Nella scheda **Gestione magazzino**, imposta il campo **Criteri di adempimento ordine cliente** sul nome dei criteri che vuoi utilizzare. 
- Per impostare criteri di adempimento specifici del cliente per ordini cliente, vai a **Contabilità clienti \> Clienti \> Tutti i clienti**. Nella scheda **Gestione magazzino**, imposta il campo **Criteri di adempimento** sul nome dei criteri che vuoi utilizzare.

Per visualizzare i criteri predefiniti che si applica a qualsiasi ordine e applicare una sostituzione specifica dell'ordine, procedi come segue.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Apri l'ordine cliente che vuoi esaminare o modificare.
1. Seleziona la visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Magazzino**, esamina e modifica i seguenti campi come necessario:

    - **Criteri di adempimento ordine**: seleziona i criteri di adempimento da utilizzare per l'ordine selezionato. I criteri predefiniti verranno ignorati. Per utilizzare i criteri di adempimento predefiniti visualizzati nel campo **Criteri di adempimento predefiniti**, lascia vuoto questo campo.
    - **Criteri di adempimento predefiniti**: questo campo mostra i criteri di adempimento predefiniti che si applicano se il campo **Criteri di adempimento ordine** è vuoto. Questo campo è di sola lettura. Se è vuoto, non viene definito alcun criterio di adempimento predefinito globale o specifico del cliente.

    Se entrambi i campi **Criteri di adempimento ordine** e **Criteri di adempimento predefiniti** sono vuoti, non vengono applicati criteri di adempimento. Tuttavia, potrebbero essere in vigore altre restrizioni, che potrebbero richiedere il rispetto di prenotazioni o altre condizioni affinché l'ordine cliente possa essere rilasciato.

## <a name="set-the-delivery-mode-and-terms-on-individual-purchase-order-lines"></a>Impostare la modalità e i termini di consegna per singole righe dell'ordine fornitore

Tutti gli ordini fornitore includono le impostazioni **Termini di consegna** e **Modalità di consegna** nell'intestazione dell'ordine. La funzionalità *Automazione dell'offerta Produzione su ordine* aggiunge queste impostazioni a ogni riga ordine. Pertanto, puoi definire le sostituzioni del valore **Termini di consegna** e/o **Modalità di consegna** per una o tutte le righe ordine come necessario. Per le righe in cui non è stata definita alcuna sostituzione, viene utilizzato il valore dell'intestazione. Puoi specificare se una modifica al valore di uno o entrambi questi campi nell'intestazione dell'ordine deve aggiornare anche tutte le righe.

Per specificare l'impatto sulle impostazioni relative alle righe se un utente modifica il valore **Termini di consegna** e/o **Modalità di consegna** nell'intestazione di un ordine, procedi come segue.

1. Passare a **Approvvigionamento \> Impostazioni \> Parametri di approvvigionamento**.
1. Nella scheda **Generale**, nella Scheda dettaglio **Valori e parametri predefiniti**, seleziona il collegamento **Aggiorna righe ordine**.
1. Nella finestra di dialogo **Aggiorna righe ordine**, nei campi **Aggiorna termini di consegna** e **Aggiorna modalità di consegna**, seleziona uno dei seguenti valori:

    - *Mai*: non aggiornare mai le righe ordine dopo aver modificato le impostazioni nell'intestazione dell'ordine.
    - *Sempre*: aggiorna sempre tutte le righe ordine dopo aver modificato le impostazioni nell'intestazione dell'ordine.
    - *Prompt*: se un utente modifica una o entrambe le impostazioni nell'intestazione dell'ordine, viene aperta una finestra di dialogo che chiede se l'utente desidera aggiornare tutte le righe in modo che corrispondano alla modifica a una o entrambe le impostazioni.

Per impostare le informazioni di consegna nell'intestazione di un ordine fornitore, procedi come segue.

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Apri l'ordine fornitore che vuoi modificare.
1. Seleziona la visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Consegna**, imposta i campi **Modalità di consegna** e **Termini di consegna** come necessario.
1. A seconda delle impostazioni nella pagina **Parametri di approvvigionamento**, è possibile che ti venga chiesto se desideri applicare le modifiche a tutte le righe ordine.

Per impostare sostituzioni per le informazioni di consegna per una riga dell'ordine fornitore, procedi come segue.

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Apri l'ordine fornitore che vuoi modificare.
1. Seleziona la visualizzazione **Righe**.
1. Nella Scheda dettaglio **Righe ordine fornitore**, seleziona la riga da modificare.
1. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, imposta i campi **Modalità di consegna** e **Termini di consegna** come necessario. Deseleziona uno o entrambi i campi per utilizzare le impostazioni di corrispondenza nell'intestazione.

Per gli ordini interaziendali, i valori per i campi **Modalità di consegna** e **Termini di consegna** in ogni riga dell'ordine fornitore verranno sincronizzati tra l'ordine fornitore e l'ordine cliente correlato.

## <a name="sync-external-item-ids-and-descriptions-for-intercompany-orders"></a>Sincronizzare descrizioni e ID di articoli esterni per ordini interaziendali

Per gli ordini interaziendali, la funzionalità *Automazione dell'offerta Produzione su ordine* consente di sincronizzare descrizioni di testo e ID di articoli esterni nelle righe dell'ordine fornitore con le righe dell'ordine cliente interaziendale correlate, indipendentemente dal fatto che l'ordine fornitore sia per la consegna diretta o meno. La funzionalità aggiunge anche la possibilità di specificare l'account cliente esterno finale in un ordine fornitore interaziendale. Il sistema acquisirà quindi automaticamente descrizioni di testo e ID di articoli esterni dal record cliente esterno anziché dal record fornitore interaziendale (interno).

Per impostare un fornitore interaziendale per la sincronizzazione di nomi e ID di articoli esterni tra gli ordini fornitore interaziendali e i relativi ordini cliente interaziendali correlati, procedi come segue.

1. Andare ad **Approvvigionamento \> Fornitori \> Tutti i fornitori**.
1. Seleziona il fornitore interaziendale che vuoi impostare.
1. Nel riquadro Azioni, nella scheda **Generale**, nel gruppo **Impostazione**, seleziona **Interaziendale**.
1. Nella pagina **Interaziendale**, nella scheda **Criteri ordini fornitore**, nella sezione **Ordine fornitore interaziendale -\> Ordine cliente interaziendale**, seleziona la casella di controllo **Nome articolo e ID articolo esterno**.

Per specificare l'account cliente esterno finale per un ordine fornitore interaziendale, procedi come segue. Il campo **Conto cliente** si applica solo agli ordini fornitore interaziendali. Utilizzalo per specificare il numero di conto del cliente che alla fine riceverà la merce. Quando questo campo è impostato, le righe dell'ordine fornitore acquisiranno i numeri e le descrizioni degli articoli esterni dal conto cliente specificato anziché dal fornitore interaziendale specificato nell'ordine fornitore. Se modifichi l'account cliente in un secondo momento, le descrizioni e gli ID di articoli esterni verranno aggiornati di modo che corrispondano ai valori del nuovo account. Le descrizioni e gli ID di articoli esterni per ogni riga verranno sincronizzati anche con l'ordine cliente interaziendale corrispondente.

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Apri l'ordine fornitore che vuoi impostare o creane uno.
1. Seleziona la visualizzazione **Intestazione**.
1. Nella sezione **Riferimento**, imposta il campo **Conto cliente** sull'account cliente esterno pertinente.

Per specificare descrizioni di testo e ID di articoli esterni per una riga ordine fornitore di un ordine interaziendale, procedi come segue. I valori che imposti verranno sincronizzati con le righe dell'ordine cliente interaziendale correlate, indipendentemente dal fatto che l'ordine fornitore sia per la consegna diretta o meno.

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Apri l'ordine fornitore che vuoi impostare o creane uno.
1. Seleziona la visualizzazione **Righe**.
1. Nella Scheda dettaglio **Righe ordine fornitore**, seleziona la riga da modificare.
1. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Generale**, nella sezione **Riga ordine**, nel campo **Testo**, fornisci una descrizione esterna dell'articolo specificato nella riga ordine selezionata. Questo valore verrà sincronizzato con la riga dell'ordine cliente interaziendale correlata.
1. Nella sezione **Riferimento**, nel campo **Esterno**, fornisci un ID di articolo esterno per l'articolo specificato nella riga ordine selezionata. Questo valore verrà sincronizzato con la riga dell'ordine cliente interaziendale correlata.

Per ulteriori informazioni, vedi [Creare e fatturare un ordine cliente interaziendale per un cliente esterno](../sales-marketing/intercompany-sales-order-for-external-customer.md).
