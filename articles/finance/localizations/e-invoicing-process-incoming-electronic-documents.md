---
title: Elaborazione dei documenti elettronici in entrata
description: In questo articolo viene fornita una panoramica dell'elaborazione per i documenti elettronici in entrata.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: dec4c16c8ba9f0ba55f30f3944eff172cf9db724
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910010"
---
# <a name="processing-of-incoming-electronic-documents"></a>Elaborazione dei documenti elettronici in entrata

[!include [banner](../includes/banner.md)]

I documenti elettronici in entrata, come le fatture elettroniche dei fornitori, possono essere importati ed elaborati in due modi:

- I file vengono recuperati da canali esterni e passati direttamente all'applicazione connessa. Lì subiscono un'ulteriore trasformazione e vengono quindi importati nel database.
- I file vengono sottoposti a preelaborazione nel servizio di fatturazione elettronica e vengono quindi trasferiti all'applicazione collegata.

La fatturazione elettronica supporta due canali per i documenti in entrata: e-mail e cartelle Microsoft SharePoint.

Esistono due tipi di configurazione per specificare se i documenti devono essere sottoposti a preelaborazione o passati direttamente all'applicazione connessa:

- **Canale dati** – Il sistema passerà il documento direttamente all'applicazione connessa.
- **Canale dati con pipeline di elaborazione** – È possibile configurare azioni aggiuntive che verranno eseguite prima che il documento venga passato all'applicazione connessa.

Per informazioni su come configurare gli scenari per l'elaborazione dei documenti elettronici in entrata per i diversi canali, vedi [Configurare un canale di posta elettronica](e-invoicing-configure-email.md) e[ Configurare un canale SharePoint](e-invoicing-configure-sharepoint-channel.md).
