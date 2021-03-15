---
title: Assegnazione magazzino
description: Questo argomento fornisce informazioni sull'assegnazione magazzino. L'assegnazione magazzino consente di consolidare la domanda per articolo e unità di misura dagli ordini con stato Ordinato, Prenotato o Rilasciato. Aiuta i responsabili del magazzino a pianificare in modo intelligente le ubicazioni di prelievo prima di rilasciare ordini al magazzino e creare attività di prelievo.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fb39daba393944471ee5d412b1eb61754843926f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993755"
---
# <a name="warehouse-slotting"></a>Assegnazione magazzino

[!include [banner](../includes/banner.md)]

Diverse funzionalità di assegnazione magazzino sono disponibili per i responsabili del magazzino per pianificare in modo intelligente le ubicazioni di prelievo prima di rilasciare ordini al magazzino e creare attività di prelievo.

La *funzionalità di assegnazione magazzino* consente di consolidare la domanda per articolo e unità di misura dagli ordini con stato *Ordinato*, *Prenotato* o *Rilasciato*. La domanda generata può quindi essere applicata alle ubicazioni che verranno utilizzate per il prelievo, in base a quantità, unità, dimensioni fisiche, ubicazioni fisse e altro. Dopo aver stabilito il piano di assegnazione, è possibile creare un lavoro di rifornimento per portare la quantità appropriata di scorte in ciascuna ubicazione.

La funzionalità *Assegnazione magazzino per ordini di trasferimento* consente ai responsabili del magazzino di rifornire le ubicazioni di prelievo, in base alla domanda degli ordini di trasferimento non ancora rilasciati al magazzino. Assicura che le ubicazioni di prelievo includano tutti gli articoli necessari per gli ordini di trasferimento dopo che sono stati rilasciati al magazzino. Questa funzione richiede anche l'attivazione della *funzionalità di assegnazione magazzino*.

La funzione *Allocazione dell'assegnazione di magazzino migliorata* aggiunge un'opzione per le righe del modello utilizzate dalla *funzione di assegnazione magazzino*. L'opzione consente al sistema di considerare le scorte disponibili esistenti in un'ubicazione di destinazione. Pertanto, potrebbero essere generati meno rifornimenti per l'assegnazione. La funzione *Allocazione dell'assegnazione di magazzino migliorata* richiede anche l'attivazione della *funzione di assegnazione magazzino*. Opzionalmente può essere utilizzato insieme alla funzione *Assegnazione magazzino per ordini di trasferimento*.

## <a name="turn-on-the-warehouse-slotting-features"></a>Attivare le funzioni di assegnazione magazzino

Prima di poter utilizzare queste funzionalità, è necessario attivarle nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle funzionalità e attivarle se sono obbligatorie. Attivare le seguenti funzionalità come richiesto:

- Funzionalità di assegnazione magazzino
- Assegnazione magazzino per ordini di trasferimento

    > [!IMPORTANT]
    > La *funzione di assegnazione magazzino* deve essere attivata prima di questa funzione.

- Allocazione dell'assegnazione di magazzino migliorata

    > [!IMPORTANT]
    > La *funzione di assegnazione magazzino* deve essere attivata prima di questa funzione.

## <a name="set-up-warehouse-slotting"></a>Configurare l'assegnazione magazzino

Per utilizzare l'assegnazione magazzino, devi configurare gli elementi seguenti nel sistema:

- Livelli unità di misura assegnazione
- Codici direttiva
- Modelli di assegnazione
- Direttive ubicazione

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a>Creare livelli di unità di misura per l'assegnazione

I livelli di unità di misura consentono di raggruppare più unità di misura ai fini dell'assegnazione. Ad esempio, se vengono prelevate più dimensioni di scatole dalla stessa area di selezione delle scatole, è possibile creare un livello per tutte le dimensioni. **È necessario creare una riga per ogni unità di misura che dovrebbe far parte del livello.**

1. Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Livelli di unità di misura assegnazione**.
1. Selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Livello unità di misura:** *EaBoxPl*
    - **Descrizione:** *Ogni pallet di scatole*

1. Selezionare **Salva**.
1. Nella Scheda dettaglio **Unità di misura**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Unità:** *Scatola*
    - **Descrizione:** lasciare vuoto questo campo. Verrà compilato automaticamente quando salvi le modifiche.
    - **Classe di unità:** *Quantità*

1. Seleziona **Nuova** per aggiungere una seconda riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Unità:** *unità*
    - **Descrizione:** lasciare vuoto questo campo. Verrà compilato automaticamente quando salvi le modifiche.
    - **Classe di unità:** *Quantità*

1. Seleziona **Nuova** per aggiungere una terza riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Unità:** *PALLET*
    - **Descrizione:** lasciare vuoto questo campo. Verrà compilato automaticamente quando salvi le modifiche.
    - **Classe di unità:** *Quantità*

1. Seleziona **Salva** per salvare il livello.

### <a name="create-a-directive-code-for-slotting"></a>Creare un codice di direttiva per l'assegnazione

È necessario selezionare il codice di direttiva che deve essere associato a un modello.

1. Vai a **Gestione magazzino \> Impostazioni \> Codici di direttiva**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Codice direttiva**, immetti *Assegnazione*.
1. Nel campo **Descrizione direttiva**, immetti *Assegnazione*.

### <a name="set-up-slotting-templates"></a>Configurare modelli di assegnazione

Ogni modello di assegnazione controlla il modo in cui le scorte vengono assegnate alle ubicazioni per un magazzino specifico. Ogni modello deve includere una riga per ciascuna specifica assegnazione. Utilizza le procedure in questa sezione per impostare i modelli di assegnazione.

1. Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di assegnazione**.
1. Seleziona **Nuovo** per creare un modello.

Successivamente, devi impostare l'intestazione del modello, le specifiche di assegnazione e le direttive di ubicazione, come spiegato nelle sottosezioni seguenti. L'impostazione per l'assegnazione per ordini di trasferimento è simile a quella per l'assegnazione per ordini cliente, ma il campo **Tipo di domanda** è impostato su *Ordini di trasferimento* anziché *Ordine cliente*.

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a>Impostare l'intestazione per un modello di assegnazione ordini cliente

1. Nell'intestazione del modello, imposta i seguenti valori:

    - **Modello di assegnazione:** _61_
    - **Descrizione:** _61_
    - **Tipo di domanda:** *Ordine cliente*

        > [!NOTE]
        > Attualmente, *Ordini cliente* e *Ordini di trasferimento* sono gli unici tipi di domanda supportati. È possibile selezionare *Ordini di trasferimento* solo se la funzionalità *Assegnazione magazzino per ordini di trasferimento* è attivata.

    - **Strategia della domanda:** _Ordinato_

        In questo campo sono disponibili i seguenti valori:

        - **Ordinato**: l'intera quantità ordinata nell'ordine cliente deve essere considerata domanda.
        - **Prenotata**: solo le quantità della riga ordine cliente prenotate (fisiche e ordinate) devono essere considerate domanda.
        - **Rilasciato** - La quantità rilasciata deve essere considerata come domanda.

    - **Magazzino:** _61_
    - **Consenti domanda ondata per utilizzare le quantità non prenotate:** _Sì_

Puoi inoltre specificare una query per restringere l'ambito della domanda che viene valutata.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Impostare le specifiche di assegnazione per ciascun modello

Per ogni modello di ordine cliente creato, attenersi alla seguente procedura per aggiungere una riga per ciascuna specifica di assegnazione.

1. Nella Scheda dettaglio **Dettagli modello di assegnazione**, seleziona **Nuova** per creare una riga di modello.
1. Nella nuova riga, imposta i seguenti valori:

    - **Sequenza:** _1_
    - **Descrizione:** _Ubicazione fissa_
    - **Quantità minima:** _1_

        Questo campo definisce la quantità minima di domanda richiesta per la riga.

    - **Quantità massima:** _1000000_

        Questo campo definisce la quantità massima di domanda valida per la riga.

    - **Unità:** lascia vuoto questo campo.

        Questo campo definisce l'unità di misura a cui si riferiscono le quantità minima e massima.

    - **Livello unità di misura:** _EaBoxPl_

        Questo campo definisce le unità di misura della domanda valide per la riga. Per ulteriori informazioni, vedi la sezione [Impostare livelli di unità di misura per l'assegnazione](#unit-tiers) descritta in precedenza in questo argomento.

    - **Criteri assegnazione fascia:** _Consider qtà_

        In questo campo sono disponibili i seguenti valori:

        - **Presumi vuoto**: questo sistema dovrebbe presumere che tutte le ubicazioni nell'area di prelievo siano vuote e non dovrebbe controllare tali ubicazioni per le scorte.
        - **Considera qtà**: il sistema dovrebbe controllar ele ubicazioni nell'area di prelievo per le scorte e ignorare tutte le ubicazioni che non sono vuote.
        - **Considera scorte** - Il sistema verifica se un'ubicazione di destinazione contiene le quantità non prenotate per l'articolo nella riga di domanda. Se la quantità è sufficiente a soddisfare almeno un'unità della riga di domanda, il record del piano di assegnazione generato viene ridotto della quantità disponibile. Ad esempio, se la domanda è di 10 casi e un caso è disponibile, la domanda individuata sarà di nove casi. Se la domanda è di 10 casi e un caso è disponibile, la domanda individuata sarà di 10 casi. Questo valore è disponibile solo quando la funzionalità *Allocazione dell'assegnazione di magazzino migliorata* è attivata.

    - **Codice direttiva:** _Assegnazione_

        Questo campo definisce la direttiva di ubicazione utilizzata per trovare l'ubicazione di prelievo del lavoro di rifornimento.

    - **Ubicazione di overflow:** lascia vuoto questo campo.

        Questo campo definisce l'ubicazione in cui viene effettuato l'inventario se non è possibile trovare un'ubicazione per la quantità durante l'elaborazione della riga.

    - **Consenti rallentamento:** _Sì_

        Quando questa opzione è impostata su *Sì*, se una domanda non può essere assegnata, verrà creato un lavoro di spostamento per estrarre le scorte dalle ubicazioni in cui sono presenti , ma dove non è stata effettuata alcuna assegnazione. Il modello viene quindi eseguito nuovamente. Questa volta, ignora le scorte nelle ubicazioni. Questa funzionalità funziona al meglio quando il campo **Criteri assegnazione fascia** è impostato su _Considera qtà_.

    - **Utilizzo ubicazioni fisse** _Solo ubicazioni fisse per il prodotto_

        In questo campo sono disponibili i seguenti valori:

        - **Ubicazioni fisse e non fisse**: il sistema non dovrebbe essere limitato all'uso di ubicazioni fisse.
        - **Solo ubicazioni fisse per il prodotto**: il sistema deve effettuare assegnazioni solo in ubicazioni fisse per il prodotto.
        - **Solo ubicazioni fisse per la variante prodotto**: il sistema deve effettuare assegnazioni solo in ubicazioni fisse per la variante prodotto.

> [!NOTE]
> Se il modello di assegnazione contiene almeno una riga in cui il campo **Criteri assegnazione fascia** è impostato su *Considera scorte*, i rallentamenti non sono più consentiti per nessuna riga del modello.

1. Selezionare **Salva**.
1. Seleziona **Nuova** per creare una seconda riga del modello.
1. Nella nuova riga, imposta i seguenti valori:

    - **Sequenza:** _2_
    - **Descrizione:** _Altro_
    - **Qtà minima:** _1_
    - **Qtà massima:** _1000000_
    - **Unità:** lascia vuoto questo campo.
    - **Livello unità di misura:** _EaBoxPl_
    - **Criteri assegnazione fascia:** _Consider qtà_
    - **Codice direttiva:** _Assegnazione_
    - **Ubicazione di overflow:** lascia vuoto questo campo.
    - **Consenti rallentamento:** _Sì_
    - **Utilizza ubicazioni fisse:** seleziona _Ubicazioni fisse e non fisse_

    Nella query per la seconda riga, dovrai ora specificare i criteri utilizzati per determinare in quali ubicazioni è possibile assegnare la domanda per quella riga.

1. Seleziona la riga in cui il campo **Sequenza** è impostato su *2*.
1. Selezionare **Modifica query**.
1. Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Tabella derivata:** *Ubicazioni*
    - **Campo:** *ID profilo ubicazione*
    - **Criteri:** *Pick-06* (seleziona il doppio segno più \[**++**\] nel campo per espandere l'elenco, quindi seleziona *Pick-06* - *Sito di prelievo 6* .)

1. Selezionare **OK**.

#### <a name="set-up-location-directives"></a>Imposta direttive ubicazione

Almeno una direttiva di ubicazione deve essere impostata per supportare i prelievi di assegnazione. Utilizza le procedure in questa sezione per impostare una nuova *direttiva di ubicazione di rifornimento* per i prelievi di assegnazione.

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, nel campo **Tipo di ordine di lavoro**, seleziona *Rifornimento*.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione della nuova direttiva ubicazione, nel campo **Nome**, immetti *Prelievo di assegnazione 61*.
1. Nel campo **Numero sequenza** accettare il valore predefinito.

##### <a name="configure-the-location-directives-fasttab"></a>Configurare la scheda dettaglio Direttive ubicazione

1. Nella Scheda dettaglio **Direttive ubicazione**, imposta i seguenti valori. Accetta i valori predefiniti per tutti gli altri campi.

    - **Tipo di lavoro:** _Prelievo_
    - **Sito:** _6_
    - **Magazzino:** _61_
    - **Codice direttiva:** _Assegnazione_

1. Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.

##### <a name="configure-the-lines-fasttab"></a>Configurare la Scheda dettaglio Righe

1. Nella Scheda dettaglio **Righe** seleziona **Nuova** per creare una riga.
1. Nella nuova riga, imposta i seguenti valori.

    - **Da quantità:** _0_
    - **A quantità:** _1000000_

1. Accettare i valori predefiniti per i campi rimanenti.
1. Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Configurare la scheda dettaglio Azioni direttiva ubicazione

1. Nella Scheda dettaglio **Azioni direttiva ubicazione** seleziona **Nuova** per creare una riga.
1. Nella nuova riga, imposta i seguenti valori. Accetta i valori predefiniti per tutti gli altri campi.

    - **Numero sequenza:** accetta il valore predefinito.
    - **Nome:** _In blocco_
    - **Strategia:** _Nessuna_

1. Accettare i valori predefiniti per i campi rimanenti.
1. Seleziona **Salva** per rendere il pulsante **Modifica query** disponibile.

##### <a name="edit-the-query"></a>Modificare la query

1. Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.
1. Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Tabella derivata:** *Ubicazioni*
    - **Campo:** *ID zona*
    - **Criteri:** *In blocco* (seleziona il doppio segno più \[**++**\] nel campo per espandere l'elenco, quindi seleziona *In blocco*.)

1. Selezionare **OK**.

## <a name="scenario"></a>Scenario

### <a name="set-up-the-scenario"></a>Impostare lo scenario

Per questo scenario, utilizzare i dati di esempio incorporati e creare i record descritti in questa sezione.

#### <a name="use-the-usmf-sample-data"></a>Utilizzare i dati di esempio USMF

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

#### <a name="create-demand"></a>Creare domanda

Seguire questi passaggi per creare la domanda a cui applicare l'assegnazione.

1. Vai a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona _US-007_.
1. Nel campo **Magazzino** selezionare _61_.
1. Selezionare **OK**.
1. Viene aperto il nuovo ordine cliente. Include una riga vuota nella Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Articolo:** _L0101_
    - **Quantità:** _20_

1. Seleziona **Aggiungi riga** per aggiungere una nuova riga, quindi imposta i seguenti valori:

    - **Articolo:** _T0100_
    - **Quantità:** _8_

1. Selezionare **Salva**.
1. Seleziona **Nuovo** per creare un secondo ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona _US-008_.
1. Nel campo **Magazzino** selezionare _61_.
1. Viene aperto il nuovo ordine cliente. Include una riga vuota nella Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Articolo:** _T0100_
    - **Quantità:** _1_

1. Selezionare **Salva**.

### <a name="walk-through-a-typical-slotting-scenario"></a>Eseguire un tipico scenario di assegnazione

Dopo che tutti gli elementi dei prerequisiti sono presenti, come descritto nella sezione precedente, sei pronto per provare la funzione utilizzando ogni esercizio in questa sezione.

#### <a name="generate-demand"></a>Genera domanda

1. Vai a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli assegnazione** e seleziona il modello di assegnazione che hai creato in precedenza.
1. Nel riquadro azioni, seleziona **Genera domanda**. Questo comando valuta tutta la domanda presente nel sistema e corrisponde alla query del modello di assegnazione. La domanda totale per tutti gli ordini viene quindi consolidata su una riga per quantità/unità di misura. Un messaggio informativo appare quando il processo è completato.

#### <a name="slotting-demand"></a>Domanda di assegnazione

La *domanda di assegnazione* mostra i risultati della generazione della domanda, in base all'impostazione del modello di assegnazione.

- Nel riquadro azioni seleziona **Domanda di assegnazione** per visualizzare i risultati dal comando **Genera domanda**. Le righe nella domanda di assegnazione possono essere modificate. Puoi eliminare una riga, aggiungere una nuova riga o modificare i dettagli della riga.

> [!NOTE]
> Puoi modificare manualmente la domanda oppure importarla da un sistema esterno utilizzando la gestione dei dati. Qualunque sia il contenuto della domanda di assegnazione verrà utilizzata nel passaggio successivo, indipendentemente da dove provenga.

#### <a name="locate-demand"></a>Rileva la richiesta

Dopo che la domanda è stata generata, è necessario utilizzare il comando **Trova la domanda** per generare il *piano di assegnazione*.

- Nel riquadro azioni, seleziona **Trova domanda**. Viene eseguito il processo di assegnazione. Un messaggio informativo appare quando il processo è completato.

#### <a name="slotting-plan"></a>Piano di assegnazione

Il piano di assegnazione mostra l'ubicazione a cui è stato assegnato ciascun articolo/quantità, se è stato utilizzato l'overflow, se è stato creato il lavoro di rallentamento e la riga del modello utilizzata. *Qualsiasi domanda che non è stato possibile assegnare è evidenziata in rosso.*

- Nel riquadro azioni seleziona **Piano di assegnazione** per visualizzare i risultati.

> [!NOTE]
> - I processi **Genera domanda**, **Individua domanda** ed **Esegui rifornimento** vengono ora eseguiti in una sandbox. (Questi processi sono disponibili dal riquadro azioni nella pagina **Modelli di assegnazione**.)
> - I processi **Genera domanda**, **Individua domanda** ed **Esegui rifornimento** hanno un blocco per garantire che non possano essere attivati contemporaneamente. In caso contrario, i dati utilizzati potrebbero essere eliminati.
> - I processi **Genera domanda** e **Individua domanda** mostrano un avviso se l'esecuzione non ha generato record o se nei record mancano informazioni.
> - Quando si seleziona **Piano di assegnazione**, la pagina non include i pulsanti **Nuovo**, **Modifica** o **Elimina** nel riquadro azioni, perché l'origine dati non può essere modificata.
> - Quando si seleziona **Esegui rifornimento**, il sistema convalida il modello di assegnazione selezionato e i processi.

#### <a name="create-replenishment"></a>Creare rifornimento

Dopo aver creato il piano di assegnazione, è necessario creare il *lavoro di rifornimento*, in base al piano.

- Nel riquadro azioni seleziona **Esegui rifornimento**. Un messaggio informativo appare quando il processo è completato. Questo messaggio indica il numero di intestazioni create per l'ID build di lavoro.

Le direttive di ubicazione che verranno utilizzate sono identificate in base al codice della direttiva specificato su ciascuna riga del modello.

## <a name="tips"></a>Suggerimenti

### <a name="set-up-automatic-slotting"></a>Configurare l'assegnazione automatica

Dopo aver inserito tutti gli elementi richiesti, è possibile impostare l'assegnazione per l'esecuzione automatica seguendo questi passaggi.

1. Vai a **Gestione magazzino \> Rifornimento \> Esegui assegnazione**.
1. Specifica le fasi di assegnazione da eseguire. Seleziona una o più delle seguenti fasi di assegnazione:

    - Genera domanda
    - Rileva la richiesta
    - Crea lavoro di rifornimento

    > [!NOTE]
    > I passaggi di assegnazione sono progressivi. Se vuoi selezionare *Trova domanda*, devi prima selezionare *Genera domanda*.

1. Specifica il modello di assegnazione da utilizzare.
1. Imposta la ricorrenza per l'esecuzione automatica, se lo desideri.

Per gli esercizi nello scenario, **non** impostare l'assegnazione automatica.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]