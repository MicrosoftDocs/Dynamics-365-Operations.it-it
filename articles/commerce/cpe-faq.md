---
title: Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento fornisce risposte alle domande frequenti sull'ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e8a3e760353b351d42aff82c0d372d2aca350cd2
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343560"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento fornisce risposte alle domande frequenti sull'ambiente di valutazione Microsoft Dynamics 365 Commerce.

## <a name="can-we-use-the-commerce-evaluation-environment-as-an-e-commerce-storefront-for-customers-that-currently-implement-retail"></a>Possiamo usare l'ambiente di valutazione Commerce come vetrina di e-commerce per i clienti che attualmente implementano Retail?

N. L'ambiente di valutazione Commerce è solo per scopi di valutazione. Se è necessario un ambiente per un cliente che implementa Retail, contattare Microsoft.

## <a name="can-the-commerce-evaluation-environment-be-used-to-provision-the-e-commerce-features-on-top-of-an-existing-applicationenvironment-that-implements-retail"></a>È possibile utilizzare l'ambiente di valutazione Commerce per eseguire il provisioning delle funzionalità di e-commerce su un'applicazione/ambiente esistente che implementa Retail?

No (nella maggior parte dei casi). I componenti di valutazione di Commerce sono disponibili solo per gli ambienti che corrispondono alle configurazioni specificate nei prerequisiti e nella guida di provisioning. Inoltre, i dati demo di base necessari non saranno disponibili negli ambienti distribuiti con una versione iniziale precedente alla versione 10.0.8. 

## <a name="what-costs-are-involved-in-deploying-the-commerce-evaluation-environment-on-microsoft-azure-via-microsoft-dynamics-lifecycle-services-lcs"></a>Quali sono i costi associati alla distribuzione dell'ambiente di valutazione Commerce su Microsoft Azure mediante Microsoft Dynamics Lifecycle Services (LCS)?

Un ambiente di dimostrazione di Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce Headquarters (macchina virtuale \[VM\]) sarà ospitato nella sottoscrizione Azure. Puoi usare il [Calcolatore prezzi di Azure ](https://azure.microsoft.com/pricing/calculator/) per stimare questo costo.

Altri componenti come Commerce Scale Unit, Creazione di siti Web di Commerce e il proprio sito di e-Commerce saranno disponibili come software come un servizio (SaaS) e ospitati da Microsoft.

## <a name="which-azure-geographies-are-currently-supported-for-the-commerce-evaluation-environment"></a>Quali aree geografiche di Azure sono attualmente supportate per l'ambiente di valutazione Commerce?

L'ambiente di valutazione Commerce può essere distribuito solo nell'area geografica del Nord America.

## <a name="is-there-a-downloadable-virtual-hard-disk-vhd-that-has-the-complete-onebox-virtual-machine-vm-option"></a>Esiste un disco rigido virtuale scaricabile (VHD) con l'opzione completa della macchina virtuale (VM) OneBox?

Dynamics 365 Commerce ed Commerce Scale Unit sono totalmente SaaS (software as a service, software come un servizio) e devono essere ospitati sul cloud.

## <a name="how-long-can-the-commerce-evaluation-environment-be-used"></a>Per quanto tempo può essere utilizzato l'ambiente di valutazione Commerce?

L'ambiente di valutazione Commerce ha un limite di tempo di 30 giorni dalla data in cui viene eseguito il provisioning dei componenti SaaS come Commerce Scale Unit, Creazione di siti Web di Commerce e il proprio sito di e-Commerce.

## <a name="can-i-extend-the-time-limit-for-my-commerce-evaluation-environment"></a>Posso estendere il limite di tempo per il mio ambiente di valutazione Commerce?

L'estensione del limite di tempo è un'eccezione alla norma e viene considerata caso per caso. Per assistenza, contattare il partner Microsoft.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'ambiente di valutazione Dynamics 365 Commerce](cpe-overview.md)

[Provisioning di un ambiente di valutazione Dynamics 365 Commerce](provisioning-guide.md)

[Configurare un ambiente di valutazione Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce](cpe-bopis.md)

[Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
