---
title: Abilitare il rilevamento del punto vendita basato sull'ubicazione
description: In questo argomento viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 66ffe56f9d969c9d62ed4ff49f0848fab7e58a56
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096871"
---
# <a name="enable-location-based-store-detection"></a>Abilitare il rilevamento del punto vendita basato sull'ubicazione


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il rilevamento del punto vendita basato sull'ubicazione in Commerce consente di fornire contenuto del sito ai clienti, in base all'ubicazione. Quando il rilevamento del punto vendita basato sull'ubicazione è attivato il servizio di rendering di Commerce utilizza le informazioni sul paese dell'indirizzo IP del Web browser del cliente per indirizzare il cliente alla migliore configurazione geografica del sito che è disponibile.

## <a name="privacy-notice"></a>Informativa sulla privacy

Se si attiva la funzionalità di rilevamento del punto vendita basato sull'ubicazione, le informazioni del browser del cliente vengono inviate a un servizio di ubicazione di Microsoft. Queste informazioni vengono quindi utilizzate per fornire contenuto del cliente relativo alla sua ubicazione. Le informazioni inviate dal browser del cliente e le informazioni basate sull'ubicazione restituite al cliente sono soggette a criteri di conformità relativi a privacy e cookie.

## <a name="turn-on-location-based-store-detection"></a>Attivare il rilevamento del punto vendita basato sull'ubicazione

Per attivare il rilevamento del punto vendita basato sull'ubicazione in Commerce, procedere come descritto di seguito.

1. Nello strumento di creazione, accedere al sito.
1. Selezionare **Gestione sito** nel pannello di navigazione a sinistra.
1. Selezionare **Impostazioni sito**.
1. Impostare l'opzione **Abilita rilevamento del punto vendita basato sull'ubicazione** su **Attivato**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo sito di e-commerce](deploy-ecommerce-site.md)

[Impostare un canale punto vendita online](online-stores.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito online a un canale](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti di URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)
