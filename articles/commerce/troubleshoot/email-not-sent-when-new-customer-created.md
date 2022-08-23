---
title: Il messaggio e-mail di benvenuto non viene inviato quando vengono creati nuovi clienti
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili se non viene inviata una notifica e-mail di benvenuto quando viene creato un nuovo cliente in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 5aa7d864555f96194500989e2d7ad200d8892121
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219406"
---
# <a name="welcome-email-isnt-sent-when-new-customers-are-created"></a>Il messaggio e-mail di benvenuto non viene inviato quando vengono creati nuovi clienti

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili se non viene inviata una notifica e-mail di benvenuto quando viene creato un nuovo cliente in Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Quando viene creato un nuovo cliente in Commerce Headquarters, al cliente non viene inviata una notifica e-mail di benvenuto, anche se è configurata una notifica e-mail per il tipo di notifica e-mail **Cliente creato**.

## <a name="resolution"></a>Risoluzione

### <a name="associate-an-email-notification-profile-under-commerce-parameters"></a>Associare un profilo di notifica tramite posta elettronica in Parametri di Commerce

1. In headquarters, vai a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di Commerce \> Generale**.
2. Nell'elenco a discesa **Profilo di notifica tramite posta elettronica**, seleziona il profilo di notifica tramite posta elettronica che contiene un mapping tra il tipo di notifica cliente creato e un modello di posta elettronica cliente creato.  

> [!NOTE] 
> Quando abiliti le notifiche cliente creato, i clienti creati in tutti i canali nella persona giuridica riceveranno un'e-mail cliente creato. Attualmente, le notifiche cliente creato non possono essere limitate a un singolo canale.

Per ulteriori informazion vedi [Creare modelli e-mail per eventi transazionali](../email-templates-transactions.md). 

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un profilo di notifica tramite posta elettronica](../email-notification-profiles.md)
