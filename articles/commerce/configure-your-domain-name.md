---
title: Configurare il proprio nome di dominio
description: In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8b7bc322b1a42190d5eec99f89a34025c34ba09f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220488"
---
# <a name="configure-your-domain-name"></a>Configurare il proprio nome di dominio


[!include [banner](includes/banner.md)]

In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365. 

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