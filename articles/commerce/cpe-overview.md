---
title: Panoramica dell'ambiente di anteprima Commerce
description: In questo argomento viene fornita una panoramica dell'ambiente di anteprima Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
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
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906072"
---
# <a name="commerce-preview-environment-overview"></a>Panoramica dell'ambiente di anteprima Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene fornita una panoramica dell'ambiente di anteprima Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

L'ambiente di anteprima di Commerce è un ambiente di anteprima completo facoltativo di Dynamics 365 Commerce che consente ai potenziali clienti di provare il prodotto Commerce prima del rilascio generale al pubblico.

A parte alcune limitazioni minori che non influiscono su caratteristiche o funzionalità, l'ambiente di anteprima Commerce offre l'esperienza Commerce completa e può essere utilizzato da clienti e partner di implementazione per valutare il prodotto, fornire feedback e fare analisi di corrispondenza/scarto.

## <a name="limitations-of-the-commerce-preview-environment"></a>Limiti dell'ambiente di anteprima di Commerce

Sebbene l'ambiente di anteprima di Commerce fornisca il set completo di caratteristiche e funzionalità di Commerce, ci sono alcune limitazioni minori:

- Sebbene lo stesso ambiente di anteprima di Commerce non abbia limiti geografici, il provisioning di componenti dell'ambiente, come Retail Cloud Scale Unit (RCSU) e le applicazioni di e-commerce, può essere eseguito solo negli Stati Uniti.
- L'utilizzo dell'ambiente di anteprima di Commerce ha un limite di 30 giorni dalla data dell'effettuazione del provisioning di e-Commerce.
- L'ambiente di anteprima di Commerce può essere distribuito e inizializzato correttamente solo in un ambiente che utilizza la topologia dimostrativa, in cui tutti i componenti di un ambiente sono distribuiti in una singola macchina virtuale (VM). Il limite principale di questa topologia della macchina virtuale (VM) OneBox è il numero di utenti simultanei che può supportare l'ambiente di anteprima.
- L'ambiente di anteprima di Commerce può essere valutato solo fino alla disponibilità generale (GA) del prodotto Commerce. I nuovi ambienti dimostrativi saranno disponibili dopo la versione GA.

## <a name="get-started"></a>Inizia subito

Per effettuare il provisioning dell'ambiente di anteprima di Commerce, consultare [Provisioning di un ambiente di anteprima Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Provisioning di un ambiente di anteprima Commerce](provisioning-guide.md)

[Configurare un ambiente di anteprima Commerce](cpe-post-provisioning.md)

[Configurare le funzioni facoltative per un ambiente di anteprima Commerce](cpe-optional-features.md)

[Domande frequenti sull'ambiente di anteprima Commerce](cpe-faq.md)
