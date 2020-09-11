---
title: Scenari supportati per l'impostazione della doppia scrittura
description: Questo argomento descrive gli scenari supportati per l'impostazione della doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 275d24d8f32fd1d2d15356d14c5c6591e8503c65
ms.sourcegitcommit: ec4df354602c20f48f8581bfe5be0c04c66d2927
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "3706254"
---
# <a name="supported-scenarios-for-dual-write-setup"></a>Scenari supportati per l'impostazione della doppia scrittura

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

È possibile impostare una connessione di doppia scrittura tra un ambiente Finance and Operations e un ambiente Common Data Service.

+ Un **ambiente Finance and Operations** fornisce la piattaforma sottostante per le **app Finance and Operations** (ad esempio Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Retail).
+ Un **ambiente Common Data Service** fornisce la piattaforma sottostante per le **app basate su modello in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).

>[!IMPORTANT]
>Human Resources in Finance and Operations supporta le connessioni a doppia scrittura, al contrario dell'app Dynamics 365 Human Resources.

Il meccanismo di impostazione varia in base alla sottoscrizione e all'ambiente.

+ Per le nuove istanze di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia in Microsoft Dynamics Lifecycle Services (LCS). Se è disponibile una licenza per Microsoft Power Platform, si ottiene uno nuovo ambiente Common Data Service se il tenant ne è privo.
+ Per le istanze esistenti di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia nell'ambiente Finance and Operations.

Sono supportati gli scenari di impostazione che seguono:

+ [Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello](#new-new)
+ [Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente](#new-existing)
+ [Una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di app basata su modello](#new-demo-new)
+ [Una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di app basata su modello esistente](#new-demo-existing)
+ [Un'istanza di app Finance and Operations esistente e un'istanza di app basata su modello nuova o esistente](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a>Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e una nuova istanza di un'app basata su modello in Dynamics 365, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md). Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:

- Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.
- Viene eseguito il provisioning di una nuova istanza vuota di un'app basata su modello in cui è installata la soluzione principale CRM.
- Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.
- Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.

Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a>Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e un'istanza di un'app basata su modello esistente in Dynamics 365, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md). Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:

- Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.
- Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.
- Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.

Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.

Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.

1. Creare una nuova società nell'app Finance and Operations.
2. Aggiungere la società alla configurazione della connessione a doppia scrittura.
3. [Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere International Organization for Standardization (ISO).

Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a>Una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di app basata su modello

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di un'app basata su modello in Dynamics 365, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello](#new-new) precedente in questo argomento. Al termine della configurazione della connessione, se si desidera sincronizzare i dati dimostrativi con l'app basata su modello, attenersi alla seguente procedura.

1. Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a>Una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di app basata su modello esistente

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di un'app basata su modello esistente in Dynamics 365, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente](#new-existing) precedente in questo argomento. Al termine della configurazione della connessione, se si desidera sincronizzare i dati dimostrativi con l'app basata su modello, attenersi alla seguente procedura.

1. Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.

1. Creare una nuova società nell'app Finance and Operations.
2. Aggiungere la società alla configurazione della connessione a doppia scrittura.
3. [Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere ISO.

Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a>Un'istanza di app Finance and Operations esistente e un'istanza di app basata su modello nuova o esistente

L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e un'istanza nuova o esistente di un'app basata su modello in Dynamics 365 si verifica nell'ambiente Finance and Operation.

1. Impostare la connessione dall'app Finance and Operations.
2. Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, [avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice azienda ISO di tre lettere.

Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.
