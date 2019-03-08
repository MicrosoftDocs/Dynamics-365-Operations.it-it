---
title: Elaborazione di prodotti a peso variabile con la gestione magazzino
description: Questo argomento descrive come utilizzare i modelli di lavoro e le direttive di ubicazione per stabilire come e dove il lavoro viene effettuato nel magazzino.
author: perlynne
manager: AnnBe
ms.date: 01/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 5161860e3b1c5b0ae795d109159268be085ec5af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "334061"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Elaborazione di prodotti a peso variabile con la gestione magazzino
[!include [preview banner](../../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

**Esposizione della funzionalità**

Per elaborare prodotti a peso variabile con la gestione magazzino, è necessario utilizzare una chiave di configurazione di licenza per attivare la funzionalità. Accedere a **Amministrazione sistema \> Impostazioni \> Configurazione licenza**. Quindi, nella scheda **Chiavi di configurazione**, espandere **Commercio \> Gestione magazzino e trasporto** e selezionare la casella di controllo **Peso variabile per il magazzino**.

> [!NOTE]
> Anche la chiave di configurazione di licenza **Gestione magazzino e trasporto** e le chiavi di configurazione di licenza **Peso variabile processo di distribuzione** devono essere attivate.

Dopo l'attivazione della chiave di configurazione di licenza, quando si crea un prodotto rilasciato, è possibile selezionare **Peso variabile**. È inoltre possibile associare il prodotto rilasciato a un gruppo di dimensioni di immagazzinamento per il quale il parametro **Usa processi di gestione magazzino** è selezionato.

Prima di utilizzare il prodotto nella gestione magazzino, è necessario effettuare alcune impostazioni di base specifiche del prodotto per il peso variabile:

- Definire la conversione del peso nominale tra l'unità di peso variabile (scatola) e l'unità di magazzino (chilogrammo \[kg\]) come parte di una definizione di conversione dell'unità.
- Definire le tolleranze di peso minima e massima nella configurazione dell'unità di peso variabile.
- Impostare un gruppo di sequenze unità dove l'unità a peso variabile è definita come unità di stockkeeping (SKU) minima.
- Impostare criteri di gestione articoli a peso variabile

Per ulteriori informazioni, vedere [Configurazione e gestione di articoli a peso variabile](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Rettifiche transazioni

Poiché il peso delle scorte all'arrivo in magazzino può differire da quello delle scorte quando escono dal magazzino, l'elaborazione del prodotto a peso variabile deve rettificare le scorte.

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

Se il peso effettivo viene acquisito nel centro d'imballaggio durante i processi di imballaggio del contenitore, agli addetti del magazzino non verrà richiesto di acquisire il peso durante il lavoro di prelievo. Il peso medio dell'inventario fisico verrà invece utilizzato come peso delle scorte magazzino prelevate che vengono trasferite all'area di imballaggio.

Per i processi di gestione magazzino interni come il conteggio e la rettifica, è possibile definire se il peso deve essere acquisito o meno. Se non viene acquisito, verrà utilizzato il peso nominale.

È inoltre possibile definire il modo in cui peso viene acquisito. In uno dei due flussi principali, i tag a peso variabile vengono tracciati e utilizzati per acquisire il peso. Nell'altro flusso, i tag a peso variabile non vengono tracciati.

- **Sì** - L'articolo utilizza tag a peso variabile. Ogni numero di tag rappresenta un'unità a peso variabile (scatola); un peso e altre informazioni sono associate al tag. Per i processi in uscita, viene utilizzato il peso associato al tag.
- **No** - L'articolo non utilizza tag a peso variabile. I processi di pesatura in entrata e in uscita sono basati sul peso effettivo acquisito durante ogni processo.

Il processo di tracciabilità di tag a peso variabile può essere utilizzato per gli articoli il cui peso non cambierà durante il periodo di immagazzinamento. Il peso verrà acquisito solo durante il processo di magazzino in entrata. Durante il processo in uscita, i tag a peso variabile saranno soltanto analizzati e i pesi associati ai tag saranno utilizzati per l'elaborazione transazionale in uscita.

### <a name="how-to-capture-catch-weight"></a>Come acquisire il peso variabile

Quando si utilizza la tracciabilità dei tag a peso variabile, un tag deve essere sempre creato per ogni unità di peso variabile ricevuta e ogni tag deve sempre essere associato a un peso.

Ad esempio, **Scatola** è l'unità a peso variabile e si riceve un pallet di otto scatole. In questo caso, otto tag a peso variabile univoci devono essere creati e un peso deve essere associato a ogni tag. A seconda del tag a peso variabile in entrata, è possibile acquisire il peso di tutte e otto le scatole, e il peso medio può quindi essere distribuito a ciascuna scatola, oppure un peso univoco per ogni scatola.

Quando la tracciabilità dei tag a peso variabile non viene utilizzata, il peso può essere acquisito per ogni set di dimensioni (ad esempio, per ogni targa e dimensione di tracciabilità). In alternativa, il peso può essere acquisito in base a un livello di aggregazione, ad esempio cinque targhe (pallet).

Per i metodi di acquisizione del peso in uscita, è possibile definire se la pesatura viene eseguita per ogni unità a peso variabile (ovvero per scatola), oppure se il peso viene acquisito in base alla quantità che verrà prelevata (ad esempio, tre scatole). Tenere presente che per il processo di prelievo della riga di produzione, il peso medio verrà utilizzato se l'opzione **Non acquisito** è utilizzata.

## <a name="supported-scenarios"></a>Scenari supportati

Non tutti i flussi di lavoro supportano l'elaborazione di prodotti a peso variabile con la gestione magazzino. Attualmente, vengono applicate le restrizioni descritte di seguito.
 
### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configurazione di prodotti a peso variabile per processi di gestione magazzino

- Per i prodotti a peso variabile, il gruppo di dimensioni di immagazzinamento per gli articoli non può essere modificato (di conseguenza, è possibile utilizzare processi di gestione magazzino).
- Solo l'elaborazione della formula viene supportata per i prodotti a peso variabile (non la distinta base).
- I prodotti a peso variabile non possono essere associati a un gruppo di dimensioni di tracciabilità utilizzando la dimensione Proprietario.
- I prodotti a peso variabile non possono essere utilizzati come servizi.
- I prodotti a peso variabile possono essere utilizzati come "prodotti stoccati" solo come parte del gruppo di modelli di articoli.
- I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per la tracciabilità "Attiva in processo di vendita".
- I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per l'acquisizione di numeri di serie. Di conseguenza, i prodotti non possono essere trasferiti da un "vuoto" a un numero di serie durante il processo di prelievo/imballaggio.
- I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per la registrazione di numeri di serie prima del consumo.
- I prodotti a peso variabile abilitati da variante non possono essere utilizzati insieme alla funzionalità per la conversione delle unità di misura di variante.
- I prodotti a peso variabile non possono essere contrassegnati come kit di prodotti vendita al dettaglio.
- I prodotti a peso variabile possono essere utilizzati solo con un gruppo di sequenze unità che ha unità movimentazione a peso variabile e l'unità a peso variabile come sequenza inferiore.
- Per i prodotti a peso variabile, è possibile convertire l'unità di magazzino in unità a peso variabile solo se la conversione genera una quantità nominale maggiore di 1.
- L'impostazione di codici a barre per prodotti a peso variabile non supporta un'impostazione peso variabile.
 
### <a name="order-processing"></a>Elaborazione ordine

- L'elaborazione di ordini interaziendali non è supportata.
- La creazione di Advance Shipping Notice (strutture di imballaggio/ASN) non supporta informazioni relative al peso.
- La quantità ordine deve essere gestita in base all'unità a peso variabile.
 
### <a name="inbound-warehouse-processing"></a>Elaborazione di magazzino in entrata

- Il ricevimento di targhe richiede che i pesi siano assegnati durante la registrazione in quanto le informazioni relative al peso non sono supportate nell'Advance Shipping Notice. Quando si utilizzano i processi dei tag a peso variabile, il numero di tag deve essere assegnato manualmente per unità a peso variabile.
- Il ricevimento di targhe miste non è supportato per i prodotti a peso variabile.
 
### <a name="inventory-and-warehouse-operations"></a>Operazioni relative a scorte e magazzino

- La creazione manuale di ordini di quarantena non è supportata per i prodotti a peso variabile.
- Il movimento manuale delle scorte relativo al lavoro non è supportato per i prodotti a peso variabile.
- Il consolidamento di targhe non è supportato per i prodotti a peso variabile.
- Le modifiche allo stato delle scorte magazzino come parte di un'attività periodica non sono supportate per i prodotti a peso variabile.
- Le modifiche allo stato delle scorte definite da una query non sono supportate per i prodotti a peso variabile (non sono supportate nemmeno le modifiche allo stato delle scorte dell'ordine di controllo qualità).
- Per i prodotti a peso variabile, lo stato delle scorte non può essere modificato dalla pagina **Disponibili per ubicazione**.
- Per i prodotti a peso variabile, lo stato delle scorte non può essere modificato come parte del lavoro di movimento dell'app magazzino.
- Il caricamento targa per inizializzare le scorte di magazzino non è supportato per i prodotti a peso variabile.
- I processi di bilanciamento del batch non sono supportati per i prodotti a peso variabile.
- La gestione dell'inventario fisico negativo non è supportata per i prodotti a peso variabile.
- Il contrassegno scorte non può essere utilizzato per i prodotti a peso variabile.
 
### <a name="outbound-warehouse-processing"></a>Elaborazione di magazzino in uscita

- La funzionalità per il prelievo del cluster non è supportata per i prodotti a peso variabile.
- L'elaborazione di magazzino per prelievo e imballaggio non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, il lavoro non può essere completato nella pagina **Lavoro**.
- Per i prodotti a peso variabile, il lavoro definito in un modello di lavoro può essere eseguito automaticamente.
- La funzionalità per lo storno del lavoro non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, l'elaborazione manuale presso il centro d'imballaggio in cui il lavoro viene creato dopo la chiusura dei contenitori non è supportata.
- La funzionalità per la scansione pezzo per pezzo non è supportata per i prodotti a peso variabile.
 
### <a name="production-processing"></a>Elaborazione della produzione

- Per i prodotti a peso variabile, sono supportati solo gli ordini batch per prodotti formula.
- La funzionalità kanban non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, i numeri di serie non possono essere registrati prima del consumo.
- La funzionalità per lo storno delle targhe non è supportata per i prodotti a peso variabile.
- Per i prodotti a peso variabile, la dichiarazione di finito può essere registrata mediante il numero di serie.

### <a name="transportation-management-processing"></a>Elaborazione della gestione trasporto

- L'elaborazione del workbench di allestimento del carico non è supportata per i prodotti a peso variabile.
- Le righe di richiesta trasporto non sono supportate per i prodotti a peso variabile.
 
### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Altri restrizioni e comportamenti per l'elaborazione di prodotti a peso variabile con la gestione magazzino

- Quando si acquisiscono tag a peso variabile nell'ambito dell'elaborazione dell'app magazzino, l'utente non può annullare il flusso di lavoro.
- Durante i processi di prelievo in cui all'utente non viene richiesto di identificare le dimensioni di tracciabilità, l'assegnazione del peso viene effettuata in base al peso medio. Questo comportamento si verifica quando, ad esempio, una combinazione di dimensioni di tracciabilità viene utilizzata nella stessa ubicazione e, dopo che un utente elabora il prelievo, solo un valore di dimensione di tracciabilità rimane nell'ubicazione.
- Quando le scorte sono prenotate per un prodotto a peso variabile configurato per processi di gestione magazzino, la prenotazione viene eseguita in base al peso minimo definito, anche se questa quantità è l'ultima quantità movimentazioni disponibile. Questo comportamento differisce da quello degli articoli che non sono configurati per i processi di gestione magazzino.
- I processi che utilizzano il peso per i calcoli di capacità (soglie ondata, interruzioni lavoro massime, numero massimo di contenitori, capacità del carico ubicazione e così via), non utilizzano il peso effettivo delle scorte. I processi sono invece basati sul peso di gestione fisica definito per il prodotto.
- In generale, la funzionalità per la vendita al dettaglio non è supportata per i prodotti a peso variabile.
 
### <a name="catch-weight-tags"></a>Tag a peso variabile

Attualmente, la funzionalità per i tag a peso variabile è supportata solo nei seguenti scenari:

- Durante l'elaborazione del ricevimento di ordini fornitore tramite l'app magazzino.
- Durante l'elaborazione del ricevimento del carico tramite l'app magazzino.
- Per il ricevimento di targhe relativo a un carico ordine fornitore, l'assegnazione del peso è richiesta durante il processo di ricevimento. Di contro, per il ricevimento dell'ordine di trasferimento, viene utilizzato il peso dai dati di spedizione per l'ordine di trasferimento.
- Per il ricevimento di righe e articoli dell'ordine di trasferimento da un processo di gestione non di magazzino.
- L'elaborazione del ricevimento di ordini di reso cliente può registrare tag a peso variabile, ma l'elaborazione non verrà convalidata se i tag sono gli stessi originariamente spediti per una particolare riga ordine cliente.
- Quando si elabora uno stato delle scorte modificato utilizzando l'app magazzino.
- Quando un trasferimento tra magazzini viene eseguito mediante l'app magazzino.
- Quando si elabora la rettifica in entrata e in uscita via l'app magazzino.
- Quando il lavoro di prelievo viene elaborato per ordini cliente e di trasferimento (da notare che i tag a peso variabile non possono essere registrati per il prelievo di componenti di produzione).
- Quando le quantità prelevate sono ridotte dalle righe di carico, indipendentemente dall'uso o meno di contenitori.
- Quando i prodotti sono imballati in contenitori presso un centro d'imballaggio.
- Quando i contenitori vengono riaperti.
- Quando i prodotti della formula vengono registrati come finiti utilizzando l'app magazzino.
- Quando i carichi di trasporto sono elaborati mediante l'app magazzino.
