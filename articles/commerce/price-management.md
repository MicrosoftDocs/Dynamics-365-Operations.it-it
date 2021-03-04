---
title: Gestione dei prezzi di vendita al dettaglio in Retail
description: Questo argomento descrive i concetti di creazione e gestione dei prezzi di vendita in Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a90f5706c87d398f495fae40f42f6c2d408b1c2a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413332"
---
# <a name="retail-sales-price-management"></a>Gestione dei prezzi di vendita Retail

[!include [banner](includes/banner.md)]

Questo argomento fornisce informazioni sul processo di creazione e gestione dei prezzi di vendita in Dynamics 365 Commerce. Si concentra sui concetti coinvolti in questo processo e sugli effetti delle varie opzioni di configurazione per i prezzi di vendita.

## <a name="terminology"></a>Terminologia

In questo argomento vengono utilizzati i seguenti termini:

| Termine | Definizione, utilizzo e note |
|---|---|
| Prezzo | L'importo unitario in base a cui un prodotto viene venduto in un POS o in un ordine cliente. In questo argomento, il termine *prezzo* si riferisce sempre al prezzo di vendita, non al prezzo di magazzino o al prezzo di costo. |
| Prezzo di base | Il prezzo impostato nel campo **Prezzo** di un prodotto rilasciato. |
| Prezzo accordo commerciale | Il prezzo di vendita impostato per un prodotto o una variante tramite un accordo commerciale con tipo **Prezzo (Vend.)**. |
| Prezzo migliore | Quando è possibile applicare più di un prezzo o uno sconto a un prodotto, l'importo del prezzo inferiore e/o l'importo di sconto maggiore che produce l'importo netto più basso possibile che il cliente deve pagare. In questo argomento, il concetto di miglior prezzo viene sempre definito "il migliore prezzo". Questo prezzo migliore differisce e non deve essere confuso con il valore di enumerazione del prezzo migliore per la modalità di concorrenza di uno sconto **Prezzo migliore**. |

## <a name="price-groups"></a>Gruppi prezzi

I gruppi di prezzi sono al centro della gestione dei prezzi e degli sconti in Commerce. I gruppi di prezzi vengono utilizzati per assegnare prezzi e sconti a entità commerciali (ovvero canali, cataloghi, affiliazioni e programmi fedeltà). Poiché i gruppi di prezzi vengono utilizzati per tutti i prezzi e gli sconti, è molto importante pianificare in che modo si prevede di utilizzarli prima di iniziare.

Di per sé, un gruppo di prezzi è solo un nome, una descrizione e, facoltativamente, una priorità di determinazione prezzo. L'aspetto principale da ricordare sui gruppi di prezzi è che sono utilizzati per gestire le relazioni molti-a-molti che sconti e prezzi hanno con le entità commerciali.

La seguente illustrazione mostra come vengono utilizzati i gruppi di prezzi. In questa illustrazione, si noti che "Gruppo di prezzi" è letteralmente al centro della gestione dei prezzi e degli sconti. Le entità commerciali che è possibile utilizzare per gestire prezzi e sconti differenziali si trovano sulla sinistra e i record di prezzo e sconto effettivi sono sulla destra.

![Gruppi di prezzi](./media/PriceGroups.png "Gruppi di prezzi")

Quando si creano gruppi di prezzi, evitare utilizzare un singolo gruppo di prezzi per più tipi di entità commerciali. In caso contrario, può essere difficile determinare il motivo per cui un prezzo o uno sconto specifico viene applicato a una transazione.

Come mostra la linea tratteggiata rossa nell'illustrazione, Commerce supporta la funzionalità principale di Microsoft Dynamics 365 di un gruppo di prezzi che viene impostato direttamente su un cliente. Tuttavia, in questo caso, si ottengono solo accordi commerciali sui prezzi di vendita. Se si desidera applicare prezzi specifici del cliente, si consiglia di non impostare i gruppi di prezzi direttamente sul cliente. Utilizzare invece le affiliazioni. 

Da notare che se il gruppo di prezzi è impostato sul cliente, questo gruppo di prezzi viene associato all'intestazione di ordine di vendita degli ordini creati per questo cliente. Se l'utente modifica il gruppo di prezzi nell'intestazione dell'ordine, il vecchio gruppo di prezzi viene sostituito con quello nuovo solo per l'ordine corrente. Ad esempio, il vecchio gruppo di prezzi non influirà sull'ordine corrente, ma rimarrà associato al cliente per ordini futuri.

Nelle sezioni seguenti vengono fornite ulteriori informazioni sulle entità commerciali che è possibile utilizzare per impostare prezzi distinti quando vengono utilizzati i gruppi di prezzi. La configurazione dei prezzi e degli sconti per tutte queste entità è un processo in due fasi. Questi passaggi possono essere eseguiti in qualsiasi ordine. Tuttavia, l'ordine logico è di impostare prima i gruppi di prezzi sulle entità, poiché è probabile che questo passaggio sia una configurazione unica eseguita durante l'implementazione. Quindi, quando vengono creati i prezzi e gli sconti, è possibile impostare i gruppi di prezzi su tali prezzi e sconti singolarmente.

### <a name="channels"></a>Canali

Nel settore del commercio, è molto diffuso l'uso di prezzi diversi su canali diversi. I due fattori principali che influenzano i prezzi specifici del canale sono i costi e le condizioni del mercato locale.

- **Costi**: più il canale è lontano dall'origine del prodotto, più costa immagazzinare scorte di un prodotto. Ad esempio, i prodotti freschi hanno una durata a scaffale limitata e requisiti di produzione specifici (ad esempio, una stagione di crescita). Durante l'inverno, la lattuga fresca probabilmente costa di più nei climi nordici rispetto ai climi meridionali. Se vengono impostati i prezzi per i canali su una vasta area geografica, probabilmente si vorranno impostare prezzi diversi in canali diversi.
- **Condizioni del mercato locale**: un punto vendita che ha un concorrente diretto dall'altra parte della strada sarà molto più sensibile al prezzo di un punto vendita che non ha un concorrente diretto nelle vicinanze.

### <a name="affiliations"></a>Rapporti

La definizione generale di affiliazione è un collegamento o un'associazione con un gruppo. In Commerce, le affiliazioni sono gruppi di clienti. Le affiliazioni sono uno strumento molto più flessibile per i prezzi e gli sconti dei clienti rispetto al concetto principale di gruppi di clienti e gruppi di sconto di Microsoft Dynamics 365. In primo luogo, un'affiliazione può essere utilizzata sia per i prezzi che per gli sconti, mentre i prezzi non al dettaglio hanno un gruppo diverso per ogni tipo di sconto e prezzo. Successivamente, un cliente può appartenere a più affiliazioni ma può appartenere a un solo gruppo di prezzi non Retail di ciascun tipo. Infine, anche se le affiliazioni possono essere impostate in modo che siano collegate a un cliente, questo non è necessario. Un'affiliazione ad hoc può essere utilizzata per i clienti anonimi presso il POS. Un tipico esempio di uno sconto di affiliazione anonimo è uno sconto per studenti o studenti, in cui un cliente può ricevere uno sconto solo mostrando una scheda di appartenenza a un gruppo.

Sebbene le affiliazioni siano spesso associate a sconti,è possibile utilizzarle anche per impostare prezzi diversi. Ad esempio, quando un rivenditore vende a un dipendente, potrebbe voler cambiare il prezzo di vendita anziché applicare uno sconto al prezzo normale. Come altro esempio, un rivenditore che vende sia ai clienti consumer sia ai clienti business potrebbe offrire ai clienti business prezzi migliori, in base al volume degli acquisti. Report consentono entrambi questi scenari.

### <a name="loyalty-programs"></a>Programmi fedeltà

In relazione a prezzi e sconti, i programmi fedeltà sono fondamentalmente solo un'affiliazione con un nome speciale. Sia i prezzi che gli sconti possono essere impostati per un programma fedeltà, così come possono essere impostati per un'affiliazione. Tuttavia, il modo in cui i clienti ottengono prezzi fedeltà durante una transazione o un ordine differisce dal modo in cui ottengono i prezzi di affiliazione. I clienti possono ottenere prezzi fedeltà solo se una carta fedeltà viene aggiunta a una transazione. Quando una carta fedeltà viene aggiunta a una transazione, viene aggiunto anche il programma fedeltà. Il programma fedeltà consente quindi prezzi e sconti speciali.

I programmi fedeltà possono avere più livelli e gli sconti possono differire per i diversi livelli. In questo modo, i rivenditori possono offrire ai clienti frequenti premi più grandi senza doverli aggiungere manualmente in un gruppo speciale.

I programmi fedeltà hanno funzionalità aggiuntive oltre a prezzi e sconti. Tuttavia, dal punto di vista dei prezzi e degli sconti, sono uguali alle affiliazioni.

### <a name="catalogs"></a>Cataloghi

Alcuni rivenditori utilizzano cataloghi fisici o virtuali per commercializzare prodotti e prezzi per gruppi mirati di clienti. Come parte del loro modello di business per un approccio marketing mirato tramite catalogo, questi rivenditori possono fissare prezzi differenziali nei vari cataloghi. Microsoft Dynamics 365 supporta questa funzionalità consentendo di definire sconti e prezzi specifici del catalogo, così come è possibile definire sconti specifici per canale o di affiliazione. Quando si modifica un catalogo, è possibile associare i gruppi di prezzi al catalogo, così come è possibile associarli a un canale, affiliazione o programma fedeltà.

### <a name="best-practices-for-price-groups"></a>Procedure consigliate per i gruppi di prezzi

Non utilizzare un gruppo di prezzi per più tipi di entità. Utilizzare invece un gruppo di gruppi di prezzi per i canali, un diverso set di gruppi di prezzi per affiliazioni o programmi fedeltà e così via. È possibile utilizzare un prefisso o un suffisso nel nome del gruppo di prezzi per raggruppare visivamente i vari tipi di gruppi di prezzi in uso.

Evitare di impostare i gruppi di prezzi direttamente per un cliente. Usare invece un'affiliazione. In questo modo, è possibile assegnare tutti i tipi di prezzi e sconti ai clienti, non solo gli accordi commerciali sui prezzi di vendita.

## <a name="pricing-priority"></a>Priorità determinazione prezzi

Di per sé, una priorità di prezzo è solo un numero e una descrizione. Le priorità dei prezzi possono essere applicate a gruppi di prezzi oppure direttamente sugli sconti. Quando vengono utilizzate le priorità di prezzi, queste consentono a un rivenditore di ignorare il principio del prezzo migliore controllando l'ordine in cui i prezzi e gli sconti vengono applicati ai prodotti. Un numero di priorità di prezzo superiore viene valutato prima di un numero di priorità di prezzo inferiore. Inoltre, se viene trovato un prezzo o uno sconto per qualsiasi numero di priorità, tutti i prezzi o gli sconti con numeri di priorità inferiori vengono ignorati.

Il prezzo e uno sconto possono derivare da due diverse priorità di prezzo, poiché le priorità di prezzo si applicano in modo indipendente a prezzi e sconti.

Per utilizzare la priorità di prezzo per i prezzi, è necessario assegnare una priorità di prezzo a un gruppo di prezzi e quindi creare un accordo commerciale di prezzo di vendita per quel gruppo di prezzi.

La funzionalità di priorità dei prezzi è stata introdotta per supportare lo scenario in cui un rivenditore desidera applicare prezzi più elevati in uno specifico gruppo di punti vendita. Ad esempio, un rivenditore ha definito i prezzi regionali per la costa orientale degli Stati Uniti, ma desidera prezzi più elevati per alcuni prodotti nei punti vendita di New York, poiché il costo di vendita di alcuni prodotti è superiore in città e/o perché il mercato locale supporta un prezzo più alto.

Come descritto nella sezione "Miglior prezzo" di questo argomento, il motore dei prezzi seleziona in genere valore minimo tra due prezzi. Di conseguenza, al rivenditore di solito viene impedito di utilizzare il prezzo più alto di due prezzi in un punto vendita che ha sia i gruppi di prezzi della costa orientale sia quelli di New York. Per risolvere questo problema, prima che fosse introdotta la funzionalità di priorità dei prezzi, il rivenditore doveva definire i prezzi per ogni prodotto due volte e non assegnare entrambi i gruppi di prezzi. In alternativa, il rivenditore ha dovuto creare gruppi di prezzi extra per isolare i prodotti che hanno prezzi più alti da quelli che hanno i prezzi abituali più bassi.

Tuttavia, la funzionalità di priorità dei prezzi consente al rivenditore di creare una priorità di prezzo per i prezzi dei punti vendita superiore alla priorità dei prezzi per i prezzi regionali. In alternativa, il rivenditore può creare una priorità di prezzo solo per i prezzi dei punti vendita e lasciare i prezzi regionali con la priorità di prezzo predefinita, che è 0 (zero). Entrambe le configurazioni consentono di garantire che i prezzi dei punti vendita vengano sempre utilizzati prima dei prezzi regionali.

### <a name="pricing-priority-example"></a>Esempio di priorità determinazione prezzi

Esaminiamo un esempio in cui i prezzi dei punti vendita prevalgono su altri prezzi.

Un rivenditore nazionale fissa la maggior parte dei prezzi per regione con quattro aree: North east, South east, Mid-west e West. Ha identificato diversi mercati ad alto costo in grado di supportare prezzi più elevati. Questi mercati si trovano a New York, Chicago e nell'area della Baia di San Francisco.

In questo esempio, esploreremo la regione North east. Il punto vendita 1 corrisponde a Boston e il punto vendita 2 è a Manhattan. Per il punto vendita di Boston, due canali di prezzo sono collegati al canale: North East e POS 1. Per il punto vendita di Manhattan, tre canali di prezzo sono collegati al canale: North East, NYC e POS 2.

Il rivenditore imposta due priorità di prezzo: il costo elevato ha un numero di priorità 5 e i prezzi del punto vendita hanno un numero di priorità 10. Tenere presente che, per impostazione predefinita, la priorità di valutazione è 0 \[zero\] e un prezzo o uno sconto che ha un numero di priorità più elevato viene utilizzato prima di un prezzo o uno sconto con un numero di priorità inferiore. Per il gruppo di prezzi del North East la priorità del prezzo viene lasciata al valore predefinito di **0** (zero). Per il gruppo di prezzi di New York, la priorità del prezzo è fissata a **5**, perché New York City è un mercato ad alto costo. Per i gruppi di prezzi POS 1 e POS 2, la priorità del prezzo è impostata su **10**.

I due prodotti venduti dal rivenditore sono il prodotto 1 (una maglietta sportiva) e il prodotto 2 (jeans moda specifici del marchio).

| Prodotto | Prezzo North East | Prezzo NYC | Prezzo punto vendita |
|---|---|---|---|
| Maglietta | $15 | Non impostato | Non impostato |
| Jeans moda | $50 | $70 | Non impostato |

La maglietta viene venduta allo stesso prezzo (ovvero $15) nei punti vendita di Boston e Manhattan, perché nel gruppo di prezzi del North East un solo prezzo è collegato a entrambi i canali. I jeans alla moda vengono venduti a $50 nel punto vendita di Boston, perché quel prezzo è l'unico prezzo disponibile in quel punto vendita. Tuttavia, nel punto vendita di Manhattan sono disponibili due prezzi: $50 e $70. Poiché la priorità di prezzo 5 per il gruppo di prezzi di New York è superiore alla priorità di prezzo 0 (zero) per il gruppo di prezzi di North East, il prezzo verrà pubblicato come $70 nel sistema POS.

> [!NOTE]
> Per ogni priorità di prezzo, è richiesto un passaggio completo attraverso la logica per il motore dei prezzi di Retail. Pertanto, per contribuire a mantenere le prestazioni del calcolo del prezzo e dello sconto, è necessario utilizzare le priorità del prezzo con parsimonia.

## <a name="types-of-prices"></a>Tipi di prezzi

In Microsoft Dynamics 365 è possibile impostare il prezzo di un prodotto in tre aree:

- Direttamente nel prodotto (prezzo di base)
- In un accordo commerciale sul prezzo di vendita
- In una rettifica prezzo

Il prezzo base e il prezzo dell'accordo commerciale fanno parte del core di Dynamics 365 e sono disponibili anche se non si utilizza Commerce. La funzionalità di rettifica prezzo è disponibile solo in Commerce. La sezione successiva fornisce ulteriori informazioni su ciascuna di queste opzioni per l'impostazione dei prezzi e spiega come le opzioni funzionano insieme.

## <a name="setting-prices"></a>Impostazione dei prezzi

### <a name="base-price"></a>Prezzo di base

Il punto più semplice per impostare il prezzo di un prodotto è direttamente nel prodotto. Il valore impostato direttamente in un prodotto viene spesso definito come il prezzo base del prodotto. È possibile impostare il prezzo di base nel campo **Prezzo** della scheda **Vendi** della pagina **Dettagli prodotto rilasciato**. Il valore immesso è nella valuta della società. Per impostazione predefinita, il prezzo corrisponde a una quantità pari a 1 dell'unità di misura (UdM) impostata nel campo **Unità** nella scheda **Vendi**. Il prezzo effettivo per unità di un prodotto si basa sull'UdM, sulla quantità del prezzo e sulla valuta.

Se un prodotto è associato un prezzo uguale per tutti, il prezzo base rappresenta il modo più efficiente per gestire il prezzo di tale prodotto. Anche se si utilizzano gli accordi commerciali per definire i prezzi, è possibile impostare il prezzo base in un prodotto. In questo modo,, se non si utilizza un accordo commerciale **Tutto**, si ha un prezzo di fallback che viene utilizzato quando non si applica un accordo commerciale.

Se la valuta di un canale differisce dalla valuta della società, il prezzo di base in quel canale viene determinato utilizzando la conversione di valuta del prezzo impostato nel prodotto.

Sebbene l'unità di prezzo non sia uno scenario comune, il motore di determinazione dei prezzi lo supporta. Se l'unità di prezzo viene impostata su un valore diverso da **0** (zero), il prezzo unitario è uguale a Prezzo ÷ Unità di prezzo. Ad esempio, se il prezzo di un prodotto è $ 10,00 e l'unità di prezzo è 50, il prezzo per una quantità di 1 è $ 0,20 (= $ 10,00 ÷ 50).

### <a name="sales-price-trade-agreement"></a>Accordo commerciale sul prezzo di vendita

Utilizzando il giornale di registrazione accordi commerciali, è possibile creare accordi commerciali sui prezzi di vendita per ogni prodotto. In Microsoft Dynamics 365, sono disponibili tre ambiti per i clienti per gli accordi di commerciali sui prezzi: **Tabella**, **Gruppo** e **Tutto**. L'ambito del cliente determina i clienti ai quali si applica un determinato accordo commerciale di vendita.

Un accordo commerciale sui prezzi di vendita **Tabella** è per un singolo cliente che viene impostato direttamente sull'accordo commerciale. Questo scenario non è uno scenario tipico business-to-consumer (B2C). Tuttavia, se si verifica, il motore dei prezzi utilizza gli accordi commerciali **Tabella** quando determina il prezzo.

Un accordo commerciale sui prezzi di vendita **Gruppo** è il tipo più utilizzato. Al di fuori di Commerce, gli accordi commerciali sui prezzi di vendita **Gruppo** si riferiscono a un gruppo di clienti semplice. Tuttavia, in Commerce, il concetto di gruppo di clienti è stato esteso in modo tale che si tratti di un gruppo di prezzi più generico. Un gruppo di prezzi può essere collegato a un canale, un'affiliazione, un programma fedeltà o a un catalogo. Per informazioni dettagliate sui gruppi di prezzi, vedere la sezione "Gruppi di prezzi" in precedenza in questo argomento.

> [!NOTE]
> Il prezzo dell'accordo commerciale viene sempre utilizzato prima del prezzo di base.

### <a name="price-adjustment"></a>Rettifica prezzo

Come suggerisce il nome, una rettifica prezzo viene utilizzata per modificare il prezzo che è stato impostato direttamente sul prodotto o impostato utilizzando un accordo commerciale. Una rettifica prezzo può essere utilizzata solo per ridurre il prezzo, non per aumentarlo. Una rettifica prezzo rappresenta il metodo consigliato per i rivenditori per creare, tracciare e gestire i ribassi dei prezzi per i loro prodotti nel tempo.

Sono disponibili tre tipi di rettifica prezzo: percentuale sottratta, importo sottratto e prezzo. Una rettifica prezzo del tipo percentuale sottratta o importo sottratto viene sempre applicata a una transazione di vendita. Tuttavia, una rettifica prezzo del tipo di prezzo viene applicata solo se il prezzo rettificato è inferiore al prezzo stabilito utilizzando il prezzo base o il prezzo dell'accordo commerciale. Pertanto, se il prezzo impostato in una rettifica di prezzo è superiore al prezzo non rettificato, la rettifica del prezzo non viene utilizzata.

## <a name="determining-price-for-a-product-in-a-transaction"></a>Determinazione del prezzo per un prodotto in una transazione

Il calcolo del prezzo e dello sconto su una transazione utilizza il principio di ricerca del prezzo migliore per il cliente. In base a questo principio, se viene trovato più di un prezzo, viene utilizzato il prezzo più basso. Inoltre, viene utilizzata la combinazione di sconti che produce l'importo di sconto maggiore per l'intera transazione. In alcuni casi, uno sconto minore deve essere utilizzato su un singolo prodotto, in modo che ulteriori sconti possano essere applicati ad altri prodotti nella transazione.

L'unica eccezione al principio di ricerca del prezzo migliore per il cliente è un'opzione per gli sconti gamma meno costosi. Questa opzione consente sconti meno costosi che favoriscono il rivenditore quando i prodotti vengono selezionati e raggruppati. Pertanto, quando una transazione include più prodotti di quelli necessari per l'idoneità allo sconto meno costoso, il motore di determinazione del prezzo seleziona i prodotti che producono il minor sconto possibile per il cliente.

Il motore dei prezzi restituisce tre prezzi per ogni prodotto: il prezzo base, il prezzo dell'accordo commerciale e il prezzo attivo.

Il prezzo base è solo la proprietà sul prodotto ed è uguale per tutti ovunque.

Nell'accordo commerciale sul prezzo di vendita, se l'opzione **Trova successivo** è impostata su **Sì**, il prezzo più basso trovato per gli accordi commerciali sui prezzi di vendita applicabili viene utilizzato come prezzo dell'accordo commerciale. Gli accordi commerciali possono essere trovati utilizzando i gruppi di prezzi o il codice conto **TUTTO**. In alternativa, gli accordi commerciali possono essere assegnati direttamente a un cliente. Se l'opzione **Trova successivo** è impostata su **No**, viene utilizzato il primo prezzo dell'accordo commerciale trovato. Se non vengono trovati accordi commerciali relativi ai prezzi di vendita, il prezzo dell'accordo commerciale viene impostato come pari al prezzo base.

Il prezzo attivo viene calcolato prendendo il prezzo dell'accordo commerciale e applicando la maggiore rettifica prezzo applicabile al prodotto. Se non viene trovata alcuna rettifica prezzo o se il prezzo attivo calcolato è superiore al prezzo dell'accordo commerciale, il prezzo attivo è pari al prezzo dell'accordo commerciale. Tenere presente che non è possibile aumentare il prezzo di un prodotto utilizzando una rettifica prezzo. Le rettifiche di prezzo applicabili possono essere trovate solo utilizzando i gruppi di prezzi assegnati a un canale, un catalogo, un'affiliazione o un programma fedeltà.

## <a name="category-price-rules"></a>Regole prezzi di categoria

Le regole dei prezzi di categoria presenti in Commerce offrono un modo semplice per creare nuovi accordi commerciali per tutti i prodotti di una categoria. Questa funzione consente inoltre di trovare automaticamente gli accordi commerciali esistenti per i prodotti nella categoria e la relativa scadenza.

Quando si seleziona l'opzione di scadenza degli accordi commerciali esistenti, il sistema crea un nuovo giornale di registrazione accordi commerciali per i prodotti della categoria con un accordo commerciale attivo. Tuttavia, il giornale deve essere registrato manualmente. Inoltre, le regole dei prezzi delle categorie possono trovare accordi commerciali esistenti solo se si utilizza la stessa regola dei prezzi (ovvero, se si crea una nuova regola dei prezzi in cui viene utilizzata la stessa categoria precedente). Se non si utilizza la stessa regola dei prezzi, gli accordi commerciali esistenti non saranno scaduti.

I prezzi possono essere aumentati o diminuiti utilizzando i campi della **Regola prezzo** e **Base prezzo** dei prezzi di categoria.

- Nel campo **Regola prezzo**, selezionare il tipo di variazione prezzo da utilizzare:

    - **Ricarico**: una percentuale della base di prezzo viene utilizzata per calcolare il prezzo di vendita. Ad esempio, un prodotto che costa 10,00 e viene venduto per 15,00 ha un ricarico del 50%.
    - **Margine**: una percentuale del prezzo di vendita utilizzata per calcolare l'importo del profitto. Ad esempio, un prodotto che costa 10,00 e viene venduto per 15,00 ha un margine del 33,3%.
    - **Importo fisso**: un importo aggiunto alla base di prezzo utilizzata per calcolare il prezzo di vendita. Ad esempio, un prodotto che costa 10,00 e viene venduto per 15,00 ha un importo fisso di 5,00.

- Nel campo **Base prezzo** selezionare il tipo di prezzo da modificare:

    - **Costo base**: l'importo che il rivenditore ha pagato al fornitore.
    - **Prezzo base**: il prezzo di vendita prima che vengano applicati gli accordi commerciali e le rettifiche prezzo.
    - **Prezzo corrente**: il prezzo di vendita dopo che sono stati applicati gli accordi commerciali e le rettifiche prezzo.

Per aggiornare facilmente i prezzi di vari prodotti di diverse categorie di prodotti, è possibile utilizzare le categorie di prodotti supplementari insieme alle regole dei prezzi delle categorie.

## <a name="best-practices"></a>Procedure consigliate

Microsoft SQL Server Express viene spesso utilizzato per i database dei canali a causa del costo (gratuito). Tenere presente che SQL Server Express presenta limitazioni hardware e limiti per la dimensione dei dati. Se non si pianifica correttamente, è possibile raggiungere rapidamente i limiti delle dimensioni dei dati di SQL Server Express. Questa considerazione si applica non solo ai prezzi, ma anche ad altre aree del prodotto. Di seguito sono riportate alcuni procedure consigliate utili per ridurre la dimensione dei dati:

- Se si utilizzano accordi commerciali e i prezzi cambiano, è necessario applicare la scadenza ai vecchi accordi commerciali impostando una data di fine. Nel tempo, tale approccio consente di ridurre il numero di accordi commerciali contenuti nel database del canale. Inoltre, consente di ridurre la quantità di dati con cui l'algoritmo di calcolo del prezzo deve funzionare.
- Se i prezzi variano in base alla variante del prodotto, considera l'utilizzo del prezzo base del prodotto come il prezzo della variante più comune. Quindi utilizza gli accordi commerciali solo per i prezzi varianti che sono eccezioni. Questo approccio consente di ridurre il numero di record dell'accordo commerciale. Poiché è semplice importare dati in Microsoft Dynamics 365, si potrebbe essere tentati di importare un accordo commerciale per ogni variante di ogni prodotto. Tuttavia, questo approccio può produrre molti accordi commerciali che hanno lo stesso valore. Di conseguenza, può aumentare inutilmente la dimensione dei dati.
- Commerce elabora i prezzi specifici della variante in ordine dal più specifico al meno specifico. Se una dimensione di prodotto non influisce sul prezzo, non è necessario definire accordi commerciali per essa. Ad esempio, un prodotto è disponibile in tre colori e quattro dimensioni, ma il prezzo varia solo in base alle dimensioni. Se si definisce un accordo commerciale per ogni variante, si creano 12 record. In alternativa, è possibile definire un accordo commerciale solo per ogni dimensione e lasciare vuota la dimensione Colore. In questo caso, si producono solo quattro record.

    In alternativa, se non tutti i valori di una dimensione producono un prezzo diverso, è possibile definire un accordo commerciale per la rappresentazione generale prodotto e lasciare vuote tutte le dimensioni prodotto. Quindi definire un accordo commerciale distinto solo per ciascun valore di dimensione che produce un prezzo diverso. Ad esempio, se la taglia XXL ha un prezzo più alto, ma tutte le altre taglie hanno lo stesso prezzo, sono necessari solo due accordi commerciali: uno per la rappresentazione generale prodotto e uno per la taglia XXL.

## <a name="prices-that-include-tax-vs-prices-that-exclude-tax"></a>Prezzi comprensivi di imposte e prezzi senza imposte

Quando si impostano i prezzi di vendita in Dynamics 365, non si specifica se il valore del prezzo è comprensivo o meno di imposte. Il valore è solo il prezzo. Tuttavia, l'impostazione **Prezzo comprensivo di IVA** nei canali consente di configurare i canali in modo che i prezzi siano o meno comprensivi di IVA. Questa impostazione viene configurata nel canale e può essere modificata anche in una singola società.

Se si utilizzano sia tipi di prezzi comprensivi di imposte che non comprensivi di imposte, è molto importante configurare i prezzi correttamente, poiché l'importo totale che il cliente paga cambierà se il campo **Prezzo comprensivo di IVA** del canale è stato modificato.

## <a name="differences-between-retail-pricing-and-non-retail-pricing"></a>Differenze tra i prezzi di vendita al dettaglio e i prezzi non al dettaglio

Un unico motore di determinazione del prezzo viene utilizzato per calcolare i prezzi in tutti i canali: Servizio clienti, Punto vendita al dettaglio e Punto vendita online. In questo modo è possibile consentire scenari commerciali unificati.

La determinazione dei prezzi è progettata per funzionare con entità di vendita al dettaglio anziché con entità di vendita non al dettaglio. In particolare, è progettata per impostare i prezzi per punto vendita, non per magazzino.

Il motore di determinazione del prezzo **non supporta** le seguenti funzionalità dei prezzi:

- L'impostazione dei prezzi in base alle dimensioni di immagazzinamento del sito o del sito e del magazzino non è supportata. Se si specifica solo la dimensione del sito negli accordi commerciali, il motore dei prezzi ignora il sito e applica l'accordo commerciale a tutti i siti. Se si specificano sia il sito sia il magazzino, il comportamento è indefinito/non testato perché è previsto che i rivenditori utilizzino i gruppi di prezzi del negozio per controllare i prezzi per ciascun negozio/magazzino.
- I prezzi basati sugli attributi non sono supportati.
- Il pass-through dello sconto fornitore non è supportato.
- Il motore di determinazione dei prezzi standard di Supply Chain Management supporta il calcolo dei prezzi in base alla "Data di spedizione richiesta" e alla "Data di ricevimento richiesta" insieme alla data corrente. Tuttavia, i prezzi al dettaglio attualmente non supportano questi valori. Il motivo è che per gli scenari B2C i clienti non si aspettano che la data di consegna richiesta influisca sul prezzo dell'articolo. In alcuni casi, i rivenditori hanno entrambe le operazioni B2B e B2C. Per le operazioni B2B è comune modificare i prezzi in base alle date di consegna. Questi rivenditori possono utilizzare i prezzi di Supply Chain Management per le operazioni B2B e i prezzi di vendita al dettaglio per le operazioni B2C. I prezzi di vendita al dettaglio sono utilizzati solo se l'utente dell'applicazione viene aggiunto come utente di servizio clienti, quindi i rivenditori possono assegnare determinati utenti che utilizzeranno i prezzi di Supply Chain Management e assegnarne alcuni che utilizzeranno i prezzi di vendita al dettaglio, ovvero questi utenti devono essere aggiunti come utenti di servizio clienti. Inoltre, la proprietà **Usa data odierna per calcolare i prezzi** nella sezione **Parametri di commercio > Prezzi e sconti > Varie** deve essere attivata. In questo modo possono continuare a utilizzare il valore del parametro di contabilità clienti di Data di spedizione richiesta o Data di ricezione richiesta per i prezzi di Supply Chain Management, ma i prezzi al dettaglio continueranno a utilizzare la data odierna per il calcolo dei prezzi.

Inoltre, **solo** il motore di determinazione del prezzo supporta le seguenti funzionalità dei prezzi:

- Il prezzo si basa sulle dimensioni prodotto, in ordine dal prezzo variante più specifico al prezzo variante meno specifico alla rappresentazione generale prodotto. Un prezzo impostato utilizzando due dimensioni prodotto (ad esempio Colore e Dimensione) viene utilizzato prima di un prezzo impostato utilizzando una sola dimensione prodotto (ad esempio, Dimensione).
- Lo stesso gruppo di prezzi può essere utilizzato per controllare i prezzi e gli sconti.

## <a name="pricing-api-enhancements"></a>Miglioramenti dell'API sui prezzi

Il prezzo è uno dei fattori più importanti che governano le decisioni di acquisto di molti clienti e la maggior parte di questi confronta i prezzi in vari siti prima di effettuare un acquisto. Per avere la certezza di fornire prezzi concorrenziali, i rivenditori vigilano sui loro concorrenti e spesso eseguono promozioni. Per consentire ai rivenditori di attirare clienti, è molto importante che la ricerca dei prodotti, la funzionalità di esplorazione, gli elenchi e la pagina dei dettagli visualizzino i prezzi più accurati.

In una versione imminente di Commerce, l'API (Application Programming Interface) **GetActivePrices** restituirà i prezzi che includono sconti semplici (ad esempio sconti a riga singola che non dipendono da altri articoli nel carrello). In questo modo, i prezzi visualizzati sono prossimi all'importo effettivo che i clienti pagheranno per gli articoli. Questa API includerà tutti i tipi di sconti semplici: sconti in base all'affiliazione, alla fedeltà, al catalogo e al canale. Inoltre, l'API restituirà i nomi e le informazioni di validità per gli sconti applicati, di modo che i rivenditori possano fornire una descrizione più dettagliata del prezzo e creare un senso di urgenza se la validità dello sconto scade ben presto.


[!INCLUDE[footer-include](../includes/footer-banner.md)]