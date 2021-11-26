---
title: Unità di scala in una topologia ibrida distribuita
description: Questo argomento fornisce informazioni sulle unità di scala nel cloud e nella rete perimetrale per i carichi di lavoro di gestione della produzione e del magazzino.
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3111de1f9862cbf926e763f963c86059f4121fc0
ms.sourcegitcommit: 4b7e9d074e368a08d2f75482b722dce0c69a4bbd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7733441"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>Unità di scala in una topologia ibrida distribuita

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> La funzionalità di unità di scala per Microsoft Dynamics 365 Supply Chain Management è disponibile in base ai termini che regolano l'utilizzo del servizio. Per ulteriori informazioni, vedere [Informazioni legali di Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> Quando abiliti le unità di scala nel cloud e nella rete perimetrale, ti viene richiesto di dichiarare di comprendere che alcuni dati correlati alla configurazione e all'elaborazione di unità di scala nel cloud e nella rete perimetrale potrebbero essere archiviati in un data center situato negli Stati Uniti. Per ulteriori informazioni sull'elaborazione dei dati per le unità di scala nel cloud e nella rete perimetrale, vedere la sezione [Elaborazione dati durante la gestione di unità scala](#data-processing-management) in questo argomento.

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>Proposta di valori di base per una topologia ibrida distribuita

Le aziende che lavorano con la produzione e la distribuzione devono essere in grado di eseguire processi aziendali chiave 24 ore su 24, 7 giorni su 7, senza interruzioni e su larga scala. Una topologia ibrida distribuita consente alle aziende di eseguire processi di produzione e magazzino cruciali senza interruzioni, anche di fronte a problemi di latenza o di connettività di rete occasionali.

Una topologia ibrida distribuita introduce il concetto di *unità di scala*, che consente la distribuzione dei carichi di lavoro di esecuzione del reparto produzione e del magazzino tra ambienti diversi. Questa funzionalità può aiutare a migliorare le prestazioni, prevenire le interruzioni del servizio e massimizzare il tempo di attività. Le unità di scala vengono fornite tramite i seguenti componenti aggiuntivi per l'abbonamento a Supply Chain Management:

- Componente aggiuntivo unità di scala nel cloud per Dynamics 365 Supply Chain Management
- Componente aggiuntivo unità di scala nella rete perimetrale per Dynamics 365 Supply Chain Management

Le funzionalità del carico di lavoro vengono rilasciate su base continua attraverso miglioramenti incrementali.

## <a name="scale-units-and-dedicated-workloads"></a>Unità di scala e carichi di lavoro dedicati

Le unità di scala estendono l'ambiente centrale dell'hub di Supply Chain Management aggiungendo capacità di elaborazione dedicata. Le unità di scala possono essere eseguite nel cloud. In alternativa, possono essere eseguite nella rete perimetrale nelle strutture locali dell'utente.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 con unità di scala.":::

Le unità di scala forniscono resilienza, affidabilità e scalabilità per i carichi di lavoro assegnati. Le unità di scala nelle reti perimetrali possono essere temporaneamente disconnesse dall'ambiente hub cloud e i lavoratori continuano a lavorare nei carichi di lavoro assegnati sulla rete perimetrale.

Un *carico di lavoro* è un insieme definito di funzionalità aziendali che può essere scomposto e delegato a un'unità di scala. Sebbene il carico di lavoro per la gestione del magazzino sia stato rilasciato, il carico di lavoro per l'esecuzione della produzione è ancora in anteprima.

È possibile configurare l'ambiente hub utilizzato e le unità di scale nel cloud per carichi di lavoro selezionati utilizzando il [portale di gestione delle unità di scala](https://sum.dynamics.com). È anche possibile assegnare più carichi di lavoro per unità di scala. Per informazioni sui prerequisiti e sui limiti per le unità di scala nel cloud nella versione corrente, vedere la sezione [Prerequisiti e limitazioni per le unità di scala nel cloud](#cloud-scale-unit-prerequisites) più avanti in questo argomento.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Funzionalità di carico di lavoro di gestione del magazzino dedicate in un'unità di scala

Il carico di lavoro di gestione del magazzino consente di eseguire processi di gestione del magazzino su una distribuzione isolata.
Per ulteriori informazioni, vedere [Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Funzionalità di carico di lavoro di esecuzione della produzione dedicate in un'unità di scala

Il carico di lavoro di produzione offre le seguenti funzionalità:

- Gli operatori macchine e i supervisori del reparto di produzione possono accedere al piano di produzione operativo.
- Gli operatori possono mantenere il piano aggiornato eseguendo lavori di produzione discreti e di elaborazione.
- Il supervisore del reparto di produzione può modificare il piano operativo.
- I lavoratori possono accedere alle funzionali di orario e presenze per l'entrata e l'uscita dalla rete perimetrale per garantire il corretto calcolo della retribuzione.

Per ulteriori informazioni, vedere [Carichi di lavoro di esecuzione della produzione per unità di scala nel cloud e nella rete perimetrale](cloud-edge-workload-manufacturing.md).

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Considerazioni prima di abilitare la topologia ibrida distribuita per Supply Chain Management

Abilitando la topologia ibrida distribuita, si esegue la transizione dell'ambiente cloud di Supply Chain Management in modo che funzioni come hub. È inoltre possibile associare ambienti aggiuntivi configurati come unità di scala nel cloud o nella rete perimetrale.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>Prerequisiti e limiti per unità di scala nel cloud

Nella versione corrente per le unità di scala, alcune funzionalità non sono ancora disponibili ma potrebbero essere aggiunte in versioni incrementali nel tempo.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>È necessario essere un cliente con licenza di Supply Chain Management

Per eseguire l'onboarding alla topologia distribuita, si deve disporre di una licenza per Supply Chain Management. L'ambiente cloud esistente diventerà l'hub della topologia ibrida utilizzata. È possibile dichiarare sia gli ambienti sandbox che gli ambienti di produzione come ambienti hub e aggiungere unità di scala in base ai componenti aggiuntivi acquisiti.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>Il progetto esistente deve essere amministrato tramite la versione commerciale globale di LCS

Il progetto Microsoft Dynamics Lifecyle Services (LCS) esistente deve soddisfare i seguenti requisiti di versione:

- Il progetto deve essere amministrato tramite la versione commerciale globale di LCS nel sito [lcs.dynamics.com](https://lcs.dynamics.com).
- Versioni locali di LCS (come [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) e [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com)) non sono supportate.
- Le versioni cloud per enti governativi di LCS non sono supportate.
- La versione Mooncake di LCS non è supportata.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>L'ambiente di produzione corrente deve essere di tipo Self-Service in LCS

L'ambiente di produzione corrente deve essere contrassegnato con il tipo **Self service** in LCS. Questo tipo indica che il tenant del progetto LCS è già stato convertito in modo che supporti il modello di hosting Azure Service Fabric.

> [!IMPORTANT]
> I tipi di ambiente che vengono eseguiti come infrastruttura distribuita come servizio (IaaS) non sono supportati. Questi ambienti sono tipicamente contrassegnati con il tipo **Gestito da Microsoft** in LCS. Se si dispone di ambienti di questo tipo, collaborare con il contatto Microsoft per comprendere la cronologia della migrazione al tipo **Self service**.

Microsoft sta eseguendo la transizione di tutti gli ambienti cloud di Supply Chain Management da un modello IaaS a una topologia ospitata in Service Fabric. Questa transizione offre una migliore scalabilità e aiuta a semplificare la gestione dei servizi. Pertanto, le operazioni di distribuzione e manutenzione sono più veloci. Allo stesso modo, i componenti del servizio vengono migrati al concetto di microservizi e il modello di hosting del servizio [eseguirà la transizione](/virtualization/windowscontainers/about/containers-vs-vm) da un modello di macchina virtuale (VM) a un'architettura containerizzata leggera.

Infine, la stessa infrastruttura di servizi containerizzata basata su Service Fabric alimenterà le istanze del servizio nel cloud e nella rete perimetrale, indipendentemente dal fatto che un'istanza sia un hub nel cloud o un'unità di scala nel cloud o nella rete perimetrale.

Prima di poter eseguire l'onboarding alla topologia ibrida che supporta le unità di scala, è necessario eseguire la transizione del tenant del progetto al modello ospitato da Service Fabric. Inoltre, qualsiasi ambiente che fungerà da hub deve essere convertito.

> [!TIP]
> Per informazioni sullo stato del tenant del progetto LCS, cercare il tipo di ambiente in [LCS](https://lcs.dynamics.com/) oppure contattare il partner o il contatto Microsoft.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>Gli ambienti di dati aziendali locali non sono supportati come hub per le unità di scala

Gli ambienti locali non possono funzionare come hub per le unità di scala. Gli ambienti hub devono essere sempre ospitati nel cloud.

#### <a name="scale-unit-management-capabilities-are-limited"></a>Le funzionalità di gestione delle unità di scala sono limitate

Le funzionalità di gestione che possono aiutare nello spostamento di carichi di lavoro sono limitate. Alcune operazioni di gestione non sono supportate in modalità self-service ed è possibile che sia necessario richiedere supporto tramite il partner o il contatto Microsoft. Gli esempi includono alcuni movimenti di carichi di lavoro tra unità di scala e movimenti ad-hoc temporanei in scenari di emergenza.

#### <a name="metrics-and-measurements-arent-yet-available"></a>Metriche e misurazioni non sono ancora disponibili

Le metriche e le misure che potrebbero essere utili nella selezione della migliore applicazione per le unità di scala non sono ancora disponibili. Collaborare con il contatto Microsoft o il partner di implementazione per selezionare l'applicazione più vantaggiosa.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>Elaborazione dati durante la gestione di unità di scala

Quando si abilita l'ambiente Dynamics 365 per supportare la topologia ibrida distribuita per unità di scale nel cloud e nella rete perimetrale, alcuni servizi di gestione saranno ospitati solo negli Stati Uniti, come con LCS. Questo comportamento influisce sul trasferimento e sulla risorsa di archiviazione di alcune informazioni amministrative e di configurazione utilizzate dal [portale di gestione delle unità di scala](https://sum.dynamics.com). Di seguito sono riportati alcuni esempi.

- Nome e ID dei tenant
- ID del progetto LCS
- Indirizzi di posta elettronica dell'amministratore e del proprietario del progetto utilizzati per l'accesso
- ID ambiente per l'hub e le unità di scala
- Configurazioni del carico di lavoro, inclusi i nomi e gli indirizzi fisici di persone giuridiche e strutture, in modo che la topologia possa essere visualizzata su una mappa geografica
- Metriche raccolte (come latenza e velocità effettiva) che verranno mostrate nella pagina di analisi della mappa per aiutare a selezionare l'uso più vantaggioso delle unità di scala

I dati trasferiti e archiviati nei data center degli Stati Uniti verranno eliminati in base ai criteri di conservazione dei dati di Microsoft. La privacy degli utenti è importante per Microsoft. Per ulteriori informazioni, leggere l'[Informativa sulla privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.

## <a name="onboarding-in-two-stages"></a>Onboarding in due fasi

Il processo di onboarding nella topologia ibrida distribuita prevede due fasi. Durante la prima fase, è necessario convalidare le personalizzazioni per assicurarsi che funzionino nella topologia distribuita con unità di scala. Gli ambienti sandbox e di produzione vengono spostati solo durante la seconda fase.

### <a name="stage-1-evaluate-customizations-in-one-box-development-environments"></a>Fase 1: valutare le personalizzazioni in ambienti di sviluppo one-box

Prima di iniziare a eseguire l'onboarding degli ambienti sandbox o di produzione, è consigliabile esplorare le unità di scala in una configurazione di sviluppo, come un ambiente one-box (noto anche come ambiente di livello 1), in modo da poter convalidare processi, personalizzazioni e soluzioni. Durante questa fase, i dati e le personalizzazioni verranno applicati agli ambienti one-box. Un ambiente assume il ruolo dell'hub e l'altro assume il ruolo di unità di scala. Questa configurazione fornisce il modo migliore per identificare e risolvere i problemi. L'ultima build PEAP può essere utilizzata anche per completare questa fase.

Per la fase 1, si deve usare gli [strumenti di distribuzione delle unità di scala per ambienti di sviluppo one-box](https://github.com/microsoft/SCMScaleUnitDevTools). Questi strumenti consentono di configurare hub e unità di scala in uno o due ambienti one-box distinti. Gli strumenti sono forniti come versione binaria e nel codice sorgente su GitHub. Esaminare il wiki del progetto, che include una [guida d'uso dettagliata](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) che descrive come vengono utilizzati gli strumenti.

### <a name="stage-2-acquire-add-ins-and-deploy-in-your-sandbox-and-production-environments"></a>Fase 2: acquisire componenti aggiuntivi ed eseguire la distribuzione in ambienti sandbox e di produzione

Per eseguire l'onboarding di uno degli ambienti sandbox o di produzione alla nuova topologia, è necessario acquisire componenti aggiuntivi per una o più unità di scala nel cloud (e, in futuro, per unità di scala nella rete perimetrale). I componenti aggiuntivi garantiranno gli slot di progetto e ambiente corrispondenti in [LCS](https://lcs.dynamics.com/) in modo che gli ambienti delle unità di scala possano essere distribuiti.

> [!NOTE]
> I componenti aggiuntivi delle unità di scala non sono associati a un numero limitato di utenti ma possono essere utilizzati da qualsiasi utente nella sottoscrizione esistente, in base ai ruoli assegnati dall'amministratore.

Le unità di scala sono offerte in più unità di stockkeeping (SKU) e opzioni per la determinazione dei prezzi. Pertanto, è possibile scegliere l'opzione che meglio soddisfa il volume di transazioni mensili pianificato e i requisiti di prestazioni.

Lo SKU semplice è noto come *Base* e lo SKU più efficace è noto come *Standard*. Ogni SKU è precaricato con un numero specifico di transazioni mensili. Tuttavia, è possibile aumentare il budget mensile delle transazioni aggiungendo componenti aggiuntivi in eccesso per ogni SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Componente aggiuntivo per unità di scala nel cloud.":::

> [!TIP]
> Per identificare il dimensionamento che meglio soddisfa le proprie esigenze, collaborare con il partner e Microsoft per comprendere la dimensione della transazione mensile richiesta.

L'acquisto di ogni componente aggiuntivo di unità di scala non solo fornisce un volume mensile di transazioni, ma dà anche diritto a un numero specifico di slot di ambiente in LCS. Per ogni componente aggiuntivo Unità di scala nel cloud, si ha diritto a un nuovo slot di produzione e un nuovo slot sandbox. Durante il processo di onboarding, verrà aggiunto un nuovo progetto LCS con questi slot. I diritti di utilizzo per gli slot sono vincolati di modo che gli slot debbano essere usati come unità di scala che dispongono di un hub cloud.

I componenti aggiuntivi in eccesso non danno diritto a nuovi slot di ambiente.

Se si desidera acquisire più ambienti sandbox, è possibile acquistare slot sandbox normali aggiuntivi. Microsoft può quindi fornire assistenza per abilitare quegli slot come unità di scala sandbox per la topologia ibrida.

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Eseguire l'onboarding alla topologia ibrida distribuita per Supply Chain Management

### <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Selezionare il tenant del progetto LCS e il processo di onboarding dettagliato

Dopo aver finito di pianificare il modo in cui eseguire l'onboarding alla topologia ibrida distribuita per Supply Chain Management, si utilizzerà il [portale di gestione delle unite di scala](https://aka.ms/SCMSUM) per iniziare il processo di onboarding. Nel portale, selezionare la scheda **Tenant di Dynamics 365**. Questa scheda mostra l'elenco dei tenant di cui fa parte l'account in uso e in cui l'utente è proprietario o amministratore dell'ambiente per un progetto LCS.

Se il tenant cercato non è nell'elenco, andare a [LCS](https://lcs.dynamics.com/v2) e verificare di essere un amministratore dell'ambiente o un proprietario del progetto LCS per quel tenant. Solo gli account Azure Active Directory (Azure AD) del tenant selezionato sono autorizzati a completare la registrazione.

> [!NOTE]
> Dopo aver applicato le modifiche a LCS, potrebbero essere necessari fino a 30 minuti perché l'elenco di tenant rifletta le modifiche.

Per ogni tenant, l'elenco mostra lo stato dell'onboarding.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Elenco di tenant nella scheda Tenant di Dynamics 365.":::

Selezionare **Clicca qui per iniziare** per richiedere l'onboarding per il tenant LCS. È necessario accettare le condizioni. È inoltre necessario fornire un indirizzo e-mail aziendale a cui Microsoft possa inviare comunicazioni correlate al processo di onboarding.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Invio registrazione per un tenant.":::

Microsoft esaminerà la richiesta e informerà l'utente sui passaggi successivi inviando un messaggio e-mail all'indirizzo che fornito nel modulo di registrazione. Microsoft lavorerà a stretto contatto con il cliente per abilitare le unità di scala nella topologia ibrida per lo scenario aziendale.

Al termine dell'onboarding, è possibile utilizzare la porta per configurare unità di scala e carichi di lavoro.

### <a name="manage-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Gestire unità di scala e carichi di lavoro utilizzando il portale di gestione delle unità di scala

Andare al [portale di gestione delle unità di scala](https://aka.ms/SCMSUM) e iscriversi con il proprio account tenant. Nella pagina **Configura unità di scala** è possibile aggiungere un ambiente hub, se non è ancora elencato. È quindi possibile selezionare l'hub che si desidera configurare con unità di scala e carichi di lavoro.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Portale di gestione delle unità di scala, pagina Configura unità di scala.":::

Per aggiungere una o più unità di scala disponibili nelle sottoscrizioni, selezionare **Aggiungi unità di scala**.

Nella scheda **Carichi di lavoro predefiniti**, utilizzare il pulsante **Crea carico di lavoro** per aggiungere un carico di lavoro di gestione del magazzino a una delle unità di scala. Per ogni carico di lavoro, è necessario specificare il contesto dei processi che saranno di proprietà del carico di lavoro stesso. Per i carichi di lavoro di gestione del magazzino, il contesto è un magazzino specifico in un sito e in una persona giuridica specifici.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Finestra di dialogo Definisci carichi di lavoro.":::

#### <a name="manage-workloads"></a>Gestire i carichi di lavoro

Quando uno o più carichi di lavoro sono abilitati, utilizza l'opzione **Gestisci carichi di lavoro** per avviare e gestire processi come quelli elencati nella tabella seguente.

| Elaborazione | Description |
|---|---|
| Sospendere la comunicazione dell'unità di scala | Sospendi i messaggi della pipeline tra l'hub e un'unità di scala. Questo processo interromperà la comunicazione e ridurrà la pipeline di dati tra l'hub e le unità di scala. Devi eseguire questo processo prima di eseguire un'operazione di manutenzione di Supply Chain Management sull'hub o sull'unità di scala, ma è possibile utilizzarlo anche in altre situazioni. |
| Riprendere la comunicazione dell'unità di scala | Riprendi i messaggi della pipeline tra l'hub e un'unità di scala. Potrebbe essere necessario utilizzare questo processo, ad esempio, dopo aver eseguito un'operazione di manutenzione di Supply Chain Management sull'hub o sull'unità di scala. |
| Aggiornare i carichi di lavoro | Sincronizza le nuove funzionalità tra l'hub e i carichi di lavoro dell'unità di scala. Potrebbe essere necessario utilizzare questo processo, ad esempio, quando la manutenzione ha causato la modifica delle query di scambio dati e/o ha aggiunto nuove tabelle o campi al carico di lavoro. |
| Trasferire i carichi di lavoro a un'unità di scala | Pianifica un carico di lavoro attualmente in esecuzione nell'hub per essere spostato su un'unità di scala. Quando questo processo viene eseguito, verrà eseguita la sincronizzazione dei dati e sia l'hub che l'unità di scala verranno impostati per modificare la proprietà del carico di lavoro. |
| Trasferire unità di scala all'hub | Pianifica un carico di lavoro attualmente in esecuzione su un'unità di scala per essere spostato nell'hub. Quando questo processo viene eseguito, verrà eseguita la sincronizzazione dei dati e sia l'hub che l'unità di scala verranno impostati per modificare la proprietà del carico di lavoro.
| Transizione di emergenza all'hub | <p>Trasferisci immediatamente un carico di lavoro esistente all'hub. *Questo processo modificherà la proprietà solo dei dati attualmente disponibili nell'hub.*</p><p><strong>Avvertimento:</strong> questo processo può causare la perdita di dati per i dati non sincronizzati ed errori nell'elaborazione aziendale. Pertanto, dovrebbe essere utilizzato solo in caso di emergenza, in cui i processi aziendali devono essere elaborati sull'hub perché l'unità di scala ha un'interruzione del servizio che non può essere mitigata entro un tempo ragionevole.</p> |
| Ritirare la topologia distribuita | Rimuovere la distribuzione di un'unità di scalabilità ed eseguirla solo nell'hub, senza elaborazione del carico di lavoro. |

:::image type="content" source="media/sum-manage-workloads.png" alt-text="Gestione di unità di scala e carichi di lavoro.":::

> [!TIP]
> Nel tempo, all'esperienza di gestione delle unità di scala verranno aggiunti miglioramenti incrementali per semplificare le operazioni di gestione del ciclo di vita. Le funzionalità specifiche per la versione corrente sono documentate in un manuale di onboarding disponibile per i clienti che sono in procinto di eseguire l'onboarding alla topologia ibrida distribuita per Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
