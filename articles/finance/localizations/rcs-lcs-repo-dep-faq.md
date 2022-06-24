---
title: Regulatory Configuration Service (RCS) - Deprecazione dell'archiviazione di Lifecycle Services (LCS)
description: Questo articolo fornisce informazioni sulla deprecazione dell'archiviazione di Microsoft Dynamics Lifecycle Services (LCS) pianificata come parte dell'implementazione del repository globale di Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: 4a35941d1521d26f95bacf29213fee42daeb42ab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849733"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) – Deprecazione dell'archiviazione di Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

L'utilizzo di Microsoft Dynamics Lifecycle Services (LCS) come repository di archiviazione per le configurazioni di Creazione di report elettronici (ER) sta per essere deprecato. Questa deprecazione comporterà le seguenti modifiche:

- Le configurazioni prodotte da Microsoft e usate nelle applicazioni Microsoft Dynamics 365 non verranno più pubblicate nella libreria delle risorse condivise in LCS. Verranno invece pubblicate solo tramite il repository globale RCS. Tuttavia, le configurazioni per Dynamics AX 2012 continueranno a essere pubblicate nella libreria di risorse condivise in LCS fino al termine del ciclo di vita del supporto per AX 2012.
- La funzionalità che ti consente di caricare le configurazioni nella libreria delle risorse del progetto in LCS dalle app per la finanza e le operazioni e da RCS verrà disattivata. Tuttavia, sarai comunque in grado di utilizzare il browser in LCS per caricare le configurazioni nella libreria di risorse del progetto. Pertanto, potrai sempre aggiungere configurazioni a LCS in modo che possano essere incluse nei pacchetti della soluzione.
- L'importazione di configurazioni da LCS continuerà ad essere disponibile e supportata nelle app per la finanza e le operazioni e in RCS per qualche tempo. In futuro, però, questa funzionalità verrà deprecata (la data esatta della deprecazione sarà annunciata in seguito).

## <a name="deprecation-notice"></a>Avviso di deprecazione

La deprecazione dell'uso di LCS come spazio di archiviazione è stata comunicata in [Funzionalità rimosse o deprecate in Dynamics 365 Finance - Avviso di deprecazione di LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). La data di deprecazione prevista è il 1° aprile 2022.

## <a name="key-features"></a>Funzionalità principali

- Usa RCS per creare e modificare le configurazioni ER e le funzionalità di globalizzazione.
- Invia le configurazioni direttamente dalla progettazione RCS a un'applicazione connessa, come un ambiente Dynamics 365 Finance, in modo da poter apportare e testare rapidamente le modifiche alle configurazioni.
- Archivia, condividi e gestisci centralmente il ciclo di vita sia per le configurazioni ER che per le funzionalità di globalizzazione tramite l'archiviazione centralizzata del repository globale.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Guida per azioni una tantum e continuative

Questa sezione descrive una serie di passaggi che devono essere completati una volta. Illustra inoltre i passaggi che devono essere completati su base continuativa in seguito.

### <a name="one-time-action"></a>Azione una tantum

Importa tutte le configurazioni richieste da LCS a RCS, quindi pubblicale da RCS al repository globale. Se utilizzi librerie di risorse specifiche del progetto per archiviare configurazioni derivate in LCS, dovrai completare i seguenti passaggi mentre LCS è ancora accessibile.

1. Se un'istanza RCS non è già disponibile, esegui il provisioning di un'istanza. Per maggiori informazioni, vedi [Panoramica di RCS](rcs-overview.md).
2. Nell'istanza RCS di cui hai eseguito il provisioning, per ogni progetto LCS nella libreria delle risorse che include configurazioni ER derivate, registra il repository LCS appropriato.
3. Importa le configurazioni ER dai repository LCS a RCS. Per ulteriori informazioni, vedi [Importare configurazioni da LCS](/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services).
4. Se il repository globale non viene fornito automaticamente, registralo in RCS.
5. Carica tutte le configurazioni derivate dall'istanza RCS corrente nel repository globale. Utilizza la funzionalità **Pacchetti di configurazione** per semplificare il caricamento. Per ulteriori informazioni, vedi [Caricamento del repository globale RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>Operazioni successive

Utilizza le soluzioni di progettazione visiva in RCS per i seguenti scopi:

- Estendi i modelli forniti da Microsoft.
- Crea nuove configurazioni richieste dalla tua organizzazione.
- Personalizza le funzionalità di globalizzazione per la fatturazione elettronica e il servizio di calcolo imposte.

Utilizza il repository globale per i seguenti scopi:

- Accedi alle configurazioni prodotte da Microsoft e alle funzionalità di globalizzazione.
- Carica le configurazioni che hai creato o esteso nel repository globale per l'archiviazione e condividile negli ambienti dell'applicazione Dynamics 365 della tua organizzazione o con organizzazioni esterne. Per ulteriori informazioni, vedi [Creare la configurazione ER in RCS e caricarla nel repository globale](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Questa modifica significa che LCS non può essere utilizzato come spazio di archiviazione centrale per le configurazioni?

Sì. La funzionalità che ti consente di caricare le configurazioni nella libreria delle risorse del progetto in LCS dalle app per la finanza e le operazioni verrà deprecata. Tuttavia, sarai comunque in grado di utilizzare il browser in LCS per caricare le configurazioni nella libreria di risorse del progetto in funzione delle tue esigenze.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Pensavo che RCS fosse un repository sostitutivo per l'importazione di file modello globali. Non pensavo che fosse usato per archiviare le configurazioni. Quale delle due affermazioni è corretta?

RCS è un servizio di progettazione per la creazione e la modifica di configurazioni ER. RCS dispone di un proprio repository noto come repository globale. Questo repository permette di archiviare le configurazioni create in RCS. Dopo che l'utilizzo di LCS come spazio di archiviazione sarà deprecato, il repository globale sarà l'unica origine per le configurazioni Microsoft. Devi completare un'azione una tantum per importare tutte le configurazioni necessarie da LCS a RCS e quindi pubblicarle da RCS al repository globale.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Senza LCS, qual è il modo suggerito per archiviare le configurazioni in modo che le configurazioni di "test" e "produzione" possano essere facilmente gestite e trasferite?

RCS utilizza il concetto di *applicazione connessa*. Un'applicazione connessa stabilisce una connessione tra RCS e qualsiasi istanza delle app per la finanza e le operazioni. Poiché RCS può essere utilizzato per modificare le configurazioni, l'applicazione connessa può essere usata per inviare le configurazioni direttamente dal progettista agli ambienti delle app per la finanza e le operazioni. Pertanto, puoi modificare e testare rapidamente le tue configurazioni anziché dover passare attraverso l'archiviazione a livello di progetto LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Ci sono esempi che mostrano la configurazione e la gestione?

Non ci sono esempi, ma puoi completare i passaggi precedenti in questo articolo per migrare le tue configurazioni al repository globale RCS.

### <a name="is-rcs-a-prerequisite-to-configure-electronic-reporting"></a>RCS è un prerequisito per configurare la Creazione di report elettronici?

Sì. RCS include funzionalità che supportano l'impostazione delle funzionalità di globalizzazione utilizzate dai servizi di globalizzazione come la fatturazione elettronica e il servizio di calcolo imposte. Tuttavia, il servizio ha la stessa funzionalità della soluzione di progettazione visiva che consente di estendere o creare nuove configurazioni ER. RCS fornisce anche la gestione del ciclo di vita sia per le configurazioni ER che per le funzionalità di globalizzazione.

### <a name="which-regions-can-rcs-be-deployed-in"></a>In quali aree può essere distribuito RCS?

RCS è disponibile nelle seguenti aree di Azure:

- Stati Uniti
- India
- Francia
- Europa

Per ulteriori informazioni sul supporto del prodotto, vedi [Panoramica dei servizi di globalizzazione Dynamics](globalization-services-overview.md). Per ulteriori informazioni sul supporto geografico, vedi [Dynamics 365 e Power Platform: disponibilità, posizione dei dati, lingua e localizzazione](https://aka.ms/rcs/D365Productavailabilityguide).

### <a name="whats-the-cost-of-using-rcs"></a>Qual è il costo dell'utilizzo di RCS?

RCS e il repository globale sono forniti gratuitamente come parte delle esistenti licenze dell'app per la finanza e le operazioni. Nessun costo separato è associato all'utilizzo del servizio di progettazione RCS o alla memorizzazione delle configurazioni nel repository globale. Attualmente non c'è limite al numero di configurazioni o applicazioni connesse.