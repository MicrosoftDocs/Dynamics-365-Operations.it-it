---
title: Configurare il proprio nome di dominio
description: In questo articolo viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365.
author: josaw1
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 298ce84008e60cc82a494320b6a41f35338508c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278626"
---
# <a name="configure-your-domain-name"></a>Configurare il proprio nome di dominio


[!include [banner](includes/banner.md)]

In questo articolo viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Aggiungere domini durante l'inizializzazione di e-commerce

Per associare domini all'ambiente di e-commerce Dynamics 365 Commerce, inizializzare e-commerce come descritto in [Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md). Durante l'inizializzazione, viene richiesto di immettere informazioni che verranno utilizzate per eseguire il provisioning dell'ambiente di e-commerce. Nel campo **Nomi host supportati**, aggiungere tutti i domini che si prevede di utilizzare con questo ambiente. I domini devono essere separati con un punto e virgola. In questo modo, i domini vengono configurati in tutti i componenti di Commerce necessari e sono pronti per essere utilizzati quando si passa il traffico dalla rete per la distribuzione di contenuti (CDN) o dal server Web ai front-end di e-commerce.

## <a name="add-domains-after-e-commerce-initialization"></a>Aggiungere domini dopo l'inizializzazione di e-commerce

Per associare nuovi domini all'ambiente di e-commerce dopo l'inizializzazione di e-commerce, è necessario inviare una richiesta di assistenza.

## <a name="additional-resources"></a>Risorse aggiuntive

[Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

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
