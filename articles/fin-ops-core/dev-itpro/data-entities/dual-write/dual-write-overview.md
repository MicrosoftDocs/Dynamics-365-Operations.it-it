---
title: Panoramica della doppia scrittura
description: Questo articolo illustra una panoramica sulla doppia scrittura che fornisce interazione quasi in tempo reale tra le app di interazione con i clienti e le app per la finanza e le operazioni.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 943607a3ef28db11b7bc7805257914117e6ae38c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289640"
---
# <a name="dual-write-overview"></a>Panoramica della doppia scrittura

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>Che cos'è la doppia scrittura?

La doppia scrittura è un'infrastruttura predefinita che fornisce un'interazione in tempo quasi reale tra le app di interazione con i clienti e le app per la finanza e le operazioni. Quando i dati su clienti, prodotti, persone e operazioni scorrono oltre i confini delle applicazioni, tutti i reparti di un'organizzazione sono potenziati.

La doppia scrittura offre un'integrazione bidirezionale strettamente associata tra le app per la finanza e le operazioni e Dataverse. Qualsiasi modifica dei dati nelle app per la finanza e le operazioni genera scritture in Dataverse e qualsiasi modifica dei dati in Dataverse genera scritture nelle app per la finanza e le operazioni. Questo flusso di dati automatizzato offre un'esperienza utente integrata tra le app.

![Rapporto dei dati tra le app.](media/dual-write-overview.jpg)

La doppia scrittura ha due aspetti: un aspetto *infrastruttura* e un aspetto *applicazione*.

### <a name="infrastructure"></a>Infrastruttura

L'infrastruttura a doppia scrittura è estensibile e affidabile e include le seguenti funzionalità chiave:

+ Flusso di dati sincrono e bidirezionale tra le applicazioni
+ Sincronizzazione, insieme alle modalità di riproduzione, pausa e ammortamento per supportare il sistema in modalità online e offline/asincrona.
+ Possibilità di sincronizzare i dati iniziali tra le applicazioni
+ Visualizzazione combinata dei log di attività ed errori per gli amministratori dei dati
+ Possibilità di configurare allarmi e soglie personalizzate e di iscriversi alle notifiche
+ Interfaccia utente intuitiva per filtraggio e trasformazioni
+ Capacità di impostare e visualizzare le dipendenze e le relazioni tra tabelle
+ Estensibilità per tabelle e mappe standard e personalizzate
+ Gestione affidabile del ciclo di vita delle applicazioni
+ Esperienza di installazione predefinita per i nuovi clienti

### <a name="application"></a>Domanda di lavoro

La doppia scrittura crea una mappatura tra i concetti nelle app per la finanza e le operazioni e concetti nelle app di interazione con i clienti. Questa integrazione supporta i seguenti scenari:

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


## <a name="top-reasons-to-use-dual-write"></a>Principali motivi per utilizzare la doppia scrittura

La doppia scrittura fornisce l'integrazione dei dati tra le applicazioni Microsoft Dynamics 365. Questa solido framework collega gli ambienti e consente a diverse applicazioni aziendali di lavorare insieme. Ecco i motivi principali per cui usare la doppia scrittura:

+ La doppia scrittura fornisce un'integrazione strettamente collegata, quasi in tempo reale e bidirezionale tra le app finance and operations e le app di interazione con i clienti. Questa integrazione rende Microsoft Dynamics 365 il punto principale per tutte le soluzioni aziendali. I clienti che usano Dynamics 365 Finance e Dynamics 365 Supply Chain Management, ma che utilizzano soluzioni non Microsoft per la gestione delle relazioni con i clienti (CRM), si stanno muovendo verso Dynamics 365 per il supporto della doppia scrittura.
+ I dati provenienti da clienti, prodotti, operazioni, progetti e Internet of Things (IoT) passano automaticamente a Dataverse attraverso la doppia scrittura. Questa connessione è utile per le aziende interessate alle espansioni Power Platform.
+ L'infrastruttura a doppia scrittura segue il principio senza codice/poco codice. È necessario un minimo sforzo di progettazione per estendere le mappe da tabella a tabella standard e per includere mappe personalizzate.
+ La doppia scrittura supporta sia la modalità online che la modalità offline. Microsoft è l'unica azienda che offre supporto per le modalità online e offline.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Cosa significa la doppia scrittura per sviluppatori e architetti di app di interazione con i clienti?

La doppia scrittura automatizza il flusso di dati tra le app per la finanza e le operazioni e di interazione con i clienti. La doppia scrittura è composta da due soluzioni AppSource installate su Dataverse. Le soluzioni espandono lo schema delle tabelle, i plug-in e i flussi di lavoro in Dataverse in modo che possano scalare alla dimensione ERP. Per un'implementazione corretta, gli sviluppatori e gli architetti delle app di interazione con i clienti devono comprendere questi cambiamenti e collaborare con le loro controparti delle app per la finanza e le operazioni.

Per creare parità con le applicazioni per la finanza e le operazioni, la doppia scrittura apporta alcune modifiche cruciali nello schema Dataverse. Se si comprende il piano, è possibile evitare alcune modifiche di progettazione e sviluppo in futuro.

+ Quando il il pacchetto AppSource di doppia scrittura è installato, Dataverse avrà nuovi concetti come società e parte. Questi concetti aiutano le applicazioni basate su Dataverse, inclusi Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service, a interagire perfettamente con le app per la finanza e le operazioni.

+ Le attività e le note sono unificate e ampliate per supportare sia i C1 (utenti del sistema) che i C2 (clienti del sistema).

+ Per evitare la perdita di dati durante la trasmissione di valuta tra le app per la finanza e le operazioni e Dataverse, è possibile estendere il numero di cifre decimali nel tipo di dati di valuta delle app di interazione con i clienti. La funzione converte automaticamente le righe esistenti nel nuovo stato esteso a livello dei metadati. Durante questo processo, il valore della valuta viene convertito in dati decimali anziché in dati monetari e il valore della valuta supporta 10 cifre decimali. Questa funzione richiede il consenso esplicito e le organizzazioni che non richiedono più di 4 cifre decimali di precisione non hanno bisogno di aderire. Per ulteriori informazioni, vedere [Migrazione del tipo di dati valuta per la doppia scrittura](currrency-decimal-places.md).

+ [Validità della data](../../dev-tools/date-effectivity.md) sarà aggiunta a Dataverse. Supporterà i dati passati, presenti e futuri nella stessa tabella.

+ Le [conversioni di unità](../../../../supply-chain/pim/tasks/manage-unit-measure.md) del prodotto sono supportate per prodotti, offerte, ordini e fatture.

Per ulteriori informazioni sulle modifiche imminenti, vedere [Novità o modifiche della doppia scrittura](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

