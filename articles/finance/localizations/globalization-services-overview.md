---
title: Servizi di globalizzazione di Dynamics 365
description: In questo argomento viene fornita una panoramica dei servizi di globalizzazione di Microsoft Dynamics 365.
author: JaneA07
manager: AnnBe
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8c6f3b7fb4dec0dffe55014e9e2d60620dc3b193
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893050"
---
# <a name="dynamics-365-globalization-services"></a>Servizi di globalizzazione di Dynamics 365

[!include [banner](../includes/banner.md)]

I seguenti servizi di globalizzazione possono essere configurati per estendere le funzionalità esistenti in alcuni servizi di Microsoft Dynamics 365 Online:

- **Regulatory Configuration Service (RCS)** supporta la configurazione di diversi tipi di report e documenti elettronici. RCS fornisce una versione avanzata del designer Creazione di report elettronici (ER) in cui il repository di configurazione è un servizio autonomo. Per ulteriori informazioni, vedere [Regulatory Configuration Service](rcs-overview.md).
- **Fatturazione elettronica** raggruppa formati configurabili per trasformazioni, firme digitali e integrazioni configurabili per la connettività con servizi Web esterni, inclusa la certificazione e la gestione delle risposte. Per ulteriori informazioni, vedere [Fatturazione elettronica](e-invoicing-service-overview.md).
- **Calcolo imposte** fornisce una maggiore flessibilità supportando più ID fiscali, determinazione del codice fiscale, designer del calcolo delle imposte e un motore di runtime per conformarsi a normative fiscali complesse in tutto il mondo. Per ulteriori informazioni, vedere [Calcolo imposte](global-tax-calcuation-service-overview.md).

Questi servizi di globalizzazione forniscono un'integrazione immediata con i seguenti servizi online di Dynamics 365.

| Servizio online | RCS | Fatturazione elettronica | Calcolo imposte (anteprima) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | Sì | Sì | Sì | 
| Dynamics 365 Supply Chain Management | Sì | Sì | Sì | 
| Dynamics 365 Project Operations | Sì | Sì | Non applicabile | 
| Dynamics 365 Commerce | Sì | Non applicabile | Non applicabile | 

> [!NOTE]
> A causa delle differenze nella disponibilità delle posizioni geografiche di Azure (aree geografiche) per RCS, la configurazione di questo servizio potrebbe causare il trasferimento dei dati del cliente al di fuori dell'area geografica selezionata per il servizio online Dynamics 365 applicabile. Per ulteriori informazioni, vedere [Dynamics 365 e Power Platform: disponibilità, posizione dei dati, lingua e localizzazione](https://aka.ms/rcs/D365Productavailabilityguide).