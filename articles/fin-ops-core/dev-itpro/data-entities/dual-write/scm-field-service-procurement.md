---
title: Integrare l'approvvigionamento tra Supply Chain Management e Field Service
description: In questo argomento viene descritto come l'integrazione della doppia scrittura supporta la creazione di ordini fornitore e gli aggiornamenti sia da Supply Chain Management che da Field Service.
author: RichardLuan
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c2b0d5be38425b5ceebb38b7964f5ec600b1c838
ms.sourcegitcommit: ca05440ee503bf15fe98fe138d317c1cdf21ad16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "5141906"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>Integrare l'approvvigionamento tra Supply Chain Management e Field Service

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management fornisce funzionalità avanzate di approvvigionamento. Dynamics 365 Field Service offre funzionalità simili che supportano i processi di acquisto associati al processo di servizio. La funzionalità di queste due app è integrata tramite doppia scrittura e i casi d'uso interfunzionali risultanti sono abilitati tramite mapping di tabelle, logica della soluzione, visualizzazioni e moduli.

Questa integrazione supporta la creazione di ordini fornitore e, nella maggior parte dei casi, aggiornamenti da entrambe le app. Tuttavia, Supply Chain Management controlla prezzi, indirizzi ed entrata dei prodotti. Diversi potenti casi d'uso interfunzionali sono abilitati per le organizzazioni che utilizzano sia Field Service che Supply Chain Management. Questi casi d'uso consentono di avviare e monitorare gli approvvigionamenti su entrambi i sistemi.

La figura seguente mostra le tabelle in entrambi i sistemi e il modo in cui sono mappate tra loro. Gli ordini fornitore in Field Service fanno riferimento a una riga *account*, mentre gli ordini fornitore in Supply Chain Management fanno riferimento a una riga *fornitore*. Per risolvere l'integrazione, la doppia scrittura utilizza un riferimento per collegare le righe *fornitore* alle righe *account*. Per ulteriori informazioni, vedere [Dati master fornitori integrati](vendor-mapping.md).

![Mapping per l'approvvigionamento](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>Prerequisiti

Per integrare Supply Chain Management con Field Service, è necessario installare i seguenti componenti:

- Field Service versione 8.8.31.60 o successiva, per l'integrazione completa dell'ordine fornitore
- Supply Chain Management versione 10.0.14 o versione successiva
- Doppia scrittura, per eseguire la soluzione OneFSSCM

## <a name="installation-guidelines"></a>Linee guida per l'installazione

### <a name="prerequisites"></a>Prerequisiti

+ **Doppia scrittura**: per ulteriori informazioni, vedere [Home page doppia scrittura](dual-write-home-page.md#dual-write-setup).
+ **Dynamics 365 Field Service**: per altre informazioni, vedere [Come installare Dynamics 365 Field Service](https://docs.microsoft.com/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service).

Quando sono abilitate in Microsoft Dataverse, la doppia scrittura e Field Service introducono diversi livelli di soluzioni che estendono l'ambiente con nuovi metadati, moduli, visualizzazioni e logica. Queste soluzioni possono essere abilitate in qualsiasi ordine, sebbene in genere vengano installate nell'ordine indicato qui:

1. **Field Service Common**: Field Service Common viene installato quando Field Service è installata nell'ambiente.
2. **Field Service (ancoraggio)**: Field Service (ancoraggio) viene installato quando Field Service è installata nell'ambiente. 
3. **Supply Chain Management estesa**: Supply Chain Management estesa viene installata automaticamente quando la doppia scrittura è abilitata in un ambiente. 
4. **Soluzione OneFSSCM**: OneFSSCM viene installato automaticamente da qualsiasi soluzione (Field Service o Supply Chain Management) venga installata per ultima.

    + Se Field Service è già installata nell'ambiente e si abilita la doppia scrittura, che installa Supply Chain Management estesa, OneFSSCM è installato.
    + Se Supply Chain Management estesa è già installata nell'ambiente e si installa Field Service, OneFSSCM è installato.

## <a name="initial-synchronization"></a>Sincronizzazione iniziale

Per creare nuovi ordini fornitore e utilizzare gli ordini fornitore esistenti, è necessario sincronizzare i dati di riferimento tra Supply Chain Management e Dataverse. Utilizzare la funzionalità di scrittura iniziale per rilevare le relazioni tra le tabelle e trovare le tabelle che è necessario abilitare per una determinata mappa.

È necessario sincronizzare le seguenti tabelle:

- Modelli di prodotto

    Quando si esegue la scrittura iniziale, viene visualizzato un elenco completo delle tabelle obbligatorie. Di seguito sono riportati alcuni esempi di modelli:

    - Tutti i prodotti
    - Prodotti rilasciati V2
    - Prodotti specifici Dataverse rilasciati

- Siti
- Magazzini
- Modelli di categorie di approvvigionamento

    Di seguito sono riportati alcuni esempi di modelli:

    - Categorie di approvvigionamento
    - Pro
    - Gerarchia di categorie prodotto
    - Assegnazioni categoria prodotto

- Modelli di fornitori, come Fornitore V2
- Modelli di persone di contatto, come Contatti Dataverse V2
- Modelli di lavoratore, come Lavoratore

La sincronizzazione delle tabelle garantisce che tutti i documenti (ordini fornitore ed entrate di prodotti) in Supply Chain Management siano disponibili in Dataverse.

### <a name="account-and-vendor-tables"></a>Tabelle Conto e Fornitore

Gli ordini fornitore in Field Service si basano sulla tabella Contro per tener traccia dei fornitori. Pertanto, le tabelle Dataverse per gli ordini fornitore utilizzano i conti per tener traccia dei fornitori. Per tenere conto di questa differenza fondamentale, è necessario attivare i seguenti quattro flussi di lavoro per mantenere sincronizzati conti e fornitori: 

- Creare fornitori nella tabella Conto
- Creare fornitori nella tabella Fornitori
- Aggiornare fornitori nella tabella Conti
- Aggiornare fornitori nella tabella Fornitori

Se OneFSSCM è installato, poiché sono installati sia Field Service che Supply Chain Management estesa, questi flussi di lavoro vengono attivati automaticamente. Se Field Service non è installata, ma desideri integrare le tabelle degli ordini fornitore con Dataverse, è necessario attivare questi flussi di lavoro. In entrambi i casi, a meno che non si inizi da zero, è consigliabile assicurarsi che tutti i fornitori siano creati come conti in Dataverse prima di creare ordini fornitore. Altrimenti, potrebbero verificarsi degli errori.

### <a name="initial-synchronization"></a>Sincronizzazione iniziale

Dopo aver impostato tutti i prerequisiti, se si desidera che gli ordini fornitore e le entrate di prodotti esistenti siano disponibili in entrambi i sistemi, è necessario eseguire una sincronizzazione iniziale dei seguenti modelli:

- Intestazione ordine fornitore V2
- Riga ordine fornitore CDS
- Eliminazione temporanea della riga ordine fornitore CDS
- Ricevimento ordini fornitore
- Entrata prodotti ordini fornitore

## <a name="mappings-with-logic"></a>Mapping con logica

L'integrazione dell'approvvigionamento estende il mapping dei prodotti con la seguente logica per garantire che la colonna **Tipo di prodotto Field Service** sia impostata correttamente nella tabella dei prodotti in Dataverse:

- Se **Tipo di prodotto** è impostato su *Prodotto* e **Gruppo di modelli articolo, Prodotto stoccato** è impostata su *Vero*, **Tipo di prodotto Field Service** è impostata su *Magazzino*.
- Se **Tipo di prodotto** è impostato su *Prodotto* e **Gruppo di modelli articolo, Prodotto stoccato** è impostata su *Falso*, **Tipo di prodotto Field Service** è impostata su *Non in magazzino*.
- Se **Tipo di prodotto** è impostata su *Servizio*, **Tipo di prodotto Field Service** è impostata su *Servizio*.

Inoltre, Dataverse include la logica che mappa i fornitori ai relativi conti. Questa logica imposta il conto fornitore della fattura predefinito. Al momento della creazione, la logica del plug-in lato server imposta il conto fornitore della fattura predefinito dal fornitore correlato all'account. Il fornitore dispone di un riferimento al conto fattura utilizzato per impostare questo valore.

## <a name="supported-scenarios"></a>Scenari supportati

+ Gli ordini fornitore possono essere creati e aggiornati dagli utenti di Dataverse. Tuttavia, il processo e i dati sono controllati da Supply Chain Management. I vincoli sugli aggiornamenti alle colonne dell'ordine fornitore in Supply Chain Management si applicano quando gli aggiornamenti provengono da Field Service. Ad esempio, non è possibile aggiornare un ordine fornitore se è stato finalizzato. 
+ Se l'ordine fornitore è controllato dalla gestione delle modifiche in Supply Chain Management, un utente di Field Service può aggiornare l'ordine fornitore solo quando lo stato di approvazione di Supply Chain Management è *Bozza*.
+ Diverse colonne sono gestite solo da Supply Chain Management e non possono essere aggiornate in Field Service. Per sapere quali colonne non possono essere aggiornate, rivedere le tabelle di mapping nel prodotto. Per motivi di semplicità, la maggior parte di queste colonne è impostata per la sola lettura nelle pagine Dataverse. 

    Ad esempio, le colonne per le informazioni sui prezzi sono gestite da Supply Chain Management. Supply Chain Management ha accordi commerciali da cui Field Service può trarre vantaggio. Colonne come **Prezzo unitario**, **Sconto** e **Importo netto** provengono solo da Supply Chain Management. Per assicurarsi che il prezzo sia sincronizzato con Field Service, è consigliabile utilizzare la funzionalità **Sincronizza** nelle pagine **Ordine fornitore** e **Prodotto ordine fornitore** in Dataverse quando sono stati inseriti i dati dell'ordine fornitore. Per altre informazioni, vedere [Sincronizzare con i dati di approvvigionamento di Dynamics 365 Supply Chain Management su richiesta](#sync-procurement).

+ La colonna **Totali** è disponibile solo in Field Service, poiché non ci sono totali aggiornati dell'ordine fornitore in Supply Chain Management. I totali in Supply Chain Management vengono calcolati in base a più parametri non disponibili in Field Service.
+ Le righe ordine fornitore in cui è specificata solo una categoria di approvvigionamento o in cui il prodotto specificato è un articolo del tipo di prodotto *Servizio* o del tipo di prodotto Field Service, possono essere avviate solo in Supply Chain Management. Le righe vengono quindi sincronizzate con Dataverse e sono visibili in Field Service.
+ Se è installata solo Field Service, non Supply Chain Management, la colonna **Magazzino** è obbligatoria nell'ordine fornitore. Tuttavia, se Supply Chain Management è installata, questo requisito viene attenuato, perché Supply Chain Management consente righe ordine fornitore in cui in determinate situazioni non è specificato alcun magazzino.
+ Le entrate di prodotti (ricevute degli ordini fornitore in Dataverse) sono gestite da Supply Chain Management e non possono essere create da Dataverse se è installata Supply Chain Management. Le entrate prodotti da Supply Chain Management vengono sincronizzate da Supply Chain Management a Dataverse.
+ La consegna in difetto è consentita in Supply Chain Management. La soluzione OneFSSCM aggiunge la logica in modo che, quando la riga di entrata del prodotto (o il prodotto di entrata dell'ordine fornitore in Dataverse) viene creata o aggiornata, viene creata una riga del giornale di registrazione inventario in Dataverse per regolare la quantità rimanente ordinata per scenari di consegna in difetto.

## <a name="unsupported-scenarios"></a>Scenari non supportati

+ Field Service impedisce l'aggiunta di righe a un ordine fornitore annullato in Supply Chain Management. Come soluzione alternativa, è possibile modificare lo stato di sistema dell'ordine fornitore in Field Service, quindi aggiungere la nuova riga in Field Service o Supply Chain Management.
+ Sebbene le righe di approvvigionamento influiscano sui livelli di scorte in entrambi i sistemi, questa integrazione non garantisce l'allineamento delle scorte tra Supply Chain Management e Field Service. Sia Field Service che Supply Chain Management hanno altri processi che aggiornano i livelli di scorte. Questi processi esulano dall'ambito dell'approvvigionamento.

## <a name="status-management"></a>Gestione dello stato

Gli stati degli ordini fornitore in Field Service differiscono dagli stati in Supply Chain Management.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Stati dell'ordine fornitore e del prodotto ordine fornitore di Field Service

| Intestazione: stato del sistema | Intestazione: stato dell'approvazione | Stato articolo |
|---|---|---|
| <ul><li>Bozze</li><li>Inviate</li><li>Operazione annullata</li><li>Prodotto ricevuto</li><li>Fatturato</li></ul> | <ul><li>Null</li><li>Importo approvato</li><li>Rifiutati</li></ul> | <ul><li>In sospeso</li><li>Ricevuti</li><li>Operazione annullata</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Stati dell'ordine fornitore e della riga ordine fornitore di Supply Chain Management

Gli stati di approvazione della riga sono attivi solo quando è presente un flusso di lavoro della riga.

| Intestazione: stato dei documenti | Intestazione: stato dell'approvazione | Stato riga | Stato approvazione riga |
|---|---|---|---|
| <ul><li>Ordine aperto (ordine arretrato)</li><li>Ricevuti</li><li>Fatturate</li><li>Operazione annullata</li></ul> | <ul><li>Bozze</li><li>In revisione</li><li>Importo approvato</li><li>Rifiutati</li><li>In revisione esterna</li><li>Confermata</li><li>Finalizzato</li></ul> | <ul><li>Ordine aperto (ordine arretrato)</li><li>Ricevuti</li><li>Fatturate</li><li>Operazione annullata</li></ul> | <ul><li>Non inviata</li><li>In revisione</li><li>Importo approvato</li><li>Rifiutati</li></ul> |

Le seguenti regole vengono applicate alle colonne di stato:

+ Lo stato in Supply Chain Management non può essere aggiornato da Field Service. Tuttavia, in alcuni casi, lo stato in Field Service verrà aggiornato quando lo stato dell'ordine fornitore in Supply Chain Management viene modificato.
+ Se un ordine fornitore in Supply Chain Management è in fase di gestione delle modifiche e una modifica è in corso di elaborazione, lo stato di approvazione è *Bozza* o *In revisione*. In questo caso, lo stato di approvazione di Field Service sarà impostato su *Null*.
+ Se lo stato di approvazione dell'ordine fornitore in Supply Chain Management è impostato su *Approvato*, *In revisione esterna*, *Confermato* o *Finalizzato*, lo stato di approvazione dell'ordine fornitore di Field Service sarà impostato su *Approvato*.
+ Se lo stato di approvazione dell'ordine fornitore in Supply Chain Management è impostato su *Rifiutato*, lo stato di approvazione dell'ordine fornitore di Field Service sarà impostato su *Rifiutato*.
+ Se lo stato dell'intestazione del documento in Supply Chain Management viene modificato in *Ordine aperto (ordine arretrato)* e lo stato dell'ordine fornitore in Field Service è *Bozza* o *Annullato*, lo stato dell'ordine fornitore di Field Service cambierà in *Inviato*.
+ Se lo stato dell'intestazione del documento in Supply Chain Management viene modificato in *Annullato* e nessun prodotto con ricevuta dell'ordine fornitore in Field Service è associato all'ordine fornitore (tramite i prodotti dell'ordine di acquisto), lo stato del sistema Field Service è impostato su *Annullato*.
+ Se lo stato della riga dell'ordine fornitore in Supply Chain Management è *Annullato*, lo stato del prodotto dell'ordine fornitore in Field Service è impostato su *Annullato*. Inoltre, se lo stato della riga dell'ordine fornitore in Supply Chain Management viene modificato da *Annullato* a *Ordine arretrato*, lo stato dell'articolo prodotto dell'ordine fornitore in Field Service è impostato su *In sospeso*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Sincronizzare con i dati di approvvigionamento di Supply Chain Management su richiesta

Supply Chain Management include dati di approvvigionamento che gestiscono accordi commerciali, sconti e altri scenari che si basano su processi secondari in Supply Chain Management. Il motore di approvvigionamento utilizza regole complesse per determinare il prezzo migliore per un determinato ordine fornitore. Quando si utilizza la doppia scrittura, i dati non vengono sempre mantenuti sincronizzati tra i due ambienti, specialmente negli scenari in cui la riga è stata creata o aggiornata da Dataverse e potrebbe attivare processi di follow-on in Supply Chain Management.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Sincronizzare i dati di approvvigionamento da Supply Chain Management

1. In Dataverse, andare a **Magazzino \> Ordine fornitore**.
2. Selezionare **Nuovo** per creare un nuovo ordine fornitore o selezionare una riga per un ordine fornitore esistente.
3. Dall'ordine fornitore o dalla riga dell'ordine fornitore.
4. Nel riquadro azioni, selezionare **Sincronizza**.

Tutte le colonne da Dataverse e Field Service condivise da Supply Chain Management vengono sincronizzate.

Ecco le situazioni in cui è consigliabile utilizzare la funzione **Sincronizza**:

- Se si apportano più modifiche successive alla stessa riga da Dataverse, eseguire la funzione **Sincronizza**.
- Se non si è sicuri che una modifica possa essere la seconda modifica successiva da Dataverse, potrebbe avere senso eseguire la funzione **Sincronizza**.
- Se si riceve un messaggio di errore sull'aggiornamento di un valore da Supply Chain Management, eseguire la funzione **Sincronizza**, quindi ritentare l'aggiornamento in Dataverse.

## <a name="cancelling-the-posting-process"></a>Annullamento del processo di registrazione

Se il processo di registrazione dell'entrata prodotti viene annullato durante l'elaborazione, la doppia scrittura potrebbe creare una riga dell'entrata prodotti in Dataverse, ma non creare una riga di entrata prodotti in Supply Chain Management. Questa situazione si verifica perché la doppia scrittura non supporta le transazioni distribuite.

## <a name="templates"></a>Modelli

I seguenti modelli sono disponibili per l'integrazione dei documenti relativi agli appalti.

| Gestione della supply chain | Field Service | descrizione |
|---|---|---|
| Intestazione ordine fornitore V2 | msdyn\_Purchaseorders | Questa tabella contiene le colonne che rappresentano l'intestazione dell'ordine fornitore. |
| Entità riga ordine fornitore | msdyn\_PurchaseOrderProducts | Questa tabella contiene le righe che rappresentano righe su un ordine fornitore. Il numero di prodotto viene utilizzato per la sincronizzazione. Ciò identifica il prodotto come unità di stockkeeping (SKU), comprese le dimensioni del prodotto. Per ulteriori informazioni sull'integrazione del prodotto con Dataverse, vedere [Esperienza prodotto unificata](product-mapping.md). |
| Intestazione entrata prodotti | msdyn\_purchaseorderreceipts | Questa tabella contiene le intestazioni dell'entrata prodotti che vengono create quando un'entrata prodotti viene registrata in Supply Chain Management. |
| Riga entrata prodotti | msdyn\_purchaseorderreceiptproducts | Questa tabella contiene le righe dell'entrata prodotti che vengono create quando un'entrata prodotti viene registrata in Supply Chain Management. |
| Entità eliminata temporaneamente della riga ordine fornitore | msdyn\_purchaseorderproducts | Questa tabella contiene informazioni sulle righe ordine fornitore eliminate temporaneamente. Una riga dell'ordine fornitore in Supply Chain Management può essere eliminata temporaneamente solo quando l'ordine fornitore è stato confermato o approvato, se la gestione delle modifiche è attivata. La riga esiste nel database di Supply Chain Management ed è contrassegnata come **IsDeleted**. Poiché Dataverse non prevede un concetto di eliminazione temporanea, è importante che queste informazioni vengano sincronizzate con Dataverse. In questo modo, le righe eliminate temporaneamente in Supply Chain Management possono essere eliminate automaticamente da Dataverse. In questo caso, la logica per eliminare una riga in Dataverse si trova in Supply Chain Management estesa. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/productreceiptheader-msdyn-purchaseorderreceipts.md)]

[!include [Currency](includes/productreceiptline-msdyn-purchaseorderreceiptproducts.md)]

[!include [Currency](includes/purchaseorderheadersv2-msdyn-purchaseorders.md)]

[!include [Currency](includes/purchaseorderlinesoftdeletedtable-msdyn-purchaseorderproducts.md)]

[!include [Currency](includes/purchaseorderlinetable-msdyn-purchaseorderproducts.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]