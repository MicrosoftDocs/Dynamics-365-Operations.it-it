---
title: Utilizzare le direttive di ubicazione
description: Questo argomento descrive come utilizzare le direttive di ubicazione. Le direttive ubicazione sono regole definite dall'utente che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte.
author: Mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84821fe4e7c5054b2121dbd7f9e536c80080b978
ms.sourcegitcommit: 1f23adbc6c7e6f9ffe8c48c10659b9fae2155aeb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470521"
---
# <a name="work-with-location-directives"></a>Utilizzare le direttive di ubicazione

[!include [banner](../includes/banner.md)]

Le direttive ubicazione sono regole che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte. Ad esempio, in una transazione dell'ordine cliente, la direttiva ubicazione determina il punto di prelievo e il punto di stoccaggio degli articoli. Le direttive di ubicazione sono costituite da un'intestazione e dalle righe associate. Vengono create per *tipi di ordini di lavoro* specifici.

> [!NOTE]
> Questo argomento si applica alle funzionalità nel modulo **Gestione magazzino**. Non viene applicato alle funzionalità nel modulo [Gestione inventario](../inventory/inventory-home-page.md).

È possibile utilizzare le direttive ubicazione per effettuare le seguenti attività:

- Stoccare gli articoli in arrivo.
- Prelevare e stoccare gli articoli per le transazioni in uscita.
- Prelevare e stoccare le materie prime per la produzione.
- Rifornire le ubicazioni.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter creare una direttiva di ubicazione, è necessario seguire questi passaggi per assicurarsi che i prerequisiti siano presenti.

1. Verificare che la chiave di licenza richiesta sia attivata. Andare a **Amministrazione sistema \> Imposta \> Configurazione licenza**, espandere la chiave di licenza **Commercio**, quindi selezionare la chiave di configurazione **Gestione magazzino e trasporto**. Si noti che per questo passaggio è necessario l'accesso come amministratore.
1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
1. Creare un magazzino.
1. Nella scheda **Magazzino**, impostare l'opzione **Usa processi di gestione magazzino** su *Sì*.
1. Creare le ubicazioni, i tipi di ubicazione, i profili e i formati delle ubicazioni. Per ulteriori informazioni, vedere [Configurare le ubicazioni in un magazzino abilitato WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Creare siti, zone e gruppi di zone. Per ulteriori informazioni, vedere [Impostare un magazzino](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) e [Configurare le ubicazioni in un magazzino abilitato WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="work-order-types-for-location-directives"></a>Tipi di ordine di lavoro per direttive di ubicazione

Molti campi che possono essere impostati per le direttive di ubicazione sono comuni a tutti i tipi di ordine di lavoro. Tuttavia, altri campi sono specifici per particolari tipi di ordini di lavoro.

![Tipi di ordine di lavoro direttive di ubicazione](media/Location_Directives_Work_Order_Types.png "Tipi di ordine di lavoro direttive di ubicazione")

> [!NOTE]
> Due tipi di ordini di lavoro, *Lavoro annullato* e *Conteggio ciclo*, vengono utilizzati solo dal sistema. Non è possibile creare direttive di ubicazione per questi tipi di ordini di lavoro.

Le tabelle nelle sottosezioni seguenti elencano i campi comuni e specifici del tipo di ordine di lavoro disponibili quando si imposta una direttiva di ubicazione.

### <a name="fields-that-are-common-to-all-work-order-types"></a>Campi comuni a tutti i tipi di ordine di lavoro

La tabella seguente elenca i campi comuni a tutti i tipi di ordine di lavoro.

| Scheda dettaglio | Campo |
|---|---|
| Direttive ubicazione | Tipo di lavoro |
| Direttive ubicazione | Sito |
| Direttive ubicazione | Magazzino |
| Direttive ubicazione | Codice direttiva |
| Direttive ubicazione | Più SKU |
| Righe | Numero progressivo |
| Righe | Da quantità |
| Righe | A quantità |
| Righe | Unità |
| Righe | Trova quantità |
| Righe | Limita per unità |
| Righe | Arrotonda a unità |
| Righe | Individua quantità di imballaggio |
| Righe | Consenti divisione |
| Azioni direttiva ubicazione | Numero progressivo |
| Azioni direttiva ubicazione | Nome |
| Azioni direttiva ubicazione | Utilizzo ubicazioni fisse |
| Azioni direttiva ubicazione | Consenti inventario negativo |
| Azioni direttiva ubicazione | Batch abilitato |
| Azioni direttiva ubicazione | Strategia |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>Campi specifici per tutti i tipi di ordine di lavoro

La tabella seguente elenca i campi specifici per i tipi di ordine di lavoro particolari.

| Scheda dettaglio | Campo | Tipo ordine di lavoro |
|---|---|---|
| Direttive ubicazione | Individua per | Ordine fornitore |
| Direttive ubicazione | Codice smaltimento applicabile | Ordine fornitore |
| Direttive ubicazione | Codice smaltimento | Ordine fornitore |
| Direttive ubicazione | Codice smaltimento applicabile | Stoccaggio prodotti finiti |
| Direttive ubicazione | Codice smaltimento | Stoccaggio prodotti finiti |
| Direttive ubicazione | Codice smaltimento applicabile | Ordini di reso |
| Direttive ubicazione | Codice smaltimento | Ordini di reso |
| Direttive ubicazione | Codice smaltimento applicabile | Stoccaggio kanban |
| Direttive ubicazione | Codice smaltimento applicabile | Prelievo kanban |
| Righe | Modello per il rifornimento immediato | Gestione ordini cliente |
| Righe | Modello per il rifornimento immediato | Prelievo materie prime |
| Righe | Modello per il rifornimento immediato | Uscita di trasferimento |
| Righe | Modello per il rifornimento immediato | Prelievo kanban |

## <a name="open-the-location-directives-page"></a>Aprire la pagina Direttive ubicazione

Per aprire la pagina **Direttive ubicazione** andare a **Gestione magazzino \> Imposta \> Direttive ubicazione**.

In questo punto è possibile visualizzare, creare e modificare le direttive di ubicazione utilizzando i comandi nel riquadro azioni. Vedere le sezioni rimanenti di questo argomento per informazioni su come utilizzare tutti i campi disponibili nella pagina.

## <a name="action-pane"></a>Riquadro azioni

Il riquadro azioni nella pagina **Direttive ubicazione** contiene pulsanti che consentono di creare, modificare ed eliminare direttive (**Modifica**, **Nuovo** ed **Elimina**). La pagina contiene inoltre i seguenti pulsanti che consentono di modificare la sequenza in cui viene elaborata la direttiva di ubicazione e di configurare una query che definisce i criteri per l'applicazione della direttiva di ubicazione:

- **Sposta su** - Sposta la direttiva di ubicazione selezionata verso l'alto nella sequenza. Ad esempio, è possibile spostarla dal numero di sequenza 4 al numero di sequenza 3.
- **Sposta giù** - Sposta la direttiva di ubicazione selezionata verso il basso nella sequenza. Ad esempio, è possibile spostarla dal numero di sequenza 4 al numero di sequenza 5.
- **Modifica query** - Apre una finestra di dialogo in cui è possibile definire le condizioni in base alle quali deve essere elaborata la direttiva di ubicazione selezionata. Ad esempio, potrebbe essere opportuna applicarla solo a un magazzino specifico.

## <a name="location-directives-header"></a>Intestazione direttive di ubicazione

L'intestazione della direttiva di ubicazione include i seguenti campi per il numero di sequenza e il nome descrittivo della direttiva di ubicazione:

- **Numero progressivo** - Questo campo indica la sequenza con cui il sistema cerca di applicare ciascuna direttiva di ubicazione per il tipo di ordine di lavoro selezionato. I numeri bassi vengono applicati per primi. È possibile modificare la sequenza utilizzando i pulsanti **Sposta su** e **Sposta giù** nel riquadro azioni.
- **Nome** - Immettere un nome descrittivo per la direttiva di ubicazione. Questo nome deve aiutare a identificare lo scopo generale della direttiva. Ad esempio, immettere *Prelievo ordini cliente in magazzino 24*.

## <a name="location-directives-fasttab"></a>Scheda dettaglio direttive di ubicazione

I campi nella Scheda dettaglio **Direttive di ubicazione** sono specifici per il tipo di ordine di lavoro selezionato nel campo **Tipo ordine di lavoro** nel riquadro elenco.

- **Tipo di lavoro** - Selezionare il tipo di lavoro da eseguire. I valori disponibili dipendono dal tipo di transazioni di inventario selezionate nel campo **Tipo ordine di lavoro**. Selezionare uno dei seguenti valori:

    - **Stoccaggio** - La direttiva di ubicazione cercherà di trovare l'ubicazione migliore in cui stoccare o individuare le scorte che entrano nel sistema tramite il ricevimento, la produzione o le correzioni delle scorte. L'opzione consente anche di definire uno stoccaggio nell'ubicazione di gestione temporanea o l'ubicazione di spedizione finale.
    - **Prelievo** - La direttiva di ubicazione proverà a trovare le ubicazioni migliori da cui prenotare fisicamente le scorte (ovvero creare lavoro). Il prelievo può essere completato (la riga di lavoro di prelievo può essere chiusa) anche se il lavoro non è completato. L'utente può completare il prelievo fisico. Nel sistema, quell'azione è un passaggio di prelievo. L'utente può quindi eseguire l'annullamento da da un dispositivo mobile e completare il lavoro in un secondo momento. Tuttavia, l'intestazione del lavoro viene chiusa innanzitutto quando viene completato lo stoccaggio finale.

    > [!IMPORTANT]
    > Gli altri valori nel campo **Tipo di lavoro** non sono rilevanti per le direttive di ubicazione. Vengono visualizzati solo perché il campo non è filtrato per corrispondere al tipo di ordine di lavoro selezionato.

- **Sito** - Questo campo è obbligatorio perché la direttiva di ubicazione deve essere in grado di determinare il sito e il magazzino per cui è valida.
- **Magazzino** - Questo campo è obbligatorio perché la direttiva di ubicazione deve essere in grado di determinare il sito e il magazzino per cui è valida.
- **Codice direttiva** - Selezionare il codice della direttiva da associare a un modello di lavoro o un modello di rifornimento. Nella pagina **Codice direttiva**, è possibile creare nuovi codici che possono essere utilizzati per collegare modelli di lavoro o di rifornimento a direttive di ubicazione. I codici di direttiva possono essere utilizzati anche per impostare il collegamento tra una qualsiasi riga del modello di lavoro e una direttiva di ubicazione (ad esempio l'ubicazione finale o di gestione temporanea).

    > [!TIP]
    > Se è impostato un codice di direttiva, il sistema non cercherà le direttive di ubicazione per numero di sequenza quando il lavoro deve essere generato. Cercherà invece per codice di direttiva. In questo modo, è possibile essere più precisi riguardo il modello di ubicazione utilizzato per un passaggio particolare in un modello di lavoro, ad esempio la gestione temporanea dei materiali.

- **Più SKU** - Impostare questa opzione su *Sì* per abilitare l'utilizzo di più unità di stockkeeping in un'ubicazione. Ad esempio, è necessario abilitare più unità di stockkeeping per un'ubicazione finale. Se si abilitano più unità di stockkeeping, l'ubicazione di stoccaggio verrà specificata nel lavoro, come previsto. Tuttavia, l'ubicazione di stoccaggio sarà in grado di gestire solo uno stoccaggio multi-articolo (se il lavoro include unità di stockkeeping diverse che devono essere prelevate e stoccate). Non sarà in grado di gestire uno stoccaggio per una singola unità di stockkeeping. Se si imposta questa opzione su *No*, l'ubicazione di stoccaggio verrà specificata solo se lo stoccaggio prevede un solo tipo di unità di stockkeeping.

    > [!IMPORTANT]
    > Per eseguite stoccaggi multi-articolo e per una singola unità di stockkeeping, è necessario specificare due righe con la stessa struttura e la stessa impostazione, ma è necessario impostare l'opzione **Più SKU** su *Sì* per una riga e su *No* per l'altra. Di conseguenza, per le operazioni di stoccaggio, è necessario disporre di due direttive ubicazioni identiche, anche se non è necessario fare distinzione tra unità di stockkeeping singole e più unità di stockkeepng in un iD lavoro. Spesso, se non si impostano entrambe queste direttive di ubicazione, le ubicazioni dei processi aziendali impreviste deriveranno dalla direttiva di ubicazione applicata. È necessario utilizzare una configurazione simile per le direttive di ubicazione **Tipo di lavoro** uguale a *prelievo* se è necessario elaborare ordini che includono più unità di stockkeeping.

    Utilizzare l'opzione **Più SKU** per le righe di lavoro che gestiscono più di un numero di articolo. Il numero dell'articolo sarà vuoto nei dettagli del lavoro e verrà visualizzato come **Multiplo** nelle pagine di elaborazione nell'app di magazzino.

    In uno scenario di esempio tipico, un modello di lavoro è impostato in modo che abbia più di una coppia prelievo/stoccaggio. In questo caso, è opportuno cercare un'ubicazione di gestione temporanea specifica da utilizzare per le righe con un **Tipo di lavoro** uguale a *Stoccaggio*.

    > [!NOTE]
    > Se l'opzione **Più SKU** è impostata su *Sì*, non è possibile selezionare **Modifica query** nel riquadro azioni perché la query non può essere valutata a livello di articolo quando sono presenti più articoli. Per assicurarsi che sia selezionata la direttiva di ubicazione desiderata, utilizzare il campo **Codice direttiva** per guidare la selezione della direttiva di ubicazione correlata alle righe di stoccaggio in cui tale codice direttiva è assegnato nel modello di lavoro.

    A meno che non si lavori sempre con operazioni su un singolo articolo o su articoli, è importante definire due direttive di ubicazione per il tipo di lavoro *Stoccaggio*: una dove l'opzione **Più SKU** è impostata su *Sì* e una dove l'opzione è impostata su *No*.

- **Codice smaltimento applicabile** - Specificare se il codice smaltimento della direttiva di ubicazione deve corrispondere al codice smaltimento che si applica all'articolo in ricevimento o se la direttiva di ubicazione può essere selezionata in base a qualsiasi codice smaltimento. Se si seleziona *Corrispondenza esatta* e il campo **Codice smaltimento** è vuoto, solo i codici smaltimento vuoti verranno presi in considerazione per la direttiva di ubicazione.

    > [!NOTE]
    > Questo campo è disponibile solo per i tipi di ordine di lavoro selezionati in cui è consentito il rifornimento. Per un elenco completo, vedere la sezione [Campi specifici per i tipi di ordine di lavoro](#fields-specific-types) precedente in questo argomento.

- **Trova per** - Specificare se la quantità di stoccaggio deve essere l'intera quantità sulla targa o se deve essere considerata articolo per articolo. Utilizzare questo campo per assicurarsi che tutti i contenuti di una targa siano stoccati in un'unica ubicazione e che il sistema non suggerisca di dividere i contenuti in più ubicazioni per i processi di ricevimento **ASN** (ricevimento targa), **Ricevimento targa mista** e **Cluster**. Il processo di ricevimento **Cluster** processo di ricezione richiede che l'opzione *Funzione stoccaggio cluster* sia attivata. Il comportamento della query della direttiva di ubicazione, le righe e le azioni della direttiva di ubicazione variano a seconda del valore selezionato. La Scheda dettaglio **Righe** viene utilizzata solo quando l'opzione **Trova per** è impostato su *Articolo*.

    > [!NOTE]
    > Questo campo è disponibile solo per i tipi di ordine di lavoro selezionati in cui è consentito il rifornimento. Per un elenco completo, vedere la sezione [Campi specifici per i tipi di ordine di lavoro](#fields-specific-types).

- **Codice smaltimento** - Questo campo viene utilizzato per le direttive di ubicazione con tipo di ordine di lavoro uguale a *Ordini fornitore*, *Stoccaggio prodotti finiti* oppure *Ordini di reso* e un tipo di lavoro uguale a *Stoccaggio*. Utilizzarlo per guidare il flusso per utilizzare una direttiva di ubicazione specifica, a seconda del codice di smaltimento che un lavoratore ha selezionato nell'app di magazzino. Ad esempio, è possibile indirizzare le merci restituite a un'ubicazione di ispezione prima che vengano restituite nelle scorte. Un codice di smaltimento può essere collegato a uno stato dell'inventario. In questo modo, può essere utilizzato per modificare lo stato dell'inventario come parte di un processo di ricevimento. Ad esempio, può essere presente un codice di smaltimento *QA* che imposta lo stato dell'inventario su *QA*. È quindi possibile disporre di una direttiva di ubicazione separata per spostare l'inventario in una posizione di quarantena.

    > [!NOTE]
    > Questo campo è disponibile solo per i tipi di ordine di lavoro selezionati in cui è consentito il rifornimento. Per un elenco completo, vedere la sezione [Campi specifici per i tipi di ordine di lavoro](#fields-specific-types).

## <a name="lines-fasttab"></a>Scheda dettaglio Righe

Utilizzare la Scheda dettaglio **Righe** per stabilire le condizioni per l'applicazione delle azioni correlate specificate nella Scheda dettaglio **Azioni direttiva di ubicazione**. Per ogni riga, è possibile specificare la quantità minima e la quantità massima a cui devono essere applicate le direttive. È inoltre possibile specificare che le azioni devono essere applicate a un'unità di magazzino specifica.

- **Numero progressivo** - Immettere la sequenza in cui verrà elaborata ogni riga di direttiva di ubicazione per il tipo di lavoro selezionato. È possibile modificare la sequenza in base alle esigenze utilizzando i pulsanti **Sposta su** e **Sposta giù** sulla barra degli strumenti.
- **Da quantità** - Specificare l'inizio dell'intervallo di quantità a cui si applica la riga. Specificare la quantità in unità di misura selezionata nel campo **Unità**.
- **A quantità** - Specificare la fine dell'intervallo di quantità a cui si applica la riga. Specificare la quantità in unità di misura selezionata nel campo **Unità**.
- **Unità** - Selezionare l'unità di misura per gli articoli. È possibile specificare una quantità minima e una quantità massima a cui la direttiva deve essere applicata e specificare che la direttiva deve essere destinata a un'unità di magazzino specifica. Il campo **Unità** viene utilizzato *solo* per la valutazione della della quantità. Per determinare se la riga di direttiva di ubicazione è applicabile, il sistema utilizza la quantità nell'unità specificata in tale riga. Ogni volta che accede a una riga della direttiva di ubicazione, il sistema tenta di convertire l'unità della domanda nell'unità specificata nella riga. Se la conversione delle unità di misura non esiste, il sistema si sposta sulla riga successiva.
- **Trova quantità** - Questo campo viene utilizzato solo durante i tentativi di stoccaggio o ricerca di articoli nel magazzino. Di conseguenza, si applica solo quando il campo **Tipo di lavoro** è impostato su *Stoccaggio*. Selezionare uno dei seguenti valori per specificare la quantità utilizzata per valutare se una quantità è all'interno dell'intervallo con estremi **Da quantità** e **A quantità**:

    - **Quantità targa** - Utilizzare la quantità sulla targa ricevuta.
    - **Quantità in unità** - Utilizzare la quantità utilizzata durante la transazione. Ad esempio, si può ricevere una quantità pari a 1000 in un magazzino e suddividerla in 10 targhe, a ciascuna delle quali viene assegnata una quantità pari a 100. In questo caso, è possibile utilizzare una quantità di 1000 articoli invece della quantità di targa pari a 100.
    - **Quantità rimanente** - Utilizzare la quantità ancora da ricevere nella riga dell'ordine fornitore in fase di elaborazione.
    - **Quantità prevista** - Utilizzare la quantità totale della riga dell'ordine fornitore, indipendentemente da ciò che è già stato ricevuto.

- **Limita per unità** - Questa casella di controllo consente di rendere la riga della direttiva di ubicazione specifica per un'unità di misura o più unità di misura. Selezionare la casella di controllo per limitare le unità di misura considerate come criteri di selezione validi per le righe della direttiva di ubicazione. Questa funzionalità è supportata solo per direttive di ubicazione per cui il campo **Tipo di lavoro** è impostato su *Prelievo*.

    Ad esempio, quando si prenotano quantità, si desidera prenotare i pallet solo da un insieme specifico di ubicazioni. In questo caso, le righe limiteranno tale sequenza ai pallet in modo tale che qualsiasi quantità inferiore a un pallet non verrà selezionata per la direttiva di ubicazione.

    Si noti che la casella di controllo **Limita per unità** non controlla l'unità o le unità applicate alle righe di lavoro. La restrizione delle unità si applica solo alle unità rese disponibili tramite il gruppo di sequenze delle unità. Ad esempio, un'unità viene associata a un gruppo di sequenze di unità che include entrambe le unità *pallet* e *pz*. È stata definita un'unità di misura dove 1 pallet = 100 pezzi e la direttiva di ubicazione utilizza la funzione **Limita per unità** solo per i pallet. Inoltre, è stato definito un modello di lavoro che limita la creazione dell'intestazione di lavoro a 50 pezzi. In questo caso verranno create righe di lavoro da 50 pz. Per specificare l'unità di misura per la restrizione, eseguire queste operazioni:

    1. Nella Scheda dettaglio **Righe** selezionare **Limita per unità** sulla barra degli strumenti. Questo pulsante diventa disponibile solo dopo aver selezionato la casella di controllo **Limita per unità** sulla riga, quindi selezionare **Salva**.
    1. Nella pagina **Limita per unità**, nel campo **Unità** selezionare l'unità di misura in base si desidera porre un limite per i processi di prelievo e stoccaggio.

- **Arrotonda a unità** - Questo campo funziona insieme alla casella di controllo **Limita per unità**. Ad esempio, se le opzioni **Limita per unità** e **Arrotonda a unità** sono selezionata sulla riga di direttiva di ubicazione, il lavoro generato dalla direttiva per il prelievo della materia prima deve essere arrotondato fino a un multiplo dell'unità di movimentazione specificata nella pagina **Limita per unità**.

    > [!NOTE]
    > L'impostazione **Arrotonda a unità** funziona solo per il tipo di ordine di lavoro *Prelievo materie prime* e solo per direttive di ubicazione in cui il campo **Tipo di lavoro** è impostato su *Prelievo*.

- **Individua quantità di imballaggio** - Se si specifica una quantità di imballaggio in un ordine cliente, un ordine di trasferimento o un ordine di produzione, questa casella di controllo consente di limitare il sistema in modo che possa selezionare solo le ubicazioni che hanno almeno la quantità di imballaggio specificata.

    > [!NOTE]
    > Questa funzionalità è supportata solo con direttive di ubicazione di tipo *Prelievo*.

- **Consenti divisione** - Specifica se una direttiva di ubicazione può suddividere la quantità ricevuta o prenotata tra più ubicazioni magazzino o se l'intera quantità deve essere individuata in una singola ubicazione o prenotata da una singola ubicazione per creare lavoro.
- **Modello per il rifornimento immediato** - Utilizzare questo campo per creare una connessione a un modello di rifornimento per iniziare immediatamente il rifornimento se gli articoli non sono allocati. Se il campo viene lasciato vuoto, il rifornimento degli articoli non inizierà fino all'elaborazione di tutte le righe della direttiva ubicazione.

    > [!NOTE]
    > Questo campo è disponibile solo per i tipi di ordine di lavoro selezionati in cui è consentito il rifornimento. Per un elenco completo, vedere la sezione [Campi specifici per i tipi di ordine di lavoro](#fields-specific-types).

## <a name="location-directive-actions-fasttab"></a>Scheda dettaglio azioni direttive di ubicazione

È possibile definire più azioni direttive ubicazione per ciascuna riga. Ancora una volta, viene utilizzato un numero progressivo per determinare l'ordine in cui le azioni vengono valutate. A questo livello, è possibile impostare una query per definire come individuare l'ubicazione migliore nel magazzino. È inoltre possibile utilizzare i valori di **Strategia** predefiniti per trovare un'ubicazione ottimale.

- **Numero progressivo** - Questo campo mostra la sequenza in cui verranno elaborate le azioni per il tipo di lavoro selezionato. È possibile modificare la sequenza utilizzando i pulsanti **Sposta su** e **Sposta giù** sulla barra degli strumenti.
- **Nome** - Immettere il nome dell'azione della direttiva di ubicazione. Utilizzare un nome specifico, in modo che l'azione eseguita sia chiara dal nome stesso.
- **Utilizzo ubicazioni fisse** - Specificare le ubicazioni che la direttiva di ubicazione deve prendere in considerazione. Selezionare uno dei seguenti valori:

    - **Posizioni fisse e non fisse**: la direttiva ubicazione considererà tutte le ubicazioni.
    - **Solo ubicazioni fisse per il prodotto**: la direttiva ubicazione considererà solo le ubicazioni fisse per i prodotti.
    - **Solo ubicazioni fisse per la variante prodotto**: la direttiva ubicazione considererà solo le ubicazioni fisse per le varianti prodotti.

- **Consenti inventario negativo** - Selezionare questa opzione per consentire scorte negative nell'ubicazione di magazzino specificata nelle direttive ubicazione.
- **Batch abilitato** - Selezionare questa casella di controllo per utilizzare le strategie batch per gli articoli abilitati per il batch. È importante selezionare questa casella di controllo per i processi che utilizzano le direttive di ubicazione per trovare ubicazioni da cui prelevare articoli tracciati con numero di batch. In questo modo viene inclusa la ricerca di ubicazioni che contengono articoli tracciati con numero di batch. Se questa casella di controllo è selezionata e il campo **Strategia** è impostato su *Nessuna*, il sistema passerà alla successiva riga dell'azione.
- **Strategia** - Per semplificare e velocizzare la definizione delle azioni associate a ogni riga di direttiva di ubicazione, selezionare una delle strategie predefinite seguenti:

    - **Nessuna** - Non verrà utilizzata alcuna strategia.
    - **Corrispondenza quantità imballaggio** - Questa strategia consente di verificare se un'ubicazione di prelievo dispone della quantità di imballaggio specificata. Questa strategia è valida solo quando il campo **Tipo di lavoro** è impostato su *Preleva*.
    - **Consolidato** - Questa strategia consente di consolidare gli articoli in un'ubicazione specifica quando articoli simili sono già disponibili. Questa strategia è valida solo quando il campo **Tipo di lavoro** è impostato su *Stoccaggio*. Una configurazione tipica di stoccaggio tenta di consolidare la prima riga dell'azione, quindi, sulla seconda riga, tenta di eseguire lo stoccaggio senza consolidamento. Il consolidamento delle merci rende più efficiente il prelievo in un secondo momento.
    - **Prenotazione batch FEFO** - Questa strategia utilizza le prenotazioni batch FEFO (First Expiry, First Out). Utilizzare questa strategia quando il magazzino viene individuato utilizzando una data di scadenza batch e allocato per la prenotazione batch. È possibile utilizzare questa strategia solo per gli articoli abilitati per il batch. Questa strategia è valida solo quando il campo **Tipo di lavoro** è impostato su *Prelievo*.
    - **Arrotonda per eccesso alla targa completa e al batch FEFO** - Questa strategia combina gli elementi delle strategie *Prenotazione batch FEFO* e *Arrotonda per eccesso alla targa completa*. È valida solo per gli articoli abilitati per batch e per le direttive di ubicazione che hanno un tipo di lavoro *Prelievo*. Per utilizzare la strategia *Prenotazione batch FEFO*, la riga deve essere abilitata per il batch e la strategia *Arrotonda per accesso alla targa completa* può essere utilizzata solo per il rifornimento. Se questa strategia è configurata insieme a un limite di stoccaggio dell'ubicazione, può causare il sovraccarico dell'ubicazione di lavoro selezionata e ignorare i limiti di stoccaggio.
    - **Arrotonda per eccesso alla targa completa** - Questa strategia consente di arrotondare per eccesso la quantità di scorte da abbinare alla quantità di targa assegnata agli articoli da prelevare. È possibile utilizzare questa strategia solo per le direttive di ubicazione di rifornimento di tipo *Prelievo*. Se questa strategia è configurata insieme a un limite di stoccaggio dell'ubicazione, può causare il sovraccarico dell'ubicazione di lavoro selezionata e ignorare i limiti di stoccaggio.
    - **Targa guidata** - Utilizzare questa strategia quando si rilascia l'ordine al magazzino per creare il lavoro di prelievo e stoccaggio. È possibile utilizzare questo approccio per più targhe. Questa strategia tenterà di prenotare e creare lavori di prelievo nelle ubicazioni contenenti le targhe richieste che sono state associate alle righe dell'ordine di trasferimento. Tuttavia, se queste azioni non possono essere completate, ma si desidera comunque creare un lavoro di prelievo, è necessario ricorrere a un'altra strategia per le azioni di direttiva di ubicazione. A seconda dei requisiti del processo aziendale, potrebbe essere necessario cercare l'inventario in un'altra area del magazzino.
    - **Ubicazione vuota senza alcun lavoro in entrata** - Questa strategia viene utilizzata per individuare le ubicazioni vuote. Un'ubicazione viene considerata vuota se non è presente un inventario fisico e non è previsto lavoro in entrata. È possibile utilizzare questa strategia solo per le direttive di ubicazione con tipo di lavoro *Stoccaggio*.
    - **FIFO aging ubicazione** - Utilizzare la strategia FIFO (First In, First Out) per spedire sia articoli di cui viene tenuta traccia in batch sia articoli di cui non viene tenuta traccia in batch, in base alla data in cui le scorte sono entrate in magazzino. Questa funzionalità può essere particolarmente utile per le scorte di cui non viene tenuta traccia in batch, dove una data di scadenza non è disponibile per l'ordinamento. La strategia FIFO trova l'ubicazione che contiene la data di aging meno recente e alloca il prelievo in base a tale data di aging.
    - **LIFO aging ubicazione** - Utilizzare la strategia LIFO (Last In, First Out) per spedire sia articoli di cui viene tenuta traccia in batch sia articoli di cui non viene tenuta traccia in batch, in base alla data in cui le scorte sono entrate in magazzino. Questa funzionalità può essere particolarmente utile per le scorte di cui non viene tenuta traccia in batch, dove una data di scadenza non è disponibile per l'ordinamento. La strategia LIFO trova l'ubicazione che contiene la data di aging più recente e alloca il prelievo in base a tale data di aging.

## <a name="example-using-location-directives"></a>Esempio: Utilizzo di direttive di ubicazione

Per questo esempio, considerare un processo di ordine fornitore in cui la direttiva ubicazione deve individuare capacità libera all'interno di un magazzino per gli articoli di magazzino registrati immediatamente alla banchina di entrata. Innanzitutto, occorre cercare capacità libera all'interno del magazzino consolidando le scorte disponibili esistenti. Se il consolidamento non è possibile, occorre cercare di individuare un'ubicazione vuota.

Per questo scenario, è necessario definire due azioni di direttiva ubicazione. La prima azione nella sequenza deve utilizzare la strategia *Consolida* e la seconda deve utilizzare la strategia *Ubicazione vuota senza alcun lavoro in entrata*. A meno che non si definisca una terza azione per gestire uno scenario di overflow, sono possibili due risultati in caso non vi sia più capacità in magazzino: il lavoro può essere creato anche se non è definita un'ubicazione o il processo di creazione di lavoro può interrompersi. Il risultato viene determinato dall'impostazione nella pagina **Errori direttiva ubicazione**, in cui è possibile scegliere se selezionare l'opzione **Interrompi lavoro in caso di errore direttiva ubicazione** per ogni tipo di ordine di lavoro.

## <a name="next-step"></a>Passaggio successivo

Una volta create le direttive ubicazione, è possibile associare ciascun codice di direttiva a un codice di modello di lavoro per la creazione del lavoro. Per ulteriori informazioni, vedere [Rifornimento e Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="additional-resources"></a>Risorse aggiuntive

- Video: [Approfondimento sulla configurazione della gestione magazzino](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Argomento della Guida: [Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
