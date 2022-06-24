---
title: Provare unità di scala in una topologia ibrida distribuita
description: Questo articolo fornisce informazioni su come provare le unità di scala nel cloud e nella rete perimetrale per i carichi di lavoro di gestione della produzione e del magazzino.
author: perlynne
ms.date: 05/02/2022
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-03-03
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 5645955109e7a942e617b3b90a27065c2a8fe4a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893586"
---
# <a name="try-out-scale-units-in-a-distributed-hybrid-topology"></a>Provare unità di scala in una topologia ibrida distribuita

[!include [banner](../includes/banner.md)]

Il processo di sperimentazione della topologia ibrida distribuita è semplice. Durante la prima fase, è consigliabile convalidare le personalizzazioni per assicurarsi che funzionino nella topologia distribuita. Sono disponibili due opzioni.

## <a name="option-1-evaluate-customizations-in-development-environments"></a>Opzione 1: valutare le personalizzazioni in ambienti di sviluppo

Prima di iniziare a eseguire l'onboarding degli ambienti sandbox, è consigliabile esplorare le unità di scala in una configurazione di sviluppo, come un ambiente one-box (noto anche come ambiente di livello 1), in modo da poter convalidare processi, personalizzazioni e soluzioni. Durante questa fase, i dati e le personalizzazioni verranno applicati agli ambienti one-box. È possibile eseguire in un unico ambiente, che può assumere il ruolo sia dell'hub aziendale che dell'unità di scalabilità. In alternativa, è possibile disporre di due ambienti di sviluppo, uno dei quali assume il ruolo di hub e l'altro il ruolo di unità di scala. Questa configurazione fornisce il modo migliore per identificare e risolvere i problemi. L'ultima [build di anteprima](../../fin-ops-core/fin-ops/get-started/one-version.md#how-can-i-get-early-access-to-non-released-platform-updates) può anche essere utilizzata per completare questa fase.

È consigliabile usare gli [strumenti di distribuzione delle unità di scala per ambienti di sviluppo one-box](https://github.com/microsoft/SCMScaleUnitDevTools) per installare e mantenere gli ambienti. Questi strumenti consentono di configurare hub e unità di scala in uno o due ambienti one-box. Gli strumenti sono forniti come versione binaria e nel codice sorgente su GitHub. Esaminare il wiki del progetto, che include una [guida d'uso dettagliata](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) che descrive come vengono utilizzati gli strumenti. Se stai [distribuendo unità di scala perimetrali su hardware personalizzato utilizzando i dati aziendali locali (LBD)](cloud-edge-edge-scale-units-lbd.md), devi seguire una procedura diversa.

## <a name="option-2-acquire-add-ins-and-deploy-in-your-sandbox-environments"></a>Opzione 2: acquisire componenti aggiuntivi ed eseguire la distribuzione in ambienti sandbox

Per provare la topologia ibrida distribuita, è necessario disporre di due ambienti sandbox (livello 2), uno dei quali contiene i dati (hub aziendale) e l'altro è per l'unità di scala e dispone di "dati vuoti".

È necessario acquisire componenti aggiuntivi per almeno un'unità cloud o edge scale. Saranno quindi concessi gli slot corrispondenti per il progetto e l'ambiente in [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), in modo che gli ambienti delle unità di scala possano essere distribuiti utilizzando il [portale Scale Unit Manager](https://aka.ms/SCMSUM).

Contatta il supporto tecnico Microsoft per richiedere l'abilitazione degli ambienti sandbox.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
