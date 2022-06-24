---
title: Il messaggio e-mail di benvenuto non viene inviato quando vengono creati nuovi clienti
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili se non viene inviata una notifica e-mail di benvenuto quando viene creato un nuovo cliente in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 8e95b33d4b8a9af13c613ab89dd33de6b4934694
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853685"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>Il messaggio e-mail di benvenuto non viene inviato quando vengono creati nuovi clienti

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili se non viene inviata una notifica e-mail di benvenuto quando viene creato un nuovo cliente in Microsoft Dynamics 365 Commerce.

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
