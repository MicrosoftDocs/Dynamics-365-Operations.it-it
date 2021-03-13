---
title: Identificatori di prodotto
description: Questo argomento fornisce informazioni sui vari tipi di identificatori di prodotto e descrive come è possibile aggiungere identificatori di prodotto nei dati del prodotto.
author: cvocph
manager: tfehr
ms.date: 03/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductEntityIdentifierCode, EcoResProductListPage, EcoResProductDetailsExtended, EcoResProductVariantsPerCompany
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: f28193f9671bcae1345d5c1085ea3f2446e6e088
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011372"
---
# <a name="product-identifiers"></a>Identificatori di prodotto

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sui vari tipi di identificatori di prodotto e descrive come è possibile aggiungere identificatori di prodotto nei dati del prodotto.

Quando si utilizzano prodotti nello shop floor o in un magazzino in Microsoft Dynamics ERP oppure in Microsoft Dynamics CRM, è necessario disporre di una strategia idonea per l'identificazione di questi prodotti e delle varianti prodotto.

## <a name="unique-product-numberproduct-id"></a>ID prodotto/numero di prodotto univoco

In Dynamics 365 Supply Chain Management, l'identificatore principale di un prodotto è il numero prodotto, vale a dire l'ID prodotto univoco. Questo numero può essere generato automaticamente da una sequenza numerica oppure associato manualmente a un prodotto. Per le varianti prodotto, i numeri possono essere definiti tramite il modello di nomenclatura di prodotto.

In molti casi, il numero di prodotto non viene originariamente creato in Dynamics 365 Supply Chain Management. È invece associato a un prodotto in un sistema PLM (Product Lifecycle Management) o in un sistema PDM (Product Data Management). In questo caso, si utilizzano le entità di dati per importare i prodotti e le varianti prodotto. Supply Chain Management quindi utilizza i numeri in tutte le operazioni.

Dopo l'implementazione di Supply Chain Management, è necessario prestare speciale attenzione alla strategia per i numeri di prodotto. Un buon sistema di numerazione migliora i flussi logici e aiuta a prevenire gli errori. Un buon identificatore di prodotto contiene un massimo di 15 caratteri. Idealmente, contiene meno di 10 caratteri e non include più di cinque caratteri di classificazione. È anche possibile utilizzare nomi di ricerca per abilitare ricerche rapide. Il nome di ricerca è un nome aggiuntivo che rappresenta le classificazioni di un prodotto.

Quando si utilizza Microsoft Dataverse, il numero prodotto in Supply Chain Management è anche il numero prodotto in Microsoft Dataverse. Le varianti prodotto vengono sincronizzate con il Dataverse come prodotti specifici.

## <a name="item-number-and-product-dimensions"></a>Numero di articolo e dimensioni prodotto

Il numero di articolo costituisce l'identificatore del prodotto utilizzato da una persona giuridica specifica. Idealmente, il numero articolo deve essere identico al numero prodotto. Se la nomenclatura differisce in base alla persona giuridica, diventa difficile seguire un prodotto nella supply chain e vengono introdotti complessi processi di rietichettatura e di riferimento. Questo modello viene mantenuto per compatibilità con le versioni precedenti, vale a dire Microsoft Dynamics AX 2009 e versioni precedenti. È tuttavia consigliabile eliminare gli identificatori che sono specifici a persone giuridiche ogni volta che è possibile. È consigliabile utilizzare il numero prodotto univoco come identificatore principale.

Inoltre, una variante prodotto non può essere identificata in modo univoco da un numero di articolo. Richiede sempre la combinazione di un numero di articolo e delle dimensioni prodotto definite nella rappresentazione generale prodotto. Tale requisito può risultare scomodo e rallentare i processi di identificazione. Anche per questo motivo, è consigliabile utilizzare il numero prodotto univoco invece del numero articolo ogni volta che è possibile.

Molte pagine hanno ancora il numero di articolo e le dimensioni prodotto degli identificatori principali. I numeri prodotto possono tuttavia essere utilizzati per le ricerche. In **Vendite e marketing** &gt; **Impostazioni** &gt; **Ricerca** &gt; **Parametri ricerca** è possibile modificare la ricerca in modo da utilizzare i numeri prodotto invece dei numeri articolo come principale strategia di ricerca. Se si imposta l'opzione **Abilita ricerca prodotto** su **Sì**, la ricerca non mostrerà solo le rappresentazioni generali prodotto ma anche le varianti prodotto. Per ulteriori informazioni, vedere [Ricerca di prodotti e varianti prodotto durante la registrazione ordine](search-products-product-variants.md).

Inoltre, sarà possibile cercare e applicare un filtro al numero prodotto, al nome prodotto e alla descrizione e agli ID di dimensione prodotto della variante prodotto. Quando si seleziona una variante, verranno selezionati il numero di articolo correlato e tutti gli ID di dimensioni prodotto. Di conseguenza, è possibile individuare e selezionare con maggiore facilità la variante corretta. Questa impostazione è vivamente consigliata se si utilizzano le varianti prodotto e il numero di prodotto univoco come identificatori principali dei prodotti. La sola eccezione potrebbe essere il settore della moda, dove i processi aziendali spesso richiedono la selezione della rappresentazione generale del prodotto prima della selezione di una variante. È necessario valutare attentamente questa opzione prima dell'implementazione del sistema di numerazione.

> [!NOTE]
> Il numero articolo per un prodotto non può essere modificato una volta che esistono una o più transazioni per quel prodotto.

## <a name="product-name-and-description"></a>Nome e descrizione del prodotto

Il nome e la descrizione di un prodotto sono identificatori in formato leggibile di un prodotto e possono essere in più lingue. Per impostazione predefinita, il client Supply Chain Management mostra tutte le informazioni sul prodotto nella lingua predefinita della società, non nella lingua dell'utente. Tuttavia, in tutte le comunicazioni con i clienti e i fornitori vengono utilizzati i nomi e le descrizioni dei prodotti tradotti. Le traduzioni sono basate sul codice lingua dei conti cliente e fornitore.

Per le varianti prodotto, il nome prodotto può essere generato tramite un modello di nomenclatura di prodotto. Poiché non è necessario che i nomi prodotti siano univoci, è possibile trovare più prodotti con lo stesso nome.

## <a name="product-and-item-search-names"></a>Nomi di ricerca prodotto e articolo

Supply Chain Management fornisce un nome di ricerca secondario per i prodotti nonché per gli articoli (prodotti rilasciati). Questo nome di ricerca non deve essere univoco e può essere modificato dopo la creazione di un prodotto o una variante prodotto. Si consiglia di utilizzare il nome di ricerca per cercare prodotti per categorie. I nomi di ricerca consentono ricerche rapide, in particolare nei processi di vendita e di acquisto.

Il nome di ricerca può inoltre contenere un ID prodotto cliente o fornitore, oppure un altro ID di prodotto esterno, se tale ID esterno è il criterio di ricerca primario per un prodotto.

## <a name="external-product-identifiers-customer-and-vendor-identifiers"></a>Identificatori del prodotto esterni (identificatori clienti e fornitori)

Per i prodotti rilasciati, è possibile gestire i numeri articolo, i nomi e le descrizioni degli articoli utilizzati dal cliente o dal fornitore. I riferimenti sono mostrati come documenti esterni, quali ordini fornitore, ordini cliente, documenti di trasporto e fatture. Nella versione corrente di Supply Chain Management, i riferimenti esterni non sono visualizzati nelle pagine delle operazioni principali. La sola eccezione è il numero di articolo del fornitore. Questo numero viene visualizzato nella finestra di dialogo **Informazioni sul prodotto** se un fornitore predefinito viene definito per il prodotto rilasciato.

È possibile gestire gli identificatori di prodotto esterni per prodotto rilasciato, variante di prodotto rilasciato, cliente o gruppo di clienti oppure fornitore o gruppo di fornitori.

Nella pagina **Prodotti rilasciati**, effettuare una delle seguenti operazioni.

- Per i clienti, nella scheda **Vendi** nel gruppo **Informazioni correlate** selezionare **Descrizione esterna articolo**.
- Per i fornitori, nella scheda **Acquisti** nel gruppo **Informazioni correlate** selezionare **Descrizione esterna articolo**.

Nella pagina **Descrizioni esterne articolo**, è possibile associare il numero articolo del fornitore o del cliente a un prodotto rilasciato. Questa associazione deve essere eseguita per ogni persona giuridica. È possibile acquisire le informazioni seguenti. Purtroppo, le etichette sono leggermente fuorvianti nella versione corrente di Supply Chain Management. Tuttavia, queste etichette potrebbero venire modificate in una versione successiva.

| Campo | Informazioni cliente corrispondente | Informazioni fornitore corrispondente |
|-------|------------------------------------|----------------------------------|
| Numero articolo esterno | Il numero di articolo del cliente | Il numero di articolo del fornitore |
| descrizione | Il nome del cliente associato all'articolo | Il nome del fornitore associato all'articolo |
| Testo esterno articolo | La descrizione dell'articolo del cliente | La descrizione dell'articolo del fornitore |

Se molti clienti o fornitori utilizzano gli stessi numeri articolo (come ad esempio nel caso di un'associazione di acquisti o di un gruppo commercio), è possibile creare gruppi di clienti o di fornitori per semplificare la gestione delle informazioni esterne di prodotto.

- Per i gruppi di clienti, passare a **Vendite** &gt; **Impostazioni** &gt; **Articoli** &gt; **Descrizione esterna articolo** per creare e gestire i gruppi e i numeri articolo correlati. Per associare clienti a un gruppo, accedere a **Contabilità clienti** &gt; **Clienti** &gt; **Tutti i clienti**, quindi nella Scheda dettaglio **Impostazioni predefinite ordine cliente**, specificare un valore nel campo **Articolo - Gruppo di clienti**.
- Per i gruppi di fornitori, passare ad **Approvvigionamento** &gt; **Impostazioni** &gt; **Gruppo descrizioni esterne articolo** per creare e gestire i gruppi e i numeri articolo correlati. Per associare fornitori a un gruppo, accedere a **Contabilità fornitori** &gt; **Fornitori** &gt; **Tutti i fornitori**, quindi nella Scheda dettaglio **Impostazioni predefinite ordine fornitore**, specificare un valore nel campo **Articolo - Gruppo di fornitori**.
 
## <a name="bar-codes"></a>Codici a barre

Se si desidera utilizzare uno scanner di codici a barre per identificare i prodotti, l'identificatore del prodotto deve soddisfare i requisiti dello standard dei codici a barre utilizzato. Di conseguenza, i codici a barre non contengono in genere il numero di prodotto non elaborato ma un numero generato specificatamente per la tecnologia di codici a barre selezionata. È possibile gestire più codici a barre per tipo di codice a barre. È inoltre possibile associare lo stesso codice a barre a molteplici prodotti e quindi selezionare l'associazione attiva effettiva quando si esegue la scansione di un codice a barre.

Prima di definire i codici a barre, è possibile definire una o più configurazioni dei codici a barre. Le impostazioni di codici a barre consentono di verificare che i codici a barre seguono le linee guida necessarie e che quindi possono essere stampati e sottoposti a scansione. È anche possibile gestire codici a barre speciali per specifiche quantità di prodotto.

Si consiglia di utilizzare l'impostazione di codice a barre per gestire i codici GTIN o EAN.

Per gestire codici a barre, nella pagina **Prodotti rilasciati**, nella scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **Codici a barre**.

## <a name="gtin-codes"></a>Codici GTIN

Nell'e-commerce è fondamentale che tutte le parti parlino una lingua comune e facciano riferimento ai prodotti utilizzando un set di identificatori comune. Di conseguenza, alcuni settori si basano sul [GTIN](https://www.gs1.org/id-keys/gtin), ovvero un sistema di numeri di articolo globale facilitato da GS1.

Si consiglia di conservare il GTIN come codice a barre. È tuttavia possibile mantenerlo nella pagina **Articolo - GTIN**. Per aprire questa pagina, nella pagina **Prodotti rilasciati**, nella scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **Codici GTIN**. Si noti che il numero GTIN non viene gestito come numero globale. È invece gestito dalla persona giuridica.

In Supply Chain Management, si definiscono le varianti di imballaggio nelle operazioni di magazzino definendo unità di misura specifiche. Ad esempio, un articolo può essere archiviato in pezzi, in aggregazioni di sei unità, in cassetti da 18 unità o in pallet completi. Un'unità di misura specifica verrà definita per ognuna di queste varianti di imballaggio. Poiché il GTIN è in genere correlato all'unità di imballaggio di un prodotto, la pagina **Articolo - GTIN** consente di gestire più codici GTIN per prodotto e per unità di misura. Non è tuttavia possibile utilizzare lo stesso codice GTIN più volte per articoli diversi o varianti prodotto diverse di una persona giuridica.

Per gestire **Codici GTIN**, nella pagina **Prodotti rilasciati**, nella scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **GTIN**.

## <a name="external-codes"></a>Codici esterni

I codici esterni possono essere definiti per numerose entità. Ad esempio, è possibile definire codici esterni per identificare i prodotti e i prodotti rilasciati. Questi codici esterni possono essere utilizzati per associare codici statistici o codici imposta a prodotti rilasciati e varianti prodotto rilasciato. I codici esterni vengono definiti in base alla persona giuridica e al tipo di codice. Devono essere univoci per persona giuridica, tipo di codice e riferimento di tabella.

Purtroppo, non esiste alcuna funzionalità standard che consente di cercare prodotti in base a codici esterni.

## <a name="data-entities-that-are-used-to-import-and-export-product-identifiers"></a>Entità di dati utilizzate per importare ed esportare gli identificatori del prodotto

| Nome entità | Importare gli identificatori | Esportare gli identificatori | Commenti |
|-------------|--------------------|--------------------|----------|
| Prodotti V2 | Numero di prodotto, nome di ricerca prodotto, nome di prodotto, descrizione prodotto | Numero di prodotto, nome di ricerca prodotto, nome di prodotto, descrizione prodotto | A seconda delle impostazioni dell'entità e della sequenza numerica del numero prodotto, il numero prodotto può essere creato automaticamente al momento dell'importazione. |
| Varianti prodotto | Numero di prodotto, nome di ricerca prodotto, nome di prodotto, descrizione prodotto | Numero di prodotto, nome di ricerca prodotto, nome di prodotto, descrizione prodotto | A seconda del modello di nomenclatura di prodotto, il numero prodotto può essere creato automaticamente al momento dell'importazione. È tuttavia possibile importare qualsiasi numero prodotto univoco e tale numero prodotto non deve necessariamente seguire la struttura dei modelli di nomenclatura di prodotto. |
| Traduzioni prodotto | Nome di prodotto, descrizione prodotto | Nome di prodotto, descrizione prodotto | Questa entità sovrascrive qualsiasi lingua. Da notare che quando il nome o la descrizione della lingua madre di una persona giuridica viene sovrascritto, il nome e la descrizione del prodotto vengono modificati. |
| Creazione prodotti rilasciati V2 | Numero di articolo, numero di prodotto, nome di ricerca articolo| Numero di articolo, numero di prodotto, nome di ricerca articolo, nome di ricerca prodotto, nome di prodotto | L'uso di questa entità può essere problematico quando le sequenze numeriche sono utilizzate durante la creazione di nuovi prodotti rilasciati. Sia la sequenza numerica **Numero articolo** che la sequenza numerica **Numero prodotto** hanno un impatto. Tuttavia, la sequenza numerica **Numero articolo** è per persona giuridica, mentre la sequenza numerica **Numero prodotto** è globale. Pertanto, non si consiglia di utilizzare la sequenza numerica **Numero articolo** nella distribuzione di nuovi prodotti rilasciati. Ovviamente, quando l'entità è utilizzata per rilasciare un prodotto esistente, il numero di prodotto deve essere indicato nell'entità. Per ulteriori informazioni, vedere la sezione relativa alle sequenze numeriche dell'articolo e del prodotto in questo argomento. |
| Varianti prodotti rilasciati | Numero di articolo, dimensioni prodotto, numero di prodotto | Numero di prodotto, nome di ricerca prodotto, nome di prodotto, descrizione prodotto, dimensioni prodotto | Come l'entità **Varianti prodotto**, questa entità può essere utilizzata per creare nuovi prodotti che seguono il modello di nomenclatura dei prodotti o utilizzano i propri numeri di prodotto per la variante. |
| Descrizione esterna dell'articolo per i clienti | Numero articolo cliente, nome articolo cliente, descrizione cliente, conto cliente | Numero articolo cliente, nome articolo cliente, descrizione cliente, conto cliente | È possibile aggregare un gruppo di clienti (ad esempio un'associazione di acquirenti) in un unico gruppo utilizzando l'entità **Gruppo di clienti per le descrizioni esterne dell'articolo**. |
| Descrizione esterna dell'articolo per i fornitori | Numero di articolo del fornitore, nome di articolo del fornitore, descrizione fornitore, conto fornitore | Numero di articolo del fornitore, nome di articolo del fornitore, descrizione fornitore, conto fornitore | È possibile aggregare un gruppo di fornitori (ad esempio un'associazione di vendita o un'organizzazione di settore) in un unico gruppo utilizzando l'entità **Gruppi di fornitori per le descrizioni esterne dell'articolo**. |
| Codice a barre articolo | Codice a barre | Codice a barre | Tenere presente che, al momento dell'importazione, è necessario fare riferimento a un'impostazione di codice a barre definita nel sistema di destinazione. I riferimenti di codici a barre importati vengono convalidati in base a quella impostazione di codice a barre e vengono rifiutati se i codici a barre non soddisfano i requisiti definiti in quella impostazione. |
| Codici esterni per prodotti rilasciati | Codice esterno | Codice esterno, classi di codice esterno, numero articolo | I codici esterni vengono definiti in base alla persona giuridica. Per l'importazione, è necessario fare riferimento a una classe di codice definita. Importare le classi di codice utilizzando l'entità **Classi di codici esterni per prodotti rilasciati**. |
| Codici esterni per varianti di prodotto rilasciate | Codice esterno | Codice esterno, classi di codice esterno, numero articolo, dimensioni prodotto | I codici esterni vengono definiti in base alla persona giuridica. Per l'importazione, è necessario fare riferimento a una classe di codice definita. Importare le classi di codice utilizzando l'entità **Classi di codici esterni per prodotti rilasciati**. Questa entità fa riferimento a varianti prodotto per numero di articolo e dimensioni prodotto. |
| Codici esterni per varianti prodotto rilasciate in base all'identificatore del numero prodotto | Codice esterno | Codice esterno, classi di codice esterno, numero prodotto | I codici esterni vengono definiti in base alla persona giuridica. Per l'importazione, è necessario fare riferimento a una classe di codice definita. Importare le classi di codice utilizzando l'entità **Classi di codici esterni per prodotti rilasciati**. Questa entità fa riferimento a varianti prodotto per numero di prodotto della variante. (Dalla prossima versione principale) |
| GTIN | Non applicabile | Non applicabile | Attualmente, nessuna entità specifica viene utilizzata per importare ed esportare i codici GTIN. Si consiglia di utilizzare piuttosto l'entità **Codice a barre articolo**. |
| Entità dell'identificatore Common Data Service dell'entità prodotto | Non applicabile | Numero di articolo, nome di ricerca articolo, nome di ricerca prodotto, numero di articolo del fornitore, numero di articolo del cliente, codici esterni, codici GTIN, codici a barre | Questa entità consolida tutte gli identificatori in un modello di dati di modo che sia possibile utilizzare un'interfaccia per esportare facilmente tutti gli identificatori e i relativi tipi correlati. Utilizzare l'entità **Codici identificatori entità prodotto** per esportare le descrizioni e i codici identificatore. Utilizzare l'entità **Ambito identificatore entità prodotto** per esportare ulteriori informazioni sull'ambito in un identificatore, ad esempio parte, persona giuridica, quantità o unità. |

### <a name="product-and-item-number-sequences"></a>Sequenze di numero di articolo e numero di prodotto

È possibile definire due differenti sequenze numeriche:

- La sequenza numerica **Numero prodotto** per il numero di prodotto globale
- La sequenza numerica **Numero articolo** per il numero di articolo per persona giuridica

> [!NOTE]
> È necessario utilizzare il numero di articolo come identificatore distinto solo quando si esegue la migrazione di differenti persone giuridiche da origini diverse che hanno sistemi di numerazione differenti. È necessario tentare sempre di utilizzare un identificatore di prodotto univoco tra tutte le persone giuridiche. Di conseguenza, è necessario impostare l'opzione **Manuale** su **Sì** per la sequenza numerica **Numero articolo**. In questo modo, il numero di articolo seguirà il numero di prodotto alla creazione. Se Supply Chain Management non è il sistema principale per i nuovi numeri prodotto, è consigliabile impostare l'opzione **Manuale** su **Sì** per entrambe le sequenze numeriche **Numero articolo** e **Numero prodotto**.

Quando si utilizza l'entità **Creazione prodotti rilasciati V2** per creare prodotti, molteplici impostazioni possono influire sulla modalità di utilizzo delle sequenze numeriche per creare il numero di prodotto e il numero di articolo:

- Impostazioni della sequenza numerica **Numero prodotto**
- Impostazioni della sequenza numerica **Numero articolo**
- Il mapping del numero di articolo 
- Il mapping del numero di prodotto

Nella seguente tabella viene fornita una panoramica dei risultati di importazione e di creazione manuale con combinazioni specifiche di impostazioni di mappatura di sequenza numerica e campo.

| Sequenza numerica Numero prodotto | Sequenza numerica del numero di articolo | Mappatura di un numero articolo | Mappatura di un numero di prodotto | Risultato dell'importazione dell'entità | Risultato della creazione manuale | Conclusioni |
|--------------------------------|-----------------------------|----------------------------|-------------------------------|-------------------------|----------------------------|-----------|
| Manuale = No | Manuale = No | Nessun mapping | Nessun mapping | I numeri di prodotto utilizzano la sequenza numerica **Numero prodotto**. I numeri di articolo utilizzano la sequenza numerica **Numero articolo**. | I numeri di prodotto utilizzano la sequenza numerica **Numero prodotto**. I numeri di articolo utilizzano la sequenza numerica **Numero articolo**. | Con questa configurazione, i numeri dei prodotti seguiranno la sequenza dei numeri dei prodotti e i numeri degli articoli seguiranno la sequenza dei numeri degli articoli. Tuttavia, questa configurazione non funzionerà se è necessario importare più di un articolo (riga). |
| Manuale = No | Manuale = Sì | Generazione automatica | Nessun mapping | Sia i numeri prodotto che i numeri articolo utilizzano la sequenza numerica **Numero articolo**. | Sia i numeri prodotto che i numeri articolo utilizzano la sequenza numerica **Numero prodotto**. | Sia i numeri prodotto che i numeri articolo seguono la sequenza numerica del prodotto. Questo è l'approccio consigliato per importare prodotti in blocco con l'entità di dati Creazione prodotti rilasciati V2. |
| Manuale = No | Manuale = Sì | Nessun mapping | Nessun mapping | Sia i numeri prodotto che i numeri articolo utilizzano la sequenza numerica **Numero prodotto**. | Sia i numeri prodotto che i numeri articolo utilizzano la sequenza numerica **Numero prodotto**. | Sia i numeri prodotto che i numeri articolo usano la sequenza numerica del prodotto. Tuttavia, questa configurazione non funzionerà se è necessario importare più di un articolo (riga). |
| Manuale = Sì | Non applicabile | Non applicabile | Generazione automatica | Viene visualizzato il seguente messaggio di errore: "Impossibile rilevare la sequenza numerica.". | A seconda della sequenza numerica di **Numero articolo** | Questa impostazione non è supportata per l'importazione. |

## <a name="product-entity-identifier-export-all-product-identifiers"></a>Identificatore entità prodotto (Esportare tutti gli identificatori di prodotto)

Il modello di identificatore entità prodotto è stato creato per consentire il provisioning della versione 1.0 del Dataverse con tutti gli identificatori utilizzati per fare riferimento a un prodotto. Per semplificare questa attività, tutti gli identificatori vengono aggregati in una tabella di identificatori globale in modo che possano essere esportati come modello. Tenere presente che questa versione del Dataverse non utilizza il modello degli identificatori del prodotto. Di conseguenza, l'entità **Entità dell'identificatore Common Data Service dell'entità prodotto** e questo processo sono poco utilizzati e saranno probabilmente modificati in futuro.

La tabella degli identificatori di prodotto è una tabella globale generata a partire da tutte le tabelle di riferimenti della persona giuridica principale mediante un processo batch ricorrente. È necessario selezionare una persona giuridica e una gerarchia di categorie di prodotti come definizione dell'ambito complessivo della rappresentazione generale prodotto. La generazione della tabella di identificatori di prodotto globale è limitata ai prodotti rilasciati alla persona giuridica selezionata e ai prodotti che sono membri della gerarchia di prodotto selezionato per il ruolo **Common Data Service** nella gerarchia delle categorie di prodotto.

Questo processo presuppone che i dati di rappresentazione generale prodotto siano principalmente gestiti in una persona giuridica centrale. Tuttavia, questa persona giuridica può essere una persona giuridica virtuale utilizzata solo per gestire i dati master globali.

Per configurare l'ambiente, attenersi a questa procedura.

1. Selezionare la gerarchia di categorie per il Dataverse. Nella pagina **Associazioni del ruolo gerarchia di categorie**, se nessuna gerarchia è associata al ruolo **Common data service**, è necessario creare una nuova associazione. Selezionare il ruolo **Common Data Service** e quindi associare la gerarchia di categorie che rappresenta il portafoglio di prodotti che deve essere sincronizzato con Dataverse.
2. Selezionare la persona giuridica per i dati globali di rappresentazione generale prodotto. Nella pagina **Parametri di gestione informazioni sul prodotto**, nella scheda **Attributi del prodotto**, selezionare la società generale in cui gli identificatori dell'articolo e del prodotto vengono gestiti principalmente.
3. Definire i tipi di codice identificatore e i codici che devono essere esportati. Passare a **Gestione informazioni sul prodotto** &gt; **Impostazioni** &gt; **Codici identificatori entità prodotto**. Per generare i tipi di codice identificatore, selezionare **Genera codici**. Una voce tipo di codice viene generata per ogni tipo per l'identificatore che viene trovato nella persona giuridica selezionata.

    Tenere presente che, per i codici a barre, un tipo di codice viene generato per ogni impostazione di codice a barre. Per i codici esterni, viene generato un tipo di codice per ogni classe di codice esterno.

    È ora possibile gestire l'elenco di tipi di codice. È possibile modificare codice, nome e descrizione. È anche possibile eliminare tipi di codice. I tipi di codice che vengono eliminati non verranno utilizzati per popolare le tabelle di identificatori entità prodotto globali.

4. Al termine della definizione dei tipi di codice d'identificatore di prodotto, è possibile creare identificatori nella tabella globale avviando il processo **Crea identificatori entità prodotto** nella pagina **Codici identificatori entità prodotto**. Questo processo dovrebbe essere eseguito in un batch. Questo processo deve essere impostato come processo batch periodico di modo che la tabella venga popolata in base a nuove voci.

È ora possibile utilizzare le entità di dati **Entità dell'identificatore Common Data Service dell'entità prodotto**, **Codici identificatori entità prodotto** e **Ambito identificatore entità prodotto** per esportare gli identificatori per qualsiasi sistema di destinazione.

## <a name="related-topic"></a>Argomento correlato

[Ricerca di prodotti e varianti prodotto durante la registrazione ordine](search-products-product-variants.md)
