---
title: Esperienza prodotto unificata
description: In questo argomento viene descritta l'integrazione dei dati prodotto tra le app Finance and Operations e Dataverse.
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 6941a38e96520befd3bdba65956d45a6bbaee4be
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306391"
---
# <a name="unified-product-experience"></a>Esperienza prodotto unificata

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Quando un ecosistema aziendale è costituito da applicazioni Dynamics 365, come Finance, Supply Chain Management e Sales, le aziende spesso utilizzano queste applicazioni per acquisire dati di prodotto. Questo perché tali app forniscono una robusta infrastruttura di prodotto completata da sofisticati concetti di valutazione e dati di magazzino disponibile accurati. Le aziende che utilizzano un sistema esterno di gestione del ciclo di vita del prodotto per l'acquisizione dei dati di prodotto possono dirigere i prodotti dalle app Finance and Operations ad altre app Dynamics 365. L'esperienza di prodotto unificata importa il modello di dati di prodotto integrato in Dataverse, di modo che tutti gli utenti delle applicazioni inclusi gli utenti di Power Platform possano usufruire dei dati di prodotto avanzati delle app Finance and Operations.

Di seguito è riportato il modello di dati di prodotto di Sales.

![Modello di dati per prodotti in CE](media/dual-write-product-4.jpg)

Di seguito è riportato il modello di dati per prodotti delle app Finance and Operations.

![Modello di dati per prodotti in Finance and Operations](media/dual-write-products-5.jpg)

Questi due modelli di dati di prodotto sono stati integrati in Dataverse come mostrato di seguito.

![Modello di dati per prodotti nelle app Dynamics 365](media/dual-write-products-6.jpg)

Le mappe della tabella di doppia scrittura per i prodotti sono state progettate per un flusso di dati esclusivamente unidirezionale e rappresentano un'esperienza pressoché in tempo reale dalle Finance and Operations app a Dataverse. Tuttavia, l'infrastruttura di prodotto è stata aperta per renderla bidirezionale, se necessario. Sebbene possa essere personalizzata, l'esecuzione è a proprio rischio, in quanto Microsoft non consiglia questo approccio.

## <a name="templates"></a>Modelli

Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento. Come mostrato nella tabella seguente, una raccolta di mappe della tabella viene creata per sincronizzare i prodotti e le informazioni correlate.

App di Finance and Operations | Altre app Dynamics 365 | Descrizione
-----------------------|--------------------------------|---
Prodotti rilasciati V2 | msdyn\_sharedproductdetails | La tabella **msdyn\_sharedproductdetails** contiene le colonne delle app Finance and Operations che definiscono il prodotto e che contengono le informazioni finanziarie e di gestione del prodotto. 
Prodotti specifici Dataverse rilasciati | Prodotto | La tabella **Prodotto** contiene le colonne che definiscono il prodotto. Include singoli prodotti (prodotti con prodotto di sottotipo) e varianti prodotto. Nella seguente tabella sono riportati i mapping.
Codice a barre identificatore di numeri prodotto | msdyn\_productbarcodes | I codici a barre sono utilizzati per identificare in modo univoco i prodotti.
Impostazioni ordine predefinite | msdyn\_productdefaultordersettings
Impostazioni ordine predefinite specifiche del prodotto | msdyn_productdefaultordersettings
Gruppi di dimensioni prodotto | msdyn\_productdimensiongroups | Il gruppo di dimensioni prodotto determina le dimensioni prodotto che definiscono il prodotto. 
Gruppi di dimensioni di immagazzinamento | msdyn\_productstoragedimensiongroups | Il gruppo di dimensioni di immagazzinamento prodotto rappresenta il metodo utilizzato per definire l'ubicazione del prodotto in magazzino.
Gruppi di dimensioni di tracciabilità | msdyn\_producttrackingdimensiongroups | Il gruppo di dimensioni di tracciabilità prodotto rappresenta il metodo utilizzato per tenere traccia del prodotto in magazzino.
Colori | msdyn\_productcolors
Dimensioni | msdyn\_productsizes
Stili | msdyn\_productsytles
Configurazioni | msdyn\_productconfigurations
Colori rappresentazione generale prodotto | msdyn_sharedproductcolors | La tabella **Colore prodotto condiviso** indica i colori che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
Dimensioni rappresentazione generale prodotto | msdyn_sharedproductsizes | La tabella **Dimensione prodotto condivisa** indica le dimensioni che una rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
Stili rappresentazione generale prodotto | msdyn_sharedproductstyles | La tabella **Stile prodotto condiviso** indica gli stili che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
Configurazioni rappresentazione generale prodotto | msdyn_sharedproductconfigurations | La tabella **Configurazione prodotto condivisa** indica le configurazioni che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
Tutti i prodotti | msdyn_globalproducts | La tabella Tutti i prodotti contiene tutti i prodotti disponibili nelle app Finance and Operations, ovvero i prodotti rilasciati e quelli non rilasciati.
Unità | uoms
Conversioni unità | msdyn_ unitofmeasureconversions
Conversione di unità di misura specifiche del prodotto | msdyn_productspecificunitofmeasureconversion
Categorie prodotti | msdyn_productcategories | Le categorie di prodotti e le informazioni sulla struttura e sulle caratteristiche sono contenute nella tabella categoria di prodotti. 
Gerarchie di categorie prodotto | msdyn_productcategoryhierarhies | Utilizzare le gerarchie di prodotti per classificare o raggruppare prodotti. Le gerarchie di categorie sono disponibili in Dataverse utilizzando la tabella gerarchia di categorie di prodotti. 
Ruoli gerarchia di categorie prodotto | msdyn_productcategoryhierarchies | Le gerarchie di prodotti possono essere utilizzate per ruoli diversi in D365 Finance and Operations. Specificano quale categoria viene utilizzata in ciascun ruolo utilizzato dalla tabella ruolo della categoria di prodotti. 
Assegnazioni categoria prodotto | msdyn_productcategoryassignments | Per assegnare un prodotto a una categoria è possibile utilizzare la tabella assegnazioni di categoria di prodotto.

## <a name="integration-of-products"></a>Integrazione di prodotti

In questo modello, il prodotto è rappresentato dalla combinazione di due tabelle in Dataverse: **Prodotto** e **msdyn\_sharedproductdetails**. Mentre la prima tabella contiene la definizione di un prodotto (identificatore univoco per il prodotto, il nome del prodotto e la descrizione), la seconda tabella contiene le colonne archiviate a livello del prodotto. La combinazione di queste due tabelle viene utilizzata per definire il prodotto in base al concetto di unità di stockkeeping. Ogni prodotto rilasciato avrà le relative informazioni nelle tabelle menzionate (Prodotto e Dettagli prodotto condivisi). Per tenere traccia di tutti i prodotti (rilasciati e non rilasciati) si utilizza la tabella **Prodotti globali**. 

Poiché il prodotto è rappresentato come unità di stockkeeping, i concetti di prodotti specifici, rappresentazioni generali prodotto e varianti prodotto possono essere acquisiti in Dataverse nel seguente modo:

- I **prodotti con prodotto di sottotipo** sono prodotti auto-definiti. Nessuna dimensione deve essere definita. Un esempio è un registro specifico. Per tali prodotti, viene creato una riga nella tabella **Prodotto** e una riga nella tabella **msdyn\_sharedproductdetails**. Non viene creato nessuna riga di famiglia di prodotti.
- Le **rappresentazioni generali prodotto** sono utilizzate come prodotti generici che contengono la definizione e le regole che determinano il comportamento nei processi aziendali. In base a queste definizioni, è possibile generare i prodotti specifici noti come varianti prodotto. Ad esempio, Maglietta è la rappresentazione generale prodotto e può avere le dimensioni Colore e Dimensione. È possibile rilasciare varianti che hanno differenti combinazioni di queste dimensioni, come una maglietta blu di taglia S o una maglietta verde di taglia M. Nell'integrazione, una riga per variante viene creato nella tabella dei prodotti. Tale riga contiene informazioni specifiche della variante, come le differenti dimensioni. Le informazioni generiche per il prodotto sono archiviate nella tabella **msdyn\_sharedproductdetails**. (queste informazioni generiche si trovano nella rappresentazione generale prodotto). Le informazioni relative alla rappresentazione generale prodotto vengono sincronizzate con Dataverse non appena viene creata la rappresentazione generale prodotto rilasciata (ma prima del rilascio delle varianti).
- I **prodotti specifici** fanno riferimento a tutti i prodotti di sottotipo e a tutte le varianti prodotto. 

![Modello di dati per prodotti](media/dual-write-product.png)

Con la funzionalità di doppia scrittura attivata, i prodotti Finance and Operations sono sincronizzate in altri prodotti Dynamics 365 nello stato **Bozza**. Queste vengono aggiunte al primo listino prezzi con la stessa valuta. In altre parole, sono aggiunte al primo listino prezzi in un'app Dynamics 365 che corrisponde alla valuta della persona giuridica in cui il prodotto viene rilasciato in un'app Finance and Operations. Se non esiste un listino prezzi per la valuta data, verrà creato automaticamente un listino prezzi e il prodotto gli verrà assegnato. 

L'attuale implementazione dei plugin a doppia scrittura che associano il listino prezzi predefinito all'unità cerca la valuta associata all'app Finance and Operations e trova il primo listino prezzi nell'app di interazione con i clienti utilizzando l'ordinamento alfabetico sul nome del listino prezzi. Per impostare un listino prezzi predefinito per una valuta specifica quando si dispone di più listini prezzi per quella valuta, è necessario aggiornare il nome del listino prezzi a un nome che appare prima nell'ordine alfabetico rispetto a qualsiasi altro listino prezzi per quella stessa valuta.

Per impostazione predefinita, i prodotti delle app Finance and Operations sono sincronizzati con altre app Dynamics 365 nello stato di **Bozza**. Per sincronizzare il prodotto con stato **Attivo** di modo che sia possibile utilizzarlo direttamente, ad esempio, nelle offerte di ordine cliente, è necessario selezionare **Creare prodotti in stato attivo = Sì** in **Sistema > Amministrazione > Amministrazione sistema > Impostazioni di sistema > Vendite**. 

Quando i prodotti sono sincronizzati, è necessario immettere un valore per il campo **Unità di vendita** nell'app Finance and Operations, perché è un campo obbligatorio in Sales.

La creazione di famiglie di prodotti in Dynamics 365 Sales non è supportata con la sincronizzazione a doppia scrittura dei prodotti.

La sincronizzazione dei prodotti avviene dall'app Finance and Operations in Dataverse. Ciò significa che i valori delle colonne tabella prodotto possono essere modificati in Dataverse, ma quando viene attivata la sincronizzazione (quando una colonna del prodotto viene modificato in un'app Finance and Operations), questo sovrascriverà i valori in Dataverse. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [products](includes/EcoResReleasedDistinctProductCDSEntity-products.md)]

[!include [product details](includes/EcoResReleasedProductV2-msdyn-sharedproductdetails.md)]

[!include [global products](includes/EcoResEveryProductEntity-msdyn-globalproducts.md)]

## <a name="product-dimensions"></a>Dimensioni prodotto 

Le dimensioni prodotto sono caratteristiche che identificano una variante prodotto. Le quattro dimensioni prodotto (colore, dimensione, stile e configurazione) vengono inoltre mappati a Dataverse per definire le varianti prodotto. Nella figura seguente è illustrato il modello di dati per la dimensione prodotto Colore. Lo stesso modello viene applicato a Dimensioni, Stili e Configurazioni. 

![Modello di dati per dimensioni di prodotto](media/dual-write-product-two.png)

[!include [product colors](includes/EcoResProductColorEntity-msdyn-productcolor.md)]

[!include [product sizes](includes/EcoResProductSizeEntity-msdyn-productsizes.md)]

[!include [product sizes](includes/EcoResProductStyleEntity-msdyn-productstyles.md)]

[!include [product sizes](includes/EcoResProductConfigurationsEntity-msdyn-productconfigurations.md)]

Quando un prodotto ha dimensioni prodotto differenti (ad esempio una rappresentazione generale prodotto ha Colore e Prodotto come dimensioni prodotto, ovvero ogni variante prodotto) è definito come combinazione di tali dimensioni prodotto. Ad esempio, il numero prodotto B0001 è una maglietta nera di taglia XS e il numero prodotto B0002 è una maglietta nera di taglia S. In questo caso, le combinazioni esistenti delle dimensioni prodotto sono definite. Ad esempio, la maglietta dell'esempio precedente può essere nera e di taglia XS, S, M o L, ma non può essere nera e di taglia XL. In altre parole, le dimensioni prodotto che una rappresentazione generale prodotto può avere sono specificate e le varianti possono essere rilasciate in base a tali valori.

Per tenere traccia delle dimensioni prodotto che una rappresentazione generale prodotto può utilizzare, le seguenti tabelle vengono create e mappate in Dataverse per ogni dimensione prodotto. Per ulteriori informazioni, vedere [Panoramica delle informazioni sul prodotto](../../../../supply-chain/pim/product-information.md). 

[!include [product colors](includes/EcoResProductMasterColorEntity-msdyn-sharedproductcolors.md)]

[!include [product sizes](includes/EcoResProductMasterSize-msdyn-sharedproductsizes.md)]

[!include [product styles](includes/EcoResProductMasterStyleEntity-msdyn-sharedproductstyles.md)]

[!include [product configurations](includes/EcoResProductMasterConfigurationEntity-msdyn-sharedproductconfigurations.md)]

[!include [product bar codes](includes/EcoResProductNumberIdentifiedBarcode-msdyn-productbarcodes.md)]

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Impostazioni ordine predefinite e impostazioni ordine predefinite specifiche del prodotto

Le impostazioni ordine predefinite definiscono il sito e il magazzino in cui gli articoli saranno prelevati o archiviati, le quantità minima, massima, multipla e standard che verrà utilizzata per il commercio o la gestione degli articoli, i lead time, il flag di interruzione e il metodo delle promesse ordine. Queste informazioni sono disponibili in Dataverse mediante le impostazioni ordine predefinite e le impostazioni ordine predefinite specifiche del prodotto. Per ulteriori informazioni sulla funzionalità, vedere l'argomento [Impostazioni ordine predefinite](../../../../supply-chain/production-control/default-order-settings.md).

[!include [product sizes](includes/InventProductDefaultOrderSettingsEntity-msdyn-productdefaultordersetting.md)]

[!include [product sizes](includes/InventProductSpecificOrderSettingsV2Entity-msdyn-productspecificdefaultordersetting.md)]

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unità di misura e conversioni di unità di misura

Le unità di misura e la relativa conversione sono disponibili in Dataverse mediante il modello di dati visualizzato nel diagramma.

![Modello di dati per unità di misura](media/dual-write-product-three.png)

Il concetto di unità di misura è integrato tra le app Finance and Operations e altre app Dynamics 365. Per ogni classe di unità di misura in un'app Finance and Operations, viene creato un gruppo di unità in un'app Dynamics 365, che contiene le unità appartenenti alla classe di unità di misura. Un'unità di base predefinita viene inoltre creata per ogni gruppo di unità. 

[!include [unit of measure](includes/UnitOfMeasureEntity-uom.md)]

[!include [unit of measure conversions](includes/UnitOfMeasureConversionEntity-msdyn-unitofmeasureconversions.md)]

[!include [product-specific unit of measure conversions](includes/EcoResProductSpecificUnitConversionEntity-msdyn-productspecificunitofmeasureconversions.md)]

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Sincronizzazione iniziale della corrispondenza dei dati delle unità tra Finance and Operations e Dataverse

### <a name="initial-synchronization-of-units"></a>Sincronizzazione iniziale delle unità

Quando la doppia scrittura è abilitata, le unità delle app Finance and Operations sono sincronizzate con altre app Dynamics 365. I gruppi di unità sincronizzati dalle app Finance and Operations in Dataverse dispongono di un flag che indica che sono "gestiti esternamente".

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Corrispondenza di unità e dati di classi/gruppi di unità da Finance and Operations e altre app di Dynamics 365

Innanzitutto, è importante notare che la chiave di integrazione per l'unità è msdyn_symbol. Di conseguenza, questo valore deve essere univoco in Dataverse o in altre app Dynamics 365. Poiché in altre app Dynamics 365 è la coppia "ID gruppo unità" e "Nome" che definiscono l'unicità di un'unità, è necessario prendere in considerazione scenari diversi per la corrispondenza dei dati dell'unità tra app Finance and Operations e Dataverse.

Per le unità che corrispondono o si sovrappongono nelle app Finance and Operations e altre app di Dynamics 365:

+ **L'unità appartiene a un gruppo di unità in altre app Dynamics 365 che corrisponde alla classe di unità associata nelle app Finance and Operations**. In questo caso, la colonna msdyn_symbol in altre app Dynamics 365 deve essere compilato con il simbolo dell'unità dalle app Finance and Operations. Pertanto, quando i dati verranno abbinati e il gruppo di unità verrà impostato come "Gestito esternamente" in altre app di Dynamics 365.
+ **L'unità appartiene a un gruppo di unità in altre app Dynamics 365 che non corrisponde alla classe di unità associata nelle app Finance and Operations (nessuna classe di unità esistente nelle app Finance and Operations per la classe di unità in altre app Dynamics 365)**. In questo caso, il campo msdyn_symbol deve essere compilato con una stringa casuale. Notare che questo valore deve essere univoco in altre app Dynamics 365.

Per le unità e le classi di unità in Finance and Operations che non esistono in altre app di Dynamics 365:

Come parte della doppia scrittura, i gruppi di unità dalle app Finance and Operations e le unità corrispondenti vengono create e sincronizzate in altre app Dynamics 365 e Dataverse e il gruppo di unità verrà impostato come "Gestito esternamente". Non è richiesto alcun ulteriore azione di bootstrap.

Per le unità in altre app di Dynamics 365 che non esistono nelle app Finance and Operations:

La colonna msdyn_symbol deve essere compilato per tutte le unità. Le unità possono sempre essere create nelle app Finance and Operations nella classe di unità corrispondente (se esiste). Se la classe di unità non esiste, è necessario innanzitutto creare la classe di unità (tenere presente che non è possibile creare una classe di unità nelle app Finance and Operations se non tramite l'estensione se si sta estendendo l'enumerazione) corrispondente all'altro gruppo di unità delle app Dynamics 365. È possibile quindi creare l'unità. Si noti che il simbolo dell'unità nelle app Finance and Operations deve essere il campo msdyn_symbol precedentemente specificato in altre app Dynamics 365 per l'unità.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Criteri di prodotto: gruppi di dimensioni, tracciabilità e archiviazioni

I criteri di prodotto sono set di criteri utilizzati per definire i prodotti e le relative caratteristiche in magazzino. Il gruppo di dimensioni prodotto, di dimensioni di tracciabilità e di dimensioni di immagazzinamento sono disponibili come criteri di prodotto. 

[!include [product dimension group](includes/EcoResProductDimensionGroup-msdyn-productdimensiongroups.md)]

[!include [product tracking dimension group](includes/EcoResTrackingDimensionGroup-msdyn-producttrackingdimensiongroups.md)]

[!include [product storage dimension group](includes/EcoResStorageDimensionGroup-msdyn-productstoragedimensiongroups.md)]

## <a name="product-hierarchies"></a>Gerarchie di prodotti

[!include [product category hierarchy](includes/EcoResProductCategoryHierarchyEntity-msdyn-productcategoryhierarchy.md)]

[!include [product category](includes/EcoResProductCategoryEntity-msdyn-productcategory.md)]

[!include [product category assignments](includes/EcoResProductCategoryAssignmentEntity-msdyn-productcategoryassignment.md)]

[!include [product category role](includes/EcoResProductCategoryHierarchyRoleEntity-msdyn-productcategoryhierarchyrole.md)]


## <a name="integration-key-for-products"></a>Chiave di integrazione per i prodotti 

Per identificare in modo univoco i prodotti tra Dynamics 365 for Finance and Operations e i prodotti in Dataverse vengono utilizzate le chiavi di integrazione. Per i prodotti, il **(productnumber)** è la chiave univoca che identifica un prodotto in Dataverse. È composta dalla concatenazione di: **(società, msdyn_productnumber)**. La **società** indica la persona giuridica in Finance and Operations e **msdyn_productnumber** indica il numero del prodotto specifico in Finance and Operations. 

Per gli utenti di altre app Dynamics 365, il prodotto viene identificato nell'interfaccia utente con **msdyn_productnumber** (notare che l'etichetta della colonna è **Numero prodotto**). Nel modulo del prodotto sono mostrati sia l'azienda che il msydn_productnumber. Tuttavia, la colonna (productnumber), la chiave univoca per un prodotto, non viene visualizzato. 

Se si creano app in Dataverse, è necessario prestare attenzione all'utilizzo di **productnumber** (l'ID univoco del prodotto) come chiave di integrazione. Non usare **msdyn_productnumber** perché non è univoco. 

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Sincronizzazione iniziale dei prodotti e migrazione dei dati da Dataverse a Finance and Operations

### <a name="initial-synchronization-of-products"></a>Sincronizzazione iniziale dei prodotti 

Quando la doppia scrittura è abilitata, i prodotti delle app Finance and Operations sono sincronizzati con Dataverse e altre app di interazione con i clienti. I prodotti creati in Dataverse e nelle altre app Dynamics 365 prima del rilascio della doppia scrittura non verranno aggiornati o abbinati ai dati del prodotto da Finance and Operations.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Corrispondenza dei dati di prodotto da Finance and Operations e altre app di Dynamics 365

Se gli stessi prodotti vengono mantenuti (sovrapposti/corrispondenti) in Finance and Operations e in Dataverse e in altre app Dynamics 365, quando si abilita la doppia scrittura verrà eseguita la sincronizzazione dei prodotti di Finance and Operations e verranno visualizzate righe duplicate in Dataverse per lo stesso prodotto.
Per evitare la situazione precedente, se altre app Dynamics 365 hanno prodotti che si sovrappongono/corrispondono a Finance and Operations, l'amministratore che abilita la doppia scrittura deve avviare le colonne **Società** (esempio: "USMF") e **msdyn_productnumber** (esempio: "1234:Black:S") prima che abbia luogo la sincronizzazione dei prodotti. In altre parole, queste due colonne nel prodotto in Dataverse devono essere compilati con la rispettiva società in Finance and Operations a cui il prodotto deve essere associato e con il suo numero di prodotto. 

Quindi, quando la sincronizzazione è abilitata e ha luogo, i prodotti di Finance and Operations verranno sincronizzati con i prodotti corrispondenti in Dataverse e altre app di Dynamics 365. Ciò è applicabile sia a prodotti distinti sia a varianti di prodotto. 


### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migrazione dei dati di prodotto da altre app di Dynamics 365 a Finance and Operations

Se altre app di Dynamics 365 hanno prodotti che non sono presenti in Finance and Operations, l'amministratore può innanzitutto utilizzare **EcoResReleasedProductCreationV2Entity** per importare tali prodotti in Finance and Operations. In secondo luogo, abbina i dati di prodotto di Finance and Operations e altre app di Dynamics 365 come descritto sopra. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
