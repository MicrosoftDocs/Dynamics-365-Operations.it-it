---
title: Unità di scala nel cloud e nella rete perimetrale per i carichi di lavoro di gestione della produzione e del magazzino
description: Questo argomento fornisce informazioni sulle unità di scala nel cloud e nella rete perimetrale per i carichi di lavoro di gestione della produzione e del magazzino.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 28301cdfb86d00ea6f04e996fe7fb1485e83b2d4
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104966"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Unità di scala nel cloud e nella rete perimetrale per i carichi di lavoro di gestione della produzione e del magazzino

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le unità di scala nel cloud e nella rete perimetrale consentono la distribuzione dei carichi di lavoro di esecuzione nel reparto produzione e nel magazzino tra ambienti diversi. Questa funzionalità può aiutare a migliorare le prestazioni, prevenire le interruzioni del servizio e massimizzare il tempo di attività. È fornita dai componenti aggiuntivi seguenti:

- Componente aggiuntivo unità di scala nel cloud per Dynamics 365 Supply Chain Management
- Componente aggiuntivo unità di scala nella rete perimetrale per Dynamics 365 Supply Chain Management

Le aziende che lavorano con la produzione e la distribuzione devono essere in grado di eseguire processi aziendali chiave 24 ore su 24, 7 giorni su 7, senza interruzioni e su larga scala. Le unità di scala nel cloud e nella rete perimetrale consentono alle aziende di eseguire processi di produzione e magazzino cruciali senza interruzioni, anche di fronte a problemi di latenza o di connettività di rete occasionali.

## <a name="public-preview-information"></a>Informazioni sull'anteprima pubblica

L'anteprima fornisce un ambiente che funziona come un hub basato sul cloud dell'ambiente Dynamics 365 Supply Chain Management in uso e un ambiente che funziona come un'unità di scala nel cloud.

<!-- You will also be able to use Local Business Data (LBD) to configure an on-premises environment as an edge scale unit for the hub you received as part of the preview program.-->

### <a name="preview-availability"></a>Disponibilità dell'anteprima

L'anteprima per le unità di scala nel cloud e nella rete perimetrale diventa disponibile per i clienti esistenti di Supply Chain Management nell'ottobre 2020.

Per accedere alla versione di anteprima 10.0.15/aggiornamento piattaforma 39 di ottobre per la distribuzione nell'ambiente [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2) in uso, è necessario partecipare al programma PEAP (Preview Early Access Program) per Supply Chain Management. È possibile iscriversi al programma PEAP se si è già membri del più ampio [Dynamics Insider Program](https://experience.dynamics.com/insider). È sufficiente selezionare il programma specifico denominato "Finance & Operations: Preview early access program (PEAP)".

> [!IMPORTANT]
> La funzionalità di unità di scala per Supply Chain Management è disponibile solo se si accettano le [condizioni per l'anteprima cloud + rete perimetrale per Finance and Operations](https://Aka.ms/SCMCnETerms).

### <a name="data-processing-for-the-preview"></a>Elaborazione dati per l'anteprima

Durante l'anteprima pubblica, alcuni servizi di gestione saranno ospitati solo negli Stati Uniti. Tuttavia, quando la funzionalità sarà disponibile a livello generale, questi servizi di gestione saranno disponibili in tutte le aree geografiche supportate da Supply Chain Management. Ciò influisce sul trasferimento e l'archiviazione delle informazioni amministrative utilizzate dal responsabile dell'unità di scala, tra cui:

- Nome e ID dei tenant
- ID del progetto LCS
- Indirizzi e-mail dell'amministratore utilizzati per l'accesso
- ID ambiente per hub e unità di scala
- Configurazione dei carico di lavoro
- Metriche raccolte (come latenza e velocità effettiva) visualizzate nella pagina di analisi della mappa

I dati trasferiti e archiviati nei data center degli Stati Uniti verranno eliminati quando gli ambienti di anteprima verranno chiusi.

### <a name="sign-up-for-the-preview"></a>Iscriversi all'anteprima

Per iscriversi all'anteprima per il cloud e per la rete perimetrale per Supply Chain Management, l'organizzazione deve già disporre di un ambiente cloud di Supply Chain Management attivo.

Le funzionalità di unità di scala sono attualmente in anteprima pubblica. Per l'iscrizione, è necessario utilizzare un account utente sul tenant specifico. È necessario anche essere un proprietario del progetto o un amministratore dell'ambiente in LCS per un progetto Dynamics 365 LCS attivo in quel tenant.

Durante l'iscrizione per l'anteprima, selezionare un tenant e seguire i passaggi indicati. Non appena Microsoft potrà allocare la funzionalità di anteprima, invieremo all'utente un messaggio di posta elettronica che include i dettagli di provisioning e i codici promozionali (promo) per due ambienti (un hub e un'unità di scala) per il progetto LCS appropriato. Sarà quindi possibile distribuire i due ambienti come ambienti sandbox di livello 2. Tali ambienti saranno validi 60 giorni dalla data di creazione dei codici promozionali. Non sarà possibile utilizzare i due ambienti fino al completamento del passaggio descritto nel paragrafo successivo.

Dopo aver confermato con Microsoft che i due ambienti sono stati distribuiti utilizzando i codici promozionali, uno degli ambienti verrà configurato per funzionare come hub e l'altro sarà configurato per funzionare come unità di scala. È quindi possibile configurare le unità di scala e distribuire la gestione del magazzino selezionata e i carichi di lavoro di produzione utilizzando il [portale di gestione delle unità di scala](https://aka.ms/SCMSUM).

Gli ambienti di anteprima verranno eliminati automaticamente dopo 60 giorni. Tuttavia, potrebbero essere eliminati prima se sembra che non vengano utilizzati. Dopo che gli ambienti di anteprima sono stati eliminati, è possibile registrarsi e mettersi in coda per una nuova distribuzione in anteprima.

Per registrarsi per l'anteprima, andare al [portale di gestione delle unità di scala](https://aka.ms/SCMSUM).

### <a name="limitations-that-apply-during-the-preview-period"></a>Limitazioni che si applicano durante il periodo di anteprima

> [!IMPORTANT]
> Per la fase iniziale del programma di anteprima per questa funzionalità, Microsoft supporta solo hub con unità di scala nel cloud, non hub con unità di scala nella rete perimetrale. Le unità di scala nella rete perimetrale vengono installate in locale e si prevede che diventino disponibili durante una fase imminente del programma.

Poiché le unità di scala nel cloud e nella rete perimetr ale sono una funzionalità di anteprima, i servizi correlati sono attualmente disponibili in paesi e regioni limitati. Abilitando le unità di scala nel cloud e nella rete perimetrale, l'utente dichiara di comprendere che alcuni dati correlati alla configurazione e all'elaborazione di unità di scala nel cloud e nella rete perimetrale potrebbero essere archiviati in un data center situato negli Stati Uniti. Se si abilitano le unità di scala nel cloud e nella rete perimetrale, si accettano anche le [condizioni per l'anteprima cloud + rete perimetrale per Finance and Operations](https://Aka.ms/SCMCnETerms). Per ulteriori informazioni sulle unità di scala nel cloud e nella rete perimetrale, vedere la [documentazione](https://aka.ms/scmcne).

La privacy degli utenti è importante per Microsoft. Per ulteriori informazioni, leggere l'[Informativa sulla privacy](https://aka.ms/privacy) di Microsoft.

> [!IMPORTANT]
> Alcune funzionalità aziendali non sono completamente supportate nell'anteprima pubblica quando i carichi di lavoro vengono utilizzati nelle unità di scala. Per ulteriori informazioni sui carichi di lavoro funzionali, vedere le sezioni più avanti in questo argomento.

## <a name="scale-units-and-dedicated-workloads"></a>Unità di scala e carichi di lavoro dedicati

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 con unità di scala":::

Le unità di scala estendono l'ambiente centrale dell'hub di Supply Chain Management aggiungendo capacità di elaborazione dedicata. Le unità di scala possono essere eseguite nel cloud. In alternativa, possono essere eseguite nella rete perimetrale nelle strutture locali dell'utente. Le unità di scala possono essere temporaneamente scollegate dall'ambiente hub. Quando sono connesse, le unità di scala ricevono tutte le informazioni necessarie per eseguire l'elaborazione dedicata per i carichi di lavoro assegnati.

:::image type="content" source="media/cloud_edge-previewoptions.png" alt-text="Opzioni di unità di scala nell'anteprima pubblica":::

Per l'anteprima pubblica, è possibile configurare un ambiente hub con carichi di lavoro selezionati su un'unità di scala nel cloud tramite il portale di gestione delle unità di scala. I partecipanti all'anteprima che hanno accesso a un ambiente locale di dati aziendali locali (LBD) possono anche configurare l'ambiente LBD come unità di scala nella rete perimetrale.

Un carico di lavoro è un insieme definito di funzionalità aziendali che può essere scomposto e delegato a un'unità di scala. Attualmente, le funzionalità di anteprima presentano due tipi di carichi di lavoro:

- Esecuzione produzione
- Gestione magazzino

È possibile assegnare un carico di lavoro per tipo per unità di scala. 

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Funzionalità di carico di lavoro di esecuzione della produzione dedicate in un'unità di scala

Per l'esecuzione della produzione, le unità di scala nel cloud e nella rete perimetrale offrono le seguenti funzionalità, anche quando le unità della rete perimetrale non sono connesse al cloud:

- Gli operatori macchine e i supervisori del reparto di produzione possono accedere al piano di produzione operativo.
- Gli operatori possono mantenere il piano aggiornato eseguendo lavori di produzione discreti e di elaborazione.
- Il supervisore del reparto di produzione può modificare il piano operativo.
- I lavoratori possono accedere alle funzionali di orario e presenze per l'entrata e l'uscita dalla rete perimetrale per garantire il corretto calcolo della retribuzione.

Per ulteriori informazioni, vedere i [dettagli sul carico di lavoro delle unità di scala di produzione](cloud-edge-workload-manufacturing.md).

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Funzionalità di carico di lavoro di gestione del magazzino dedicate in un'unità di scala

Per la gestione del magazzino, le unità di scala nel cloud e nella rete perimetrale offrono le seguenti funzionalità, anche quando le unità della rete perimetrale non sono connesse al cloud:

- L'elaborazione dei metodi di ciclo selezionati è abilitata per gli ordini cliente e il rifornimento della domanda.
- Gli addetti al magazzino possono eseguire le vendite e il lavoro di rifornimento del magazzino in base alla domanda utilizzando l'app di magazzino.
- Gli addetti al magazzino possono richiedere informazioni sulle scorte disponibili utilizzando l'app di magazzino.
- Gli addetti al magazzino possono creare ed eseguire movimenti di scorte utilizzando l'app di magazzino.
- Gli addetti al magazzino possono registrare gli ordini fornitore ed eseguire lo stoccaggio utilizzando l'app di magazzino.

Per ulteriori informazioni, vedere i [dettagli sul carico di lavoro delle unità di scala di magazzino](cloud-edge-workload-warehousing.md).

## <a name="onboard-scale-units-for-your-supply-chain-management-environment"></a>Eseguire l'onboarding di unità di scala per l'ambiente di Supply Chain Management in uso

### <a name="deploy-the-preview-for-cloud-and-edge-scale-units"></a>Distribuire l'anteprima per unità di scala nel cloud e nella rete perimetrale

La figura seguente mostra il flusso di registrazione e provisioning per l'anteprima pubblica per le unità di scala nel cloud.

:::image type="content" source="media/cloud_edge-previewsignup.png" alt-text="Passaggi di registrazione all'anteprima":::

### <a name="select-your-lcs-project-tenant-and-the-detailed-preview-process"></a>Seleziona il tenant del progetto LCS e il processo di anteprima dettagliato

Nell'anteprima pubblica, il [portale di gestione delle unità di scala](https://aka.ms/SCMSUM) mostra l'elenco dei tenant di cui fa parte l'account in uso e in cui l'utente è proprietario o amministratore dell'ambiente per un progetto LCS.

Se il tenant cercato non è in questo elenco, andare a [LCS](https://lcs.dynamics.com/v2) e verificare di essere un amministratore dell'ambiente o un proprietario del progetto LCS per quel tenant. Si noti che solo gli account Azure Active Directory (Azure AD) del tenant selezionato sono autorizzati a completare la registrazione.

> [!NOTE]
> Dopo aver applicato le modifiche a LCS, potrebbero essere necessari fino a 30 minuti perché l'elenco di tenant rifletta le modifiche.

Per ogni tenant, l'elenco mostra lo stato di registrazione.

:::image type="content" source="media/cloud_edge-Signup1.png" alt-text="Opzione di registrazione per un tenant":::

Selezionare il collegamento **Fai clic per registrarti** per consentire al tenant LCS di partecipare all'anteprima. È necessario accettare le condizioni. È inoltre necessario fornire un indirizzo e-mail aziendale a cui Microsoft possa inviare comunicazioni correlate al processo di registrazione per l'anteprima.

:::image type="content" source="media/cloud_edge-Signup2.png" alt-text="Invio registrazione per un tenant":::

Microsoft esaminerà la richiesta e informerà l'utente sui passaggi successivi inviando un messaggio e-mail all'indirizzo che fornito nel modulo di registrazione.

Dopo aver ottenuto l'accesso al programma di anteprima, l'utente riceverà due codici promozionali per il progetto LCS. È ora possibile utilizzare questi codici promozionali per distribuire due ambienti in LCS. Gli ambienti devono utilizzare il programma PEAP, versione 10.0.15 o successiva. Dopo aver completato l'applicazione dei codici promozionali, avvisare Microsoft (come indicato), in modo che possa completare l'abilitazione degli ambienti per le funzionalità di anteprima. Microsoft avviserà l'utente quando questo passaggio di configurazione sarà completato.

È ora possibile iniziare a configurare unità di scala e carichi di lavoro nell'ambiente di anteprima.

> [!IMPORTANT]
> Quando si configurano le unità di scala nel cloud, è possibile [eseguire tutti i passaggi richiesti nel portale di gestione delle unità di scala](#scale-unit-manager-portal).
<!-- 
> If want to use edge scale units with your preview deployment, you must do all scale unit configuration in the user interface on the hub as described in [Configure the hub environment for use with edge scale units](cloud-edge-edge-scale-units-lbd.md#configure-the-hub-environment). You can't use Scale Unit Manager portal if you include an edge scale unit. -->

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Gestire unità di scala e carichi di lavoro utilizzando il portale di gestione delle unità di scala

Andare al [portale di gestione delle unità di scala](https://aka.ms/SCMSUM) e iscriversi con il proprio account tenant. Nella pagina **Configura unità di scala** è possibile aggiungere un ambiente hub, se non è ancora elencato. È quindi possibile selezionare l'hub che si desidera configurare con unità di scala e carichi di lavoro.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Gestione di unità di scala e carichi di lavoro":::

Per aggiungere una o più unità di scala disponibili nella topologia, selezionare **Aggiungi unità di scala**. Nell'anteprima, è possibile visualizzare l'unità di scala nel cloud distribuita da uno dei codici promozionali ricevuto come parte del programma di anteprima.

<!--  [!IMPORTANT]
> In the public preview, the Scale Unit Manager portal shows the cloud scale unit that you received as part of the preview program. Any edge scale unit that you created based on an LBD configuration can't be managed in the Scale Unit Manager portal yet. For configuration details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md) -->

Nella scheda **Carichi di lavoro predefiniti**, utilizzare il pulsante **Crea carico di lavoro** per aggiungere un carico di lavoro di gestione del magazzino o di esecuzione della produzione a una delle unità di scala. Per ogni carico di lavoro, è necessario specificare il contesto dei processi che saranno di proprietà del carico di lavoro stesso. Per i carichi di lavoro di gestione del magazzino, il contesto è un magazzino specifico in un sito e in una persona giuridica specifici. Per i carichi di lavoro di esecuzione della produzione, il contesto è un sito specifico in una persona giuridica.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Creazione del carico di lavoro":::

> [!IMPORTANT]
> Il portale di gestione delle unità di scala nell'anteprima non consente di rimuovere i carichi di lavoro dalle unità di scala o di annullare l'assegnazione di un'unità di scala da un hub dopo aver effettuato l'assegnazione stessa. Se è necessario rimuovere un'assegnazione, rivolgersi alla persona di contatto per la gestione del programma di anteprima.

<!-- ### Create an edge scale unit using your custom on-premises hardware appliance

In the public preview, you can create on-premises edge scale units on your custom hardware using the LBD environments. For details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md). -->


[!INCLUDE[footer-include](../../includes/footer-banner.md)]