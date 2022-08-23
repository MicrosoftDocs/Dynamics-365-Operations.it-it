---
title: Elaborazione dei documenti elettronici in entrata
description: In questo articolo viene fornita una panoramica dell'elaborazione per i documenti elettronici in entrata.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 554bc8fde3b2135eb878d885541c76ecd6d66493
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277303"
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
