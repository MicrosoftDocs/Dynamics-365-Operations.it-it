---
title: Panoramica della configurazione dei prodotti
description: La necessità di configurare i prodotti per soddisfare requisiti speciali sta diventando la regola anziché l'eccezione, sia nelle relazioni tra aziende che nelle relazioni tra azienda e utente.
author: cvocph
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails, ConfigPartOf
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75083
ms.assetid: f08072b8-cb0b-43aa-9509-f5ec32caecd9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d37b1c8ed23bf93f0480c76e10b8aaed86fe2a2
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "6015979"
---
# <a name="product-configuration-overview"></a>Panoramica configurazione prodotto

[!include [banner](../includes/banner.md)]

La necessità di configurare i prodotti per soddisfare requisiti speciali sta diventando la regola anziché l'eccezione, sia nelle relazioni tra aziende che nelle relazioni tra azienda e utente.

Un produttore che supporta scenari di configurazione su ordine ha l'opportunità di soddisfare con più attenzione le esigenze del cliente. Inoltre, immagazzinando le merci semilavorate sotto forma di componenti generici anziché di prodotti finiti, il produttore può limitare il capitale che è legato al magazzino.  

Un passaggio efficace da un'impostazione da produzione a magazzino a una di configurazione su ordine richiede un'attenta analisi delle strutture dei prodotti, l'identificazione delle famiglie di prodotti e la componentizzazione. Per ridurre il numero di parti e ridurre al minimo il numero di beni coinvolti nel processo, è molto importante capire le interfacce dei prodotti che si progettano per la riutilizzabilità.  

Ci sono numerosi principi relativi alla modellazione della configurazione prodotti, ad esempio la modellizzazione in base alle regole, alle dimensioni e ai vincoli. Alcuni studi dimostrano che la metodologia basata sui vincoli può praticamente dimezzare il numero di righe di codice rispetto ad altri principi di modellazione. Di conseguenza, questa metodologia può ridurre il costo totale di proprietà (TCO). Con il passaggio da un modello basato su regole, che si basa su codice X++, a un modello basato su vincoli, non è più necessario disporre di una licenza per sviluppatori per gestire i modelli prodotto.

## <a name="product-configuration"></a>Configurazione prodotto

Il periodo di industrializzazione ha portato a grandi i risultati nella realizzazione di prodotti completi, di alta qualità e dai prezzi accessibili. Le economie di scala hanno permesso alla maggioranza delle persone del mondo industrializzato di acquistare automobili, TV, elettrodomestici e altri beni che la maggior parte di noi considera essenziali nella vita quotidiana.  

Dal momento che molti prodotti sono diventati beni di consumo, è sorta la necessità di differenziarli tra loro. La risposta immediata dei produttori a questa sfida è stata di creare delle varianti di ciascun prodotto, in modo da offrire ai clienti più alternative. La strategia ha aumentato le sfide legate alla previsione e ha portato anche a un aumento del costo di magazzino e dei prodotti invenduti che diventano obsoleti.  

Adottando una filosofia di configurazione su ordine, i produttori hanno l'opportunità di soddisfare la domanda dei clienti relativa a prodotti esclusivi e al contempo di ridurre o eliminare gli articoli di magazzino obsoleti. Quando si passa da una filosofia di produzione a magazzino a una filosofia di configurazione su ordine, una sfida che sorge nell'immediato è che la necessità di brevi lead time deve essere bilanciata da bassi livelli di magazzino.  

La chiave del successo in questo caso sta nell'analizzare attentamente il portafoglio di prodotti e nell'individuare dei modelli nelle caratteristiche dei prodotti e nei processi. L'obiettivo è di identificare componenti generici che possano essere prodotti con le stesse apparecchiature ed essere utilizzati in tutte le varianti.  

Il set di funzionalità di configurazione prodotto include un'interfaccia utente (UI) che fornisce una panoramica visiva della struttura del modello di configurazione prodotto e anche una sintassi dei vincoli dichiarativa che non deve essere compilata. Di conseguenza, le società che desiderano supportare una procedura di configurazione possono avviare il processo con maggiore facilità. Come spiegato nelle sezioni che seguono, la progettazione di un prodotto non richiede più l'intervento di uno sviluppatore per la generazione di un modello di configurazione, il test e il rilascio all'organizzazione di vendita.

## <a name="building-a-product-configuration-model"></a>Creazione di un modello di configurazione prodotti

Sono disponibili diversi metodi che un utente può adottare per sviluppare un modello di configurazione prodotto. Un'opzione consiste nel seguire un flusso sequenziale creando per prima cosa tutti i dati di riferimento, quali le rappresentazioni generali dei prodotti, i prodotti specifici e le risorse operative e successivamente includendoli come componenti, righe della distinta base, operazioni del ciclo di lavorazione e altri elementi del modello di configurazione prodotto. In alternativa, è possibile selezionare un approccio più iterativo creando innanzitutto il modello e quindi aggiungendo i dati di riferimento all'occorrenza.

### <a name="components"></a>Componenti

Un modello di configurazione prodotto è costituito da uno o più componenti che sono legati tra loro attraverso relazioni di sottocomponenti. I componenti vengono definiti una volta e possono quindi essere utilizzati molte volte in uno o più modelli di configurazione prodotto. I componenti sono gli elementi di base principali di modello di configurazione prodotto e quasi tutte le informazioni sul modello sono a loro correlate.

### <a name="attributes"></a>Attributi

Ciascun componente dispone di uno o più attributi che ne identificano le proprietà. Gli attributi sono gli elementi che gli utenti sceglieranno durante il processo di configurazione. Gli attributi controllano sia le relazioni sia all'interno di un componente che tra componenti attraverso l'inclusione in vincoli o calcoli. Tramite le condizioni applicate alle righe DBA, gli attributi possono essere utilizzati per determinare le parti fisiche di cui sarà composto il prodotto configurato. Inoltre, un attributo può anche controllare la proprietà di una riga DBA tramite un meccanismo di mapping. Una funzionalità simile è presente per le operazioni del ciclo di lavorazione in relazione alle impostazioni dell'inclusione e delle proprietà.

>[!NOTE]
> Quando si creano tipi di attributo, evitare di creare un numero elevato di valori per il dominio del tipo di attributo. in quanto questa operazione potrebbe rallentare la configurazione del prodotto.

### <a name="expression-constraints"></a>Vincoli di espressione

L'utilizzo di un modello di configurazione prodotto basato su vincoli implica la presenza di alcune limitazioni quando l'utente seleziona dei valori per i vari attributi. Tali limitazioni possono essere implementate come vincoli di espressione utilizzando il linguaggio OML (Optimization Modeling Language). In alternativa, un vincolo può essere implementato sotto forma di vincolo di tabella.

### <a name="table-constraints"></a>Vincoli di tabella

I vincoli di tabella possono essere definiti dall'utente o dal sistema.  

Un vincolo di tabella definito dall'utente è creato dall'utente. L'utente seleziona una combinazione di tipi di attributo per rappresentare le colonne della tabella e immette i valori dai domini dei tipi di attributo selezionati per creare le righe nel vincolo di tabella.  

Un vincolo di tabella definito dal sistema viene definito selezionando la tabella da utilizzare come riferimento quindi selezionando i campi dalla tabella per creare le colonne nel vincolo. Le righe del vincolo di tabella sono le righe della tabella di Supply Chain Management che sono presenti al momento della configurazione.  

Un vincolo di tabella viene incluso in un modello di configurazione prodotto facendo riferimento alla definizione del vincolo di tabella ed eseguendo il mapping degli attributi appropriati nel modello alle colonne del vincolo di tabella.

### <a name="calculations"></a>Calcoli

I calcoli rappresentano un meccanismo per eseguire le operazioni aritmetiche in un modello di configurazione. Ad esempio, un calcolo può determinare la lunghezza di uno specifico pezzo di materia prima o il tempo di elaborazione per un'operazione di lucidatura. I calcoli sono di importanza fondamentale e stabiliscono il valore di un attributo di destinazione dopo che tutti i valori degli attributi inclusi nell'espressione di calcolo diventano disponibili.

### <a name="subcomponents"></a>Sottocomponenti

I sottocomponenti rappresentano i nodi nella struttura del modello di configurazione prodotto. Per ciascuna relazione di sottocomponente, è necessario specificare un riferimento a una rappresentazione generale prodotto con la tecnologia di configurazione varianti impostata sulla configurazione basata su vincoli.

### <a name="user-requirements"></a>Requisiti utente

Un requisito utente ha tutti gli elementi costitutivi di un sottocomponente. L'unica differenza è che il requisito utente non è legato a una rappresentazione generale prodotto. L'effetto pratico di questa differenza è che qualsiasi riga DBA o operazione del ciclo di lavorazione definita nel contesto di un requisito utente viene compressa nella struttura DBA o nel ciclo di lavorazione del componente padre. Questo comportamento è simile al comportamento di una DBA fittizia.

### <a name="bom-lines"></a>Righe DBA

Le righe DBA vengono incluse per identificare la DBA di produzione per ciascun componente. Una riga DBA deve fare riferimento a un articolo e tutte le proprietà dell'articolo possono essere impostate su un valore fisso o essere mappate a un attributo.

### <a name="route-operations"></a>Operazioni ciclo di lavorazione

Le operazioni del ciclo di lavorazione sono incluse per identificare il ciclo di produzione. Un'operazione del ciclo di lavorazione deve fare riferimento a un'operazione definita e tutte le proprietà dell'operazione possono essere impostate su un valore fisso. Tutte le proprietà ad eccezione del fabbisogno all'origine possono essere mappate a un attributo anziché a un valore.

## <a name="validating-and-testing-a-product-configuration-model"></a>Convalida e test di un modello di configurazione prodotto

La convalida di un modello di configurazione prodotto può verificarsi a diversi livelli nel modello e può pertanto coprire vari ambiti. Il livello più basso riguarda un singolo vincolo di espressione. In questo caso, la convalida viene in genere eseguita dal responsabile di design prodotto per verificare la correttezza della sintassi di un'espressione.  

Analogamente, una condizione per una riga DBA o un'operazione del ciclo di lavorazione può essere convalidata in isolamento.  

È possibile eseguire la convalida anche per una definizione di vincolo di tabella definito dall'utente. In questo caso, l'utente può verificare che i valori immessi in ogni campo rientrino nel dominio dei tipi di attributo corrispondenti.  

Infine, è possibile eseguire la convalida di un modello di configurazione prodotto completo per verificare la correttezza della sintassi completa e l'osservanza di tutte le convenzioni di denominazione e di modellazione.

### <a name="testing"></a>Test

Il test di un modello è simile a eseguire una sessione di configurazione effettiva. L'utente può procedere nelle pagine di configurazione e verificare che la struttura del modello supporta il processo di configurazione. L'utente può verificare che i valori di attributo siano corretti e che le descrizioni di attributo lo guidino alla selezione dei valori corretti. Infine, una volta completata la sessione di test, il sistema tenta di creare la DBA e il ciclo di lavorazione che corrisponde ai valori degli attributi selezionati e visualizza un messaggio nel momento in cui si verifica un errore.

### <a name="the-configuration-page"></a>Pagina di configurazione

Per passare tra i componenti, fare clic su **Successivo** o fare clic sul componente nella struttura del modello di configurazione prodotto per selezionarlo.

## <a name="finalizing-a-model-for-configuration"></a>Finalizzazione di un modello per la configurazione

Una volta che un modello di configurazione prodotto è pronto per essere utilizzato negli scenari di configurazione su ordine, è necessario crearne una versione. Esistono comunque varie opzioni che migliorano l'esperienza di modellazione.

### <a name="user-interface"></a>Interfaccia utente

L'interfaccia utente di configurazione può essere modificata introducendo i gruppi di attributi in uno o più sottocomponenti. Tale raggruppamento può evidenziare le relazioni tra attributi specifici e aiutare l'utente che si occupa della configurazione a identificare l'area del prodotto attualmente attiva.

### <a name="templates"></a>Modelli

È possibile creare uno o più modelli di configurazione per velocizzare il processo di configurazione. In alternativa, è possibile creare dei modelli per promuovere specifiche combinazioni di attributi, ad esempio come quando una campagna di vendita si concentra su un set specifico di funzionalità del prodotto.

### <a name="translations"></a>Traduzioni

Se il prodotto verrà venduto in altri paesi, è possibile inserire le traduzioni del testo che viene visualizzato nell'interfaccia utente di configurazione. Questo testo include non solo i campi dei nomi e delle descrizioni ma anche i valori di testo degli attributi.

### <a name="versions"></a>Versioni

L'ultimo passaggio, e il più importante, nel processo di completamento consiste nel creare una versione del modello di configurazione prodotto. La versione rappresenta la relazione tra la rappresentazione generale prodotto, che può essere selezionata per la configurazione su un ordine o in una riga di offerta, e il modello di configurazione prodotto. Per essere utilizzata in una sessione di configurazione, la versione deve essere prima approvata e attivata.

## <a name="extending-a-product-configuration-model-through-the-api"></a>Estensione di un modello di configurazione prodotto nell'API

È stata implementata un'API dedicata affinché i partner e altri che dispongono di una licenza per sviluppatori possano estendere le funzionalità di un modello di configurazione prodotto. L'obiettivo principale è stato quello di stabilire un meccanismo che consente ai partner e ai clienti che utilizzano il Configuratore prodotti esistente di eseguire la migrazione del codice integrato nei modelli del Configuratore prodotti verso l'API. In questo modo, possono eseguire la migrazione dei modelli dal Configuratore prodotti a una configurazione prodotto. Tuttavia, i nuovi partner e i nuovi clienti possono inoltre beneficiare dell'utilizzo dell'API per estendere nuovi modelli di configurazione prodotto.

L'API è implementata utilizzando un set di classi **PCAdaptor** che espongono la struttura dati dei modelli di configurazione prodotto. Un'istanza della classe **PCAdaptor** deve essere creata per ciascun modello che verrà esteso. Dopo che una sessione di configurazione viene completata, il sistema verifica la presenza di un'istanza di questa classe e la esegue se la trova.  

Nel seguente diagramma di flusso API viene illustrato il processo.  

[![Diagramma di flusso](./media/product_configuration_2.png)](./media/product_configuration_2.png)  

## <a name="configure-products"></a>Configurare i prodotti

### <a name="configure-one-or-more-products"></a>Configurare uno o più prodotti

È possibile configurare i prodotti dalle seguenti posizioni:

- Riga ordine cliente
- Riga offerta di vendita
- Riga ordine fornitore
- Righe dell'ordine di produzione
- Riga di richiesta articoli (progetto)

Lo scopo della configurazione è di creare una variante distinta del prodotto che soddisfi le esigenze del cliente. Per ogni nuova configurazione viene creato un ID di configurazione univoco. Questo ID consente il monitoraggio in magazzino.

### <a name="multiple-sites-and-intercompany-considerations"></a>Molteplici siti e considerazioni interaziendali

Se la configurazione viene effettuata presso un sito, o una società, diverso dal sito, o dalla società, in cui avviene la produzione, la DBA e il ciclo di lavorazione verranno creati e inseriti presso il sito del fornitore nella società fornitrice. La variante prodotto verrà rilasciata a tutte le società che partecipano alla supply chain.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]