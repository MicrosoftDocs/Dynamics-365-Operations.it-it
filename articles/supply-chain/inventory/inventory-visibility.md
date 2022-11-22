---
title: Panoramica del componente aggiuntivo Visibilità dell'inventario
description: Questo articolo spiega cos'è la visibilità dell'inventario e ne descrive le caratteristiche.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dd790bcaada0c1a05e46b4edacaa31fc4e15be92
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762809"
---
# <a name="inventory-visibility-add-in-overview"></a>Panoramica del componente aggiuntivo Visibilità dell'inventario

[!include [banner](../includes/banner.md)]

Il componente aggiuntivo di Visibilità inventario (chiamato anche *servizio di visibilità inventario*) fornisce un microservizio indipendente e altamente scalabile che consente la registrazione in tempo reale delle modifiche dell'inventario e il monitoraggio della visibilità su tutte le origini dati e sui canali. Fornisce una piattaforma che ti consente di gestire il tuo inventario globale utilizzando funzionalità che includono (ma non si limitano a) il seguente elenco:

- Tieni traccia centralmente dello stato dell'inventario più recente (come disponibile, ordinato, acquistato, in transito, restituito e messo in quarantena) in tutte le tue origini dati, magazzini e ubicazioni collegando Supply Chain Management o le origini dati logistiche di terze parti (come sistemi di gestione degli ordini, sistemi \[ERP\] di terze parti, sistemi \[POS\] e sistemi di gestione del magazzino) al servizio di visibilità inventario.
- Esegui la query sulla disponibilità e sulle carenze delle scorte disponibili e ottieni risposte immediate chiamando direttamente il servizio di visibilità inventario.
- Evita le vendite eccessive, soprattutto quando la tua domanda proviene da canali diversi, effettuando prenotazioni temporanee in tempo reale nel servizio di visibilità inventario.
- Gestisci meglio gli ordini promessi e le aspettative dei clienti fornendo date precise attuali o di prossima disponibilità, in modo che la funzione multicanale available-to-promise (ATP) possa calcolare le date di evasione degli ordini previste.

## <a name="extensibility"></a>Estendibilità

Il servizio di visibilità inventario è altamente estensibile perché l'input e l'output dei dati non sono limitati alle applicazioni Microsoft. I sistemi esterni possono accedere al servizio tramite le API (Application Programming Interface) RESTful. Oltre a utilizzare le mappature predefinite fornite per l'origine dati e le dimensioni di Supply Chain Management, è possibile integrare la visibilità dell'inventario con più sistemi di terze parti impostando origini dati aggiuntive, misure dello stato dell'inventario (denominate *misure fisiche* nel servizio di visibilità inventario) e le dimensioni dell'inventario tramite l'app di configurazione. In questo modo, puoi eseguire query e modificare in modo flessibile più origini dati e dimensioni di inventario predefinite.

Inoltre, poiché la visibilità inventario è basata su Microsoft Dataverse, i dati possono essere utilizzati per creare e integrare usando Power Apps. Puoi anche usare Power BI per creare dashboard personalizzati che soddisfino i requisiti aziendali.

## <a name="scalability"></a>Scalabilità

Il servizio di visibilità inventario può essere ridimensionato verso l'alto o verso il basso, a seconda del volume di dati. L'esperienza di scalabilità è per lo più fluida ed è condotta dal team della piattaforma Microsoft, in base al rilevamento e alla valutazione automatici del volume dei dati delle transazioni.

Nell'illustrazione riportata di seguito viene mostrata una panoramica dell'architettura di Visibilità inventario.

[<img src="media/inventory-visibility-architecture.png" alt="Inventory Visibility architecture." title="Architettura di Visibilità inventario" width="720" />](media/inventory-visibility-architecture.png)

## <a name="feature-highlights"></a>Caratteristiche principali

### <a name="get-a-global-view-of-real-time-inventory"></a>Ottenere una visione globale dell'inventario in tempo reale

La visibilità inventario ti garantisce l'accesso alle quantità di inventario più aggiornate in ogni momento, in tutti i tuoi canali, sedi e magazzini. Potrai trarre il massimo vantaggio dall'utilizzarlo per supportare la tua attività operativa quotidiana ogni volta che devi ottenere un record di inventario. L'inventario fisico disponibile, le quantità vendute e le quantità acquistate sono tutti disponibili immediatamente. Puoi anche configurare altre misure di inventario fisico (come dati restituiti, messi in quarantena e registrati) in base alle tue esigenze, per ottenere quei dettagli in tempo reale. La visibilità inventario può elaborare in modo efficiente milioni di registrazioni di modifica dell'inventario. Questi dati possono essere aggregati e riflessi nelle ultime quantità di inventario nel servizio immediatamente, al secondo o al minuto, a seconda dell'intervallo in cui i dati vengono registrati. Per maggiori informazioni, vedi [API pubbliche di Visibilità inventario](inventory-visibility-api.md).

### <a name="central-inventory-adjustment"></a>Rettifica magazzino centrale

Visibilità inventario consente ai sistemi esterni di chiamare la relativa API per pubblicare le modifiche all'inventario. Le modifiche avranno effetto immediato in Visibilità inventario. Pertanto le scorte disponibili vengono istantaneamente detratte.

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Prenotazione temporanea per evitare vendite eccessive su tutti i canali degli ordini

Una *prenotazione temporanea* ti consente di assegnare o contrassegnare quantità specifiche per evadere un ordine o una domanda. Una prenotazione temporanea non influisce sull'inventario fisico, ma viene dedotta dalla quantità di inventario *disponibile per la prenotazione* e fornisce una quantità aggiornata per l'evasione degli ordini futuri. Questa funzione sarà utile se le richieste di vendita o gli ordini arrivano alla tua azienda da uno o più canali o origini dati che sono al di fuori del tuo sistema di pianificazione delle risorse aziendali (ERP) del sistema di record.

Se non utilizzi le prenotazioni temporanee nel servizio di visibilità inventario, devi attendere che l'ordine venga sincronizzato ed elaborato dal tuo sistema ERP per ottenere un aggiornamento della quantità fisica dell'inventario. Questo processo ha in genere un'enorme latenza. Tuttavia, le prenotazioni temporanee hanno effetto immediato ogni volta che viene generata una richiesta di vendita o un ordine nei tuoi canali di vendita. Pertanto, aiutano a prevenire situazioni di vendite eccessive assicurando che i tuoi ordini multicanale non interferiscano tra loro quando alla fine raggiungono il sistema ERP. Le prenotazioni temporanee assicurano inoltre che tu possa evadere tutti gli ordini che hai promesso. Pertanto, ti aiutano a soddisfare le aspettative dei clienti e a mantenere la fedeltà dei clienti. Per maggiori informazioni, vedere [Prenotazioni di Visibilità inventario](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-quantity-and-dates"></a>Risposta immediata di quantità e date ATP

La visibilità dell'inventario previsto per il prossimo futuro (inclusi offerta, domanda e dettagli delle scorte disponibili previste) è importante, perché aiuta la tua azienda a raggiungere i seguenti obiettivi:

- Ridurre al minimo i livelli di inventario per ridurre i costi di gestione dell'inventario.
- Facilitare l'elaborazione interna degli ordini, in modo che i venditori possano calcolare le date di spedizione e consegna, in base alla disponibilità dei prodotti ordinati.
- Fornire trasparenza su quando i clienti possono aspettarsi che un articolo esaurito diventi disponibile, fornendo la successiva data di disponibilità.

La funzione ATP è facile da adottare nel processo quotidiano di evasione degli ordini. Ancora più importante, come altre offerte di visibilità inventario, la funzione ATP è *globale e in tempo reale*. Pertanto, puoi impostare più formule di calcolo dell'ATP per avere query sulla disponibilità completa dell'inventario che coprano tutti i tuoi canali aziendali e le origini dati. Per altre informazioni vedi [Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise](inventory-visibility-available-to-promise.md).

### <a name="preallocate-your-stock-to-important-channels-or-customers-with-inventory-allocation"></a>Preassegna il tuo stock a canali o clienti importanti con l'allocazione dell'inventario

La funzionalità di allocazione di Visibilità inventario consente di proteggere e delimitare le tue preziose scorte disponibili per canali, gruppi di clienti o sedi importanti. Dopo l'allocazione dello stock, il consumo di inventario è limitato al pool allocato e le quantità rimaste nel pool verranno detratte quasi in tempo reale per riflettere la quantità ancora disponibile per il consumo. Per ulteriori informazioni, vedi [Allocazione dell'inventario di Visibilità inventario](inventory-visibility-allocation.md).

### <a name="compatibility-with-wms-items"></a>Compatibilità con gli articoli WMS

Microsoft mira a fornire un'integrazione predefinita con i processi di gestione del magazzino (WMS), in modo che anche i clienti WMS possano usufruire dei vantaggi del servizio di visibilità inventario. Per il primo ciclo di rilascio del 2022 (anteprima pubblica a marzo), il servizio di inventario supporta le query WMS sugli articoli disponibili e l'ATP. La funzione di prenotazione e assegnazione temporanea sarà supportata per i clienti WMS nel prossimo ciclo. Per maggiori informazioni, vedere [Supporto di visibilità inventario per articoli WMS](inventory-visibility-whs-support.md).

La figura seguente mostra un riepilogo generale delle funzionalità esistenti e come possono essere posizionate nel flusso di dati.

[<img src="media/inventory-visibility-feature-overview.png" alt="Inventory Visibility feature overview." title="Panoramica della funzionalità Visibilità dell'inventario" width="720" />](media/inventory-visibility-feature-overview.png)

## <a name="licensing"></a>Licenze

Il servizio di visibilità inventario è disponibile nelle seguenti versioni:

- **Componente aggiuntivo Visibilità inventario per Microsoft Dynamics 365 Supply Chain Management** – Per le aziende che dispongono di una licenza di Supply Chain Management valida, Visibilità inventario è disponibile senza costi aggiuntivi. Dal momento che la visibilità dell'inventario si basa su Microsoft Power Platform, è soggetta alla capacità di archiviazione e ai limiti API di Microsoft Power Platform . La tua licenza di Supply Chain Management dovrebbe includere capacità dell'API e di archiviazione predefinita. Se hai bisogno di più spazio di archiviazione e capacità API, puoi acquistare una licenza professionale. Per i dettagli sull'allocazione dell'API predefinita e sulla licenza professionale, vedere [Richiedere limiti e allocazioni](/power-platform/admin/api-request-limits-allocations) e [Panoramica delle licenze per Microsoft Power Platform](/power-platform/admin/pricing-billing-skus). Con l'archiviazione predefinita e le allocazioni API, puoi iniziare a provare il componente aggiuntivo Visibilità inventario oggi stesso. Per i dettagli sull'installazione, vedi [Installare e configurare Visibilità inventario](inventory-visibility-setup.md). Se l'API e l'utilizzo dello spazio di archiviazione stimati superano l'allocazione standard, puoi contattare il tuo rappresentante di vendita e chiedere loro di contattare il team della piattaforma per un'eccezione.
- **Servizio di visibilità inventario come componente di IOM** – Questa versione è per i clienti di Intelligent Order Management (IOM) o per le aziende che non utilizzano Supply Chain Management come sistema ERP. La licenza è inclusa nel pacchetto Intelligent Order Management. Per ulteriori informazioni, vedi [Panoramica di Intelligent Order Management](/dynamics365/intelligent-order-management/overview).

## <a name="inventory-visibility-terminology"></a>Terminologia di Visibilità inventario

È importante comprendere i seguenti concetti e termini quando si lavora con il componente aggiuntivo Visibilità inventario:

- **Origine dati**: un'origine dati rappresenta il sistema da cui provengono i tuoi dati.
- **Dimensioni**: le dimensioni identificano le caratteristiche del prodotto. Possono essere dimensioni di immagazzinamento (come sito o magazzino) o dimensioni prodotto (come colore, taglia o stile).
- **Misure fisiche**: le misure fisiche sono quantità che misurano diversi stati dell'inventario, ad esempio disponibile, acquistato, ordinato o venduto.
- **Misure calcolate**: le misure calcolate sono misure quantitative calcolate da un insieme di misure fisiche. Ad esempio, la misura calcolata *Totale disponibile* è calcolata come *Disponibilità* + *Acquistata* – *Su ordine* – *Venduta*.
- **Partizione**: una partizione definisce una gerarchia per il modo in cui la visibilità dell'inventario distribuirà i dati ricevuti. Attualmente, la partizione predefinita è sito e posizione.
- **Gerarchia indice**: una gerarchia di indici definisce ulteriormente il modo in cui si desidera interrogare l'inventario e ottenere risultati con maggiore granularità.

Per ulteriori informazioni su questi termini e concetti, vedi [Configurare Visibilità inventario](inventory-visibility-configuration.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
