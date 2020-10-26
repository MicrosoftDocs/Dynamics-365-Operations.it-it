---
title: Panoramica dei processi di fatturazione automatizzati dei fornitori
description: In questo argomento viene descritta l'automatizzazione dell'elaborazione delle fatture fornitore e i vantaggi inerenti all'utilizzo di un processo automatizzato.
author: abruer
manager: AnnBe
ms.date: 08/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 187b3c4f1a8b2c9ec6df95c19b261756ec4562dc
ms.sourcegitcommit: 6ffbae02de2eee1f3be9bab2da37a3771aae8bec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905019"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Panoramica dei processi di fatturazione automatizzati dei fornitori

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene descritta l'automatizzazione dell'elaborazione delle fatture fornitore e i vantaggi inerenti all'utilizzo di un processo automatizzato. Questa soluzione è costituita da funzionalità attivate in Gestione funzionalità. Tali funzionalità si applicano solo alle fatture fornitore, non alle fatture elaborate tramite la pagina **Giornale di registrazione fatture** o **Giornale di registrazione del registro fatture**.

In molti casi, le organizzazioni si avvalgono di terzi parti per elaborare fatture cartacee utilizzando un provider di servizi OCR di terze parti. Il fornitore di servizi restituisce metadati di fatture leggibili da una macchina. Per facilitare l'automazione, le funzionalità di automazione della contabilità fornitori ti consentono di utilizzare questi artefatti in Contabilità fornitori.

Puoi automatizzare alcuni processi di fatturazione della contabilità fornitori. Questi processi includono l'invio di fatture fornitore importate al sistema del flusso di lavoro e l'abbinamento delle righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso. Il processo automatizzato mostra le informazioni sullo stato di avanzamento di una fattura fornitore durante ognuno dei processi. Questa soluzione può aiutare gli impiegati e i responsabili della contabilità fornitori a elaborare fatture fornitori in modo più efficiente. Aiuta anche a ridurre gli errori e le inefficienze che possono verificarsi quando le informazioni vengono inserite ed elaborate manualmente.

I processi di automazione possono essere utilizzati per eseguire queste attività:

- Inviare automaticamente fatture importate al sistema del flusso di lavoro.
- Abbinare entrate prodotti alle righe di fattura fornitore in sospeso.
- Simulare la registrazione prima della registrazione di una fattura fornitore.
- Visualizzare lo storico flusso di lavoro in modo rapido ed efficiente.
- Visualizzare e analizzare i risultati dell'automazione dell'elaborazione delle fatture fornitori.

## <a name="vendor-invoice-automation--submit-imported-vendor-invoices-to-the-workflow-system"></a>Automazione delle fatture fornitore - Inviare fatture fornitore importate al sistema del flusso di lavoro

Come parte di un processo di fatturazione della contabilità fornitori senza contatto, puoi fare in modo che il sistema invii automaticamente una fattura importata al sistema del flusso di lavoro. Il processo verrà eseguito in background, alla frequenza da te specificata (oraria o giornaliera). Per inviare automaticamente fatture importate al sistema del flusso di lavoro, è necessario che il processo inizi con una fattura importata. Per garantire che la fattura possa essere elaborata dall'inizio alla fine senza intervento manuale, devi includere un'attività di registrazione automatizzata nella configurazione del flusso di lavoro.

Le fatture correlate agli ordini fornitore e le fatture che contengono una categoria di approvvigionamento non ordine fornitore e righe non a magazzino possono essere inviate automaticamente al sistema del flusso di lavoro. Le fatture immesse manualmente e le fatture create tramite l'area di lavoro **Fatturazione di collaborazione fornitore** devono essere inviate manualmente al sistema del flusso di lavoro.

La funzionalità di automazione fornisce un framework flessibile che consente di definire regole specifiche dell'azienda per l'invio di fatture fornitore importate al sistema del flusso di lavoro e l'abbinamento delle righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso.

## <a name="vendor-invoice-automation--match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Automazione delle fatture fornitore - Abbinare entrate prodotti a righe di fattura con criteri di abbinamento a tre elementi di verifica

Il sistema può abbinare automaticamente le entrate prodotti registrate alle righe di fattura per cui sono definiti criteri di abbinamento a tre elementi di verifica. Il processo verrà eseguito fino a quando la quantità delle entrate prodotti abbinate non sarà uguale alla quantità della fattura. Come parte di questo processo, puoi specificare il numero massimo di tentativi del sistema di abbinare le entrate prodotti a una riga di fattura prima che il sistema consideri il processo come non riuscito. Il processo verrà eseguito in background, ogni ora o ogni giorno. Puoi eseguire il processo di abbinamento automatizzato come parte del processo di invio di fatture al sistema del flusso di lavoro. In alternativa, puoi eseguirlo come processo autonomo.

## <a name="vendor-invoice-automation--pre-validate-vendor-invoice-posting"></a>Automazione delle fatture fornitore - Pre-convalidare la registrazione delle fatture fornitore

La simulazione della registrazione completa i passaggi di convalida eseguiti durante il processo di registrazione delle fatture fornitore, ma nessun conto viene aggiornato. Per eseguire il processo, puoi selezionare una singola fattura o più fatture nella pagina **Fatture fornitore in sospeso**.

## <a name="vendor-invoice-automation--enhanced-experience-for-viewing-workflow-historical-information-for-vendor-invoices"></a>Automazione delle fatture fornitore - Esperienza migliorata per la visualizzazione delle informazioni dello storico flusso di lavoro per fatture fornitore

Viene fornita una visualizzazione di facile lettura dello storico flusso di lavoro delle fatture fornitore. Puoi accedere allo storico flusso di lavoro delle fatture fornitore direttamente dalla fattura fornitore. Pertanto, sono necessari meno clic per trovare tali informazioni.

## <a name="vendor-invoice-automation--analytics-and-metrics"></a>Automazione delle fatture fornitore - Analisi e metriche

L'area di lavoro **Inserimento fatture fornitore** ti consente di concentrarti sulle fatture fornitore che non hanno superato il processo automatizzato. I riquadri nell'area di lavoro elencano le informazioni sulle fatture fornitore che non sono state inviate correttamente al sistema del flusso di lavoro, importate o abbinate alle entrate prodotti. Sono inoltre disponibili metriche Microsoft Power BI per fornire ai responsabili della contabilità fornitori una visione dell'efficienza dell'automazione delle fatture fornitore.
