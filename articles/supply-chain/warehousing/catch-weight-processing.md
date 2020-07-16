---
title: Elaborazione di prodotti a peso variabile con la gestione magazzino
description: Questo argomento descrive come utilizzare i modelli di lavoro e le direttive di ubicazione per stabilire come e dove il lavoro viene effettuato nel magazzino.
author: perlynne
manager: tfehr
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: c6598a9ac2beb799ddfc4e3cce182e1281ae8d03
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530537"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Elaborazione di prodotti a peso variabile con la gestione magazzino

[!include [banner](../includes/banner.md)]


## <a name="feature-exposure"></a>Esposizione della funzionalità

Per elaborare prodotti a peso variabile con la gestione magazzino, è necessario utilizzare una chiave di configurazione di licenza per attivare la funzionalità. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**. Quindi, nella scheda **Chiavi di configurazione**, espandere **Commercio \> Gestione magazzino e trasporto** e selezionare la casella di controllo **Peso variabile per il magazzino**.

> [!NOTE]
> Anche la chiave di configurazione di licenza **Gestione magazzino e trasporto** e le chiavi di configurazione di licenza **Distribuzione processo \> Peso variabile** devono essere attivate. Per impostare le chiavi di configurazione per il peso variabile, è anche necessario attivare la funzionalità utilizzando l'area di lavoro **Gestione funzionalità**. La funzionalità principale che deve essere attivata è **Elaborazione di prodotti a peso variabile con la gestione magazzino**. Sono due le funzionalità correlate ma facoltative che si potrebbe voler attivare **Lo stato delle scorte cambia per i prodotti a peso variabile** e **Utilizzare i tag peso variabile esistenti quando si segnalano gli ordini di produzione come finiti**.

Dopo l'attivazione della chiave di configurazione di licenza, quando si crea un prodotto rilasciato, è possibile selezionare **Peso variabile**. È inoltre possibile associare il prodotto rilasciato a un gruppo di dimensioni di immagazzinamento per il quale il parametro **Usa processi di gestione magazzino** è selezionato.

Prima di utilizzare il prodotto nella gestione magazzino, è necessario effettuare alcune impostazioni di base specifiche del prodotto per il peso variabile:

- Definire la conversione del peso nominale tra l'unità di peso variabile (scatola) e l'unità di magazzino (chilogrammo \[kg\]) come parte di una definizione di conversione dell'unità.
- Definire le tolleranze di peso minima e massima nella configurazione dell'unità di peso variabile.
- Impostare un gruppo di sequenze unità dove l'unità a peso variabile è definita come unità di stockkeeping (SKU) minima.
- Impostare criteri di gestione articoli a peso variabile

Per ulteriori informazioni, vedere [Configurazione e gestione di articoli a peso variabile](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Rettifiche transazioni

Poiché il peso delle scorte all'arrivo in magazzino può differire da quello delle scorte quando escono dal magazzino, l'elaborazione del prodotto a peso variabile deve rettificare le scorte.

> [!NOTE]
> L'attività del dispositivo mobile attiverà le rettifiche delle transazioni solo se il metodo di scostamento del peso in uscita dei criteri di gestione di articoli a peso variabile è **Consenti scostamento peso**.

**Esempio 1**

Durante un processo di produzione **Dichiarazione di finito**, il peso di entrata acquisito di una targa che contiene otto scatole di un prodotto a peso variabile è di 80,1 chilogrammi. La targa viene quindi conservata nell'area dei prodotti finiti e durante il periodo di immagazzinamento, una parte del peso viene persa nell'atmosfera.

Successivamente, in un processo di prelievo ordine cliente, il peso acquisito della stessa targa è di 79,8 chilogrammi. Pertanto, nel sistema, si ha una differenza di peso nell'ambito del set di dimensioni fisiche.

In questo caso, il sistema rettifica automaticamente la differenza registrando una transazione per i 300 g mancanti.

**Esempio 2**

Nella relativa definizione, un prodotto è impostato per tollerare un peso minimo di 8 chilogrammi e un peso massimo di 12 chilogrammi per l'unità a peso variabile **Scatola**.

Si hanno due scatole del prodotto e il relativo peso registrato è 16 kg. Se un addetto del magazzino preleva e pesa una delle scatole e il peso acquisito è di 9 kg, l'altra scatola peserà 7 kg. Tuttavia, poiché il peso di 7 kg è inferiore al peso minimo, il sistema non esegue una rettifica automatica per aumentare di 1 kg il peso delle scorte disponibili.

Per impostare i conti in cui queste rettifiche sono registrate, accedere a **Gestione costi \> Impostazione criteri integrazione contabilità generale \> Registrazione**. Quindi , nella scheda **Scorte**, definire i seguenti conti:

- Conto perdite prodotti a peso variabile
- Conto profitti prodotti a peso variabile

## <a name="catch-weight-item-handling-policy"></a>Criteri di gestione articoli a peso variabile

I criteri di gestione articoli a peso variabile definiscono due flussi di gestione magazzino primari per gli articoli: quando il peso degli articoli viene acquisito e come viene acquisito.

È possibile definire quando il peso viene acquisito per l'elaborazione degli ordini cliente e di trasferimento. Il peso può essere acquisito durante uno dei seguenti processi:

- **Prelievo** - Il peso viene acquisito durante le righe di lavoro prelievo iniziali dell'ordine.
- **Imballaggio** - Il peso viene acquisito durante l'imballaggio manuale. È necessario inviare gli articoli a un centro d'imballaggio.

Se il peso effettivo viene acquisito nel centro d'imballaggio durante i processi di imballaggio del contenitore, agli addetti del magazzino non viene richiesto di acquisire il peso durante il lavoro di prelievo. Il peso medio dell'inventario fisico viene invece utilizzato come peso delle scorte magazzino prelevate che vengono trasferite all'area di imballaggio. Questo concetto si applica anche agli articoli a peso variabile tracciati con tag. Per gli articoli tracciati con tag, questi parametri determinano quando viene acquisito il tag. Il tag può essere acquisito al momento del prelievo utilizzando il dispositivo mobile o durante l'imballaggio manuale.

> [!NOTE]
> Perché l'opzione **Imballaggio** comporta l'aggiornamento delle scorte con il peso medio prelevato, ciò potrebbe generare una discrepanza che potrebbe causare una rettifica di profitti/perdite per prodotti a peso variabile e/o una differenza tra il peso delle scorte disponibili e il peso del tag di peso variabile.

Per i processi di gestione magazzino interni come il conteggio e le rettifiche, è possibile definire se il peso deve essere acquisito o meno. Se non viene acquisito, verrà utilizzato il peso nominale. Altre opzioni consentono di acquisire il peso per unità di peso variabile e per quantità di conteggio.

È inoltre possibile definire il modo in cui peso viene acquisito. In uno dei due flussi principali, i tag a peso variabile vengono tracciati e utilizzati per acquisire il peso. Nell'altro flusso, i tag a peso variabile non vengono tracciati.

- **Sì** - L'articolo utilizza tag a peso variabile. Ogni numero di tag rappresenta un'unità a peso variabile (scatola); un peso e altre informazioni sono associate al tag. Per i processi in uscita, viene utilizzato il peso associato al tag.
- **No** - L'articolo non utilizza tag a peso variabile. I processi di pesatura in entrata e in uscita sono basati sul peso effettivo acquisito durante ogni processo.

Il processo di tracciabilità di tag a peso variabile può essere utilizzato per gli articoli il cui peso non cambierà durante il periodo di immagazzinamento. Il peso verrà acquisito solo durante il processo di magazzino in entrata. Durante il processo in uscita, i tag a peso variabile saranno soltanto analizzati e i pesi associati ai tag saranno utilizzati per l'elaborazione transazionale in uscita.

Un altro parametro importante correlato all'elaborazione dei tag di peso variabile è **Metodo di tracciabilità dimensioni con tag di peso variabile**. I tag possono essere tracciati parzialmente o completamente. Se un tag viene tracciato parzialmente, tiene traccia delle dimensioni del prodotto, delle dimensioni di tracciabilità e dello stato delle scorte. Se un tag viene tracciato completamente, tiene traccia delle dimensioni del prodotto, delle dimensioni di tracciabilità e di **tutte** le dimensioni di immagazzinamento.

Inoltre, quando un articolo viene tracciato con tag, è disponibile un parametro **Metodo di acquisizione tag in uscita**. È possibile impostare questo parametro di modo che il tag venga sempre richiesto per le transazioni in uscita dal dispositivo mobile. In alternativa, è possibile impostare il parametro di modo che i tag siano richiesti solo quando necessari. Ad esempio, ci sono cinque tag di peso variabile nelle scorte per una determinata targa e si è indicato di voler selezionare tutti e cinque i tag nella targa. In questo caso, se il parametro **Metodo di acquisizione tag in uscita** è impostato su **Richiedi tag solo quando necessario**, i cinque tag vengono selezionati automaticamente. Non è necessario eseguire la scansione di ogni tag. Se il parametro è impostato su **Richiedi sempre tag**, è necessario eseguire la scansione di ogni tag, anche se tutti e cinque i tag vengono selezionati.

> [!NOTE]
> Di norma, i tag vengono acquisiti e aggiornati solo dalle voci di menu del dispositivo mobile. Tuttavia, ci sono alcuni scenari in cui i tag vengono acquisiti altrove (ad esempio nella stazione di imballaggio manuale). Tuttavia, in generale, le voci di menu del dispositivo mobile devono essere utilizzate per tutte le attività di magazzino nel caso si utilizzano i tag.

### <a name="how-to-capture-catch-weight"></a>Come acquisire il peso variabile

**Quando si utilizza la tracciabilità dei tag a peso variabile**, un tag deve essere sempre creato per ogni unità di peso variabile ricevuta e ogni tag deve sempre essere associato a un peso.

Ad esempio, **Scatola** è l'unità a peso variabile e si riceve un pallet di otto scatole. In questo caso, otto tag a peso variabile univoci devono essere creati e un peso deve essere associato a ogni tag. A seconda del tag a peso variabile in entrata, è possibile acquisire il peso di tutte e otto le scatole, e il peso medio può quindi essere distribuito a ciascuna scatola, oppure un peso univoco per ogni scatola.
Quando si utilizza la funzionalità **Utilizzare i tag peso variabile esistenti quando si segnalano gli ordini di produzione come finiti** con il processo abilitato tramite una voce di menu di un dispositivo mobile, l'inventario viene aggiornato in base alle informazioni esistenti sull'etichetta del peso variabile. Di conseguenza, l'app di magazzino non richiede l'acquisizione dei dati dei tag di peso variabile come parte di un report di produzione come operazione finita.

**Quando la tracciabilità dei tag a peso variabile non viene utilizzata**, il peso può essere acquisito per ogni set di dimensioni (ad esempio, per ogni targa e dimensione di tracciabilità). In alternativa, il peso può essere acquisito in base a un livello di aggregazione, ad esempio cinque targhe (pallet).

Per i metodi di acquisizione del peso in uscita, l'opzione **Per unità di peso variabile** consente di specificare che la pesatura deve essere eseguita per ciascuna unità di peso variabile (ad esempio per scatola). L'opzione **Per unità di prelievo** consente di specificare che il peso deve essere acquisito in base alla quantità che verrà prelevata (ad esempio, tre scatole). Tenere presente che per i processi di prelievo della riga di produzione e di movimenti interni, il peso medio verrà utilizzato se l'opzione **Non acquisito** è utilizzata.

Più metodi di acquisizione del peso sono definiti nei criteri di gestione articoli a peso variabile. Ogni parametro del metodo di acquisizione del peso viene utilizzato da varie transazioni. Nella tabella seguente è indicato quali parametri sono utilizzati da quali transazioni.

| Metodo                                     | Transazione                                |
|--------------------------------------------|--------------------------------------------|
| Metodo di acquisizione peso in uscita           | Prelievo vendite, Prelievo trasferimento            |
| Metodo di acquisizione peso prelievo produzione | Prelievo produzione, Consumo di produzione |
| Metodo di acquisizione peso movimentazione           | Movimento                                   |
| Quando acquisire la correzione di peso       | Rettifiche, Conteggio                      |
| Conteggio metodo di acquisizione peso           | Conteggio                                   |
| Metodo di acquisizione peso trasferimento di magazzino | Trasferimento di magazzino                         |

Per impedire ai processi di prelievo di gestione magazzino di acquisire pesi che danno luogo a rettifiche di profitti/perdite prodotti a peso variabile, è possibile utilizzare il metodo di scostamento del peso in uscita. metodo di scostamento del peso in uscita si applica durante i seguenti processi con dispositivo mobile: prelievo vendite, prelievo trasferimento, prelievo produzione, movimenti, conteggio e trasferimenti magazzino. È possibile usare l'opzione **Limita scostamento peso** se il peso dell'articolo a peso variabile non varia durante l'immagazzinamento e se non sono necessarie rettifiche di profitti/perdite per prodotti a peso variabile. È possibile usare l'opzione **Consenti scostamento peso** se il peso dell'articolo può variare e se sono necessarie rettifiche di profitti/perdite per prodotti a peso variabile quando si registra una variazione del peso.

## <a name="unsupported-scenarios"></a>Scenari non supportati

Non tutti i flussi di lavoro supportano l'elaborazione di prodotti a peso variabile con la gestione magazzino. Attualmente, vengono applicate le restrizioni descritte di seguito. Si applicano a tutti gli articoli a peso variabile, indipendentemente dal fatto che abbiano o meno dei tag.

### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configurazione di prodotti a peso variabile per processi di gestione magazzino

- Solo l'elaborazione della formula viene supportata per i prodotti a peso variabile (non la distinta base).
- I prodotti a peso variabile non possono essere associati a un gruppo di dimensioni di tracciabilità utilizzando la dimensione Proprietario.
- I prodotti a peso variabile non possono essere utilizzati come servizi.
- I prodotti a peso variabile possono essere utilizzati come "prodotti stoccati" solo come parte del gruppo di modelli di articoli.
- I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per la tracciabilità "Attiva in processo di vendita".
- I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per l'acquisizione di numeri di serie. Di conseguenza, i prodotti non possono essere trasferiti da un "vuoto" a un numero di serie durante il processo di prelievo/imballaggio.
- I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per la registrazione di numeri di serie prima del consumo.
- I prodotti a peso variabile abilitati da variante non possono essere utilizzati insieme alla funzionalità per la conversione delle unità di misura di variante.
- I prodotti a peso variabile non possono essere contrassegnati come kit di prodotti di commercio.
- I prodotti a peso variabile possono essere utilizzati solo con un gruppo di sequenze unità che ha unità movimentazione a peso variabile e l'unità a peso variabile come sequenza inferiore.
- Per i prodotti a peso variabile, è possibile convertire l'unità di magazzino in unità a peso variabile solo se la conversione genera una quantità nominale maggiore di 1.
- L'impostazione di codici a barre per prodotti a peso variabile non supporta un'impostazione peso variabile.

### <a name="order-processing"></a>Elaborazione ordine

- La creazione di Advance Shipping Notice (strutture di imballaggio/ASN) non supporta informazioni relative al peso.
- La quantità ordine deve essere gestita in base all'unità a peso variabile.

### <a name="inbound-warehouse-processing"></a>Elaborazione di magazzino in entrata

- Il ricevimento di targhe richiede che i pesi siano assegnati durante la registrazione in quanto le informazioni relative al peso non sono supportate nell'Advance Shipping Notice. Quando si utilizzano i processi dei tag a peso variabile, il numero di tag deve essere assegnato manualmente per unità a peso variabile.
- Il controllo qualità in entrata non è supportato per i prodotti a peso variabile. Se configurato, il controllo qualità verrà ignorato.

### <a name="inventory-and-warehouse-operations"></a>Operazioni relative a scorte e magazzino

- La creazione manuale di ordini di quarantena non è supportata per i prodotti a peso variabile.
- Il movimento manuale delle scorte relativo al lavoro aperto non è supportato per i prodotti a peso variabile.
- Il caricamento targa per inizializzare le scorte di magazzino non è supportato per i prodotti a peso variabile.
- I processi di bilanciamento del batch non sono supportati per i prodotti a peso variabile.
- La gestione dell'inventario fisico negativo non è supportata per i prodotti a peso variabile.
- Il contrassegno scorte non può essere utilizzato per i prodotti a peso variabile.

### <a name="outbound-warehouse-processing"></a>Elaborazione di magazzino in uscita

- La funzionalità per il prelievo del cluster non è supportata per i prodotti a peso variabile.
- L'elaborazione di magazzino per prelievo e imballaggio non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, il lavoro definito in un modello di lavoro può essere eseguito automaticamente.
- Per i prodotti a peso variabile, il sistema non supporta l'elaborazione manuale presso il centro d'imballaggio in cui il lavoro di prelievo dei contenitori imballati viene creato dopo la chiusura dei contenitori.
- La funzionalità per la scansione pezzo per pezzo non è supportata per i prodotti a peso variabile.

### <a name="production-processing"></a>Elaborazione della produzione

- Per i prodotti a peso variabile, sono supportati solo gli ordini batch per prodotti formula.
- La funzionalità kanban non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, i numeri di serie non possono essere registrati prima del consumo.
- La funzionalità per lo storno delle targhe dalla produzione non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, la dichiarazione di finito non può essere registrata mediante il numero di serie.

### <a name="transportation-management-processing"></a>Elaborazione della gestione trasporto

- L'elaborazione del workbench di allestimento del carico non è supportata per i prodotti a peso variabile.
- Le righe di richiesta trasporto non sono supportate per i prodotti a peso variabile.

### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Altri restrizioni e comportamenti per l'elaborazione di prodotti a peso variabile con la gestione magazzino

- Durante i processi di prelievo in cui all'utente non viene richiesto di identificare le dimensioni di tracciabilità, l'assegnazione del peso viene effettuata in base al peso medio. Questo comportamento si verifica quando, ad esempio, una combinazione di dimensioni di tracciabilità viene utilizzata nella stessa ubicazione e, dopo che un utente elabora il prelievo, solo un valore di dimensione di tracciabilità rimane nell'ubicazione.
- Quando le scorte sono prenotate per un prodotto a peso variabile configurato per processi di gestione magazzino, la prenotazione viene eseguita in base al peso minimo definito, anche se questa quantità è l'ultima quantità movimentazioni disponibile. Questo comportamento differisce da quello degli articoli che non sono configurati per i processi di gestione magazzino. C'è un'eccezione a questa limitazione. Per il prelievo produzione, quando viene prelevata l'ultima quantità di movimentazione di un prodotto a peso variabile controllato in base al numero di serie, viene utilizzato il peso effettivo.
- I processi che utilizzano il peso per i calcoli di capacità (soglie ondata, interruzioni lavoro massime, numero massimo di contenitori, capacità del carico ubicazione e così via), non utilizzano il peso effettivo delle scorte. I processi sono invece basati sul peso di gestione fisica definito per il prodotto.
- In generale, la funzionalità Commerce non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, non è possibile aggiornare lo stato delle scorte in **Modifica stato magazzino**.

### <a name="catch-weight-tags"></a>Tag di peso variabile

Un tag di peso variabile può essere creato tramite un processo dell'app del magazzino, manualmente nel modulo oppure utilizzando un processo di entità di dati. Se un tag di peso variabile è associato a una riga in entrata di documento di origine, ad esempio una riga ordine fornitore, il tag verrà registrato. Se la riga viene utilizzata per l'elaborazione in uscita, il tag verrà aggiornato come spedito.

Oltre alle restrizioni attualmente in vigore per i prodotti a peso variabile, ai prodotti a peso variabile con tag si applicano altre restrizioni.

- Tutti gli aggiornamenti manuali delle scorte (ovvero gli aggiornamenti che non vengono eseguiti utilizzando un dispositivo mobile) devono includere gli aggiornamenti manuali corrispondenti dei tag di peso variabile associati poiché questi aggiornamenti non vengono eseguiti automaticamente. Ad esempio, i giornali di registrazione di rettifiche manuali aggiorneranno le scorte ma non i tag di peso variabile associati.
- È necessario aggiornare manualmente i tag di peso variabile per riflettere i movimenti di rifornimento. Questo perché il sistema non è in grado di acquisire pesi mentre elabora il lavoro di rifornimento e quindi registra invece il peso medio.
- Il ricevimento di targhe miste non attualmente supportato per gli articoli a peso variabile con tag.
- L'elaborazione della ricezione degli ordini di reso cliente può registrare tag di peso variabile. Tuttavia, il processo non verifica se il tag restituito è lo stesso tag originariamente spedito per un ordine cliente.
- La voce di menu del dispositivo mobile che ha il codice attività **Registra consumo materiali** al momento non supporta la registrazione di tag di peso variabile.
- Sebbene supportati, i processi di conteggio per gli articoli a peso variabile con tag sono limitati. Ad esempio, è possibile utilizzare le opzioni del dispositivo mobile per il conteggio degli articoli di peso di cattura con tag e viene utilizzato il peso medio. Tuttavia, i tag di peso variabile non vengono aggiornati automaticamente mediante la transazione di conteggio. Una volta completata la transazione di conteggio, i tag di peso variabile devono essere aggiornati manualmente in modo da riflettere le scorte. Se gli articoli che non erano originariamente in un'ubicazione vengono conteggiati in quella ubicazione, viene utilizzato il peso nominale.
- Il consolidamento delle targhe attualmente non supporta gli articoli a peso variabile con tag.
- La funzionalità di storno lavoro non è supportata per gli articoli a peso variabile che sono tracciati con il numero di tag.

> [!NOTE]
> Le informazioni precedenti sui tag di peso variabile sono valide solo se il prodotto a peso variabile ha un metodo di tracciabilità delle dimensioni con tag di peso variabile completamente tracciato (ovvero, se il parametro **Metodo di tracciabilità dimensioni con tag di peso variabile** nei criteri di gestione articoli a peso variabile è impostato su **Dimensioni prodotto, dimensioni di tracciabilità e tutte le dimensioni di immagazzinamento**). Se l'articolo a peso variabile è tracciato solo parzialmente con tag (ovvero se il parametro **Metodo di tracciabilità dimensioni con tag di peso variabile** nei criteri di gestione articoli a peso variabile è impostato su **Dimensioni prodotto, dimensioni di tracciabilità e stato scorte**) si applicano ulteriori restrizioni. Poiché in questo non c'è visibilità tra tag e scorte, alcuni scenari aggiuntivi non sono supportati.
