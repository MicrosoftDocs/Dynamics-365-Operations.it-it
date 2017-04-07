---
title: "Impostare la protezione per il contenuto di potenza di analisi della contabilità industriale BI"
description: "In questo argomento viene descritto come eseguire propagare della protezione a livello dell&quot;Access nella contabilità industriale a protezione riga riga in Microsoft Power BI. Questa funzionalità assicura che gli utenti vedono solo i dati di Power BI autorizzato ad accedere a."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1e42622e7621c645d7eda3299f78c34c7e41a251
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Impostare la protezione per il contenuto di potenza di analisi della contabilità industriale BI

In questo argomento viene descritto come eseguire propagare della protezione a livello dell'Access nella contabilità industriale a protezione riga riga in Microsoft Power BI. Questa funzionalità assicura che gli utenti vedono solo i dati di Power BI autorizzato ad accedere a.

<a name="overview"></a>Panoramica
--------

** Analisi di contabilità industriale ** il contenuto di Power BI Microsoft utilizza la protezione BI riga riga di potenza per limitare l'accesso di un utente. La protezione di è basata sulla gerarchia organizzativa a livello dell'Access impostata nei parametri di contabilità industriale. Per ulteriori informazioni su ** analisi della contabilità industriale ** alimenti BI il contenuto, vedere [Contabilità industriale di analisi di Power BI contenuto] (Contabilità industriale - analysis-content-pack.md).

## <a name="setup"></a>Imposta
Per propagare della protezione a livello dell'Access per alimentare BI, il proprietario del contenuto di Power BI deve completare i passaggi seguenti. ** Nota: ** Utente che ha emesso ** analisi della contabilità industriale ** del contenuto Power BI diventa automaticamente il proprietario. Solo un responsabile può impostare la protezione in Power BI. Inoltre, il proprietario finché non aggiungere altri utenti su Nessuno PowerBI.com, a meno che il proprietario i dipendenti tutti i dati in ** analisi della contabilità industriale ** alimenti BI il contenuto.

1.  Registrare il file di definizioni per alimentare BI.
2.  Accesso all'indirizzo PowerBI.com.
3.  Individuare le il set di dati per ** analisi della contabilità industriale ** alimenti BI il contenuto.
4.  Aprire la pagina di protezione. 

    [![che apre la pagina] di protezione (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png) (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)]

5.  ** Da di oggetto di ** il ruolo è già creato. Aggiungere altri membri alla gerarchia organizzativa a livello dell'Access della contabilità industriale. 

    [![a cui aggiungere i membri (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)]

Gli utenti aggiunti ** controller di oggetto di ** al ruolo verranno visualizzati soltanto i dati che possono visualizzare, in base alla definizione della gerarchia organizzativa a livello dell'Access della contabilità industriale. ** Nota: ** la protezione Riga riga si applica a mattonelle e report in Microsoft Dynamics 365 per le operazioni incluse da Power BI.

## <a name="updating-security"></a>Aggiornamento di protezione
Se gli aggiornamenti vengono eseguiti di protezione a livello dell'Access nella contabilità industriale e si desidera Power BI riflettere gli aggiornamenti, è necessario aggiornare il punto di entità per ** analisi della contabilità industriale ** alimentate BI il contenuto. Dopo aver completato l'aggiornamento del record di entità da Dynamics 365 per le operazioni, è necessario aggiornare gli elementi in PowerBI.com. Per ulteriori informazioni sull'ente archiviare l'aggiornamento, vedere [] il record di entità aggiornamento (power-bi-integration-entity-store.md#update-entity-store). ** Il proprietario analisi della contabilità industriale ** i contenuti di Power BI necessario effettuare inoltre un aggiornamento del record di entità se nuovi utenti accesso alla gerarchia organizzativa. Inoltre, il proprietario deve aggiungere nuovi utenti ** controller di oggetto di ** al ruolo in PowerBI.com, in modo che la protezione riga riga viene applicata la merce.

## <a name="disabling-security"></a>Sicurezza restituendo non valida
Supponiamo che l'organizzazione desidera limitare l'accesso ai dati. Se, per qualsiasiasi motivo, parametri di protezione sono disattivate quando si esegue la contabilità industriale, il proprietario deve aggiungere gli utenti ** contabile di costo ** al ruolo in anziché Power BI. Se si modifica la protezione da uno stato abilitato allo stato di disabili, è consigliabile rimuovere gli utenti ** controller di oggetto di ** dal ruolo. E vice versa se riabilitate la protezione. Gli utenti possono appartenere a entrambi i ruoli. L'accesso verrà unito il sindacato di entrambi i ruoli. Nel caso di ** analisi della contabilità industriale ** alimenti BI, il contenuto utenti che hanno accesso unito avere accesso ai dati senza restrizioni. Se il target è di applicare l'accesso limitato, gli utenti devono essere assegnati solo costi ** Il controllore oggetti ** al ruolo. Negli aggiornamenti della protezione righi riga diventano immediatamente. Gli utenti devono interessati utenti devono riavviare browser.

## <a name="additional-resources"></a>Risorse aggiuntive
Per ulteriori informazioni sulla protezione BI riga riga di potenza, vedere [gestire la protezione sul modello in l Power BI] (https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).


