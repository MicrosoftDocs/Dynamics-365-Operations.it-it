---
title: Abilitare il rilevamento del punto vendita basato sull'ubicazione
description: In questo articolo viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 38c93e30a606d818d909a4ec014009c18c25e8c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274342"
---
# <a name="enable-location-based-store-detection"></a>Abilitare il rilevamento del punto vendita basato sull'ubicazione

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.

Il rilevamento del punto vendita basato sull'ubicazione in Commerce consente di fornire contenuto del sito ai clienti, in base all'ubicazione. Quando il rilevamento del punto vendita basato sull'ubicazione è attivato il servizio di rendering di Commerce utilizza le informazioni sul paese dell'indirizzo IP del Web browser del cliente per indirizzare il cliente alla migliore configurazione geografica del sito che è disponibile.

## <a name="privacy-notice"></a>Informativa sulla privacy

Se si attiva la funzionalità di rilevamento del punto vendita basato sull'ubicazione, le informazioni del browser del cliente vengono inviate a un servizio di ubicazione di Microsoft. Queste informazioni vengono quindi utilizzate per fornire contenuto del cliente relativo all'ubicazione dello stesso. Le informazioni inviate dal browser del cliente e le informazioni basate sull'ubicazione restituite al cliente sono soggette a criteri di conformità relativi a privacy e cookie.

## <a name="turn-on-location-based-store-detection"></a>Attivare il rilevamento del punto vendita basato sull'ubicazione

Per attivare il rilevamento del punto vendita basato sull'ubicazione in Commerce, procedere come descritto di seguito.

1. Nello strumento di creazione, accedere al sito.
1. Selezionare **Gestione sito** nel pannello di navigazione a sinistra.
1. Selezionare **Impostazioni sito**.
1. Impostare l'opzione **Abilita rilevamento del punto vendita basato sull'ubicazione** su **Attivato**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
