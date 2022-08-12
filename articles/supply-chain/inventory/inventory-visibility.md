---
title: Panoramica del componente aggiuntivo Visibilità dell'inventario
description: Questo articolo spiega cos'è la visibilità dell'inventario e ne descrive le caratteristiche.
author: yufeihuang
ms.date: 03/18/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 274f9b368a6074725d1938de5f2172d2810a5985
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066642"
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

## <a name="feature-highlights"></a>Caratteristiche principali

### <a name="get-a-global-view-of-real-time-inventory"></a>Ottenere una visione globale dell'inventario in tempo reale

La visibilità inventario ti garantisce l'accesso alle quantità di inventario più aggiornate in ogni momento, in tutti i tuoi canali, sedi e magazzini. Potrai trarre il massimo vantaggio dall'utilizzarlo per supportare la tua attività operativa quotidiana ogni volta che devi ottenere un record di inventario. L'inventario fisico disponibile, le quantità vendute e le quantità acquistate sono tutti disponibili immediatamente. Puoi anche configurare altre misure di inventario fisico (come dati restituiti, messi in quarantena e registrati) in base alle tue esigenze, per ottenere quei dettagli in tempo reale. La visibilità inventario può elaborare in modo efficiente milioni di registrazioni di modifica dell'inventario. Questi dati possono essere aggregati e riflessi nelle ultime quantità di inventario nel servizio immediatamente, al secondo o al minuto, a seconda dell'intervallo in cui i dati vengono registrati. Per maggiori informazioni, vedi [API pubbliche di Visibilità inventario](inventory-visibility-api.md).

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Prenotazione temporanea per evitare vendite eccessive su tutti i canali degli ordini

Una *prenotazione temporanea* ti consente di assegnare o contrassegnare quantità specifiche per evadere un ordine o una domanda. Una prenotazione temporanea non influisce sull'inventario fisico, ma viene dedotta dalla quantità di inventario *disponibile per la prenotazione* e fornisce una quantità aggiornata per l'evasione degli ordini futuri. Questa funzione sarà utile se le richieste di vendita o gli ordini arrivano alla tua azienda da uno o più canali o origini dati che sono al di fuori del tuo sistema di pianificazione delle risorse aziendali (ERP) del sistema di record.

Se non utilizzi le prenotazioni temporanee nel servizio di visibilità inventario, devi attendere che l'ordine venga sincronizzato ed elaborato dal tuo sistema ERP per ottenere un aggiornamento della quantità fisica dell'inventario. Questo processo ha in genere un'enorme latenza. Tuttavia, le prenotazioni temporanee hanno effetto immediato ogni volta che viene generata una richiesta di vendita o un ordine nei tuoi canali di vendita. Pertanto, aiutano a prevenire situazioni di vendite eccessive assicurando che i tuoi ordini multicanale non interferiscano tra loro quando alla fine raggiungono il sistema ERP. Le prenotazioni temporanee assicurano inoltre che tu possa evadere tutti gli ordini che hai promesso. Pertanto, ti aiutano a soddisfare le aspettative dei clienti e a mantenere la fedeltà dei clienti. Per maggiori informazioni, vedere [Prenotazioni di visibilità dell'inventario](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-dates-confirmation"></a>Risposta immediata di conferma date ATP

La visibilità dell'inventario previsto per il prossimo futuro (inclusi offerta, domanda e dettagli delle scorte disponibili previste) è importante, perché aiuta la tua azienda a raggiungere i seguenti obiettivi:

- Ridurre al minimo i livelli di inventario per ridurre i costi di gestione dell'inventario.
- Facilitare l'elaborazione interna degli ordini, in modo che i venditori possano calcolare le date di spedizione e consegna, in base alla disponibilità dei prodotti ordinati.
- Fornire trasparenza su quando i clienti possono aspettarsi che un articolo esaurito diventi disponibile, fornendo la successiva data di disponibilità.

La funzione ATP è facile da adottare nel processo quotidiano di evasione degli ordini. Ancora più importante, come altre offerte di visibilità inventario, la funzione ATP è *globale e in tempo reale*. Pertanto, puoi impostare più formule di calcolo dell'ATP per avere query sulla disponibilità completa dell'inventario che coprano tutti i tuoi canali aziendali e le origini dati. Per altre informazioni vedi [Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise](inventory-visibility-available-to-promise.md).

### <a name="compatibility-with-warehouse-management-processes-wms-items"></a>Compatibilità con articoli dei processi di gestione del magazzino (WMS)

Microsoft mira a fornire un'integrazione predefinita con i processi di gestione del magazzino (WMS), in modo che anche i clienti WMS possano usufruire dei vantaggi del servizio di visibilità inventario. Per il primo ciclo di rilascio del 2022 (anteprima pubblica a marzo), il servizio di inventario supporta le query WMS sugli articoli disponibili e l'ATP. La funzione di prenotazione e assegnazione temporanea sarà supportata per i clienti WMS nel prossimo ciclo. Per maggiori informazioni, vedere [Supporto di visibilità inventario per articoli WMS](inventory-visibility-whs-support.md).

## <a name="licensing"></a>Licenze

Il servizio di visibilità inventario è disponibile nelle seguenti versioni:

- **Componente aggiuntivo Visibilità inventario per Microsoft Dynamics 365 Supply Chain Management** – Per le aziende che dispongono di una licenza di Supply Chain Management valida, Visibilità inventario è disponibile senza costi di licenza aggiuntivi. Puoi iniziare a provarlo oggi. Per i dettagli sull'installazione, vedi [Installare e configurare Visibilità inventario](inventory-visibility-setup.md).
- **Servizio di visibilità inventario come componente di IOM** – Questa versione è per i clienti di Intelligent Order Management (IOM) o per le aziende che non utilizzano Supply Chain Management come sistema ERP. La licenza è inclusa nell'aggregazione IOM. Per ulteriori informazioni, vedi [Panoramica di Intelligent Order Management](/dynamics365/intelligent-order-management/overview).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
