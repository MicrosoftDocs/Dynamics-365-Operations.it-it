---
title: Linee guida per la configurazione della doppia scrittura
description: Questo articolo descrive gli scenari supportati per l'impostazione della doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 06/28/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 15dfb609b5e25b4faf2b913cc2310df71c88a74d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111251"
---
# <a name="guidance-for-dual-write-setup"></a>Linee guida per la configurazione della doppia scrittura

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



È possibile impostare una connessione di doppia scrittura tra un ambiente di finanza e operazioni e un ambiente Dataverse.

+ Un **ambiente di finanza e operazioni** fornisce la piattaforma sottostante per le **app per la finanza e le operazioni** (ad esempio Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources).
+ Un **ambiente Dataverse** fornisce la piattaforma sottostante per le **app di interazione con i clienti** in Dynamics 365 (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).


> [!IMPORTANT]
> Il modulo Risorse umane in Dynamics 365 Finance supporta le connessioni a doppia scrittura, al contrario dell'app Dynamics 365 Human Resources.

Il meccanismo di impostazione varia in base alla sottoscrizione e all'ambiente:

+ Per le nuove istanze di app per la finanza e le operazioni, la configurazione di una connessione a doppia scrittura inizia in Microsoft Dynamics Lifecycle Services (LCS). Se è disponibile una licenza per Microsoft Power Platform, si ottiene uno nuovo ambiente Dataverse se il tenant ne è privo.
+ Per le istanze esistenti di app per la finanza e le operazioni, la configurazione di una connessione a doppia scrittura inizia nell'ambiente di finanza e operazioni.

Prima di avviare la doppia scrittura su un'entità, è possibile eseguire una sincronizzazione iniziale per gestire i dati esistenti su entrambi i lati: delle app per la finanza e le operazioni e delle app di interazione con i clienti. È possibile saltare la sincronizzazione iniziale se non si devono sincronizzare i dati tra i due ambienti.

Una sincronizzazione iniziale consente di copiare i dati esistenti da un'app all'altra in modo bidirezionale. Esistono diversi scenari di configurazione a seconda degli ambienti già presenti e del tipo di dati in essi presenti.

Sono supportati gli scenari di impostazione che seguono:

+ [Una nuova istanza di app per la finanza e le operazioni e una nuova istanza di app di interazione con i clienti](#new-new)
+ [Una nuova istanza di app per la finanza e le operazioni e un'istanza di app di interazione con i clienti esistente](#new-existing)
+ [Una nuova istanza di app per la finanza e le operazioni con dati e una nuova istanza di app di interazione con i clienti](#new-data-new)
+ [Una nuova istanza di app per la finanza e le operazioni con dati e un'istanza di app di interazione con i clienti esistente](#new-data-existing)
+ [Un'istanza di app per la finanza e le operazioni esistente e una nuova istanza app di interazione con i clienti esistente](#existing-new)
+ [Un'istanza di app per la finanza e le operazioni esistente e un'istanza esistente dell'app di interazione con i clienti esistente](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Una nuova istanza di app per la finanza e le operazioni e una nuova istanza di app di interazione con i clienti

Per impostare una connessione a doppia scrittura tra una nuova istanza dell'app per la finanza e le operazioni che non contiene dati e una nuova istanza di un'app Customer Engagement, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md). Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:

- Viene eseguito il provisioning di un nuovo ambiente di finanza e operazioni vuoto.
- Viene eseguito il provisioning di una nuova istanza vuota di un'app Customer Engagement in cui è installata la soluzione principale CRM.
- Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.
- Vengono abilitate le mappe della tabella per la sincronizzazione in tempo reale.

Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Una nuova istanza di app per la finanza e le operazioni e un'istanza di app di interazione con i clienti esistente

Per impostare una connessione a doppia scrittura tra una nuova istanza dell'app per la finanza e le operazioni che non contiene dati e un'istanza di un'app di interazione con i clienti esistente, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md). Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:

- Viene eseguito il provisioning di un nuovo ambiente di finanza e operazioni vuoto.
- Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.
- Vengono abilitate le mappe della tabella per la sincronizzazione in tempo reale.

Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.

Per sincronizzare i dati Dataverse esistenti nell'app per la finanza e le operazioni, seguire questi passaggi.

1. Crea una nuova società nell'app per la finanza e le operazioni.
2. Aggiungere la società alla configurazione della connessione a doppia scrittura.
3. [Avviare](bootstrap-company-data.md) i dati Dataverse utilizzando un codice aziendale di tre lettere International Organization for Standardization (ISO).
4. Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.

Per i collegamenti a un esempio e un approccio alternativo, consulta la sezione [Esempio](#example) più avanti in questo articolo.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Una nuova istanza di app per la finanza e le operazioni con dati e una nuova istanza di app di interazione con i clienti

Per impostare una connessione a doppia scrittura tra una nuova istanza dell'app per la finanza e le operazioni con dati e una nuova istanza di un'app di interazione con i clienti, segui i passaggi nella sezione [Una nuova istanza dell'app per la finanza e le operazioni e una nuova istanza dell'app di interazione con i clienti](#new-new) precedente in questo articolo. Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.

1. Apri l'app per la finanza e le operazioni dalla pagina LCS, accedi e passa a **Gestione dati \> Doppia scrittura**.
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.

Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Una nuova istanza di app per la finanza e le operazioni con dati e un'istanza di app di interazione con i clienti esistente

Per impostare una connessione a doppia scrittura tra una nuova istanza dell'app per la finanza e le operazioni con dati e un'istanza esistente di un'app di interazione con i clienti, segui i passaggi nella sezione [Una nuova istanza dell'app per la finanza e le operazioni e un'istanza dell'app di interazione con i clienti esistente](#new-existing) precedente in questo articolo. Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.

1. Apri l'app per la finanza e le operazioni dalla pagina LCS, accedi e passa a **Gestione dati \> Doppia scrittura**.
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.

Per sincronizzare i dati Dataverse esistenti nell'app per la finanza e le operazioni, seguire questi passaggi.

1. Crea una nuova società nell'app per la finanza e le operazioni.
2. Aggiungere la società alla configurazione della connessione a doppia scrittura.
3. [Avviare](bootstrap-company-data.md) i dati Dataverse utilizzando un codice aziendale di tre lettere ISO.
4. Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.

Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Un'istanza di app per la finanza e le operazioni esistente e una nuova istanza di app di interazione con i clienti

L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app per la finanza e le operazioni e una nuova istanza di un'app di interazione con i clienti si verifica nell'ambiente di finanza e operazioni.

1. [Configura la connessione dall'app per la finanza e le operazioni](enable-dual-write.md).
2. Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.

Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Un'istanza di app per la finanza e le operazioni esistente e un'istanza esistente dell'app di interazione con i clienti esistente

L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app per la finanza e le operazioni e un'istanza esistente di un'app di interazione con i clienti esistente si verifica nell'ambiente di finanza e operazioni.

1. [Configura la connessione dall'app per la finanza e le operazioni](enable-dual-write.md).
2. Per sincronizzare i dati Dataverse esistenti nell'app per la finanza e le operazioni, [avviare](bootstrap-company-data.md) i dati Dataverse utilizzando un codice azienda ISO di tre lettere.
3. Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.

Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).

## <a name="example"></a>Esempio

Per un esempio, vedere [Abilitazione di Customers V3-mappa della tabella Contatti](enable-entity-map.md#enable-table-map)

Per un approccio alternativo che si basa sui volumi di dati in ogni entità che deve eseguire una sincronizzazione iniziale, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
