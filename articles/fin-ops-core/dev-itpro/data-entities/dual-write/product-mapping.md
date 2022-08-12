---
title: Esperienza prodotto unificata
description: In questo articolo viene descritta l'integrazione dei dati del prodotto tra le app per la finanza e le operazioni e Dataverse.
author: t-benebo
ms.date: 06/23/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1546cdaf3c63a7ff9a330ae8609595aaf48fbc48
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111488"
---
# <a name="unified-product-experience"></a>Esperienza prodotto unificata

[!include [banner](../../includes/banner.md)]



Quando un ecosistema aziendale è costituito da applicazioni Dynamics 365, come Finance, Supply Chain Management e Sales, le aziende spesso utilizzano queste applicazioni per acquisire dati di prodotto. Questo perché tali app forniscono una robusta infrastruttura di prodotto completata da sofisticati concetti di valutazione e dati di magazzino disponibile accurati. Le aziende che utilizzano un sistema esterno di gestione del ciclo di vita del prodotto per l'acquisizione dei dati di prodotto possono dirigere i prodotti dalle app per la finanza e le operazioni ad altre app Dynamics 365. L'esperienza di prodotto unificata importa il modello di dati di prodotto integrato in Dataverse, di modo che tutti gli utenti delle applicazioni inclusi gli utenti di Power Platform possano usufruire dei dati di prodotto avanzati delle app per la finanza e le operazioni.

Di seguito è riportato il modello di dati di prodotto di Sales.

![Modello di dati per prodotti in CE.](media/dual-write-product-4.jpg)

Di seguito è riportato il modello di dati di prodotto delle app per la finanza e le operazioni.

![Modello di dati per prodotti in finanza e operazioni.](media/dual-write-products-5.jpg)

Questi due modelli di dati di prodotto sono stati integrati in Dataverse come mostrato di seguito.

![Modello di dati per prodotti nelle app Dynamics 365.](media/dual-write-products-6.jpg)

Le tabelle di entità di doppia scrittura per i prodotti sono state progettate per un flusso di dati esclusivamente unidirezionale e rappresentano un'esperienza pressoché in tempo reale dalle app per la finanza e le operazioni in Dataverse. Tuttavia, l'infrastruttura di prodotto è stata aperta per renderla bidirezionale, se necessario. Sebbene possa essere personalizzata, l'esecuzione è a proprio rischio, in quanto Microsoft non consiglia questo approccio.

## <a name="templates"></a>Modelli

Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento. Come mostrato nella tabella seguente, una raccolta di mappe della tabella viene creata per sincronizzare i prodotti e le informazioni correlate.

App Finanza e operazioni | Altre app Dynamics 365 | Description
-----------------------|--------------------------------|---
[Tutti i prodotti](mapping-reference.md#138) | msdyn_globalproducts | La tabella Tutti i prodotti contiene tutti i prodotti disponibili nelle app per la finanza e le operazioni, ovvero i prodotti rilasciati e quelli non rilasciati.
[Prodotti specifici CDS rilasciati](mapping-reference.md#213) | Prodotto | La tabella **Prodotto** contiene le colonne che definiscono il prodotto. Include singoli prodotti (prodotti con prodotto di sottotipo) e varianti prodotto. Nella seguente tabella sono riportati i mapping.
[Colori](mapping-reference.md#170) | msdyn\_productcolors
[Configurazioni](mapping-reference.md#171) | msdyn\_productconfigurations
[Impostazioni ordine predefinite](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Categorie prodotti](mapping-reference.md#166) | msdyn_productcategories | Le categorie di prodotti e le informazioni sulla struttura e sulle caratteristiche sono contenute nella tabella categoria di prodotti.
[Assegnazioni categoria prodotto](mapping-reference.md#167) | msdyn_productcategoryassignments | Per assegnare un prodotto a una categoria è possibile utilizzare la tabella assegnazioni di categoria di prodotto.
[Gerarchie di categorie prodotto](mapping-reference.md#168) | msdyn_productcategoryhierarchies | Utilizzare le gerarchie di prodotti per classificare o raggruppare prodotti. Le gerarchie di categorie sono disponibili in Dataverse utilizzando la tabella gerarchia di categorie di prodotti.
[Ruoli gerarchia di categorie prodotto](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | Le gerarchie di prodotti possono essere utilizzate per ruoli diversi nelle app per la finanza e le operazioni di D365. Specificano quale categoria viene utilizzata in ciascun ruolo utilizzato dalla tabella ruolo della categoria di prodotti.
[Impostazioni ordine predefinite prodotto V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[Gruppi di dimensioni prodotto](mapping-reference.md#173) | msdyn\_productdimensiongroups | Il gruppo di dimensioni prodotto determina le dimensioni prodotto che definiscono il prodotto.
[Colori rappresentazione generale prodotto](mapping-reference.md#187) | msdyn_sharedproductcolors | La tabella **Colore prodotto condiviso** indica i colori che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
[Configurazioni rappresentazione generale prodotto](mapping-reference.md#188) | msdyn_sharedproductconfigurations | La tabella **Configurazione prodotto condivisa** indica le configurazioni che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
[Dimensioni rappresentazione generale prodotto](mapping-reference.md#190) | msdyn_sharedproductsizes | La tabella **Dimensione prodotto condivisa** indica le dimensioni che una rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
[Stili rappresentazione generale prodotto](mapping-reference.md#191) | msdyn_sharedproductstyles | La tabella **Stile prodotto condiviso** indica gli stili che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Dataverse per assicurare la coerenza dei dati.
[Codice a barre identificato per numero prodotto](mapping-reference.md#164) | msdyn\_productbarcodes | I codici a barre sono utilizzati per identificare in modo univoco i prodotti.
[Conversioni unità specifiche del prodotto](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Prodotti rilasciati V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | La tabella **msdyn\_sharedproductdetails** contiene le colonne delle app per la finanza e le operazioni che definiscono il prodotto e che contengono le informazioni finanziarie e di gestione del prodotto.
[Dimensioni](mapping-reference.md#174) | msdyn\_productsizes
[Gruppi di dimensioni di immagazzinamento](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | Il gruppo di dimensioni di immagazzinamento prodotto rappresenta il metodo utilizzato per definire l'ubicazione del prodotto in magazzino.
[Stili](mapping-reference.md#178) | msdyn\_productstyles
[Gruppi di dimensioni di tracciabilità](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | Il gruppo di dimensioni di tracciabilità prodotto rappresenta il metodo utilizzato per tenere traccia del prodotto in magazzino.
[Unità](mapping-reference.md#219) | uoms
[Conversioni unità](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>Integrazione di prodotti

In questo modello, il prodotto è rappresentato dalla combinazione di due tabelle in Dataverse: **Prodotto** e **msdyn\_sharedproductdetails**. Mentre la prima tabella contiene la definizione di un prodotto (identificatore univoco per il prodotto, il nome del prodotto e la descrizione), la seconda tabella contiene le colonne archiviate a livello del prodotto. La combinazione di queste due tabelle viene utilizzata per definire il prodotto in base al concetto di unità di stockkeeping. Ogni prodotto rilasciato avrà le relative informazioni nelle tabelle menzionate (Prodotto e Dettagli prodotto condivisi). Per tenere traccia di tutti i prodotti (rilasciati e non rilasciati) si utilizza la tabella **Prodotti globali**.

Poiché il prodotto è rappresentato come unità di stockkeeping, i concetti di prodotti specifici, rappresentazioni generali prodotto e varianti prodotto possono essere acquisiti in Dataverse nel seguente modo:

- I **prodotti con prodotto di sottotipo** sono prodotti auto-definiti. Nessuna dimensione deve essere definita. Un esempio è un registro specifico. Per tali prodotti, viene creato una riga nella tabella **Prodotto** e una riga nella tabella **msdyn\_sharedproductdetails**. Non viene creato nessuna riga di famiglia di prodotti.
- Le **rappresentazioni generali prodotto** sono utilizzate come prodotti generici che contengono la definizione e le regole che determinano il comportamento nei processi aziendali. In base a queste definizioni, è possibile generare i prodotti specifici noti come varianti prodotto. Ad esempio, Maglietta è la rappresentazione generale prodotto e può avere le dimensioni Colore e Dimensione. È possibile rilasciare varianti che hanno differenti combinazioni di queste dimensioni, come una maglietta blu di taglia S o una maglietta verde di taglia M. Nell'integrazione, una riga per variante viene creato nella tabella dei prodotti. Tale riga contiene informazioni specifiche della variante, come le differenti dimensioni. Le informazioni generiche per il prodotto sono archiviate nella tabella **msdyn\_sharedproductdetails**. (queste informazioni generiche si trovano nella rappresentazione generale prodotto). Le informazioni relative alla rappresentazione generale prodotto vengono sincronizzate con Dataverse non appena viene creata la rappresentazione generale prodotto rilasciata (ma prima del rilascio delle varianti).
- I **prodotti specifici** fanno riferimento a tutti i prodotti di sottotipo e a tutte le varianti prodotto.

![Modello di dati per prodotti.](media/dual-write-product.png)

Con la funzionalità di doppia scrittura attivata, i prodotti di finanza e operazioni sono sincronizzati in altri prodotti Dynamics 365 nello stato **Bozza**. Vengono aggiunti al primo listino con la stessa valuta usata nell'app di customer engagement e usando l'ordinamento alfabetico sul nome del listino. In altre parole, sono aggiunte al primo listino prezzi in un'app Dynamics 365 che corrisponde alla valuta della tabella giuridica in cui il prodotto viene rilasciato in un'app per la finanza e le operazioni. Se non esiste un listino prezzi per la valuta data, verrà creato automaticamente un listino prezzi e il prodotto gli verrà assegnato.

L'attuale implementazione dei plugin a doppia scrittura che associano il listino prezzi predefinito all'unità cerca la valuta associata all'app per la finanza e le operazioni e trova il primo listino prezzi nell'app di interazione con i clienti utilizzando l'ordinamento alfabetico sul nome del listino prezzi. Per impostare un listino prezzi predefinito per una valuta specifica quando si dispone di più listini prezzi per quella valuta, è necessario aggiornare il nome del listino prezzi a un nome che appare prima nell'ordine alfabetico rispetto a qualsiasi altro listino prezzi per quella stessa valuta. Se non ha alcun listino per la valuta data, ne viene creato uno nuovo.

Per impostazione predefinita, i prodotti delle app per la finanza e le operazioni sono sincronizzati con altre app Dynamics 365 nello stato di **Bozza**. Per sincronizzare il prodotto con stato **Attivo** di modo che sia possibile utilizzarlo direttamente, ad esempio, nelle offerte di ordine cliente, è necessario selezionare **Creare prodotti in stato attivo = Sì** in **Sistema > Amministrazione > Amministrazione sistema > Impostazioni di sistema > Vendite**.

Quando i prodotti sono sincronizzati, è necessario immettere un valore per il campo **Unità di vendita** nell'app per la finanza e le operazioni, perché è un campo obbligatorio in Sales.

La creazione di famiglie di prodotti in Dynamics 365 Sales non è supportata con la sincronizzazione a doppia scrittura dei prodotti.

La sincronizzazione dei prodotti avviene dalle app per la finanza e le operazioni in Dataverse. Ciò significa che i valori delle colonne tabella prodotto possono essere modificati in Dataverse, ma quando viene attivata la sincronizzazione (quando una colonna prodotto viene modificato in un'app per la finanza e le operazioni), questo sovrascriverà i valori in Dataverse.

App Finanza e operazioni | App di interazione con i clienti |
---|---
[Prodotti specifici CDS rilasciati](mapping-reference.md#213) | Prodotto |
[Prodotti rilasciati V2](mapping-reference.md#189) | msdyn_sharedproductdetails |
[Tutti i prodotti](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>Dimensioni prodotto

Le dimensioni prodotto sono caratteristiche che identificano una variante prodotto. Le quattro dimensioni prodotto (colore, dimensione, stile e configurazione) vengono inoltre mappati a Dataverse per definire le varianti prodotto. Nella figura seguente è illustrato il modello di dati per la dimensione prodotto Colore. Lo stesso modello viene applicato a Dimensioni, Stili e Configurazioni.

![Modello di dati per dimensioni di prodotto.](media/dual-write-product-two.png)

App Finanza e operazioni | App di interazione con i clienti |
---|---
[Colori](mapping-reference.md#170) | msdyn\_productcolors
[Dimensioni](mapping-reference.md#174) | msdyn\_productsizes
[Stili](mapping-reference.md#178) | msdyn\_productstyles
[Configurazioni](mapping-reference.md#171) | msdyn\_productconfigurations

Quando un prodotto ha dimensioni prodotto differenti (ad esempio una rappresentazione generale prodotto ha Colore e Prodotto come dimensioni prodotto, ovvero ogni variante prodotto) è definito come combinazione di tali dimensioni prodotto. Ad esempio, il numero prodotto B0001 è una maglietta nera di taglia XS e il numero prodotto B0002 è una maglietta nera di taglia S. In questo caso, le combinazioni esistenti delle dimensioni prodotto sono definite. Ad esempio, la maglietta dell'esempio precedente può essere nera e di taglia XS, S, M o L, ma non può essere nera e di taglia XL. In altre parole, le dimensioni prodotto che una rappresentazione generale prodotto può avere sono specificate e le varianti possono essere rilasciate in base a tali valori.

Per tenere traccia delle dimensioni prodotto che una rappresentazione generale prodotto può utilizzare, le seguenti tabelle vengono create e mappate in Dataverse per ogni dimensione prodotto. Per ulteriori informazioni, vedere [Panoramica delle informazioni sul prodotto](../../../../supply-chain/pim/product-information.md).

App Finanza e operazioni | App di interazione con i clienti |
---|---
[Colori rappresentazione generale prodotto](mapping-reference.md#187) | msdyn_sharedproductcolors |
[Configurazioni rappresentazione generale prodotto](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[Dimensioni rappresentazione generale prodotto](mapping-reference.md#190) | msdyn_sharedproductsizes |
[Stili rappresentazione generale prodotto](mapping-reference.md#191) | msdyn_sharedproductstyles |
[Codice a barre identificato per numero prodotto](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Impostazioni ordine predefinite e impostazioni ordine predefinite specifiche del prodotto

Le impostazioni ordine predefinite definiscono il sito e il magazzino in cui gli articoli saranno prelevati o archiviati, le quantità minima, massima, multipla e standard che verrà utilizzata per il commercio o la gestione degli articoli, i lead time, il flag di interruzione e il metodo delle promesse ordine. Queste informazioni sono disponibili in Dataverse mediante le impostazioni ordine predefinite e le impostazioni ordine predefinite specifiche del prodotto. Per ulteriori informazioni sulla funzionalità, vedi l'articolo [Impostazioni ordine predefinite](../../../../supply-chain/production-control/default-order-settings.md).

App Finanza e operazioni | App di interazione con i clienti |
---|---
[Impostazioni ordine predefinite](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Impostazioni ordine predefinite prodotto V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unità di misura e conversioni di unità di misura

Le unità di misura e la relativa conversione sono disponibili in Dataverse mediante il modello di dati visualizzato nel diagramma.

![Modello di dati per unità di misura.](media/dual-write-product-three.png)

Il concetto di unità di misura è integrato tra le app per la finanza e le operazioni e altre app Dynamics 365. Per ogni classe di unità di misura in un'app per la finanza e le operazioni, viene creata un'unità di vendita in un'app Dynamics 365, che contiene le unità appartenenti alla classe di unità. Un'unità di base predefinita viene inoltre creata per ogni gruppo di unità.

App Finanza e operazioni | App di interazione con i clienti |
---|---
[Conversioni unità specifiche del prodotto](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Unità](mapping-reference.md#219) | uoms
[Conversioni unità](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Sincronizzazione iniziale della corrispondenza dei dati delle unità tra le app per la finanza e le operazioni e Dataverse

### <a name="initial-synchronization-of-units"></a>Sincronizzazione iniziale delle unità

Quando la doppia scrittura è abilitata, le unità delle app per la finanza e le operazioni sono sincronizzate con altre app Dynamics 365. I gruppi di unità sincronizzati dalle app per la finanza e le operazioni in Dataverse dispongono di un flag che indica che sono "gestiti esternamente".

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Corrispondenza di unità e dati di classi/gruppi di unità da finanza e operazioni e altre app di Dynamics 365

Innanzitutto, è importante notare che la chiave di integrazione per l'unità è msdyn_symbol. Di conseguenza, questo valore deve essere univoco in Dataverse o in altre app Dynamics 365. Poiché in altre app Dynamics 365 è la coppia "ID gruppo unità" e "Nome" che definiscono l'unicità di un'unità, è necessario prendere in considerazione scenari diversi per la corrispondenza dei dati dell'unità tra app per la finanza e le operazioni e Dataverse.

Per le unità che corrispondono o si sovrappongono nelle app per la finanza e le operazioni e altre app di Dynamics 365:

+ **L'unità appartiene a un'unità di vendita in altre app Dynamics 365 che corrisponde alla classe di unità associata nelle app per la finanza e le operazioni**. In questo caso, la colonna msdyn_symbol in altre app Dynamics 365 deve essere compilato con il simbolo dell'unità dalle app per la finanza e le operazioni. Pertanto, quando i dati verranno abbinati e il gruppo di unità verrà impostato come "Gestito esternamente" in altre app di Dynamics 365.
+ **L'unità appartiene a un'unità di vendita in altre app Dynamics 365 che non corrisponde alla classe di unità associata nelle app per la finanza e le operazioni (nessuna classe di unità esistente nelle app per la finanza e le operazioni per la classe di unità in altre app Dynamics 365).** In questo caso, il campo msdyn_symbol deve essere compilato con una stringa casuale. Notare che questo valore deve essere univoco in altre app Dynamics 365.

Per le unità e le classi di unità in finanza e operazioni che non esistono in altre app di Dynamics 365:

Come parte della doppia scrittura, le unità di vendita dalle app per la finanza e le operazioni e le unità corrispondenti vengono create e sincronizzate in altre app Dynamics 365 e Dataverse e il gruppo di unità verrà impostato come "Gestito esternamente". Non è richiesto alcun ulteriore azione di bootstrap.

Per le unità in altre app di Dynamics 365 che non esistono nelle app per la finanza e le operazioni:

La colonna msdyn_symbol deve essere compilato per tutte le unità. Le unità possono sempre essere create nelle app per la finanza e le operazioni nella classe di unità corrispondente (se esiste). Se la classe di unità non esiste, è necessario innanzitutto creare la classe di unità (tenere presente che non è possibile creare una classe di unità nelle app per la finanza e le operazioni se non tramite l'estensione se si sta estendendo l'enumerazione) corrispondente all'altro gruppo di unità delle app Dynamics 365. È possibile quindi creare l'unità. Si noti che il simbolo dell'unità nelle app per la finanza e le operazioni deve essere il campo msdyn_symbol precedentemente specificato in altre app Dynamics 365 per l'unità.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Criteri di prodotto: gruppi di dimensioni, tracciabilità e archiviazioni

I criteri di prodotto sono set di criteri utilizzati per definire i prodotti e le relative caratteristiche in magazzino. Il gruppo di dimensioni prodotto, di dimensioni di tracciabilità e di dimensioni di immagazzinamento sono disponibili come criteri di prodotto.

App Finanza e operazioni | App di interazione con i clienti |
---|---
[Gruppi di dimensioni prodotto](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[Gruppi di dimensioni di immagazzinamento](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[Gruppi di dimensioni di tracciabilità](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>Gerarchie di prodotti

App Finanza e operazioni | App di interazione con i clienti |
---|---
[Assegnazioni categoria prodotto](mapping-reference.md#167) | msdyn_productcategoryassignments |
[Gerarchie di categorie prodotto](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[Ruoli gerarchia di categorie prodotto](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>Chiave di integrazione per i prodotti

Per identificare in modo univoco i prodotti tra Dynamics 365 Finance e i prodotti in Dataverse vengono utilizzate le chiavi di integrazione.
Per i prodotti, il **(productnumber)** è la chiave univoca che identifica un prodotto in Dataverse. È composta dalla concatenazione di: **(società, msdyn_productnumber)**. La **società** indica la persona giuridica in finanza e operazioni e **msdyn_productnumber** indica il numero del prodotto specifico in finanza e operazioni.

Per gli utenti di altre app Dynamics 365, il prodotto viene identificato nell'interfaccia utente con **msdyn_productnumber** (notare che l'etichetta della colonna è **Numero prodotto**). Nel modulo del prodotto sono mostrati sia l'azienda che il msydn_productnumber. Tuttavia, la colonna (productnumber), la chiave univoca per un prodotto, non viene visualizzato.

Se si creano app in Dataverse, è necessario prestare attenzione all'utilizzo di **productnumber** (l'ID univoco del prodotto) come chiave di integrazione. Non usare **msdyn_productnumber** perché non è univoco.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Sincronizzazione iniziale dei prodotti e migrazione dei dati da Dataverse a finanza e operazioni

### <a name="initial-synchronization-of-products"></a>Sincronizzazione iniziale dei prodotti

Quando la doppia scrittura è abilitata, i prodotti delle app per la finanza e le operazioni sono sincronizzati con Dataverse e altre app di interazione con i clienti. I prodotti creati in Dataverse e nelle altre app Dynamics 365 prima che fosse rilasciata la doppia scrittura non verranno aggiornati o abbinati ai dati del prodotto dalle app per la finanza e le operazioni.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Corrispondenza dei dati di prodotto da finanza e operazioni e altre app di Dynamics 365

Se gli stessi prodotti vengono mantenuti (sovrapposti/corrispondenti) in finanza e operazioni e in Dataverse e in altre app Dynamics 365, quando si abilita la doppia scrittura verrà eseguita la sincronizzazione dei prodotti di finanza e operazioni e verranno visualizzate righe duplicate in Dataverse per lo stesso prodotto.
Per evitare la situazione precedente, se altre app Dynamics 365 hanno prodotti che si sovrappongono / corrispondono a finanza e operazioni, l'amministratore che abilita la doppia scrittura deve avviare le colonne **Società** (esempio: "USMF") e **msdyn_productnumber** (esempio: "1234:Black:S") prima che abbia luogo la sincronizzazione dei prodotti. In altre parole, queste due colonne nel prodotto in Dataverse devono essere compilati con la rispettiva società in finanza e operazioni a cui il prodotto deve essere associato e con il suo numero di prodotto.

Quindi, quando la sincronizzazione è abilitata e ha luogo, i prodotti di finanza e operazioni verranno sincronizzati con i prodotti corrispondenti in Dataverse e altre app di Dynamics 365. Ciò è applicabile sia a prodotti distinti sia a varianti di prodotto.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migrazione dei dati di prodotto da altre app di Dynamics 365 a finanza e operazioni

Se altre app di Dynamics 365 hanno prodotti che non sono presenti in finanza e operazioni, l'amministratore può innanzitutto utilizzare **EcoResReleasedProductCreationV2Entity** per importare tali prodotti in finanza e operazioni. In secondo luogo, abbina i dati di prodotto di finanza e operazioni e altre app di Dynamics 365 come descritto sopra.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

