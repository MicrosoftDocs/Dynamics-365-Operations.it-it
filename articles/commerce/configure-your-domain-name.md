---
title: Configurare il proprio nome di dominio
description: In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f73c034563fb1cc6b05091b4c47e2a788d1a8b6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945538"
---
# <a name="configure-your-domain-name"></a>Configurare il proprio nome di dominio

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Aggiungere domini durante l'inizializzazione di e-Commerce

Per associare domini all'ambiente di e-Commerce, inizializzare e-Commerce come descritto in [Distribuire un nuovo sito di e-Commerce](deploy-ecommerce-site.md). Durante l'inizializzazione, viene richiesto di immettere informazioni che verranno utilizzate per eseguire il provisioning dell'ambiente di e-Commerce. Nel campo **Nomi host supportati**, aggiungere tutti i domini che si prevede di utilizzare con questo ambiente. I domini devono essere separati con un punto e virgola. In questo modo, i domini vengono configurati in tutti i componenti di e-Commerce necessari e sono pronti per essere utilizzati quando si passa il traffico dalla rete per la distribuzione di contenuti (CDN) o dal server Web ai front-end di e-Commerce.

## <a name="add-domains-after-e-commerce-initialization"></a>Aggiungere domini dopo l'inizializzazione di e-Commerce

Per associare nuovi domini all'ambiente di e-Commerce dopo l'inizializzazione di e-Commerce, è necessario inviare una richiesta di assistenza.

## <a name="additional-resources"></a>Risorse aggiuntive

[Distribuire un nuovo sito di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito online a un canale](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)
