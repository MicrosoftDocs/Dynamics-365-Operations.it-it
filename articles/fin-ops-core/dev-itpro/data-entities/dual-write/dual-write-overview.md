---
title: Panoramica della doppia scrittura
description: Questo argomento fornisce una panoramica della doppia scrittura. La doppia scrittura è un'infrastruttura che fornisce interazione quasi in tempo reale tra le app Microsoft Dynamics 365 basate su modelli e le app Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 961e6a167d4fe48c96bffcff1e54acde0ad5d805
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997426"
---
# <a name="dual-write-overview"></a>Panoramica della doppia scrittura

[!include [banner](../../includes/banner.md)]



## <a name="what-is-dual-write"></a>Che cos'è la doppia scrittura?

La doppia scrittura è un'infrastruttura predefinita che fornisce interazione quasi in tempo reale tra le app Customer Engagement e le app Finance and Operations. Quando i dati su clienti, prodotti, persone e operazioni scorrono oltre i confini delle applicazioni, tutti i reparti di un'organizzazione sono potenziati.

La doppia scrittura fornisce un'integrazione bidirezionale strettamente connessa tra le app Finance and Operations e Common Data Service. Qualsiasi modifica dei dati nelle app Finance and Operations causa scritture in Common Data Service e qualsiasi modifica dei dati in in Common Data Service causa scritture nelle app Finance and Operations. Questo flusso di dati automatizzato offre un'esperienza utente integrata tra le app.

![Rapporto dei dati tra le app](media/dual-write-overview.jpg)

La doppia scrittura ha due aspetti: un aspetto *infrastruttura* e un aspetto *applicazione*.

### <a name="infrastructure"></a>Infrastruttura

L'infrastruttura a doppia scrittura è estensibile e affidabile e include le seguenti funzionalità chiave:

+ Flusso di dati sincrono e bidirezionale tra le applicazioni
+ Sincronizzazione, insieme alle modalità di riproduzione, pausa e ammortamento per supportare il sistema in modalità online e offline/asincrona.
+ Possibilità di sincronizzare i dati iniziali tra le applicazioni
+ Visualizzazione combinata dei log di attività ed errori per gli amministratori dei dati
+ Possibilità di configurare allarmi e soglie personalizzate e di iscriversi alle notifiche
+ Interfaccia utente intuitiva per filtraggio e trasformazioni
+ Capacità di impostare e visualizzare le dipendenze e le relazioni tra entità
+ Estensibilità per entità e mappe standard e personalizzate
+ Gestione affidabile del ciclo di vita delle applicazioni
+ Esperienza di installazione predefinita per i nuovi clienti

### <a name="application"></a>Richiesta

La doppia scrittura crea una mappatura tra i concetti nelle app Finance and Operations e concetti nelle app in Customer Engagement. Questa integrazione supporta i seguenti scenari:

+ Dati master clienti integrati
+ Accesso alle carte fedeltà dei clienti e ai punti premio
+ Esperienza di gestione del prodotto unificata
+ Consapevolezza della gerarchia organizzativa
+ Dati master fornitori integrati
+ Accesso ai dati finanziari e di riferimento imposte
+ Esperienza del motore dei prezzi su richiesta
+ Esperienza integrata da prospect a contanti
+ Capacità di servire sia beni interni che beni dei clienti attraverso agenti sul campo
+ Esperienza approvvigionamento per pagamento integrata
+ Attività integrate e note per dati e documenti dei clienti
+ Capacità di cercare le scorte disponibili e i dettagli
+ Esperienza da progetto a contanti
+ Capacità di gestire più indirizzi e ruoli attraverso il concetto di parte
+ Gestione di un'unica origine per gli utenti
+ Canali integrati per la vendita al dettaglio e il marketing
+ Visibilità di promozioni e sconti
+ Funzioni di richiesta di assistenza
+ Operazioni di servizio semplificate

## <a name="top-reasons-to-use-dual-write"></a>Principali motivi per utilizzare la doppia scrittura

La doppia scrittura fornisce l'integrazione dei dati tra le applicazioni Microsoft Dynamics 365. Questa solido framework collega gli ambienti e consente a diverse applicazioni aziendali di lavorare insieme. Ecco i motivi principali per cui usare la doppia scrittura:

+ La doppia scrittura fornisce un'integrazione strettamente collegata, quasi in tempo reale e bidirezionale tra le app Finance and Operations e le app basate su modello in Dynamics 365. Questa integrazione rende Microsoft Dynamics 365 il punto principale per tutte le soluzioni aziendali. I clienti che usano Dynamics 365 Finance e Dynamics 365 Supply Chain Management, ma che utilizzano soluzioni non Microsoft per la gestione delle relazioni con i clienti (CRM), si stanno muovendo verso Dynamics 365 per il supporto della doppia scrittura.
+ I dati provenienti da clienti, prodotti, operazioni, progetti e Internet of Things (IoT) passano automaticamente a Common Data Service attraverso la doppia scrittura. Questa connessione è utile per le aziende interessate alle espansioni Power Platform.
+ L'infrastruttura a doppia scrittura segue il principio senza codice/poco codice. È necessario un minimo sforzo di progettazione per estendere le mappe da tabella a tabella standard e per includere mappe personalizzate.
+ La doppia scrittura supporta sia la modalità online che la modalità offline. Microsoft è l'unica azienda che offre supporto per le modalità online e offline.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Cosa significa la doppia scrittura per sviluppatori e architetti di app Customer Engagement?

La doppia scrittura automatizza il flusso di dati tra le app Finance and Operations e Customer Engagement. La doppia scrittura è composta da due soluzioni AppSource installate su Common Data Service. Le soluzioni espandono lo schema delle entità, i plug-in e i flussi di lavoro in Common Data Service in modo che possano scalare alla dimensione ERP. Per un'implementazione corretta, gli sviluppatori e gli architetti delle app Customer Engagement devono comprendere questi cambiamenti e collaborare con le loro controparti delle app Finance and Operations.

Per creare parità con le applicazioni Finance and Operations, la doppia scrittura apporta alcune modifiche cruciali nello schema Common Data Service. Se si comprende il piano, è possibile evitare alcune modifiche di progettazione e sviluppo in futuro.

+ Quando il il pacchetto AppSource di doppia scrittura è installato, Common Data Service avrà nuovi concetti come società e parte. Questi concetti aiutano le applicazioni basate su Common Data Service, inclusi Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service, a interagire perfettamente con le app Finance and Operations.

+ Le attività e le note sono unificate e ampliate per supportare sia i C1 (utenti del sistema) che i C2 (clienti del sistema).

+ Per evitare la perdita di dati durante la trasmissione di valuta tra le app Finance and Operations e Common Data Service, è possibile estendere il numero di cifre decimali nel tipo di dati di valuta delle app Customer Engagement. La funzione converte automaticamente i record esistenti nel nuovo stato esteso a livello dei metadati. Durante questo processo, il valore della valuta viene convertito in dati decimali anziché in dati monetari e il valore della valuta supporta 10 cifre decimali. Questa funzione richiede il consenso esplicito e le organizzazioni che non richiedono più di 4 cifre decimali di precisione non hanno bisogno di aderire. Per ulteriori informazioni, vedere [Migrazione del tipo di dati valuta per la doppia scrittura](currrency-decimal-places.md).

+ [Validità della data](../../dev-tools/date-effectivity.md) sarà aggiunta a Common Data Service. Supporterà i dati passati, presenti e futuri nella stessa entità.

+ Le [conversioni di unità](../../../../supply-chain/pim/tasks/manage-unit-measure.md) del prodotto sono supportate per prodotti, offerte, ordini e fatture.

Per ulteriori informazioni sulle modifiche imminenti, vedere [Novità o modifiche della doppia scrittura](whats-new-dual-write.md).

