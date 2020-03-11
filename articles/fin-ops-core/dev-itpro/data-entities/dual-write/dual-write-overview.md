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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075990"
---
# <a name="dual-write-overview"></a>Panoramica della doppia scrittura

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a>Che cos'è la doppia scrittura?

La doppia scrittura è un'infrastruttura predefinita che fornisce interazione quasi in tempo reale tra le app in Microsoft Dynamics 365 e le app Finance and Operations. Quando i dati su clienti, prodotti, persone e operazioni scorrono oltre i confini delle applicazioni, tutti i reparti di un'organizzazione sono potenziati.

La doppia scrittura fornisce un'integrazione bidirezionale strettamente connessa tra le app Finance and Operations e Common Data Service. Qualsiasi modifica dei dati nelle app Finance and Operations causa scritture in Common Data Service e qualsiasi modifica dei dati in in Common Data Service causa scritture nelle app Finance and Operations. Questo flusso di dati automatizzato offre un'esperienza utente integrata tra le app.

![Rapporto dei dati tra le app](media/dual-write-overview.jpg)

La doppia scrittura ha due aspetti: un aspetto *infrastruttura* e un aspetto *applicazione*.

### <a name="infrastructure"></a>Infrastruttura

L'infrastruttura a doppia scrittura è estensibile e affidabile e include le seguenti funzionalità chiave:

+ Flusso di dati sincrono e bidirezionale tra le applicazioni
+ Sincronizzazione, insieme alle modalità di riproduzione, pausa e ammortamento per supportare il sistema in modalità online e offline/asincrona.
+ Possibilità di sincronizzare i dati iniziali tra le applicazioni
+ Visualizzazione consolidata dei log di attività ed errori per gli amministratori dei dati
+ Possibilità di configurare allarmi e soglie personalizzate e di iscriversi alle notifiche
+ Interfaccia utente intuitiva per filtraggio e trasformazioni
+ Capacità di impostare e visualizzare le dipendenze e le relazioni tra entità
+ Estensibilità per entità e mappe standard e personalizzate
+ Gestione affidabile del ciclo di vita delle applicazioni
+ Esperienza di installazione predefinita per i nuovi clienti

### <a name="application"></a>Richiesta

La doppia scrittura crea una mappatura tra i concetti nelle app Finance and Operations e concetti nelle app basate su modelli in Dynamics 365. Questa integrazione supporta i seguenti scenari:

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
+ I dati provenienti da clienti, prodotti, operazioni, progetti e Internet of Things (IoT) passano automaticamente a Common Data Service attraverso la doppia scrittura. Questa connessione è molto utile per le aziende interessate alle espansioni Microsoft Power Platform.
+ L'infrastruttura a doppia scrittura segue il principio senza codice/poco codice. È necessario un minimo sforzo di progettazione per estendere le mappe da tabella a tabella standard e per includere mappe personalizzate.
+ La doppia scrittura supporta sia la modalità online che la modalità offline. Microsoft è l'unica azienda che offre supporto per le modalità online e offline.

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a>Cosa significa la doppia scrittura per gli utenti e gli architetti dei prodotti CRM?

La doppia scrittura automatizza il flusso di dati tra le app Finance and Operations e Common Data Service. Nelle versioni future, i concetti nelle app basate su modelli in Dynamics 365 (ad esempio, cliente, contatto, preventivo e ordine) verranno ridimensionati per i clienti di fascia media e medio-alta.

Nella prima versione, la maggior parte dell'automazione è gestita da soluzioni a doppia scrittura. Nelle versioni future, tali soluzioni diventeranno parte di Common Data Service. Comprendendo le imminenti modifiche a Common Data Service, è possibile risparmiare sforzi a lungo termine. Sono illustrate alcune di queste importanti modifiche:

+ Common Data Service avrà nuovi concetti, come società e parte. Questi concetti riguardano tutte le app basate su Common Data Service, ad esempio Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service.
+ Le attività e le note sono unificate e ampliate per supportare sia i C1 (utenti del sistema) che i C2 (clienti del sistema).
+ Sono illustrate alcune di queste modifiche future di Common Data Service:

    - Il tipo di dati decimali sostituirà il tipo di dati monetari.
    - La validità della data supporterà i dati passati, presenti e futuri nello stesso posto.
    - Ci sarà un maggiore supporto per i tassi di cambio e valuta e l'API **Tasso di cambio** sarà rivisitata.
    - Le conversioni di unità saranno supportate.

Per ulteriori informazioni sulle modifiche imminenti, vedere [Dati in Common Data Service - fase 1 e 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).
