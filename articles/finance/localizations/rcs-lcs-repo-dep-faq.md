---
title: Regulatory Configuration Service (RCS) - Deprecazione dell'archiviazione di Lifecycle Services (LCS)
description: Questo argomento fornisce informazioni sulla deprecazione dell'archiviazione di Microsoft Dynamics Lifecycle Services (LCS) pianificata come parte dell'implementazione del repository globale di Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 05/25/2021
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
ms.openlocfilehash: 7a738af04da4425e76bd3b224400f91bc4eb8364d323da67ea457eaba9e65643
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782200"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) – Deprecazione dell'archiviazione di Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

L'utilizzo di Microsoft Dynamics Lifecycle Services (LCS) come repository di archiviazione per le configurazioni di Creazione di report elettronici (ER) sta per essere deprecato. Questa deprecazione comporterà le seguenti modifiche:

- Le configurazioni prodotte da Microsoft e usate nelle applicazioni Microsoft Dynamics 365 non verranno più pubblicate nella libreria delle risorse condivise in LCS. Verranno invece pubblicate solo tramite il repository globale RCS. Tuttavia, le configurazioni per Dynamics AX 2012 continueranno a essere pubblicate nella libreria di risorse condivise in LCS fino al termine del ciclo di vita del supporto per AX 2012.
- La funzionalità che ti consente di caricare le configurazioni nella libreria delle risorse del progetto in LCS dalle app Finance and Operations e da RCS verrà disattivata. Tuttavia, sarai comunque in grado di utilizzare il browser in LCS per caricare le configurazioni nella libreria di risorse del progetto. Pertanto, potrai sempre aggiungere configurazioni a LCS in modo che possano essere incluse nei pacchetti della soluzione.
- L'importazione di configurazioni da LCS continuerà ad essere disponibile e supportata nelle app Finance and Operations e in RCS per qualche tempo. In futuro, però, questa funzionalità verrà deprecata (la data esatta della deprecazione sarà annunciata in seguito).

## <a name="deprecation-notice"></a>Avviso di deprecazione

La deprecazione dell'uso di LCS come spazio di archiviazione è stata comunicata in [Funzionalità rimosse o deprecate in Dynamics 365 Finance - Avviso di deprecazione di LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). La data di deprecazione prevista è il 1° aprile 2022.

## <a name="key-features"></a>Funzionalità principali

- Puoi usare RCS per creare e modificare le configurazioni. Ciò significa che potrai inviare tali configurazioni direttamente dalla soluzione di progettazione a un'applicazione connessa. Pertanto, potrai modificare e testare rapidamente le tue configurazioni.
- Il repository globale è l'archiviazione centralizzata per tutte le configurazioni ER.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Guida per azioni una tantum e continuative

Questa sezione descrive una serie di passaggi che devono essere completati una volta. Illustra inoltre i passaggi che devono essere completati su base continuativa in seguito.

### <a name="one-time-action"></a>Azione una tantum

Importa tutte le configurazioni richieste da LCS a RCS, quindi pubblicale da RCS al repository globale. Se utilizzi librerie di risorse specifiche del progetto per archiviare configurazioni derivate in LCS, dovrai completare i seguenti passaggi mentre LCS è ancora accessibile.

1. Se un'istanza RCS non è già disponibile, esegui il provisioning di un'istanza. Per maggiori informazioni, vedi [Panoramica di RCS](rcs-overview.md).
2. Nell'istanza RCS di cui hai eseguito il provisioning, per ogni progetto LCS nella libreria delle risorse che include configurazioni ER derivate, registra il repository LCS appropriato.
3. Importa le configurazioni ER dai repository LCS a RCS. Per ulteriori informazioni, vedi [Importare configurazioni da LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Se il repository globale non viene fornito automaticamente, registralo in RCS.
5. Carica tutte le configurazioni derivate dall'istanza RCS corrente nel repository globale. Usa la funzione **Pacchetti di configurazione che consentono all'utente di caricare tutte le configurazioni in GR in un'unica operazione** per semplificare il caricamento. Per ulteriori informazioni, vedi [Caricamento del repository globale RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>Operazioni successive

Usa le soluzioni di progettazione visiva di RCS per creare tutte le nuove configurazioni. Quindi, carica le configurazioni nel repository globale per l'archiviazione. Per ulteriori informazioni, vedi [Creare la configurazione ER in RCS e caricarla nel repository globale](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Questa modifica significa che LCS non può essere utilizzato come spazio di archiviazione centrale per le configurazioni?

Sì. La funzionalità che ti consente di caricare le configurazioni nella libreria delle risorse del progetto in LCS dalle app Finance and Operations verrà deprecata. Tuttavia, sarai comunque in grado di utilizzare il browser in LCS per caricare le configurazioni nella libreria di risorse del progetto in funzione delle tue esigenze.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Pensavo che RCS fosse un repository sostitutivo per l'importazione di file modello globali. Non pensavo che fosse usato per archiviare le configurazioni. Quale delle due affermazioni è corretta?

RCS è un servizio di progettazione per la creazione e la modifica di configurazioni ER. RCS dispone di un proprio repository noto come repository globale. Questo repository permette di archiviare le configurazioni create in RCS. Dopo che l'utilizzo di LCS come spazio di archiviazione sarà deprecato, il repository globale sarà l'unica origine per le configurazioni Microsoft. Devi completare un'azione una tantum per importare tutte le configurazioni necessarie da LCS a RCS e quindi pubblicarle da RCS al repository globale.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Senza LCS, qual è il modo suggerito per archiviare le configurazioni in modo che le configurazioni di "test" e "produzione" possano essere facilmente gestite e trasferite?

RCS utilizza il concetto di *applicazione connessa*. Un'applicazione connessa stabilisce una connessione tra RCS e qualsiasi istanza delle app Finance and Operations. Poiché RCS può essere utilizzato per modificare le configurazioni, l'applicazione connessa può essere usata per inviare le configurazioni direttamente dal progettista agli ambienti delle app Finance and Operations. Pertanto, puoi modificare e testare rapidamente le tue configurazioni anziché dover passare attraverso l'archiviazione a livello di progetto LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Ci sono esempi che mostrano la configurazione e la gestione?

Non ci sono esempi, ma puoi completare i passaggi precedenti in questo argomento per migrare le tue configurazioni al repository globale RCS.
