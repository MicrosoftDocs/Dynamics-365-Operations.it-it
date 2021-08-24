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
ms.openlocfilehash: 1e69aa3cb81dceb7af4cd15536164ac40d234e5fbc7f661612bc84dbb0983837
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712768"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento fornisce risposte alle domande frequenti sull'ambiente di valutazione Microsoft Dynamics 365 Commerce.

**Possiamo usare l'ambiente di valutazione Commerce come vetrina di e-commerce per i clienti che attualmente implementano Retail?**

N. L'ambiente di valutazione Commerce è solo per scopi di valutazione. Se è necessario un ambiente per un cliente che implementa Retail, contattare Microsoft.

**È possibile utilizzare l'ambiente di valutazione Commerce per eseguire il provisioning delle funzionalità di e-commerce su un'applicazione/ambiente esistente che implementa Retail?**

No (nella maggior parte dei casi). I componenti di valutazione di Commerce sono disponibili solo per gli ambienti che corrispondono alle configurazioni specificate nei prerequisiti e nella guida di provisioning. Inoltre, i dati demo di base necessari non saranno disponibili negli ambienti distribuiti con una versione iniziale precedente alla versione 10.0.8. 

**Quali sono i costi associati alla distribuzione dell'ambiente di valutazione Commerce su Microsoft Azure mediante Microsoft Dynamics Lifecycle Services (LCS)?**

Un ambiente di dimostrazione di Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce Headquarters (macchina virtuale \[VM\]) sarà ospitato nella sottoscrizione Azure. Puoi usare il [Calcolatore prezzi di Azure ](https://azure.microsoft.com/pricing/calculator/) per stimare questo costo.

Altri componenti come Commerce Scale Unit, Creazione di siti Web di Commerce e il proprio sito di e-Commerce saranno disponibili come software come un servizio (SaaS) e ospitati da Microsoft.

**Quali aree geografiche di Azure sono attualmente supportate per l'ambiente di valutazione Commerce?**

L'ambiente di valutazione Commerce può essere distribuito solo nell'area geografica del Nord America.

**Esiste un disco rigido virtuale scaricabile (VHD) con l'opzione completa della macchina virtuale (VM) OneBox?**

Dynamics 365 Commerce ed Commerce Scale Unit sono totalmente SaaS (software as a service, software come un servizio) e devono essere ospitati sul cloud.

**Per quanto tempo può essere utilizzato l'ambiente di valutazione Commerce?**

L'ambiente di valutazione Commerce ha un limite di tempo di 30 giorni dalla data in cui viene eseguito il provisioning dei componenti SaaS come Commerce Scale Unit, Creazione di siti Web di Commerce e il proprio sito di e-Commerce.

**Posso estendere il limite di tempo per il mio ambiente di valutazione Commerce?**

L'estensione del limite di tempo è un'eccezione alla norma e viene considerata caso per caso. Per assistenza, contattare il partner Microsoft.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'ambiente di valutazione Dynamics 365 Commerce](cpe-overview.md)

[Provisioning di un ambiente di valutazione Dynamics 365 Commerce](provisioning-guide.md)

[Configurare un ambiente di valutazione Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce](cpe-bopis.md)

[Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]