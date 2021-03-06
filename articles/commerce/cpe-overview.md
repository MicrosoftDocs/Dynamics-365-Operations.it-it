---
title: Panoramica dell'ambiente di valutazione Dynamics 365 Commerce
description: In questo argomento viene fornita una panoramica dell'ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c890d7c49b6607ab0cbad536bbf8a3649465a7c1
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193494"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Panoramica dell'ambiente di valutazione Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

In questo argomento viene fornita una panoramica dell'ambiente di valutazione Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Gli ambienti di valutazione di Commerce non sono generalmente disponibili e sono concessi a partner e clienti in base alla richiesta. Per ulteriori informazioni, contattare il partner Microsoft.

L'ambiente di valutazione Commerce è un ambiente di anteprima completo facoltativo di Dynamics 365 Commerce che consente ai partner e ai potenziali clienti di provare il prodotto Commerce.

Gli ambienti di valutazione sono parzialmente preconfigurati per ridurre le fasi di post-provisioning necessarie.

A parte alcune limitazioni minori che non influiscono su caratteristiche o funzionalità, l'ambiente di valutazione Commerce offre l'esperienza Commerce completa e può essere utilizzato da clienti e partner di implementazione per valutare il prodotto, fornire feedback e fare analisi di corrispondenza/scarto.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>Limiti dell'ambiente di valutazione Commerce

Sebbene l'ambiente di valutazione Commerce fornisca il set completo di caratteristiche e funzionalità di Commerce, ci sono alcune limitazioni minori:

- Sebbene lo stesso ambiente di valutazione Commerce non abbia limiti geografici, il provisioning di componenti dell'ambiente, come Retail Cloud Scale Unit (RCSU) e le applicazioni di e-commerce, deve essere eseguito solo negli Stati Uniti.
- L'utilizzo dell'ambiente di valutazione Commerce ha un limite di 30 giorni dalla data dell'effettuazione del provisioning di e-Commerce.
- L'ambiente di valutazione Commerce può essere distribuito e inizializzato correttamente solo in un ambiente che utilizza la topologia dimostrativa, in cui tutti i componenti di un ambiente sono distribuiti su una singola macchina virtuale (VM) ospitata sul cloud Il limite principale di questa topologia è il numero di utenti simultanei che può supportare l'ambiente.

## <a name="get-started"></a>Per iniziare

Per effettuare il provisioning dell'ambiente di valutazione Commerce, consultare [Provisioning di un ambiente di valutazione Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Provisioning di un ambiente di valutazione Dynamics 365 Commerce](provisioning-guide.md)

[Configurare un ambiente di valutazione Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce](cpe-bopis.md)

[Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce](cpe-optional-features.md)

[Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
