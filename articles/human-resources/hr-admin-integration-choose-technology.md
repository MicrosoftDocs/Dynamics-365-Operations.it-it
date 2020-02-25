---
title: Scegliere una tecnologia di integrazione dei dati
description: Questo articolo fornisce informazioni su varie opzioni d'integrazione dei dati gestiti con Human Resources, descrivendo le caratteristiche delle diverse tecnologie di integrazione in modo che gli integratori possano prendere decisioni informate su quali tecnologie si adattano meglio alle loro esigenze.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f2de5dd41c00e6546b4a4feadaf5774430d572bb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029890"
---
# <a name="choose-a-data-integration-technology"></a>Scegliere una tecnologia di integrazione dei dati

Dynamics 365 Human Resources gestisce dati aziendali utili in vari processi aziendali. Questo articolo fornisce informazioni su varie opzioni d'integrazione dei dati gestiti con Human Resources, descrivendo le caratteristiche delle diverse tecnologie di integrazione in modo che gli integratori possano prendere decisioni informate su quali tecnologie si adattano meglio alle loro esigenze.

## <a name="data-integration-vision"></a>Visione dell'integrazione dei dati

Microsoft considera i dati aziendali come una risorsa chiave che rende unica la tua azienda. I dati della tua azienda sono estremamente preziosi. I dati raccolti e gestiti da una parte dell'azienda sono correlati ai dati raccolti da un'altra parte dell'azienda e queste relazioni possono essere utilizzate per migliorare i processi aziendali e la business intelligence all'interno dell'organizzazione. Fornire un accesso facile, sicuro e stabile ai dati aziendali, indipendentemente dal sistema "proprietario" dei dati è un principio chiave della visione che abbiamo per l'integrazione dei dati con Human Resources.

Storicamente, l'integrazione dei dati tra più sistemi è stata sempre difficile.
Microsoft sta implementando delle soluzioni per facilitare l'integrazione dei dati e un grande passo verso questo obiettivo viene realizzato mediante [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Human Resources farà di Common Data Service l'interfaccia pubblica preferita per gestire i dati delle risorse umane. Prevediamo che in futuro tutti i dati più importanti gestiti dalle risorse umane saranno esposti in Common Data Service. Microsoft raccomanda Common Data Service come tecnologia da utilizzare per la maggior parte delle applicazioni di integrazione. Sebbene ci rendiamo conto che non tutti i dati di cui la tua applicazione necessita siano attualmente presenti in Common Data Service e che le tempistiche del tuo progetto potrebbero richiedere una tecnologia alternativa, informaci quando Common Data Service non soddisfa le tue esigenze di integrazione.

## <a name="integration-technologies"></a>Tecnologie di integrazione

Le seguenti sezioni descrivono le diverse tecnologie di integrazione di dati disponibili per l'uso con Human Resources.

### <a name="common-data-service-entities"></a>Entità di Common Data Service

Common Data Service è l'interfaccia di dati pubblici preferita per le risorse umane. Common Data Service è basato su una piattaforma matura in quanto sviluppato a partire dalla piattaforma "XRM" di Dynamics 365 sulla quale vengono create le soluzioni [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement).

Common Data Service fornisce una piattaforma per entità di dati e un'API per l'accesso a tali entità. Quando Human Resources è distribuito nella tua organizzazione, si ha la connessione a un'istanza di Common Data Service e le entità che gestiscono i dati delle risorse umane vengono distribuiti in quell'istanza di Common Data Service, rendendo le entità e i relativi dati disponibili per qualsiasi applicazione in grado di connettersi all'istanza di Common Data Service. A seconda di quali app Human Resources stai utilizzando, Human Resources esegue operazioni sui dati direttamente sulle entità di Common Data Service (è il caso di Attract e Onboard) o sincronizza i dati da/verso le entità di Common Data Service.

Una volta che le entità di dati che espongono i dati richiesti dalle tue app di integrazione sono presenti in Common Data Service, puoi sfruttare appieno [Common Data Servicee le API che supporta](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Una delle API supportate è l'[API Web di Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), che fornisce un'implementazione OData per l'accesso ai dati di Common Data Service.

Le entità di Common Data Service e le API associate sono l'opzione migliore per accedere ai dati di Human Resources da applicazioni Web, servizi Web/API e da qualsiasi altra applicazione che si collega ai feed OData.

> [!NOTE]
> Poiché la decisione di rendere Common Data Service l'interfaccia dati preferita per Human Resources è relativamente recente, è possibile che le entità di dati di Human Resources di cui necessiti per l'integrazione non siano ancora disponibili in Common Data Service<sup>1</sup>. Se le entità di Human Resources richieste per l'integrazione non sono ancora disponibili, dovrai attendere che le entità di dati diventino disponibili o dovrai utilizzare una delle altre tecnologie di integrazione descritte di seguito.
> 
> Per impostazione predefinita, l'integrazione di Common Data Service è disattivata nei nuovi ambienti che non includono i dati dimostrativi forniti. È attivata nei nuovi ambienti che contengono dati dimostrativi e gli ambienti iniziano la sincronizzazione dei dati quando se ne esegue il provisioning. Una volta che l'ambiente è pronto per sincronizzare i dati, è possibile attivare l'integrazione.

<sup>1 </sup>Per un elenco delle entità di Human Resources disponibili in Common Data Servicevedere [Human Resources e Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities). Per Attrarre e Onboard, tutte le entità sono disponibili in Common Data Service.

### <a name="dmfdixf-entities"></a>Entità DMF/DIXF

Human Resources, sviluppato principalmente sulla stessa piattaforma delle applicazioni Finance and Operations, fornisce un framework [Data Management Framework (DMF) ](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json), a volte noto anche come Data Import Export Framework o DIXF, e un insieme di entità di dati che possono essere utilizzate per importare/esportare dati in/da Human Resources. Mentre le entità di Common Data Service sono l'interfaccia di integrazione di dati preferita per le risorse umane, le entità DMF saranno ancora utili in alcune circostanze, ad esempio:

- Le entità di Common Data Service non sono ancora disponibili.

- L'integrazione richiede funzionalità di importazione/esportazione di dati in bulk ad alte prestazioni.

Le entità DMF attualmente forniscono la copertura dati più completa per i dati delle risorse umane.

DMF non è appropriato per le integrazioni in tempo reale (come quando è richiesto il feedback immediato dell'utente in un'interfaccia utente), poiché le operazioni del pacchetto sono processi batch pianificati e spesso avranno una latenza minima di 1-2 minuti prima che il servizio batch scelga il processo da eseguire, oltre al tempo necessario per completare l'operazione di importazione/esportazione.

DMF può essere l'opzione migliore quando è richiesto un throughput elevato (come l''importazione/esportazione programmata ogni sera di molte migliaia di record).

> [!NOTE]
> DMF non è disponibile per Attract e Onboard.

### <a name="dmf-package-rest-api"></a>API REST pacchetti di DMF

DMF fornisce un'[API REST](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) per la manipolazione di pacchetti di dati. Questa API può essere utilizzata per interagire a livello di programmazione con DMF, consentendo azioni come:

- Importazione di un pacchetto di dati

- Esportazione di un pacchetto di dati

- Verifica dello stato di un'operazione di importazione/esportazione.

L'API REST di pacchetti di DMF è pienamente supportata in Core HR di Human Resources.

### <a name="azure-sql-db-byod"></a>DB SQL di Azure (BYOD)

DMF offre inoltre una potente funzionalità (generalmente nota come [Portare il proprio database](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database)o BYOD) che consente alle risorse umane di esportare dati nel database SQL di Microsoft Azure. Ciò fornisce un'enorme flessibilità, perché quando i dati sono presenti nel database SQL, è possibile utilizzare qualsiasi applicazione o middleware in grado di connettersi a un archivio dati SQL.

BYOD dovrebbe essere generalmente considerato come una soluzione di sola lettura. Sebbene sia possibile manipolare e archiviare tutti i dati desiderati nel database SQL di Azure (come per i mashup di dati), i dati archiviati nel database SQL di Azure non verranno sincronizzati di nuovo con Human Resources.

La funzionalità BYOD è appropriata per le soluzioni di reporting, integrazioni di dati, mashup di dati, come origine dati per una pipeline [Azure Data Factory ](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> BYOD non è disponibile per Attract e Onboard.

### <a name="odata-enabled-entities"></a>Entità abilitate per OData

La maggior parte delle entità DMF è abilitata anche per l'accesso tramite i servizi dati di Human Resources (OData). La documentazione fornita per il [Servizio OData di Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) si applica generalmente anche a Human Resources, sebbene la documentazione sulla creazione di entità esposte a OData non sia applicabile.

Sebbene Common Data Service e l'implementazione OData fornita da Common Data Service (tramite l'[API Web di Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) sia preferita rispetto al servizio dati di Human Resources, questo servizio dati ha attualmente una copertura delle entità più completa per i dati di Human Resources.

### <a name="excel-add-in"></a>Componente aggiuntivo di Excel

Il [componente aggiuntivo di Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) utilizza le entità abilitate per OData in background. Fornisce un modo conveniente per un utente finale di recuperare e modificare i dati di Human Resources attraverso l'interfaccia utente familiare di Excel.

Il componente aggiuntivo di Excel è appropriato per importazioni/esportazioni di dati ad hoc mediante esperti del dominio aziendale. Per un'integrazione di dati ricorrente che richiede un'automazione programmatica, un'altra tecnologia di integrazione sarà più appropriata.

### <a name="data-integrator"></a>Servizio di integrazione di dati

L'esperienza amministratore di Common Data Service fornisce un [servizio di integrazione di dati](https://docs.microsoft.com/powerapps/administrator/data-integrator) che può essere utilizzato per integrazioni di dati da/verso Common Data Service. Il servizio di integrazione di dati può essere utilizzato per definire progetti di integrazione (spesso basati su modelli predefiniti che gli sviluppatori di applicazioni hanno personalizzato per integrazioni specifiche). I progetti di integrazione possono essere programmati per essere eseguiti automaticamente in base a una pianificazione ricorrente o essere eseguiti manualmente.

I progetti con il servizio di integrazione di dati sono appropriati per le integrazioni batch di Common Data Service e sono un'ottima scelta per integrazioni tra la famiglia di applicazioni Dynamics 365. Ad esempio, Microsoft fornisce un modello di servizio di integrazione di dati pronto all'uso che può essere utilizzato per integrare i dati di Human Resources in Dynamics 365 Finance. Per ulteriori informazioni, vedere [Integrazione da Dynamics 365 Human Resources a Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

Il servizio di integrazione di dati supporta anche [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) (attraverso la [funzionalità di query avanzata](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)).
Power Query fornisce funzionalità di filtro e trasformazione di dati potenti e flessibili, incluso il linguaggio di formula M, e sarà probabilmente familiare a coloro che hanno esperienza nello sviluppo di report di Power BI.

## <a name="deciding-on-an-integration-technology"></a>Scelta di una tecnologia di integrazione

Con così tante diverse tecnologie di integrazione disponibili, scegliere quale approccio di integrazione usare può talvolta risultare difficoltoso. Nel tempo, in particolare con l'evoluzione della copertura dei dati in Common Data Service, la decisione risulterà più agevole, in quanto Common Data Service diventerà l'interfaccia dati preferita nella maggior parte dei casi. Ma fino ad allora, è possibile che Common Data Service non soddisfi ancora le tue esigenze. La tabella seguente riepiloga alcune delle caratteristiche chiave delle varie opzioni di tecnologia di integrazione.

| Tecnologia/Strumento/API    | Integrazioni ricorrenti                   | Sincrona/asincrona                    | Accesso programmatico tramite un'API        | Volumi di dati appropriati                                   | Copertura dati                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Entità di Common Data Service           | Sì, utilizzando un servizio di integrazione di dati o un middleware | Sincrona asincrono, batch (tramite un servizio di integrazione di dati) | Sì, tramite l'API Web di Dynamics 365 (OData) | Varia in base al caso d'uso (supporta il paging per uso interattivo) | In miglioramento <sup>2</sup>                       |
| Entità DMF           | Sì, programmate tramite middleware        | Asincrona, batch                                | Sì, tramite l'API REST pacchetti di DMF         | Alta (centinaia di migliaia di record)                    | Alta                                |
| API REST pacchetti di DMF   | Sì, programmate tramite middleware        | Asincrona, batch                                | Sì                                       | Alta (centinaia di migliaia di record)                    | L'API supporta tutte le entità DMF       |
| BYOD                   | Sì, programmate dall'amministratore in Human Resources        | Asincrona, batch                                | No<sup>3</sup>                                    | Alta (centinaia di migliaia di record)                    | Supporta tutte le entità DMF           |
| Entità abilitate per OData | Sì, utilizzando un middleware                    | Sincronizza                                        | Sì, tramite il servizio dati di Human Resources (OData)  | Varia in base al caso d'uso (supporta il paging per uso interattivo) | Alta                                |
| Componente aggiuntivo di Excel           | Nessuno                                       | Sincronizza                                        | Nessuno                                        | Media (decine di migliaia di record)                      | Supporta tutte le entità abilitate per OData |
| Servizio di integrazione di dati        | Sì, programmato nel servizio di integrazione di dati        | Asincrona, batch                                | Nessuno                                        | Varia con il caso d'uso                                       | Supporta tutte le entità di Common Data Service           |

<sup>2 </sup>Microsoft sta investendo massicciamente nell'aumento della copertura dei dati per le entità di Common Data Service e raccomanda Common Data Service come interfaccia dati preferita quando la copertura è disponibile. Attualmente, la copertura dati di Common Data Service è bassa rispetto alle entità abilitate per DMF e OData.

<sup>3 </sup>È possibile accedere al database SQL a livello programmatico.

## <a name="summary"></a>Riepilogo

I dati aziendali sono una risorsa preziosa, ma il loro valore può essere notevolmente ridotto se è difficile utilizzare i dati per scopi specifici (come report, mashup di dati o applicazioni personalizzate). Dynamics 365 Human Resources fornisce diverse tecnologie per l'utilizzo dei dati al di fuori dell'interfaccia utente dell'applicazione Human Resources, consentendo alle applicazioni di integrazione di accedere ai dati. Questo argomento ha descritto le tecnologie di integrazione disponibili e alcune delle loro caratteristiche chiave. Queste informazioni dovrebbero agevolare la presa di decisioni su quali approcci utilizzare per i progetti di integrazione.

