---
title: Scegliere una tecnologia di integrazione dei dati
description: Questo articolo fornisce informazioni sull'integrazione con i dati gestiti da Human Resources. Descrive diverse tecnologie di integrazione per aiutare a decidere quali tecnologie si adattano meglio alle proprie esigenze.
author: andreabichsel
ms.date: 02/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9cfa29272e794b6eee62ae5dd404d8b6339b907c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055150"
---
# <a name="choose-a-data-integration-technology"></a>Scegliere una tecnologia di integrazione dei dati

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo articolo fornisce informazioni sull'integrazione con i dati gestiti da Dynamics 365 Human Resources. Descrive diverse tecnologie di integrazione per aiutare a decidere quali tecnologie si adattano meglio alle proprie esigenze.

## <a name="data-integration-background"></a>Integrazione dati in background

I dati aziendali sono una risorsa chiave che rende unica l'azienda. I dati della tua azienda sono estremamente preziosi. È possibile utilizzare le relazioni tra i dati raccolti in tutta l'azienda per migliorare i processi aziendali e la business intelligence all'interno dell'organizzazione. Ci impegniamo a fornire un accesso facile, sicuro e stabile ai dati aziendali indipendentemente dal sistema da cui provengono.

Storicamente, l'integrazione dei dati tra più sistemi è stata sempre difficile.
Microsoft sta implementando delle soluzioni per facilitare l'integrazione dei dati e un grande passo verso questo obiettivo viene realizzato mediante [Dataverse](/powerapps/maker/common-data-service/data-platform-intro).

Human Resources utilizza Dataverse come l'interfaccia pubblica preferita per gestire i dati di Human Resources. Prevediamo che in futuro tutti i dati più importanti gestiti dalle risorse umane saranno esposti in Dataverse. Microsoft raccomanda Dataverse come tecnologia da utilizzare per la maggior parte delle applicazioni di integrazione.

Ci rendiamo conto che Dataverse potrebbe non contenere ancora tutti i dati richiesti dall'applicazione. Ci rendiamo anche conto che la cronologia del progetto potrebbe richiedere una tecnologia alternativa. È importante notificare quando Dataverse non soddisfa le esigenze di integrazione.

## <a name="integration-technologies"></a>Tecnologie di integrazione

Le seguenti sezioni descrivono le diverse tecnologie di integrazione di dati disponibili per l'uso con Human Resources.

### <a name="dataverse-tables"></a>Tabelle Dataverse

Dataverse è l'interfaccia di dati pubblici preferita per le risorse umane. È basata sulla piattaforma Dynamics 365 XRM utilizzata dalle soluzioni [Dynamics 365 Customer Engagement](/dynamics365/?panel=customer-engagement#pivot=business-apps).

Dataverse fornisce una piattaforma e l'API per le tabelle di dati. Quando si distribuisce Human Resources, ci si connette a un'istanza di Dataverse. Le entità per i dati di Human Resources vengono distribuiti nell'istanza di Dataverse. Le tabelle e i dati sono disponibili per qualsiasi applicazione in grado di connettersi all'istanza di Dataverse. Human Resources sincronizza i dati da e verso le tabelle Dataverse.

> [!NOTE]
> Le entità di Human Resources corrispondono alle tabelle Dataverse. Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)

Quando le tabelle dati richieste dalle app di integrazione sono presenti in Dataverse, è possibile utilizzare completamente [Dataverse e le API che supporta](/powerapps/?panel=developer#pivot=home). Una delle API supportate è l'[API Web di Dynamics 365](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), che fornisce un'implementazione OData per l'accesso ai dati di Dataverse.

Le tabelle di Dataverse e le API associate sono l'opzione migliore per accedere ai dati di Human Resources da applicazioni Web, servizi Web/API e da qualsiasi altra applicazione che si collega ai feed OData.

> [!NOTE]
> Poiché la decisione di rendere Dataverse l'interfaccia dati preferita per Human Resources è relativamente recente, è possibile che le entità di dati di Human Resources di cui necessiti per l'integrazione non siano ancora disponibili in Dataverse.
> </br>
> Per un elenco delle entità di Human Resources disponibili in Dataverse vedere [Human Resources e Dataverse](/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Se le entità di Human Resources richieste per l'integrazione non sono ancora disponibili, dovrai attendere che le entità di dati diventino disponibili o dovrai utilizzare una delle altre tecnologie di integrazione descritte di seguito.
> </br>
> Per impostazione predefinita, l'integrazione di Dataverse è disattivata nei nuovi ambienti che non includono i dati dimostrativi forniti. È attivata nei nuovi ambienti che contengono dati dimostrativi e gli ambienti iniziano la sincronizzazione dei dati quando se ne esegue il provisioning. Una volta che l'ambiente è pronto per sincronizzare i dati, è possibile attivare l'integrazione.

### <a name="dmfdixf-entities"></a>Entità DMF/DIXF

Human Resources, basato principalmente sulla stessa piattaforma delle applicazioni Finance and Operations, fornisce un [Data Management Framework (DMF)](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json). DMF è anche noto come Data Import Export Framework (DIXF). Human Resources fornisce una serie di entità dati che è possibile utilizzare per l'importazione e l'esportazione di dati di Human Resources. Mentre le tabelle di Dataverse sono l'interfaccia di integrazione di dati preferita per le risorse umane, le entità DMF sono ancora utili in alcune circostanze, ad esempio:

- Le tabelle di Dataverse non sono ancora disponibili.

- L'integrazione richiede funzionalità di importazione/esportazione di dati in bulk ad alte prestazioni.

> [!NOTE]
> Le entità di Human Resources corrispondono alle tabelle Dataverse. Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)

Le entità DMF attualmente forniscono la copertura dati più completa per i dati delle risorse umane.

DMF non è appropriato per integrazioni in tempo reale, ad esempio quando è necessario un feedback immediato dell'utente in un'interfaccia utente. Le operazioni del pacchetto sono lavori batch pianificati e spesso hanno una latenza minima di 1-2 minuti prima che il servizio batch raccolga il lavoro per l'esecuzione, oltre al tempo necessario per completare l'operazione di importazione/esportazione.

DMF può essere l'opzione migliore quando è richiesto un throughput elevato (come l''importazione/esportazione programmata ogni sera di molte migliaia di record).

> [!NOTE]
> DMF non è disponibile per Attract e Onboard.

### <a name="dmf-package-rest-api"></a>API REST pacchetti di DMF

DMF fornisce un'[API REST](/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) per la manipolazione di pacchetti di dati. Questa API può essere utilizzata per interagire a livello di programmazione con DMF, consentendo azioni come:

- Importazione di un pacchetto di dati

- Esportazione di un pacchetto di dati

- Verifica dello stato di un'operazione di importazione/esportazione.

L'API REST di pacchetti di DMF è pienamente supportata in Human Resources.

### <a name="azure-sql-db-byod"></a>DB SQL di Azure (BYOD)

DMF offre inoltre una potente funzionalità (nota come [Portare il proprio database](/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database)o BYOD) che consente alle risorse umane di esportare dati nel database SQL di Microsoft Azure. Questa capacità offre un'enorme flessibilità. Quando i dati sono presenti nel database SQL, è possibile utilizzare qualsiasi applicazione o middleware in grado di connettersi a un archivio dati SQL.

BYOD è principalmente una soluzione di sola lettura. Sebbene sia possibile manipolare e archiviare tutti i dati desiderati nel database SQL di Azure (come per i mashup di dati), i dati archiviati nel database SQL di Azure non vengono sincronizzati con Human Resources.

La funzionalità BYOD è appropriata per le soluzioni di reporting, integrazioni di dati, mashup di dati, come origine dati per una pipeline [Azure Data Factory ](/azure/data-factory/).

> [!NOTE]
> BYOD non è disponibile per Attract e Onboard.

### <a name="odata-enabled-entities"></a>Entità abilitate per OData

La maggior parte delle entità DMF è abilitata anche per l'accesso tramite i servizi dati di Human Resources (OData). La documentazione fornita per il [servizio Finance and Operations OData](/dynamics365/unified-operations/dev-itpro/data-entities/odata) si applica a Human Resources, ad eccezione della creazione di entità esposte a OData.

Sebbene Dataverse e l'implementazione OData fornita da Dataverse (tramite l'[API Web di Dynamics 365](/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) sia preferita rispetto al servizio dati di Human Resources, questo servizio dati ha attualmente una copertura delle entità più completa per i dati di Human Resources.

### <a name="excel-add-in"></a>Componente aggiuntivo di Excel

Il [componente aggiuntivo di Excel](/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json) utilizza le entità abilitate per OData in background. Fornisce un modo conveniente per un utente finale di recuperare e modificare i dati di Human Resources attraverso l'interfaccia utente familiare di Excel.

Il componente aggiuntivo di Excel è appropriato per importazioni/esportazioni di dati ad hoc mediante esperti del dominio aziendale. Per un'integrazione di dati ricorrente che richiede un'automazione programmatica, un'altra tecnologia di integrazione sarà più appropriata.

### <a name="data-integrator"></a>Servizio di integrazione di dati

È possibile usare il [servizio di integrazione dati](/powerapps/administrator/data-integrator) per integrare i dati da e verso Dataverse. Il servizio di integrazione di dati consente di definire progetti di integrazione (spesso basati su modelli predefiniti che gli sviluppatori di applicazioni hanno personalizzato per integrazioni specifiche). È possibile programmare i progetti di integrazione per essere eseguiti automaticamente in base a una pianificazione ricorrente o essere eseguiti manualmente.

I progetti di integrazione dei dati sono appropriati per le integrazioni batch Dataverse. Sono un'ottima scelta per le integrazioni tra le applicazioni della famiglia Dynamics 365. Ad esempio, Microsoft fornisce un modello di servizio di integrazione di dati per integrare i dati di Human Resources in Dynamics 365 Finance. Ulteriori informazioni sul modello sono disponibili in [Integrazione da Dynamics 365 Human Resources a Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

Il servizio di integrazione di dati supporta [Power Query](/power-query/power-query-what-is-power-query) attraverso la [funzionalità di query avanzata](/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering). Power Query offre filtri e trasformazioni di dati potenti e flessibili, incluso il linguaggio avanzato della formula M. Power Query sarà probabilmente già conosciuto se sono stati sviluppati report Power BI.

## <a name="deciding-on-an-integration-technology"></a>Scelta di una tecnologia di integrazione

Con così tante diverse tecnologie di integrazione disponibili, scegliere quale approccio di integrazione usare può talvolta risultare difficoltoso. Con l'evoluzione della copertura dei dati in Dataverse, la decisione risulterà più agevole, in quanto Dataverse diventerà l'interfaccia dati preferita nella maggior parte dei casi. Ma fino ad allora, è possibile che Dataverse non soddisfi ancora le tue esigenze. La tabella seguente riepiloga alcune delle caratteristiche chiave delle opzioni di tecnologia di integrazione.

| Tecnologia/Strumento/API    | Integrazioni ricorrenti                   | Sincrona/asincrona                    | Accesso programmatico tramite un'API        | Volumi di dati appropriati                                   | Copertura dati                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Tabelle Dataverse           | Sì, utilizzando un servizio di integrazione di dati o un middleware | Sincrona asincrono, batch (tramite un servizio di integrazione di dati) | Sì, tramite l'API Web di Dynamics 365 (OData) | Varia in base al caso d'uso (supporta il paging per uso interattivo) | In miglioramento <sup>2</sup>                       |
| Entità DMF           | Sì, programmate tramite middleware        | Asincrona, batch                                | Sì, tramite l'API REST pacchetti di DMF         | Alta (centinaia di migliaia di record)                    | Alta                                |
| API REST pacchetti di DMF   | Sì, programmate tramite middleware        | Asincrona, batch                                | Sì                                       | Alta (centinaia di migliaia di record)                    | L'API supporta tutte le entità DMF       |
| BYOD                   | Sì, programmate dall'amministratore in Human Resources        | Asincrona, batch                                | No<sup>3</sup>                                    | Alta (centinaia di migliaia di record)                    | Supporta tutte le entità DMF           |
| Entità abilitate per OData | Sì, utilizzando un middleware                    | Sincronizza                                        | Sì, tramite il servizio dati di Human Resources (OData)  | Varia in base al caso d'uso (supporta il paging per uso interattivo) | Alta                                |
| Componente aggiuntivo di Excel           | Nessuno                                       | Sincronizza                                        | Nessuno                                        | Media (decine di migliaia di record)                      | Supporta tutte le entità abilitate per OData |
| Servizio di integrazione di dati        | Sì, programmato nel servizio di integrazione di dati        | Asincrona, batch                                | Nessuno                                        | Varia con il caso d'uso                                       | Supporta tutte le tabelle Dataverse           |

<sup>2</sup>Microsoft sta investendo molto per aumentare la copertura dei dati per le tabelle Dataverse. Si consiglia di utilizzare Dataverse quando è disponibile la copertura. Attualmente, la copertura dati di Dataverse è bassa rispetto alle entità abilitate per DMF e OData.

<sup>3 </sup>È possibile accedere al database SQL a livello programmatico.


[!INCLUDE[footer-include](../includes/footer-banner.md)]