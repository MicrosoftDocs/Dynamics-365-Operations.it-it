---
title: Dynamics 365 Finance, Supply Chain Management e Commerce in US Government Community Cloud (GCC)
description: Questo articolo fornisce informazioni sui prodotti Microsoft Dynamics 365 US Government disponibili per enti pubblici e privati qualificati.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 90e64fec512307af209ace128d5897475de7aee5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867275"
---
# <a name="dynamics-365-finance-supply-chain-management-and-commerce-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance, Supply Chain Management e Commerce in US Government Community Cloud (GCC)

[!include [banner](../includes/banner.md)]



Seleziona i prodotti Microsoft Dynamics 365 US Government (US) disponibili per enti pubblici e privati qualificati. Tali entità sono limitate ai seguenti tipi:

- enti del governo federale, statale, locale, tribale e territoriale degli Stati Uniti
- Enti privati che utilizzano Dynamics 365 US Government per fornire soluzioni a enti governativi o a membri qualificati della comunità cloud
- Enti privati che dispongono di dati dei clienti soggetti a normative governative e Dynamics 365 US Government è il servizio appropriato per soddisfare i requisiti normativi

Per informazioni, vedi [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Inserimento

Per completare l'onboarding iniziale per un progetto di implementazione in Microsoft Dynamics Lifecycle Services (LCS), segui le istruzioni in [Onboarding di un progetto di implementazione](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Tuttavia, non utilizzare il collegamento a LCS pubblico fornito in tali istruzioni. Utilizza invece il seguente URL per aprire LCS per US Government Community Cloud (GCC): <https://gov.lcs.microsoftdynamics.us>.

Dopo aver completato l'onboarding iniziale, segui le istruzioni in [Onboarding del progetto](../lifecycle-services/project-onboarding.md). Ancora una volta, usa [LCS per GCC](https://gov.lcs.microsoftdynamics.us) invece di LCS pubblico.

## <a name="environment-deployment"></a>Distribuzione dell'ambiente

Dopo aver completato l'onboarding del progetto, puoi esaminare le funzionalità aggiuntive di LCS descritte in [Lifecycle Services (LCS) per i clienti di app per finanza e operazioni](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). Quindi passa alla distribuzione dell'ambiente.

- Per distribuire ambienti gestiti da Microsoft tramite LCS, segui le istruzioni in [Lifecycle Services (LCS) per i clienti di app per finanza e operazioni](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- Per gli ambienti ospitati su cloud, vedi [Distribuire e accedere agli ambienti di sviluppo](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md). È inoltre necessario completare il processo di onboarding di Resource Manager per i connettori, come descritto in [Completare il processo di onboarding di Azure Resource Manager per i progetti Lifecycle Services del governo degli Stati Uniti](arm-onbarding-us-goverment.md).

> [!NOTE]
> Per i progetti LCS del governo degli Stati Uniti, sono supportate solo le sottoscrizioni di Azure specifiche per il governo degli Stati Uniti.

## <a name="features-that-arent-available"></a>Funzionalità non disponibili

Alcune funzionalità non saranno disponibili per la distribuzione in GCC o non saranno disponibili per l'uso con Dynamics 365 in GCC. Per esempio, i servizi Azure DevOps non saranno disponibili in GCC. Tuttavia, i servizi Azure DevOps locale o Azure DevOps pubblico possono essere utilizzati. Per informazioni dettagliate sulla disponibilità delle funzioni, vedi [Disponibilità delle funzionalità del governo degli Stati Uniti per applicazioni aziendali](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Dynamics 365 Finance e Dynamics 365 Supply Chain Management sono supportati in GCC-High?

N. Dynamics 365 Finance e Dynamics 365 Supply Chain Management sono supportati solo in GCC.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Posso usare Azure DevOps pubblico con Finance e Supply Chain Management in GCC?

Sì, puoi usare i servizi Azure DevOps pubblico se non sono necessari requisiti per una soluzione certificata dal Federal Risk and Authorization Management Program (FEDRAMP). In alternativa, puoi usare Azure DevOps Server.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Posso distribuire un ambiente di sviluppo Tier-1 dell'ambiente ospitato nel cloud in una sottoscrizione di Azure Commercial?

N. In [LCS per GCC](https://gov.lcs.microsoftdynamics.us), è necessario usare una sottoscrizione di Azure per enti pubblici per distribuire un ambiente ospitato nel cloud.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>Cosa posso fare se ho bisogno di un pacchetto dalla libreria di risorse condivise, ma non è disponibile in LCS per GCC?

Puoi scaricare lo stesso pacchetto dalla libreria delle risorse condivise in [LCS pubblico](https://lcs.dynamics.com). In alternativa, il tuo partner può aiutarti a scaricare il pacchetto.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>Lo strumento di aggiornamento del codice è disponibile in GCC?

No, lo strumento di aggiornamento del codice non è attualmente disponibile in GCC. Tuttavia, puoi creare un progetto prospect in [LCS pubblico](https://lcs.dynamics.com) e utilizzare lo strumento di aggiornamento del codice. Tieni presente che non sarai in grado di distribuire ambienti in progetti prospect.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>Il mio partner può aprire un ticket di supporto per mio conto?

Sì. Tuttavia, se il tuo partner utilizza un'identità non GCC, il ticket di supporto verrà indirizzato alla coda di supporto pubblico. Ti consigliamo di utilizzare l'autorizzazione GCC del cliente in LCS per aprire i ticket di supporto.

## <a name="see-also"></a>Vedere anche

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [Disponibilità delle funzionalità del governo degli Stati Uniti per applicazioni aziendali](https://aka.ms/BAPFunctionalParity).
- [Manuale dell'utente di Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Panoramica distribuzione cloud](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
