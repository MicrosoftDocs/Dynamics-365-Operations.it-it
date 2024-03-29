---
title: Panoramica del portale per i clienti per Dynamics 365 Supply Chain Management (video)
description: Questo articolo introduce il portale clienti e spiega chi dovrebbe usarlo e come funziona.
author: Henrikan
ms.date: 06/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7f34acd78966cc9f26242653e9d0d16fdf22e0b2
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103832"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Panoramica sul portale clienti per Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]


## <a name="what-is-the-customer-portal"></a>Cos'è il portale clienti?

I moderni sistemi Supply Chain si basano sull'integrazione. In questi sistemi le scorte, la domanda dei clienti e i reparti vendite devono essere integrati anziché risiedere in silo separati. Il portale clienti consente alle organizzazioni che eseguono Microsoft Dynamics 365 Supply Chain Management di migliorare questa integrazione e di informare più efficacemente i propri clienti.

Il portale clienti è un modello di [portali Power Apps](/powerapps/maker/portals/overview) che consente alle aziende di creare un sito Web business-to-business (B2B) rivolto verso l'esterno per scenari correlati all'elaborazione degli ordini cliente. Il modello utilizza la [doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), Supply Chain Management e i portali Power Apps per consentire ai clienti esterni di visualizzare e creare dati dall'ambiente Dynamics 365 dell'azienda.

Il modello di portale clienti include tutte le funzionalità di personalizzazione di cui dispongono i portali Power Apps. Il modello può essere facilmente modificato per rappresentare il marchio dell'azienda, aggiungere una maggiore funzionalità e cambiare l'esperienza dell'utente. Tutte le funzionalità predefinite offerte dal modello possono essere modificate a piacere.

> [!IMPORTANT]
> Di per sé, il modello non è stato creato per essere completamente funzionale. Serve solo come attivatore per i clienti che desiderano creare un sito Web rivolto verso l'esterno di modo che i clienti aziendali possano interagire con i dati di Supply Chain Management.

> [!NOTE]
> La documentazione sul portale clienti è rivolta ad amministratori, personalizzatori e integratori di sistema che configureranno il portale clienti per un'installazione di Supply Chain Management. Nella documentazione vengono utilizzati i termini _cliente_ e _utente_ per descrivere persone che sono clienti dell'organizzazione che esegue Supply Chain Management e che useranno il portale finale.

## <a name="video"></a>Video

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

Il video della [panoramica del modello del portale clienti in Dynamics 365 Supply Chain Management](https://youtu.be/nPrqoLuHfV8) (mostrato sopra) è incluso nella playlist delle [app per la finanza e le operazioni](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.

## <a name="who-should-use-it"></a>Chi dovrebbe usarlo?

Il portale clienti è progettato per le aziende che eseguono Supply Chain Management e presentano queste caratteristiche:

- Intendono creare un sito Web rivolto verso l'esterno che comunichi informazioni sull'elaborazione degli ordini (come informazioni sullo stato dell'ordine o sull'account) direttamente dal loro sistema Supply Chain Management ai clienti aziendali.
- Stanno passando da Dynamics AX 2012 a Supply Chain Management e in precedenza utilizzavano il [portale Self service clienti di AX 2012](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal).

I seguenti tipi di organizzazioni **non** sono buoni candidati per l'implementazione del portale clienti:

- Aziende che desiderano creare un sito Web per clienti non aziendali. Queste aziende dovrebbero prendere in considerazione la creazione di un [sito Web di e-commerce Dynamics 365 Commerce](../../commerce/create-ecommerce-site.md).
- Aziende che stanno già utilizzando un sito Web di portali Power Apps esistente per uno scopo simile. Queste aziende non riceveranno ulteriori vantaggi dall'utilizzo del portale clienti. Il portale clienti viene fornito come modello che funge da guida e punto di partenza per i clienti che desiderano "connettere" la doppia scrittura, Supply Chain Management e i portali Power Apps. Se si è già configurato un sito Web che serve a questo scopo, è possibile che non sia molto vantaggioso usare il modello di portale clienti per eseguire nuovamente il provisioning di quel sito Web.

## <a name="how-does-it-work"></a>Come funziona?

Il portale clienti viene fornito come modello di portali Power Apps. Dipende dai portali Power Apps e dalla doppia scrittura.

I [portali Power Apps](/powerapps/maker/portals/overview) sono una funzionalità che consente agli utenti di creare un sito Web rivolto verso l'esterno al quale possono accedere persone esterne all'organizzazione. È possibile creare portali con poco codice o senza codice. Il portale clienti è uno dei tanti [modelli di portale Dynamics 365](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365) messi a disposizione da Microsoft.

La [doppia scrittura](/powerapps/maker/portals/overview) è un prodotto di infrastruttura predefinito che fornisce interazione quasi in tempo reale tra le app di interazione con i clienti e le app per la finanza e le operazioni. La doppia scrittura fornisce un'integrazione bidirezionale tra le app per la finanza e le operazioni e Microsoft Dataverse. Di conseguenza, offre un'esperienza utente integrata nelle app. Il portale clienti dipende da tabelle sincronizzate con la doppia scrittura. Affinché i dati di Supply Chain Management siano visualizzati nel portale clienti, è necessario abilitare la doppia scrittura per tutte le tabelle appropriate.

![Dipendenze del portale clienti.](media/customer-portal-elements.png "Dipendenze del portale clienti")

Il portale clienti funge da punto di partenza per le organizzazioni che desiderano utilizzare i portali Power Apps per creare un sito Web rivolto verso l'esterno che utilizza i dati dell'installazione di Supply Chain Management. Consente alle organizzazioni di connettere la doppia scrittura, Supply Chain Management e i portali Power Apps.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
