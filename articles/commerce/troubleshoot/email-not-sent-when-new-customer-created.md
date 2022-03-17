---
title: Il messaggio e-mail di benvenuto non viene inviato quando vengono creati nuovi clienti
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili se non viene inviata una notifica e-mail di benvenuto quando viene creato un nuovo cliente in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 1a4faf6cd189f69232e7f9ab8d0e79b320cfe2d9
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349962"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>Il messaggio e-mail di benvenuto non viene inviato quando vengono creati nuovi clienti

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili se non viene inviata una notifica e-mail di benvenuto quando viene creato un nuovo cliente in Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Quando viene creato un nuovo cliente in Commerce Headquarters, al cliente non viene inviato un messaggio un'e-mail di benvenuto, anche se è configurata una notifica e-mail per il tipo di notifica e-mail **Cliente creato**.

## <a name="resolution"></a>Risoluzione

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>Impostare il valore ID e-mail corretto per il tipo di notifica e-mail creato dal cliente

Per impostare il valore **ID e-mail** coretto per il tipo di notifica e-mail **Creato dal cliente** in Headquarters, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.
1. Selezionare il profilo di notifica e-mail.
1. In **Impostazioni notifiche evento Retail**, per il tipo di notifica e-mail **Creato dal cliente**, impostare il campo **ID e-mail** su **NewCust**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un profilo di notifica tramite posta elettronica](../email-notification-profiles.md)
