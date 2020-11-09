---
title: Linee guida su come impostare la doppia scrittura
description: Questo argomento descrive gli scenari supportati per l'impostazione della doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 2d77a1458f3f4c79b231e6a6d7cc320b8ee1fad9
ms.sourcegitcommit: ee643d651d57560bccae2f99238faa39881f5c64
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088508"
---
# <a name="guidance-for-how-to-set-up-dual-write"></a>Linee guida su come impostare la doppia scrittura

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

È possibile impostare una connessione di doppia scrittura tra un ambiente Finance and Operations e un ambiente Common Data Service.

+ Un **ambiente Finance and Operations** fornisce la piattaforma sottostante per le **app Finance and Operations** (ad esempio Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Retail).
+ Un **ambiente Common Data Service** fornisce la piattaforma sottostante per le **app Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).

>[!IMPORTANT]
>Human Resources in Finance and Operations supporta le connessioni a doppia scrittura, al contrario dell'app Dynamics 365 Human Resources.

Il meccanismo di impostazione varia in base alla sottoscrizione e all'ambiente.

+ Per le nuove istanze di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia in Microsoft Dynamics Lifecycle Services (LCS). Se è disponibile una licenza per Power Platform, si ottiene uno nuovo ambiente Common Data Service se il tenant ne è privo.
+ Per le istanze esistenti di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia nell'ambiente Finance and Operations.

Prima di avviare la doppia scrittura su un'entità, è possibile eseguire una sincronizzazione iniziale per gestire i dati esistenti su entrambi i lati delle app Finance and Operations e delle app Customer Engagement. È possibile saltare la sincronizzazione iniziale se non è necessario sincronizzare i dati tra i due ambienti.

Una sincronizzazione iniziale consente di copiare i dati esistenti da un'app all'altra in modo bidirezionale. Esistono diversi scenari di configurazione a seconda degli ambienti già presenti e del tipo di dati presenti negli ambienti.

Sono supportati gli scenari di impostazione che seguono:

+ [Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement](#new-new)
+ [Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement](#new-existing)
+ [Una nuova istanza di app Finance and Operations con dati e una nuova istanza di app Customer Engagement](#new-data-new)
+ [Una nuova istanza di app Finance and Operations con dati e un'istanza di app Customer Engagement esistente](#new-data-existing)
+ [Un'istanza esistente di app Finance and Operations e una nuova istanza di app Customer Engagement](#existing-new)
+ [Un'istanza esistente di app Finance and Operations e un'istanza esistente di app Customer Engagement](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e una nuova istanza di un'app Customer Engagement, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md). Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:

- Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.
- Viene eseguito il provisioning di una nuova istanza vuota di un'app Customer Engagement in cui è installata la soluzione principale CRM.
- Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.
- Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.

Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e un'istanza esistente di un'app Customer Engagement, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md). Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:

- Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.
- Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.
- Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.

Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.

Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.

1. Creare una nuova società nell'app Finance and Operations.
2. Aggiungere la società alla configurazione della connessione a doppia scrittura.
3. [Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere International Organization for Standardization (ISO).
4. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

Per un esempio e un approccio alternativo, vedere [Esempio](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Una nuova istanza di app Finance and Operations con dati e una nuova istanza di app Customer Engagement

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati e una nuova istanza di un'app Customer Engagement, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement](#new-new) precedente in questo argomento. Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.

1. Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

Per un esempio e un approccio alternativo, vedere [Esempio](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Una nuova istanza di app Finance and Operations con dati e un'istanza di app Customer Engagement esistente

Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati e un'istanza esistente di un'app Customer Engagement, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement](#new-existing) precedente in questo argomento. Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.

1. Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.

1. Creare una nuova società nell'app Finance and Operations.
2. Aggiungere la società alla configurazione della connessione a doppia scrittura.
3. [Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere ISO.
4. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

Per un esempio e un approccio alternativo, vedere [Esempio](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Un'istanza esistente di app Finance and Operations e una nuova istanza di app Customer Engagement

L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e una nuova istanza di un'app Customer Engagement si verifica nell'ambiente Finance and Operation.

1. [Impostare la connessione dall'app Finance and Operations](enable-dual-write.md).
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

Per un esempio e un approccio alternativo, vedere [Esempio](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Un'istanza esistente di app Finance and Operations e un'istanza esistente di app Customer Engagement

L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e un'istanza esistente di un'app Customer Engagement si verifica nell'ambiente Finance and Operation.

1. Impostare la connessione dall'app Finance and Operations.
2. Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, [avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice azienda ISO di tre lettere.
3. Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.

Per un esempio e un approccio alternativo, vedere [Esempio](#example).

## <a name="example"></a>Esempio

Per un esempio, vedere [Abilitazione di Customers V3: mappa entità contatti](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)

Per un approccio alternativo basato sui volumi di dati in ogni entità che deve eseguire la sincronizzazione iniziale, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).
