---
title: Gestione qualità per i processi di magazzino
description: Questo argomento fornisce informazioni sulla funzionalità Gestione qualità per i processi di magazzino. Questa funzionalità estende le capacità di gestione della qualità e consente agli utenti di integrare i controlli di campionamento degli articoli nel processo di ricezione del magazzino utilizzando la gestione avanzata del magazzino.
author: Henrikan
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 42280c811e1f4ed5d33c66f5a8634417a61be905
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301331"
---
# <a name="quality-management-for-warehouse-processes"></a>Gestione qualità per i processi di magazzino

La funzione _Gestione qualità per i processi di magazzino_ consente di integrare i controlli di campionamento degli articoli nel processo di ricezione del magazzino utilizzando la gestione avanzata del magazzino. Il lavoro di magazzino può essere generato automaticamente per spostare le scorte nell'ubicazione di controllo qualità, in base a una percentuale o una quantità fissa, oppure in base a ogni *n* targhe. Dopo che un ordine di controllo qualità è stato completato, il lavoro può essere generato automaticamente per spostare le scorte nella posizione successiva del processo, a seconda dei risultati di qualità.

La funzionalità _Gestione qualità per i processi di magazzino_ estende le funzionalità della funzionalità di gestione della qualità di base. Offre la possibilità di creare ordini di controllo qualità per le scorte che vengono inviate all'ubicazione di controllo di qualità, sebbene gli ordini di controllo qualità non siano sempre richiesti. Pertanto, consente un semplice processo di controllo della qualità basato sul lavoro di magazzino.

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>Attivare la funzione Gestione qualità per i processi di magazzino

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome della funzione:** *Gestione qualità per i processi di magazzino*

## <a name="key-benefits"></a>Benefit principali

La funzione _Gestione qualità per i processi di magazzino_ genera automaticamente lavoro come parte del processo di ricezione, per spostare la quantità di scorte necessaria per il controllo della qualità in un'ubicazione di controllo qualità. Se la quantità ricevuta supera la quantità richiesta per il controllo qualità (in base all'impostazione del campionamento articoli), la quantità in eccesso viene spostata in una posizione in entrata definita nell'impostazione della direttiva di ubicazione. Dopo la convalida dell'ordine di controllo qualità, viene generato automaticamente il lavoro per spostare la quantità per l'ordine di controllo qualità in una nuova ubicazione di entrata o di ritorno, in base al risultato della convalida e all'impostazione della direttiva di ubicazione. La generazione automatica di lavoro che ha solo la quantità che deve essere spostata da e verso il controllo di qualità offre un'esperienza di processo integrata.

> [!NOTE]
> Quando la funzione _Gestione qualità per i processi di magazzino_ è attiva, è possibile comunque utilizzare il processo manuale. Nel processo manuale, il movimento scorte e il movimento per modello vengono utilizzati per consentire a un addetto al magazzino di avviare la creazione di lavori di magazzino per spostare le scorte da un'ubicazione di controllo qualità ad una nuova ubicazione. È in oltre possibile impostare una direttiva di ubicazione in entrata che sposta le scorte nella sua interezza da una posizione di ricezione a un'ubicazione di controllo qualità, senza considerare l'impostazione del campionamento degli articoli.

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>Gestione della qualità e la funzione Gestione qualità per i processi di magazzino

Quando la funzione _Gestione qualità per i processi di magazzino_ è attivata, modifica l'impostazione delle principali entità di gestione del magazzino e di gestione della qualità. La seguente illustrazione fornisce una panoramica delle entità che abilitano gli ordini di controllo qualità per i processi di magazzino. Il testo tra parentesi indica le azioni suggerite quando è stata applicata la gestione della qualità prima che la funzione _Gestione qualità per i processi di gestione magazzino_ sia stata attivata.

![Processi di gestione qualità](media/quality-management-entity-diagram.png "Entità di gestione qualità")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>Addetti all'abilitazione: tipi ordine di lavoro dell'ordine di controllo qualità e campionamento di articoli di qualità

La funzione _Gestione qualità per i processi di magazzino_ introduce due tipi di ordini di lavoro che consentono il processo di creazione del lavoro:

- **Campionamento di articoli di qualità** - Questo tipo di ordine di lavoro viene utilizzato per creare lavoro, il quale sposta le scorte registrate al controllo di qualità.
- **Ordine di controllo qualità** - Questo tipo di ordine di lavoro viene utilizzato per creare lavoro che sposta le scorte dal controllo di qualità a una nuova ubicazione, in base all'impostazione della direttiva di ubicazione.

### <a name="work-classes-location-directives-and-work-templates"></a>Classi di lavoro, direttive di ubicazione e modelli di lavoro

I tipi di ordini di lavoro _Campionamento di articoli di qualità_ e _Ordine di controllo qualità_ sono utilizzati da direttive di ubicazione, classi di lavoro e modelli di lavoro.

Prima che il lavoro di magazzino possa essere generato automaticamente per spostare le scorte al controllo di qualità, è necessario seguire questi passaggi per configurare il sistema.

1. Creare classi di lavoro separate per i tipi di ordine di lavoro _Campionamento di articoli di qualità_ e _Ordine di controllo qualità_. In questo modo, si garantisce che il lavoro appropriato possa essere generato automaticamente in base ai due tipi di ordine di lavoro e che questo lavoro possa quindi essere eseguito utilizzando l'app per dispositivi mobili Gestione magazzino.
1. Impostare un modello di lavoro per ciascun tipo di ordine di lavoro:

    - Impostare un modello di lavoro che utilizza il tipo di ordine di lavoro _Campionamento di articoli di qualità_ per spostare automaticamente le scorte registrate in un'ubicazione di controllo qualità.
    - Impostare un modello di lavoro che utilizza il tipo di ordine di lavoro _ordine di controllo qualità_ per spostare le scorte da un'ubicazione di controllo qualità dopo il completamento del controllo qualità.

1. Per ogni tipo di ordine di lavoro, impostare le direttive di ubicazione che applicano le posizioni di controllo qualità corrette in cui le scorte devono essere spostate. Una volta completato il controllo di qualità, la direttiva di ubicazione per il tipo di ordine di lavoro _Ordine di controllo qualità_ garantisce che verrà selezionata una nuova ubicazione di destinazione in modo che le scorte possano essere spostate dall'ubicazione di controllo qualità.
1. Impostare le voci di menu del dispositivo mobile pertinenti per supportare lo spostamento delle scorte ricevute nell'ubicazione di controllo qualità e lo spostamento delle scorte che superano o non superano il controllo di qualità dall'ubicazione di controllo qualità a una nuova ubicazione.

Per un esempio dettagliato che mostra come completare questa configurazione, vedere lo [scenario di esempio](#example-scenario) alla fine di questo argomento.

## <a name="enable-a-warehouse-for-quality-management"></a>Abilitare un magazzino per la gestione della qualità

Prima che la funzione _Gestione qualità per i processi di magazzino_ possa essere applicata per un magazzino specifico, è necessario seguire questi passaggi per rendere disponibile la funzione per quel magazzino.

1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
1. Selezionare un magazzino per abilitare la gestione della qualità.
1. Nella scheda dettaglio **Magazzino**, impostare l'opzione **Abilita ordine di controllo qualità per i processi di magazzino** su _sì_. (Nota che questa opzione può essere impostata su _Sì_ solo per i magazzini che utilizzano i processi di gestione del magazzino).

Quando l'opzione **Abilita ordine di controllo qualità per i processi di magazzino** è impostata su _Sì_, l'impostazione dell'associazione di controllo qualità controlla se la funzione _Gestione qualità per i processi di magazzino_ viene effettivamente applicata per il magazzino selezionato. È possibile modificare l'impostazione dell'opzione su _No_ in ogni momento. In tal caso, la funzione non verrà più applicata al magazzino, indipendentemente dall'impostazione dell'associazione di controllo qualità.

## <a name="quality-control"></a>Controllo qualità

La funzione _Gestione qualità per i processi di magazzino_ controlla diverse impostazioni chiave per le associazioni di controllo qualità e il campionamento degli articoli.

### <a name="quality-associations"></a>Associazioni di controllo qualità

Ogni [record di associazione di controllo qualità](enable-quality-management.md) definisce l'insieme di test, il livello di qualità accettabile (AQL) e il piano di campionamento che si applicano agli ordini di controllo qualità generati. Per impostare un record di associazione di controllo qualità, attenersi alla seguente procedura.

1. Andare a **Gestione inventario \> Impostazione \> Controllo qualità \> Associazioni di controllo qualità**.
1. Creare o selezionare la voce dell'associazione di controllo qualità per l'articolo o il gruppo utilizzato o per tutti gli articoli.
1. Nella scheda dettaglio **Condizioni**, impostare il campo **Tipo di magazzino applicabile** su uno dei seguenti valori:

    - **Gestione della qualità solo per i processi di magazzino** - Attivare la funzionalità _Gestione qualità per i processi di magazzino_. È possibile selezionare questo valore solo se il tipo di riferimento è uno dei due valori: *Acquisto* o *Produzione*.
    - **Tutti** – Disattiva la funzione _Gestione qualità per i processi di magazzino_ . Seleziona questo valore per tutti i tipi di riferimento tranne *Acquisto* e *Produzione*.

> [!NOTE]
> La funzione _Gestione qualità per i processi di magazzino_ ha effetto solo se l'articolo nella riga del documento di origine utilizza processi avanzati di gestione del magazzino e se l'opzione **Abilita ordine di controllo qualità per i processi di magazzino** è impostata su _Sì_ per il magazzino sulla riga del documento di origine.

Poiché ogni articolo viene registrato (o dichiarato come finito), il sistema determina quali associazioni di controllo qualità si applicano ad esso.

Quando la funzione _Gestione qualità per i processi di magazzino_ è attivata, il tipo di magazzino applicabile viene inserito logicamente nel quarto gruppo di ricerca della gerarchia di ricerca dell'associazione di controllo qualità. La tabella seguente fornisce una rappresentazione logica della gerarchia di ricerca.

| Gruppo di ricerca | Descrizione |
|---|---|
| Gruppo 1 | Per ogni associazione di controllo qualità, controllare i valori **Tipo di riferimento**, **Tipo di evento** e **Account esecuzione** rispetto all'elemento. Se esiste una corrispondenza con la riga del documento di origine, passare al gruppo 2. |
| Gruppo 2 | Per ogni associazione di controllo qualità, controllare il valore **Codice articolo** (_Tabella_, _Gruppo_ o _Tutti_) rispetto all'elemento. _Tabella_ è più specifico di _Gruppo_ e _Gruppo_ è più specifico di _Tutti_. Se esiste una corrispondenza per _Tabella_ (un elemento specifico), passare al gruppo 3. Se non esiste una corrispondenza per _Tabella_, cercare una corrispondenza per _Gruppo_. Se non esiste una corrispondenza per _Gruppo_, applicare _Tutti_. Se c'è una corrispondenza, passare al gruppo 3. |
| Gruppo 3 | Per ogni associazione di controllo qualità, controllare i valori **Codice conto** e **Codice risorsa** rispetto all'elemento. La logica applicata è simile alla logica applicata per il valore **Codice articolo**. |
| Gruppo 4 | Per ogni associazione di controllo qualità, controllare il valore **Tipo di magazzino applicabile** (_Gestione della qualità solo per i processi di magazzino_ o _Tutti_) rispetto all'elemento. Se l'opzione **Abilita ordine di controllo qualità per i processi di magazzino** è impostata su _Sì_ per il magazzino nel documento di origine e l'articolo nella riga del documento di origine è impostato su _Utilizzare i processi di gestione del magazzino_, per entrambe le associazioni per le quali esiste una corrispondenza _Gestione della qualità solo per i processi di magazzino_ e associazioni per le quali esiste una corrispondenza, _Tutti_ sarà applicabile in parallelo, se esistono entrambi. Se l'opzione **Gestione qualità per i processi di magazzino** è impostata su _No_ per il magazzino sul documento di origine e l'articolo nella riga del documento di origine è impostato su _Usa processi di gestione magazzino_, sarà applicabile solo la gestione della qualità. |

Ad esempio, dopo aver definito un magazzino in cui l'opzione **Abilita ordine di controllo qualità per i processi di magazzino** è impostata su _Sì_ e si hanno due associazioni di controllo qualità definite per il tipo di riferimento *Acquisti*: uno per tutti gli articoli e uno per il tipo di evento *Registrazione*. L'unica differenza tra le due associazioni di controllo qualità è il valore **Tipo di magazzino applicabile**: è impostato su _Tutti_ per un'associazione di controllo qualità e _Gestione della qualità solo per i processi di magazzino_ per l'altro. In questo caso entrambe le associazioni di controllo qualità sono ugualmente specifiche ed entrambe saranno applicabili.

Anche il valore del campo **Gruppo di test** per le associazioni di controllo qualità è un fattore. Questo campo definisce la procedura di test che deve essere applicata. Se il valore **Gruppo di test** è lo stesso per entrambe le associazioni,verrà creato un solo ordine di controllo qualità, per l'associazione di controllo qualità in cui il valore **Tipo di magazzino applicabile** è _Gestione della qualità solo per i processi di magazzino_. Se il valore **Gruppo di test** non è lo stesso per entrambe le associazioni, verranno creati due ordini di controllo qualità. Il primo ordine di controllo qualità verrà creato per l'associazione di controllo qualità in cui il valore **Tipo di magazzino applicabile** è _Gestione della qualità solo per i processi di magazzino_. Il secondo ordine di controllo qualità verrà creato per l'associazione di controllo qualità in cui il valore **Tipo di magazzino applicabile** è _Gestione della qualità solo per i processi di magazzino_.

> [!NOTE]
> Il valore _Gestione della qualità solo per i processi di magazzino_ è considerato più specifico di _Tutti_ quando i criteri per le associazioni di controllo qualità per i gruppi 1 e 2 sono gli stessi e quando il gruppo di test è lo stesso. Due ordini di controllo qualità verranno creati solo quando i gruppi di test differiscono.

#### <a name="reference-types"></a>Tipi di riferimento

Quando il valore **Tipo di riferimento** è _Acquista_ e il valore **Tipo di magazzino applicabile** è _Gestione della qualità solo per i processi di magazzino_, il campo **Tipo di evento** sulla scheda dettaglio **Processi** deve essere impostato su _Registrazione_. _Registrazione_ è l'unico tipo di evento supportato per il tipo di riferimento _Acquista_ quando si utilizza la funzionalità _Gestione qualità per i processi di magazzino_.

#### <a name="quality-processing-policy"></a>Criteri di elaborazione controllo qualità

La funzione _Gestione qualità per i processi di magazzino_ consente di creare lavoro basato solo sul campionamento degli articoli. Pertanto, consente un processo leggero. Le scorte che vengono create dipende dal campionamento degli articoli associati all'associazione di controllo qualità. Quando viene utilizzato il processo leggero, dopo che un lavoratore inserisce la quantità nell'ubicazione di controllo qualità, il reparto qualità può creare manualmente un ordine di controllo qualità, se richiesto.

Il campo **Criteri di elaborazione della qualità** nella scheda dettaglio **Processo di ordine di controllo qualità** controlla se viene creato anche un ordine di controllo qualità quando viene creato il lavoro per spostare un articolo nell'ubicazione di controllo qualità. Questo campo può essere impostato su _Crea ordine di controllo qualità_ o _Crea solo lavoro_. Il valore predefinito è _Crea ordine di controllo qualità_.

> [!NOTE]
> Indipendentemente dal fatto che si creino ordini di controllo qualità manualmente o automaticamente, il sistema genera automaticamente il lavoro per spostare gli articoli dall'ubicazione di controllo qualità quando l'ordine di controllo qualità è contrassegnato come convalidato.

La creazione del lavoro dell'ordine di controllo qualità non è correlata alla configurazione dell'associazione di controllo qualità. Se esiste un modello di lavoro che ha un valore di **Tipo di ordine di lavoro** di *Ordine di controllo qualità* e se i criteri di query sono soddisfatti per quel modello di lavoro, la convalida di un ordine di controllo qualità attiverà la creazione di un lavoro dell'ordine di controllo qualità.

#### <a name="referenced-item-sampling"></a>Campionamento degli articoli di riferimento

Ogni associazione di controllo qualità deve fare riferimento a un campione di articoli. Un campionamento di articoli definisce la quantità che verrà inviata per il controllo di qualità. Può essere impostato in modo che si applichi solo alle associazioni di controllo qualità in cui il valore **Tipo di magazzino applicabile** è _Gestione della qualità solo per i processi di magazzino_. Se il valore **Ambito di campionamento dell'articolo** per un campionamento di articoli è _Carico_ o _Spedizione_ o il valore **Specifica della quantità** è _Targa completa_, il campionamento degli articoli può essere referenziato solo da associazioni di controllo qualità in cui il valore **Tipo di magazzino applicabile** è _Gestione della qualità solo per i processi di magazzino_.

Se si definisce il campionamento di un articolo che utilizza il tipo di magazzino applicabile _Gestione della qualità solo per i processi di magazzino_, verrà visualizzato un errore se si prova a farvi riferimento da un'associazione di controllo qualità che non utilizza la funzionalità _Gestione qualità per i processi di magazzino_.

> [!NOTE]
> Il campionamento degli articoli che utilizza il blocco completo non è supportato per le associazioni di controllo qualità in cui il campo **Tipo di magazzino applicabile** è impostato su _Gestione della qualità solo per i processi di magazzino_.

### <a name="item-sampling"></a>Campionamento articoli

Il campionamento degli articoli controlla la frequenza con cui gli articoli vengono inviati per il controllo di qualità. La funzionalità _Gestione qualità per i processi di magazzino_ introduce un concetto di _ambito di campionamento dell'articolo_. Il sistema utilizza l'ambito di campionamento dell'articolo quando valuta se e come devono essere creati gli ordini di controllo qualità e/o il lavoro di campionamento degli articoli di qualità e il lavoro dell'ordine di controllo qualità.

Per impostare il campionamento degli articoli, andare a **Gestione delle scorte \> Impostazione \> Controllo di qualità \> Campionamento degli articoli** e impostare il campo **Ambito di campionamento dell'articolo** su uno dei seguenti valori:

- **Ordine** – La riga del documento di origine sarà la base per valutare se e come vengono creati gli ordini di controllo qualità e/o il lavoro di campionamento degli articoli di qualità e il lavoro dell'ordine di controllo qualità. Questo valore è il valore predefinito e quando è selezionato, il sistema funziona come quando la funzione _Gestione qualità per i processi di magazzino_ non è attivata.
- **Carico** - I carichi verranno utilizzati come base per valutare se e come viene creato un ordine e/o un lavoro di controllo qualità. Questo valore è disponibile solo quando la funzionalità _Gestione qualità per i processi di magazzino_ è attivata.
- **Spedizione** - Le spedizioni verranno utilizzate come base per valutare se e come viene creato un ordine e/o un lavoro di controllo qualità. Questo valore è disponibile solo quando la funzionalità _Gestione qualità per i processi di magazzino_ è attivata.

> [!NOTE]
> Quando il campo **Ambito di campionamento dell'articolo** è impostato su *Carico* o *Spedizione*, verranno utilizzate l'entità di carico e le entità di spedizione, se disponibili. Se non sono disponibili, verrà utilizzata l'entità ordine.

La funzionalità _Gestione qualità per i processi di magazzino_ introduce anche il valore *Targa completa* per il campo **Specifica della quantità**. Questo valore supporta la creazione del lavoro dell'ordine di controllo qualità e del lavoro di campionamento di articoli di qualità, basati su targhe. Quando si seleziona questo valore, si verificano le seguenti modifiche:

- L'opzione **Interrompi conteggio per articolo** e il campo **Ogni n targhe padre** nella scheda dettaglio **Processi** diventa disponibile.
- Il campo **Valore** nella scheda dettaglio **Quantità di campionamento** non è più disponibile.
- Le opzioni **Per quantità aggiornata**, **Posizione** e **Targa** sono tutte impostate su *Sì* e le impostazioni non possono essere modificate.

L'opzione **Interrompi conteggio per articolo** controlla se il conteggio delle targhe viene valutato per articolo o per tutti gli articoli nell'ambito di campionamento. Le varianti di prodotto sono trattate come lo stesso articolo. Questa opzione controlla anche se il conteggio delle targhe viene ripristinato per ogni articolo.

Il valore del campo **Ogni n targhe padre** controlla la frequenza con cui vengono creati gli ordini di controllo qualità in relazione al numero di articoli registrati. Ad esempio, un valore di *3* invierà ogni terzo articolo al controllo di qualità, a partire dal primo. Il valore deve essere maggiore di 0 (zero).

Mentre i lavoratori ricevono articoli utilizzando l'app per dispositivi mobili Gestione magazzino, il sistema verifica se è stata impostata un'associazione di controllo qualità per ciascun articolo in arrivo. Se viene impostata un'associazione di controllo qualità, il sistema utilizza il record di campionamento degli articoli configurato per tale associazione di controllo qualità per determinare come creerà ordini di controllo qualità, lavori di campionamento degli articoli di qualità e lavori degli ordini fornitore.

> [!NOTE]
> Quando la registrazione della ricevuta viene effettuata nel client Web (utilizzando la piccola pagina di registrazione o il il giornale di registrazione arrivi articoli per le righe dell'ordine fornitore), non verrà creato alcun lavoro di campionamento di articoli di qualità o lavoro di ordini fornitore, indipendentemente dall'impostazione. Invece, per gli articoli che corrispondono a un'associazione di controllo qualità, il campionamento degli articoli di riferimento verrà utilizzato per controllare solo la creazione di ordini di controllo qualità.

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Esempi di generazione automatica di ordini di controllo qualità

Gli esempi seguenti mostrano in che modo l'impostazione di un'associazione di controllo qualità e un campionamento degli articoli associati influiscono sulla generazione di ordini di controllo qualità quando il campo **Tipo di magazzino applicabile** è impostato su _Gestione della qualità solo per i processi di magazzino_.

Quando il valore **Specifica della quantità** è _Targa completa_, il campo **Ogni n targhe padre** controlla i campi per i quali viene creato il lavoro di campionamento degli articoli di qualità della targa. La prima targa va sempre al controllo di qualità, quindi il valore di questo campo specifica che il controllo prosegue ogni *n* targhe dopo questa targa.

Il valore **Tipo di riferimento** per i seguenti esempi è _Acquisto_ e il valore **Tipo di evento** è *Registrazione*.

| Ambito di campionamento dell'articolo | Specifica quantità | Per quantità aggiornata | Per dimensione di immagazzinamento | Suddividi conteggio per articolo | Targa per giorno specifico | Risultato |
|---|---|---|---|---|---|---|
| Ordine | Targa completa | Sì _(bloccato/non modificabile)_ | <p>Ubicazione: Sì</p><p>Targa: Sì _(bloccato/non modificabile)_</p> | Nessuno | 3 | <p>**Quantità riga ordine: 100 EA**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP1<p>Lavoro di campionamento di articoli di qualità per 20 EA</p><p>Ordine di controllo qualità 1 per 20 EA</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP2<p>Ordine fornitore per 20 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP3<p>Ordine fornitore per 20 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP4<p>Lavoro di campionamento di articoli di qualità per 20 EA</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP5<p>Ordine fornitore per 20 EA (stoccaggio)</p></li></ol> |
| Ordine | Quantità fissa: =1 | Sì | <p>Ubicazione: Sì</p><p>Targa: Sì</p> | Nessuna | Non applicabile | <p>**Quantità riga ordine: 100**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP1<p>Lavoro di campionamento di articoli di qualità per 1 EA</p><p>Ordine di controllo qualità 1 per 1 EA</p><p>Ordine fornitore per 19 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP2<p>Lavoro di campionamento di articoli di qualità per 1 EA</p><p>Ordine di controllo qualità 1 per 1 EA</p><p>Ordine fornitore per 19 (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP3<p>Lavoro di campionamento di articoli di qualità per 1 EA</p><p>Ordine di controllo qualità 1 per 1 EA</p><p>Ordine fornitore per 19 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP4<p>Lavoro di campionamento di articoli di qualità per 1 EA</p><p>Ordine di controllo qualità 1 per 1 EA</p><p>Ordine fornitore per 19 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 20 EA, LP5<p>Lavoro di campionamento di articoli di qualità per 1 EA</p><p>Ordine di controllo qualità 1 per 1 EA</p><p>Ordine fornitore per 19 EA (stoccaggio)</p></li></ol> |
| Ordine | Percentuale = 10 | Nessuna | <p>Ubicazione: No</p><p>Targa: No</p> | Nessuna | Non applicabile | <p>**Quantità riga ordine: 100 EA**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 50 EA, LP1<p>Lavoro di campionamento di articoli di qualità per 10 EA</p><p>Ordine di controllo qualità 1 per 10 EA</p><p>Ordine fornitore per 40 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 50 EA, LP2<p>Ordine fornitore per 50 EA (stoccaggio)</p></li></ol> |
| Caricamento | Percentuale = 5 | Sì _(bloccato/non modificabile)_ | <p>Ubicazione: No</p><p>Targa: No</p> | Nessuna | Non applicabile | <p>**Quantità riga ordine: 500 EA**</p><p>**Due carichi: primo carico 200 EA, secondo carico 300 EA**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per il primo carico per 100 EA<p>Lavoro di campionamento di articoli di qualità per 5 EA</p><p>Ordine di controllo qualità 1 per 5 EA</p><p>Ordine fornitore per 95 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per il primo carico per 100 EA<p>Lavoro di campionamento di articoli di qualità per 5 EA</p><p>Ordine di controllo qualità 1 per 5 EA</p><p>Ordine fornitore per 95 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per il secondo carico per 300 EA<p>Lavoro di campionamento di articoli di qualità per 15 EA</p><p>Ordine di controllo qualità 1 per 15 EA</p><p>Ordine fornitore per 285 EA (stoccaggio)</p></li></ol> |
| Ordine | Percentuale = 10 | Sì | <p>Ubicazione: Sì</p><p>Targa: Sì</p> | Nessuno | Non applicabile | <p>**Quantità riga ordine: 100**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 50 EA, LP1<p>Lavoro di campionamento di articoli di qualità per 5 EA</p><p>Ordine di controllo qualità 1 per 5 EA</p><p>Ordine fornitore per 45 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 50 EA, LP2<p>Lavoro di campionamento di articoli di qualità per 5 EA</p><p>Ordine di controllo qualità 1 per 5 EA</p><p>Ordine fornitore per 45 (stoccaggio)</p></li></ol> |
| Caricamento | Targa completa | Sì _(bloccato/non modificabile)_ | <p>Ubicazione: Sì</p><p>Targa: Sì _(bloccato/non modificabile)_</p> | Nessuna | 3 | <p>**Due articoli:**</p><ul><li>**Quantità riga ordine per l'articolo A: 120 EA (4 pallet)**</li><li>**Quantità riga ordine per l'articolo B: 90 EA (3 pallet)**</li></ul><p>**Un carico, due righe di carico con ciascuna riga ordine**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP1<p>Lavoro di campionamento di articoli di qualità per 30 EA</p><p>Ordine di controllo qualità 1 per 30 EA</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP2<p>Ordine fornitore per 30 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP3<p>Ordine fornitore per 30 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP4<p>Lavoro di campionamento di articoli di qualità per 30 EA</p><p>Ordine di controllo qualità 1 per 30 EA</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo B, 30 EA, LP5<p>Ordine fornitore per 30 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo B, 30 EA, LP6<p>Ordine fornitore per 30 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP7<p>Lavoro di campionamento di articoli di qualità per 30 EA</p><p>Ordine di controllo qualità 1 per 30 EA</p></li></ol> |
| Caricamento | Targa completa | Sì _(bloccato/non modificabile)_ | <p>Ubicazione: Sì</p><p>Targa: Sì _(bloccato/non modificabile)_</p> | Sì | 3 | <p>**Due articoli:**</p><ul><li>**Quantità riga ordine per l'articolo A: 120 EA (4 pallet)**</li><li>**Quantità riga ordine per l'articolo B: 90 EA (3 pallet)**</li></ul><p>**Un carico, due righe di carico con ciascuna riga ordine**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP1<p>Lavoro di campionamento di articoli di qualità per 30 EA</p><p>Ordine di controllo qualità 1 per 30 EA</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP2<p>Ordine fornitore per 30 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP3<p>Ordine fornitore per 30 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP4<p>Lavoro di campionamento di articoli di qualità per 30 EA</p><p>Ordine di controllo qualità 1 per 30 EA</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo B, 30 EA, LP5<p>Lavoro di campionamento di articoli di qualità per 30 EA</p><p>Ordine di controllo qualità 1 per 30 EA</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo B, 30 EA, LP6<p>Ordine fornitore per 30 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 30 EA, LP7<p>Ordine fornitore per 30 EA (stoccaggio)</p></li></ol> |
| Caricamento | Percentuale = 10 | Sì _(bloccato/non modificabile)_ | <p>Ubicazione: No</p><p>Targa: No</p> | Nessuna | Non applicabile | <p>**Quantità riga ordine: 100 EA**</p><p>**Nessun carico creato. Viene applicato l'ambito dell'ordine.**</p><ol><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 50 EA, LP1<p>Lavoro di campionamento di articoli di qualità per 5 EA</p><p>Ordine di controllo qualità 1 per 5 EA</p><p>Ordine fornitore per 45 EA (stoccaggio)</p></li><li>Registrare la ricevuta nell'app per dispositivi mobili Gestione magazzino per l'articolo A, 50 EA, LP2<p>Lavoro di campionamento di articoli di qualità per 5 EA</p><p>Ordine di controllo qualità 1 per 5 EA</p><p>Ordine fornitore per 45 EA (stoccaggio)</p></li></ol> |

Quando un lavoratore convalida uno degli ordini di controllo qualità indicati nella tabella precedente, il sistema genera automaticamente il lavoro dell'ordine di controllo qualità per spostare le scorte dall'ubicazione di controllo qualità alla posizione definita nella direttiva di ubicazione per il tipo di ordine di lavoro _Ordine di controllo qualità_. È possibile impostare qualsiasi posizione per questo scopo, ad esempio un'ubicazione di reso o magazzino, a seconda del risultato del test per l'ordine di controllo qualità. Per un esempio di questa configurazione, consultare lo [scenario di esempio](#example-scenario) alla fine di questo argomento.

È possibile riaprire un ordine di controllo qualità che è già stato convalidato, a condizione che il lavoro dell'ordine di controllo qualità correlato allo spostamento delle scorte dall'ubicazione di controllo di qualità non abbia il valore **Stato del lavoro** su *Chiuso* o *In corso*.

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>Analisi del processo quando coesistono più associazioni di controllo qualità

È possibile definire e applicare più di una associazione di controllo qualità per la stessa riga del documento di origine e il campo **Tipo di magazzino applicabile** può essere impostato su _Gestione della qualità solo per i processi di magazzino_ per alcune associazioni di controllo qualità e su _Tutti_ per le restanti.

Nel seguente esempio, il valore **Tipo di riferimento** è _Acquisto_.

1. La prima associazione di controllo qualità è impostata nel modo seguente:

    - **Tipo di magazzino applicabile:** *Gestione della qualità solo per i processi di magazzino*
    - **Codice articolo:** *A0001*
    - **Codice conto:** *Tutti*
    - **Gruppo di test:** *Sistemi di chiusura*
    - **Campionamento articoli:** *5 pezzi*

1. La seconda associazione di controllo qualità è impostata nel modo seguente:

    - **Tipo di magazzino applicabile:** *Tutti*
    - **Codice articolo:** *Tutti*
    - **Codice conto:** *Tutti*
    - **Gruppo di test:** *Sistemi di chiusura*
    - **Campionamento articoli:** *1 pezzo*

1. La terza associazione di controllo qualità è impostata nel modo seguente:

    - **Tipo di magazzino applicabile:** *Gestione della qualità solo per i processi di magazzino*
    - **Codice articolo:** *Tutti*
    - **Codice conto:** *104*
    - **Gruppo di test:** *Impedenza*
    - **Campionamento articoli:** *Ogni seconda targa* (Questa impostazione indica che la prima, la terza, la quinta targa ricevuta e così via, genereranno un ordine di controllo qualità).

1. La quarta associazione di controllo qualità è impostata nel modo seguente:

    - **Tipo di magazzino applicabile:** *Tutti*
    - **Codice articolo:** *Tutti*
    - **Codice conto:** *Tutti*
    - **Gruppo di test:** *Impedenza*
    - **Campionamento articoli:** *5 pezzi*

1. La quinta associazione di controllo qualità è impostata nel modo seguente:

    - **Tipo di magazzino applicabile:** *Tutti*
    - **Codice articolo:** *Tutti*
    - **Codice conto:** *Tutti*
    - **Gruppo di test:** *Cono*
    - **Campionamento articoli:** *10%*

Un ordine fornitore per una quantità di 10 dell'articolo A0001 viene ora creato per il fornitore 104. Quindi una riga ordine fornitore che ha una quantità di 10 verrà registrata come ricevuta su una targa utilizzando l'app per dispositivi mobili Gestione magazzino. Questa è la formula:

- C'è un ordine di controllo qualità dalla prima associazione di controllo qualità per il gruppo di test *Sistemi di chiusura*. La quantità è 5. Non è previsto un ordine di controllo qualità dalla seconda associazione di controllo qualità, poiché i criteri per la prima associazione di controllo qualità sono più specifici rispetto al gruppo di test *Sistemi di chiusura*.
- C'è un ordine di controllo qualità per la terza associazione di controllo qualità per il gruppo di test *Impedenza*. La quantità è 10. Non è previsto un ordine di controllo qualità dalla quarta associazione di controllo qualità, poiché i criteri per la prima associazione di controllo qualità sono più specifici rispetto al gruppo di test *Impedenza*.
- C'è un ordine di controllo qualità per la quinta associazione di controllo qualità per il gruppo di test *Cono*. La quantità è 1.

Relativamente alla creazione di un ordine di controllo qualità per ciascuna delle tre associazioni di controllo qualità, verrà creato inoltre un lavoro di campionamento degli articoli di qualità. La quantità registrata è solo 10. Tuttavia, a causa dell'impostazione del campionamento degli articoli, la somma delle quantità degli ordini di controllo qualità create per il tipo di magazzino applicabile *Gestione della qualità solo per i processi di magazzino* è 16, che supera la quantità fisica registrata di 10. Pertanto, il lavoro non verrà creato per le quantità dell'ordine di controllo qualità totale (16), poiché solo 10 sono fisicamente disponibili per lo spostamento nell'ubicazione di controllo qualità. La priorità utilizzata per creare il lavoro di campionamento degli articoli di qualità segue l'ordine di creazione dell'ordine di controllo qualità:

- **Primo ordine di controllo qualità (quantità = 5):** Il lavoro di campionamento degli articoli di qualità è stato creato per 5. Una quantità di 5 (10 - 5) resta disponibile per la successiva creazione di lavori di campionamento di articoli di qualità.
- **Secondo ordine di controllo qualità (quantità = 10):** Il lavoro di campionamento degli articoli di qualità è stato creato per 5. Una quantità di 0 (zero) resta disponibile per la successiva creazione di lavori di campionamento di articoli di qualità.
- **Terzo ordine di controllo qualità (quantità = 1):** Non viene creato alcun lavoro di campionamento degli articoli di qualità.

Come parte del processo di creazione degli ordini di controllo qualità, viene creato un blocco scorte con la quantità 10. Questo blocco scorte fa riferimento a ciascuno dei tre ordini di controllo qualità. La somma delle quantità dell'ordine di controllo qualità è 16.

Quando gli ordini di controllo qualità vengono convalidati, il sistema tenta di creare un lavoro dell'ordine di controllo qualità per ciascun ordine di controllo qualità convalidato. Poiché la somma delle quantità degli ordini di controllo qualità supera la quantità effettivamente bloccata e quindi disponibile per la creazione di lavoro, non è possibile creare il lavoro dell'ordine di controllo qualità per le quantità di ordini di controllo qualità complete, come mostrato di seguito. (Questo esempio continua l'esempio precedente).

1. **Convalidare il secondo ordine di controllo qualità creato (quantità = 10). Il lavoro dell'ordine di controllo qualità viene creato per una quantità di 4.**

    La creazione del lavoro dell'ordine di controllo qualità è attivata da una modifica della quantità del blocco scorte. Poiché la somma delle quantità di ordini di controllo qualità era 16, la convalida di una quantità di 10 comporterà la convalida delle quantità di ordini di controllo qualità rimanenti pari a 6. La quantità di blocco delle scorte viene ridotta da 10 a 6. La quantità ridotta di 4 è assegnata alla creazione del lavoro dell'ordine di controllo qualità.

2. **Convalidare il primo ordine di controllo qualità creato (quantità = 5). Il lavoro dell'ordine di controllo qualità viene creato per una quantità di 5.**

    La creazione del lavoro dell'ordine di controllo qualità è attivata da una modifica della quantità del blocco scorte. Poiché la somma delle quantità di ordini di controllo qualità era 6, la convalida di una quantità di 5 comporterà la convalida delle quantità di ordini di controllo qualità rimanenti pari a 1. La quantità di blocco delle scorte viene ridotta da 6 a 1. La quantità ridotta di 5 è assegnata alla creazione del lavoro dell'ordine di controllo qualità.

3. **Convalidare il terzo ordine di controllo qualità creato (quantità = 1). Il lavoro dell'ordine di controllo qualità viene creato per una quantità di 1.**

    La creazione del lavoro dell'ordine di controllo qualità è attivata da una modifica della quantità del blocco scorte. Poiché la somma delle quantità di ordini di controllo qualità era 1, la convalida di una quantità di 1 comporterà la convalida delle quantità di ordini di controllo qualità rimanenti pari a 0 (zero). Il blocco scorte viene rimosso (ovvero, la quantità di blocco scorte viene ridotta da 1 a 0). La quantità ridotta di 1 è assegnata alla creazione del lavoro dell'ordine di controllo qualità.

> [!NOTE]
> La creazione del lavoro dell'ordine di controllo qualità dipende dalla quantità del blocco scorte a cui fa riferimento uno o più ordini di controllo qualità. Se la somma delle quantità degli ordini di controllo qualità supera la quantità del blocco scorte di riferimento, l'ordine in cui vengono convalidati gli ordini di controllo qualità determina la creazione del lavoro dell'ordine di controllo qualità.

## <a name="canceling-quality-item-sampling-work"></a>Annullamento del lavoro di campionamento degli articoli di qualità

È possibile annullare il lavoro creato per il campionamento di articoli di qualità. Per controllare cosa si verifica quando questo lavoro viene annullato, attenersi alla seguente procedura.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Generale**, nella scheda dettaglio **Lavoro**, impostare l'opzione **Annulla registrazione entrata quando si annulla il lavoro** per uno dei seguenti valori:

    - **Sì** - Quando il lavoro di campionamento degli articoli di qualità viene annullato, l'ordine di controllo qualità associato viene eliminato e le scorte non vengono registrate.
    - **No** - Quando il lavoro di campionamento degli articoli di qualità viene annullato, l'ordine di controllo qualità associato non viene eliminato e le scorte non vengono registrate.

## <a name="cross-docking"></a>Cross-docking

È possibile avere un'impostazione dell'associazione di controllo qualità che crea il lavoro di campionamento degli articoli. Tuttavia, quando il cross-docking esiste in parallelo con un'associazione di controllo qualità che crea un lavoro di campionamento degli articoli di qualità, se è presente solo la quantità sufficiente per soddisfare il cross-docking, viene creato solo il lavoro di campionamento degli articoli. Nei casi in cui l'opzione **Abilita ordine di controllo qualità per i processi di magazzino** è impostata su _Sì_ per il magazzino ricevente e il campo **Tipo di magazzino applicabile** è impostato su _Gestione della qualità solo per i processi di magazzino_ per un'associazione di controllo qualità, la creazione di lavori di campionamento di articoli di qualità ha la precedenza sulla creazione di lavori cross-dock. Se la quantità supera il requisito per il cross-docking, il sistema si limiterà a creare comunque il lavoro di campionamento degli articoli.

## <a name="destructive-testing"></a>Test distruttivo

È possibile definire un gruppo di test che crea test distruttivi. Nel caso di un test distruttivo, si presume che, indipendentemente dal risultato del test, la quantità dell'articolo testato verrà distrutta come parte del test. Il modo in cui la funzionalità _Gestione qualità per i processi di magazzino_ supporta i test distruttivi assomiglia al modo in cui la gestione della qualità li supporta quando la funzionalità non è attivata. Prima di poter convalidare l'ordine di controllo qualità, il responsabile del controllo qualità deve specificare l'ubicazione di prelievo per la quantità che è stata distrutta. È possibile registrare il prelievo dalla pagina dell'ordine controllo qualità selezionando **Scorte \> Prelievo** nel riquadro azioni. Dopo che il prelievo per la quantità dell'ordine di controllo qualità è stata registrata, la convalida può essere completata.

## <a name="example-scenario"></a>Scenario di esempio

### <a name="prepare-the-scenario"></a>Preparare lo scenario

Per eseguire questo scenario, è necessario preparare il sistema nel modo seguente:

- Assicurarsi che i dati dimostrativi siano installati nel sistema e selezionare la persona giuridica **USMF**.
- Attivare la funzionalità _Gestione qualità per i processi di magazzino_ in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configurare il magazzino 51 per utilizzare la funzionalità _Gestione qualità per i processi di magazzino_ seguendo i seguenti passaggi:

    1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
    1. Selezionare magazzino 51.
    1. Nella scheda dettaglio **Magazzino**, impostare l'opzione **Abilita ordine di controllo qualità per i processi di magazzino** su *Sì*.

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>Impostazione della qualità - Passare all'ubicazione di controllo della qualità

È ora necessario preparare una configurazione di base che consenta al sistema di supportare la funzionalità _Gestione qualità per i processi di magazzino_ per il magazzino 51. (I dati dimostrativi definiscono un percorso di gestione della qualità denominato *QMS*. A tale ubicazione viene fatto riferimento più volte in questo scenario). È necessario preparare i seguenti elementi, come descritto nelle sottosezioni di questa sezione:

- Classe lavoro
- Modello di lavoro
- Direttiva ubicazione
- Campionamento articoli
- Associazioni di controllo qualità
- Voci di menu del dispositivo mobile

#### <a name="work-class-for-quality-in"></a>Classe di lavoro per la qualità

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.
1. Creare una classe di lavoro e impostare i seguenti valori:

    - **ID classe lavoro:** _QualityIn_
    - **Descrizione:** _Campionamento di articoli di qualità_
    - **Tipo ordine di lavoro:** _Campionamento articoli di qualità_

#### <a name="work-template"></a>Modello di lavoro

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Impostare il campo **Tipo ordine di lavoro** su _Campionamento di articoli di qualità_.
1. Creare un modello di lavoro e impostare i seguenti valori:

    - **Modello di lavoro:** _51 Qualità_
    - **Descrizione modello di lavoro:** _51 Qualità_

1. Aggiungere una riga al modello di lavoro e impostare i seguenti valori:

    - **Tipo di lavoro:** _Prelievo_
    - **ID classe lavoro:** _QualityIn_

1. Aggiungere una seconda riga al modello di lavoro e impostare i seguenti valori:

    - **Tipo di lavoro:** _Stoccaggio_
    - **ID classe lavoro:** _QualityIn_

#### <a name="location-directive"></a>Direttiva ubicazione

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Impostare il campo **Tipo ordine di lavoro** su _Campionamento di articoli di qualità_.
1. Creare una direttiva di ubicazione e impostare i seguenti valori:

    - **Nome:** _51 alla qualità_
    - **Tipo di lavoro:** _Stoccaggio_
    - **Sito:** 5
    - **Magazzino:** _51_

1. Aggiungere una riga alla direttiva di ubicazione e impostare i seguenti valori:

    - **Da quantità:** _1_
    - **A quantità:** _1000000_

1. Creare una azione di direttiva di ubicazione e impostare il seguente valore

    - **Nome:** _Qualità_

1. Per l' azione della direttiva di ubicazione, selezionare **Modifica query** e specificare il record **Gamma** il quale ha i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Campo:** _ID profilo ubicazione_
    - **Criteri:** *QMS*

1. Selezionare **OK** per salvare la query e salvare la nuova direttiva di ubicazione.

Successivamente, è necessario modificare la sequenza delle direttive di ubicazione dell'ordine fornitore esistenti per il magazzino 51. I dati dimostrativi includono due direttive di ubicazione che hanno un tipo di ordine **Tipo ordine di lavoro** valore di _Acquisto_: uno è nominato _51 QMS_ e l'altro _51 PO Diretto_. Per garantire che la funzionalità *Gestione qualità per i processi di magazzino* venga applicata per il magazzino 51, è necessario assicurarsi che la direttiva di ubicazione _51 QMS_ non venga applicata. Tuttavia, invece di eliminare tale direttiva di ubicazione (poiché potrebbe essere utilizzata in futuro), è possibile semplicemente cambiare la sequenza.

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Impostare il campo **Tipo ordine di lavoro** su _Ordine fornitore_.
1. Nell'elenco delle sequenze, selezionare la sequenza numero 5, per la direttiva di ubicazione _51 PO Diretto_.
1. Spostare la sequenza selezionata fino al numero di sequenza 4.
1. Verificare che il numero di sequenza della direttiva di ubicazione _51 QMS_ sia almeno 5.

#### <a name="item-sampling"></a>Campionamento articoli

La funzionalità _Gestione qualità per i processi di magazzino_ aggiunge alcune nuove funzionalità di campionamento degli articoli. Il valore **Ambito di campionamento dell'articolo** ora può essere _Ordine_, _Spedizione_ o _Carico_ e il valore **Quantità di campionamento** ora può essere _Targa completa_.

1. Fare clic su **Gestione scorte \> Impostazioni \> Controllo qualità \> Campionamento articoli**.
1. Creare un record di campionamento degli articoli e impostare i seguenti valori:

    - **Campionamento articoli:** _3rd LP_
    - **Descrizione:** _Ogni terza targa_
    - **Ambito di campionamento dell'articolo:** _Ordine_

1. Nella scheda dettaglio **Quantità di campionamento**, impostare il campo **Specifica della quantità** a _Targa completa_.
1. Nella scheda dettaglio **Processi**, impostare il campo **Ogni n targhe padre** a _3_.
1. Nella sezione **Dimensione di immagazzinamento**, abilitare **Magazzino** e **Stato inventario**.

#### <a name="quality-associations"></a>Associazioni di controllo qualità

Creare un'associazione di controllo qualità che utilizzerà il nuovo campionamento degli articoli.

1. Andare a **Gestione inventario \> Impostazione \> Controllo qualità \> Associazioni di controllo qualità**.
1. Creare un record di associazione di controllo qualità e impostare i seguenti valori:

    - **Tipo di riferimento:** _Acquisto_
    - **Codice articolo:** _Tabella_
    - **Articolo:** _M9201_
    - **Sito:** _5_

1. Nella scheda dettaglio **Processo**, impostare il campo **Tipo di evento** su *Registrazione*.
1. Nella scheda dettaglio **Condizioni**, impostare il campo **Tipo di magazzino applicabile** su *Gestione della qualità solo per i processi di magazzino*.
1. Nella scheda dettaglio **Processo di ordine di controllo qualità**, impostare il campo **Criteri di elaborazione della qualità** su _Crea ordine di controllo qualità_.
1. Nella scheda dettaglio **Specifiche**, fare clic con il tasto destro del mouse sul campo **Gruppo di test**, quindi selezionare **Visualizza dettagli** per aprire la pagina **Gruppi di test**.
1. Nella pagina **Gruppi di test**, nella scheda **Panoramica** della griglia superiore, creare un gruppo di test e impostare i seguenti valori:

    - **Gruppo di test:** _QMS_
    - **Descrizione:** _Gruppo di test QMS_
    - **Quantità accettabile:** _100_
    - **Campionamento articoli:** _3rd LP_ (Selezionare)

1. Nella scheda **Panoramica** della griglia inferiore, aggiungere un record per un test e impostare i seguenti valori:

    - **Sequenza:** *1*
    - **Test:** *Misurazione sistemi di chiusura*

1. Nella scheda **Test** della griglia inferiore, impostare i seguenti valori:

    - **Variabili di test:** *Positivo/Negativo*
    - **Risultato predefinito:** *Positivo*

1. Salvare il nuovo gruppo di test e chiudere la pagina **Gruppi di test**.
1. Tornando alla pagina **Associazioni di controllo qualità**, nel campo **Gruppo di prova**, selezionare **QMS**.
1. Salvare il record.

#### <a name="mobile-device-menu-items-for-quality-in"></a>Voci di menu del dispositivo mobile per la qualità

Per completare l'installazione per spostare le merci nell'ubicazione di controllo qualità, è necessario rendere disponibile il campionamento degli articoli di qualità da una voce di menu del dispositivo mobile.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Selezionare la voce **Stoccaggio dell'ordine fornitore** del menu del dispositivo mobile.
1. Nella scheda dettaglio **Classi lavoro**, aggiungere l'ID classe di lavoro *QualityIn*.

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>Riepilogo: impostazione per spostare le merci al controllo di qualità completata

È ora definita un'associazione di controllo qualità che utilizza la funzionalità *Gestione qualità per i processi di magazzino* per attivare la creazione di un ordine di controllo qualità. Sono stati impostati i dati di lavoro e ubicazione per il magazzino 51 per garantire che venga creato un lavoro specifico al momento della registrazione dell'acquisto per l'articolo M9201. Questa configurazione garantisce che ogni terza targa registrata venga spostata in una posizione di qualità (_QMS_) e che verrà creato un ordine di controllo qualità equivalente al quantitativo di targhe. Il restante verrà spostato in un luogo di stoccaggio anziché nell'ubicazione di controllo qualità.

### <a name="process-quality-management-work"></a>Processi di gestione controllo qualità

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Creare un ordine fornitore e impostare i seguenti valori:

    - **Conto specifico del fornitore:** *104*
    - **Magazzino:** *51*

1. Aggiungere una riga ordine fornitore e impostare i seguenti valori:

    - **Articolo:** *M9201*
    - **Quantità:** *20*
    - **UoM:** *ea*
    - **Magazzino:** *51*

1. Annotare il numero dell'ordine fornitore, in modo da poterlo utilizzare in seguito.
1. Passare a un dispositivo mobile o un emulatore che esegue l'app per dispositivi mobili Gestione magazzino e accedere al magazzino 51 utilizzando *51* come ID utente e *1* come password.
1. Andare a **In entrata \> Entrata acquista** e inserire i seguenti valori:

    - **Numero ordine fornitore:** il numero dell'ordine fornitore appena creato
    - **Qtà:** *5*
    - **Unità:** *ea*

1. Continuare a ricevere contro la linea, *5 ea* alla volta, fino a quando la linea non viene completamente ricevuta. (Verranno create in totale quattro targhe).
1. Disconnetti l'app per dispositivi mobili Gestione magazzino.
1. Tornare nel client Web, andare a **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Trovare ed aprire l'ordine fornitore.
1. Nella sezione **Righe ordine fornitore**, selezionare la riga per il numero di articolo *M9201*, quindi selezionare **Righe ordine fornitore \> Dettagli lavoro**.
1. Si noti che la seconda e la terza intestazione di lavoro che sono state create sono normali lavori di stoccaggio, mentre la prima e la quarta intestazione di lavoro sono lavori di campionamento di articoli di controllo qualità. Questo risultato è coerente con la configurazione di campionamento degli articoli, configurata per campionare ogni terza targa.

#### <a name="move-to-the-quality-control-location"></a>Passare all'ubicazione di controllo qualità

Ora sarà possibile spostare le targhe nelle ubicazioni designate. La prima e la quarta targa andranno nell'ubicazione di controllo della qualità, mentre la seconda e la terza targa andranno direttamente in magazzino.

1. Passare a un dispositivo mobile o un emulatore che esegue l'app per dispositivi mobili Gestione magazzino e accedere al magazzino 51 utilizzando *51* come ID utente e *1* come password.
1. Andare a **In entrata \> Stoccaggio acquisti** e stoccare ogni targa dalla procedura precedente fino a quando non si è chiuso tutto il lavoro.

#### <a name="summary-process-quality-management-work"></a>Sommario: Processo del lavoro di gestione qualità

Si è eseguito il lavoro di campionamento degli articoli di qualità per la prima e la quarta targa spostandole nell'ubicazione di controllo della qualità. È stata stoccata anche la seconda e la terza targa. Il prossimo passo consiste nell'esecuzione del test e nel controllo degli ordini di controllo qualità.

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>Impostazione della qualità: passare dall'ubicazione di controllo della qualità al magazzino o al reso

Quando i lavoratori riportano i risultati degli ordini di controllo qualità, il sistema genera automaticamente il lavoro.

Ora sarà possibile proseguire con la configurazione di base richiesta della classe di lavoro, del modello di lavoro e della direttiva di ubicazione per abilitare la gestione della qualità per i processi di magazzino, in modo che il lavoro richiesto possa essere creato per spostare la quantità dell'ordine di controllo qualità dall'ubicazione di controllo qualità a un'ubicazione designata del magazzino.

#### <a name="work-class-for-quality-out"></a>Classe di lavoro per la qualità

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.
1. Creare una classe di lavoro e impostare i seguenti valori:

    - **ID classe lavoro:** *QualityOut*
    - **Descrizione:** *Qualità*
    - **Tipo di ordine di lavoro:** *Ordine di controllo qualità*

#### <a name="work-templates"></a>Modelli di lavoro

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Cambiare il valore **Tipo di ordine di lavoro** a *Ordine di controllo qualità*.
1. Creare un modello di lavoro e impostare i seguenti valori:

    - **Modello di lavoro:** *51 Qualità*
    - **Descrizione modello di lavoro:** *51 qualità*

1. Aggiungere una riga e impostare i seguenti valori:

    - **Tipo di lavoro:** *Prelevare*
    - **ID classe lavoro:** **QualityOut**

1. Aggiungere una seconda riga e impostare i seguenti valori:

    - **Tipo di lavoro:** *Inserire*
    - **ID classe lavoro:** *QualityOut*

#### <a name="location-directives"></a>Direttive ubicazione

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Cambiare il valore **Tipo di ordine di lavoro** a *Ordine di controllo qualità*.
1. Creare una direttiva di ubicazione e impostare i seguenti valori:

    - **Nome:** *51 Pass*
    - **Tipo di lavoro:** *Inserire*
    - **Sito:** *5*
    - **Magazzino:** *51*

1. Nel riquadro azioni, selezionare **Modificare query** per aprire la finestra di dialogo dell'editor di query.
1. Nella scheda **Gamma**, impostare i seguenti valori:

    - **Tabella:** *Ordini di controllo qualità*
    - **Campo:** *Stato*
    - **Criteri:** *Trasferire*

1. Selezionare **OK** per salvare la query e chiudere finestra dialogo.
1. Nella scheda dettaglio **Righe**, aggiungere una riga e impostare i seguenti valori:

    - **Da quantità:** *1*
    - **A quantità:** *1000000*

1. Nella scheda dettaglio **Azioni direttiva di ubicazione**, aggiungere una riga e impostare il seguente valore:

    - **Nome:** *Pass*

1. Nella scheda dettaglio **Azioni direttiva di ubicazione**, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query
1. Nella scheda **Gamma**, impostare i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Campo:** *ID zona*
    - **Criteri:** *Blocco*

1. Selezionare **OK** per salvare la query e chiudere finestra dialogo.
1. Nel riquadro azioni, selezionare **Salva** per salvare la nuova direttiva di ubicazione.
1. Creare una seconda direttiva di ubicazione e impostare i seguenti valori:

    - **Nome:** *51 Errore*
    - **Tipo di lavoro:** *Inserire*
    - **Sito:** *5*
    - **Magazzino:** *51*

1. Nel riquadro azioni, selezionare **Modificare query** per aprire la finestra di dialogo dell'editor di query.
1. Nella scheda **Gamma**, impostare i seguenti valori:

    - **Tabella:** *Ordini di controllo qualità*
    - **Campo:** *Stato*
    - **Criteri:** *Errore*

1. Selezionare **OK** per salvare la query e chiudere finestra dialogo.
1. Nella scheda dettaglio **Righe**, aggiungere una riga e impostare i seguenti valori:

    - **Da quantità:** *1*
    - **A quantità:** *1000000*

1. Nella scheda dettaglio **Azioni direttiva di ubicazione**, aggiungere una riga e impostare il seguente valore:

    - **Nome:** *Errore*

1. Nella scheda dettaglio **Azioni direttiva di ubicazione**, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query
1. Nella scheda **Gamma**, impostare i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Campo:** *ID zona*
    - **Criteri:** *Reso*

1. Selezionare **OK** per salvare la query e chiudere finestra dialogo.
1. Nel riquadro azioni, selezionare **Salva** per salvare la nuova direttiva di ubicazione.

#### <a name="mobile-device-menu-items-for-quality-out"></a>Voci di menu del dispositivo mobile per la qualità

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Selezionare la voce **Stoccaggio QMS** del menu del dispositivo mobile.
1. Nella scheda dettaglio **Classi lavoro**, aggiungere l'ID classe di lavoro *QualityPut*.

Gli addetti al magazzino saranno ora in grado di prelevare il lavoro dell'ordine di controllo qualità utilizzando la voce di menu **Stoccaggio QMS**. I beni che non hanno superato il controllo qualità possono essere collocati in un ubicazione di reso mentre i beni che hanno superato il controllo qualità possono essere collocati nell'ubicazione bulk-001.

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>Riepilogo: Impostazione per spostare i beni dal controllo di qualità

Sono stati impostati i dati di lavoro e ubicazione per il magazzino 51, per garantire che il lavoro venga creato automaticamente al completamento degli ordini di controllo qualità. Questa configurazione garantisce che ogni targa controllo di qualità sia spostata in un'ubicazione di blocco o in un'ubicazione di reso.

### <a name="process-quality-management-work"></a>Processi di gestione controllo qualità

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.
1. Selezionare il primo ordine di controllo qualità per le quantità registrate.
1. Selezionare **Convalida**. Lo stato del test verrà aggiornato in *Errore*.
1. Andare a **Gestione magazzino \> Tutti i lavori**.
1. Aprire il lavoro appena creato e osservare che il valore **Tipo di ordine di lavoro** è *Ordine di controllo qualità*. Il lavoro include una riga dove l'ubicazione di stoccaggio è *Reso* e lo stato è *Errore*. (Se lo stato dell'ordine di controllo qualità fosse *Superato*, l'ubicazione di stoccaggio sarebbe *Blocco*).
1. Tornare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.
1. Selezionare il secondo ordine di controllo qualità dalle quantità registrate.
1. Selezionare **Risultati** nella griglia inferiore. Aggiornare il valore **Quantità risultante** su *5* e verificare che il valore **Risultato test** venga cambiato in un segno di spunta.
1. Selezionare **Salva**, quindi chiudere la pagina.
1. Tornando alla pagina **Ordini di qualità**, selezionare **Convalida** ed effettuare la convalida. Lo stato viene aggiornato in *Superato*.

    > [!NOTE]
    > L'evento di convalida attiva la creazione del lavoro dell'ordine di controllo qualità per spostare la quantità dall'ubicazione di controllo qualità a una nuova ubicazione.

1. Andare a **Gestione magazzino \> Tutti i lavori**.
1. Selezionare il lavoro appena creato e osservare che una seconda intestazione del lavoro dell'ordine di controllo qualità è stata creata, dove l'ubicazione di stoccaggio è *BULK-001*.
1. Passare a un dispositivo mobile o un emulatore che esegue l'app per dispositivi mobili Gestione magazzino e accedere al magazzino 51 utilizzando *51* come ID utente e *1* come password.
1. Andare a **Qualità \> Stoccaggio da QMS** ed elaborare ciascuna delle due targhe relative a entrambi i pezzi di lavoro, in modo da chiudere tutti i lavori.

> [!NOTE]
> Prendere in considerazione l'aggiunta della voce di qualità a una voce di menu di un dispositivo mobile in cui si trova il codice attività *Visualizza elenco lavori aperti*. Per un esempio, vedere la voce di menu del dispositivo mobile denominata **Elenco di lavoro** nei dati dimostrativi. Per prima cosa aggiungere la classe di lavoro *Ordine di controllo qualità* a una voce di menu definita dall'utente, poiché questa classe di lavoro è necessaria per visualizzare il lavoro nell'elenco di lavoro. Quindi aggiungere la classe *Ordine di controllo qualità* alla voce del menu **Elenco di lavoro**. Gli utenti che hanno accesso all'elenco di lavoro potranno quindi selezionare ed elaborare il lavoro generato automaticamente dalla convalida dell'ordine di controllo qualità.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sulla gestione della qualità e della non conformità](quality-management-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]