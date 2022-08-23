---
title: Servizi di globalizzazione di Dynamics 365
description: In questo articolo viene fornita una panoramica dei servizi di globalizzazione di Microsoft Dynamics 365.
author: kfend
ms.date: 04/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
ms.openlocfilehash: eebf74ab30a544f6561cf5782148d12b58d9c4b7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278234"
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
