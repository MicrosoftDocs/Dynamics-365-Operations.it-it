---
title: Iscriversi al servizio di fatturazione elettronica e installarlo
description: Questo argomento fornisce informazioni su come configurare e installare il servizio Fatturazione elettronica.
author: dkalyuzh
ms.date: 02/07/2022
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
ms.openlocfilehash: 4ab16652e4a50dd71a5d0b2b49b4dd79e327f7a8
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371642"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>Iscriversi al servizio di fatturazione elettronica e installarlo

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni su come configurare e installare il servizio Fatturazione elettronica. Ci sono quattro passaggi per questo processo. I passaggi da 1 a 3 sono obbligatori e il passaggio 4 è facoltativo.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>Passaggio 1: iscriviti a Regulatory Configuration Service

Regulatory Configuration Services (RCS) fornisce l'esperienza di configurazione e progettazione utilizzata per configurare Fatturazione elettronica. Le risorse quali ambienti e funzionalità di fatturazione elettronica vengono create e gestite in RCS. Quando le risorse sono pronte, vengono pubblicate nel servizio Fatturazione elettronica.

Per altre informazioni su RCS, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).

Per iscriverti a RCS, vai alla pagina [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>Passaggio 2: installa il componente aggiuntivo per microservizi in Microsoft Dynamics Lifecycle Services

Il servizio di fatturazione elettronica è un insieme di microservizi ospitato nei data center Microsoft. Per impostazione predefinita, i clienti di Dynamics 365 Finance e Dynamics 365 Supply Chain Management non hanno accesso al servizio di fatturazione elettronica. Devi installarlo come componente aggiuntivo in Microsoft Dynamics Lifecycle Services (LCS). Quando installi il componente aggiuntivo, il tuo ambiente Finance o Supply Chain Management viene registrato nel registro delle applicazioni che possono connettersi al servizio di fatturazione elettronica.

Per completare questo passaggio, vedi [Installare il componente aggiuntivo per microservizi in Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>Passaggio 3: configura RCS

Devi configurare l'integrazione RCS e il servizio di fatturazione elettronica. È inoltre necessario configurare i componenti principali.

Per completare questo passaggio, vedi [Configurare Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md).

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>Passaggio 4: riferimento per l'amministratore del plug-in Microsoft Power Platform

Alcuni scenari richiedono l'integrazione con Dataverse nell'ambito di Microsoft Power Platform.

Attualmente, questa configurazione è obbligatoria se utilizzerai soluzioni di fatturazione elettronica per scenari di fatturazione elettronica indonesiani. Tuttavia, è facoltativo per gli scenari di fatturazione elettronica dell'Arabia Saudita. Per ulteriori informazioni, vedi [Disponibilità delle funzionalità di fatturazione elettronica per paese o area geografica](e-invoicing-country-specific-availability.md).

Per completare questo passaggio, vedi [Riferimento dell'amministratore del plug-in Microsoft Power Platform](e-invoicing-power-platform-plug-in.md).
