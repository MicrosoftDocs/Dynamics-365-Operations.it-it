---
title: Distribuire un nuovo tenant di e-commerce
description: In questo articolo viene descritto come distribuire un nuovo sito di e-commerce Dynamics 365 Commerce utilizzando Microsoft Dynamics Lifecycle Services.
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7aee33a6322ada6de142ecf5b70ba81213ffb085
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884006"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Distribuire un nuovo tenant di e-commerce

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come distribuire un nuovo sito di e-commerce Dynamics 365 Commerce utilizzando Microsoft Dynamics Lifecycle Services.

Microsoft Dynamics Lifecycle Services (LCS) è un'area di lavoro collaborativa basata su cloud che i partner e i clienti possono utilizzare per gestire progetti e ambienti, visualizzare le informazioni più recenti su prodotti e funzionalità di Microsoft Dynamics nonché per creare, tenere traccia ed esaminare richieste di supporto. Le funzionalità di gestione di e-commerce sono integrate in LCS.

Per ulteriori informazioni su LCS, vedere [Manuale dell'utente di Lifecycle Services](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Attività iniziali

Prima di inizializzare e-commerce, è necessario inizializzare un progetto, un ambiente e Retail Cloud Scale Unit (RCSU). Per eseguire l'inizializzazione in LCS, è necessario disporre delle autorizzazioni per il ruolo Proprietario progetto o Responsabile ambiente. Le topologie dell'ambiente di produzione e sandbox sono supportate.

Per ulteriori informazioni sugli ambienti, vedere [Pianificazione ambiente](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Per ulteriori informazioni su RCSU, vedere [Inizializzare Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Inizializzare e-commerce

Utilizzare questa procedura per inizializzare la funzionalità e-commerce in un ambiente esistente.

Prima di iniziare, verificare di disporre delle informazioni seguenti:

- L'unità RCSU che verrà utilizzata.
- Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per gli amministratori del sistema di e-commerce.
- Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per i moderatori di valutazioni e recensioni.
- I domini che verranno associati all'ambiente.

Inoltre, è possibile raccogliere le seguenti informazioni facoltative:

- informazioni business-to-consumer (B2C) di Azure AD:

    - Nome tenant
    - ID client
    - Dominio personalizzato per l'accesso
    - URL di risposta
    - ID criteri di iscrizione/accesso
    - ID criteri di reimpostazione password
    - ID criteri di modifica del profilo

> [!NOTE]
> Queste informazioni possono essere aggiunte successivamente, mediante una richiesta di assistenza.

Dopo aver raccolto le informazioni necessarie, attenersi alla procedura seguente per inizializzare e-commerce.

1. Accedere a [LCS](https://lcs.dynamics.com).
1. Aprire il progetto contenente l'ambiente in cui si desidera inizializzare e-commerce.
1. Nella sezione **Ambienti**, selezionare l'ambiente.
1. In **Funzionalità ambiente**, selezionare il collegamento **Gestione vendita al dettaglio**.
1. Nella scheda **e-Commerce**, selezionare **Imposta**. Viene visualizzata una finestra di dialogo, in cui è necessario immettere le informazioni richieste per il provisioning.
1. Immettere le informazioni necessarie e passare alla pagina successiva.
1. Nella pagina successiva, immettere le informazioni necessarie e inviare il modulo. Viene visualizzata di nuovo la scheda **e-Commerce**, che dovrebbe indicare l'avvio dell'inizializzazione.
1. Per visualizzare lo stato dell'inizializzazione, selezionare **Aggiorna** o ritornare in seguito alla scheda **e-Commerce**.
    
Quando e-commerce viene inizializzato da LCs, il sistema esegue il provisioning di vari componenti necessari per e-commerce e li associa all'ambiente. Al termine del provisioning, la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** viene aggiornata in base al provisioning. Nella pagina sono indicate le distribuzioni di personalizzazioni più recenti e lo stato di qualsiasi altra distribuzione in corso. Include inoltre collegamenti al sito di e-commerce e a Creazione di siti di Commerce dove i siti vengono creati.

## <a name="access-commerce-site-builder"></a>Accedere a Creazione di siti di Commerce

Per accedere a Creazione di siti di Commerce, selezionare la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** in LCS e selezionare il collegamento **Strumento di gestione del sito e-Commerce**. La pagina di destinazione di Creazione di siti Web visualizza una vista a livello di tenant. In questa pagina è possibile:

- Modificare le impostazioni a livello di tenant.
- Accedere a qualsiasi sito creato e disporre dell'autorizzazione per visualizzare. 
- Accedere alle funzionalità di verifica come Moderazione e Report.
- Creare un nuovo sito. Per ulteriori informazioni su come creare un nuovo sito, vedere [Creare un sito di e-commerce](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]