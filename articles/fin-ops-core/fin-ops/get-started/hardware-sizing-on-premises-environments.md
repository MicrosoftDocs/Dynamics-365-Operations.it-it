---
title: Requisiti di dimensionamento hardware per ambienti locali
description: Questo argomento elenca i requisiti di dimensionamento hardware per un ambiente locale.
author: sericks007
manager: AnnBe
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: b89135cd9e951e690e53c1b4bf98dfcb03f2d652
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694471"
---
# <a name="hardware-sizing-requirements-for-on-premises-environments"></a>Requisiti di dimensionamento hardware per ambienti locali

[!include [banner](../includes/banner.md)]

Prima di avviare il processo di dimensionamento dell'infrastruttura e dell'hardware per un ambiente locale, è utile conoscere i [Requisiti di sistema per le distribuzioni cloud](system-requirements.md) e le [Istruzioni di distribuzione e di configurazione](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md) per acquisire una conoscenza approfondita dell'infrastruttura sottostante.

> [!NOTE]
> Per le prestazioni ottimali, fare attenzione alle procedure consigliate per la configurazione del sistema.

Dopo avere esaminato la documentazione, è possibile iniziare il processo di stima del volume di utenti transazionali e simultanei e di dimensionamento dell'ambiente in base alla produttività media di base.

## <a name="factors-that-affect-sizing"></a>Fattori che influiscono sul dimensionamento

Tutti i fattori mostrati nella figura seguente influiscono sul dimensionamento. Più sono dettagliate le informazioni che si raccolgono e maggiore sarà la precisione con cui si determinerà il dimensionamento. Il dimensionamento hardware senza dati di supporto ha più probabilità di risultare impreciso. Il fabbisogno minimo assoluto dei dati necessari è il carico di riga di transazione di punta all'ora.

[![Dimensionamento hardware per ambienti locali](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

Osservato da sinistra a destra, il primo fattore e il più importante necessario per stimare esattamente il dimensionamento è un profilo di transazione o una caratterizzazione di transazione. È importante trovare sempre il volume transazionale di punta all'ora. Se sono presenti più periodi di punta, è necessario definirli con precisione.

Man mano che si comprende il carico che influisce sull'infrastruttura, è necessario comprendere maggiormente anche questi fattori:

- **Transazioni** – In genere le transazioni hanno determinati picchi nell'arco della giornata/settimana. Ciò dipende principalmente dal tipo di transazione. Gli orari e le voci di spesa mostrano in genere picchi una volta alla settimana, mentre le voci di un ordine cliente arrivano in massa tramite integrazione o inserimento durante la giornata.
- **Numero di utenti simultanei** - Il numero di utenti simultanei è il secondo fattore di dimensionamento più importante. Non è possibile ottenere stime di dimensionamento attendibili in base al numero di utenti simultanei, quindi se questo è l'unico dato a disposizione, occorre stimare un numero approssimativo e successivamente rivederlo quando si hanno più dati. Una definizione approfondita di utente simultaneo significa che:

    - Gli utenti denominati non sono utenti simultanei.
    - Gli utenti simultanei sono sempre un sottoinsieme di utenti denominati. 
    - Il picco di lavoro definisce la simultaneità massima per il dimensionamento.

    I criteri per gli utenti simultanei è che l'utente soddisfa tutti i criteri seguenti:

    - Ha eseguito l'accesso.
    - Transazioni/indagini in corso al momento del conteggio.
    - Non una sessione inattiva.

- **Composizione dati** - Questo fattore riguarda maggiormente la modalità di installazione e di configurazione del sistema. Ad esempio, il numero di persone giuridiche, di articoli, di livelli di DBA e il livello di complessità della sicurezza. Ognuno di questi fattori può avere un piccolo impatto sulle prestazioni, pertanto questi fattori possono essere compensati utilizzando le scelte intelligenti quando si tratta dell'infrastruttura.
- **Estensioni** - Le personalizzazioni possono essere semplici o complesse. Il numero di personalizzazioni e la natura della complessità e dell'utilizzo hanno un impatto variabile sulle dimensioni dell'infrastruttura necessaria. Per le personalizzazioni complesse, è consigliabile condurre valutazioni delle prestazioni per garantire che non siano testate solo nell'efficienza ma che aiutino anche a comprendere le esigenze dell'infrastruttura. Questo aspetto diventa ancora più critico quando le estensioni non sono codificate in base alle procedure consigliate per le prestazioni e la scalabilità.
- **Report e analisi** - Questi fattori includono in genere l'esecuzione di query pesanti rispetto a vari database nel sistema. Comprendere e ridurre la frequenza di esecuzione di report costosi aiuterà a capirne l'impatto.
- **Soluzioni di terze parti** - Queste soluzioni, ad esempio gli ISV, hanno le stesse implicazioni e gli stessi suggerimenti delle estensioni.

## <a name="sizing-your-environment"></a>Dimensionamento dell'ambiente

Per comprendere i requisiti di dimensionamento, è necessario conoscerne il picco del volume di transazioni che è necessario elaborare. La maggior parte dei sistemi ausiliari, come Strumento di creazione report di gestione oppure SSRS, è meno cruciale. Questo documento riguarda di conseguenza maggiormente Application Object Server (AOS) e SQL Server.

> [!NOTE]
> In generale, i livelli di calcolo scalano orizzontalmente e dovrebbero essere impostati secondo la modalità N+1 secondo la quale se si stimano tre AOS, se ne deve aggiungere un quarto. Il livello del database dovrebbe essere installato secondo l'impostazione di disponibilità elevata always-on.

## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>Dimensionamento

- Da 3.000 a 15.000 righe di transazione all'ora per core nel server di DB.
- Tipico rapporto di core AOS-a-SQL 3:1 per il server SQL primario. Sono richiesti core aggiuntivi in base alla configurazione della disponibilità elevata scelta.

    - L'elaborazione di operazioni di database complesse potrebbero regredire il rapporto a 2:1.

- I fattori seguenti influiscono sulle variazioni:

    - Impostazioni dei parametri in uso.
    - Livelli di estensione.
    - Utilizzo di funzionalità aggiuntive, ad esempio gli avvisi e il registro database. La registrazione estrema del database ridurrà ulteriormente la produttività oraria per core al di sotto di 3.000 righe.
    - Complessità della composizione dei dati - Un piano dei conti semplice rispetto a un piano dei conti molto dettagliato ha implicazioni sulla produttività (ad esempio).
    - Caratterizzazione della transazione.
    - Da 2 GB a 16 GB di memoria per ogni core.
    - Database ausiliari nel server DB quali i database di strumento di creazione report di gestione e SSRS.
    - DB temporaneo = 15% della dimensione del DB, con tanti file quanti sono i processori fisici.
    - Produttività e dimensione SAN in base al volume/utilizzo delle transazioni simultanee totale.

### <a name="high-availability"></a>Disponibilità elevata

È consigliabile utilizzare sempre SQL Server nell'impostazione di un cluster o di mirroring. Il secondo nodo SQL deve avere lo stesso numero di core del nodo principale.

### <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)

Per il dimensionamento di AD FS, vedere la [Documentazione relativa alla capacità del server AD FS](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity).

Per pianificare il numero di istanze nella distribuzione, è disponibile un [foglio di calcolo per il dimensionamento](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx).

## <a name="aos-online-and-batch"></a>AOS (Online e batch)

### <a name="sizing"></a>Dimensionamento

- Dimensionamento in base a volume/utilizzo delle transazioni

    - Da 2.000 e 6.000 righe per core
    - 16 GB per istanza
    - Standard - Da 4 a 24 core
    - Da 10 a 15 utenti Enterprise per core
    - Da 15 a 25 utenti di Activity per core
    - Da 25 a 50 membri di team per core

- Batch

    - Da 1 a 4 thread batch per core
    - Dimensione in base alla caratterizzazione della finestra del batch

- Tenere presente che AOS, Gestione dati e Batch sono nello stesso ruolo in Service Fabric. È necessario dimensionare questi tre carichi di lavoro combinati e non separatamente come in Microsoft Dynamics AX 2012.
- Gli stessi fattori di variabilità per SQL Server vengono applicati qui.

### <a name="high-availability"></a>Disponibilità elevata

- Assicurarsi di avere almeno 1 o 2 AOS aggiuntivi rispetto a quanto stimato.
- Assicurarsi di aver almeno 3 o 4 host virtuali disponibili.

## <a name="management-reporter"></a>Strumento di creazione report di gestione

Nella maggior parte dei casi, a meno che non siano utilizzati estesamente, i requisiti minimi consigliati che prevedono due nodi dovrebbero essere una soluzione valida. Solo nei casi in cui vi sia un utilizzo intenso sarà necessario avere più di due nodi. Scalare in base alle necessità.

## <a name="sql-server-reporting-services"></a>SQL Server Reporting Services

Per la versione di disponibilità generale è possibile distribuire un solo nodo SSRS. Monitorare il nodo SSRS durante i test e aumentare il numero di core disponibili per SSRS in base alle esigenze. Assicurarsi di aver un nodo secondario preconfigurato disponibile su un host virtuale diverso dalla VM SSRS. Ciò è importante se si verifica un problema con la macchina virtuale che ospita SSRS o l'host virtuale. In questo caso devono essere sostituiti.

## <a name="environment-orchestrator"></a>Agente di orchestrazione dell'ambiente

L'Agente di orchestrazione è il servizio che gestisce la distribuzione e la comunicazione correlata con LCS. Questo servizio viene distribuito come servizio primario Service Fabric e richiede almeno tre VM. Questo servizio è posizionato insieme ai servizi di orchestrazione Service Fabric. Questo servizio deve essere dimensionato al carico di picco del cluster. Per ulteriori informazioni, vedere [Pianificare e preparare la distribuzione del cluster Service Fabric autonomo](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="virtualization-and-oversubscription"></a>Virtualizzazione e oversubscription

I servizi cruciali come AOS devono essere ospitati in host virtuali che hanno risorse dedicate (core, memoria e disco).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]