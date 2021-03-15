---
title: Pianificazione della produzione
description: Questo argomento descrive la pianificazione della produzione e spiega come modificare gli ordini di produzione pianificati utilizzando Ottimizzazione pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: eda22aa6f1e8d665d8ef390f24b247a76d4c2956
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992397"
---
# <a name="production-planning"></a>Pianificazione della produzione

Ottimizzazione pianificazione supporta diversi scenari di produzione. Se si esegue la migrazione dal motore di pianificazione generale integrato esistente, è importante essere a conoscenza di alcuni comportamenti modificati.

<!-- The following video gives a short introduction to some of the current capabilities. 
KFM: Link to video for production functionality, coming soon... -->

## <a name="planned-production-orders"></a>Ordini di produzione pianificati

Quando la pianificazione generale crea ordini pianificati per soddisfare i requisiti, il tipo di ordine è determinato dal valore del campo **Tipo di ordine pianificato**. Se il campo **Tipo di ordine pianificato** è impostato su *Produzione*, vengono creati gli ordini di produzione pianificati. Questi ordini di produzione pianificati includono informazioni sulla distinta base (BOM) attiva e l'ID ciclo di lavorazione dalla relativa configurazione di produzione.

## <a name="requirements-from-boms"></a>Requisiti delle distinte base

Le informazioni sulla distinta base vengono rispettate durante la pianificazione generale. L'output del piano include l'offerta di materiale per coprire la domanda di materiale correlata per la produzione.

Durante la pianificazione generale, la distinta base attiva corrente viene utilizzata per determinare i materiali necessari per la produzione. Questo passaggio viene eseguito attraverso tutti i livelli della struttura della distinta base correlata all'ordine di produzione richiesto. Il fabbisogno di materiale viene soddisfatto utilizzando le scorte disponibili, la fornitura su ordinazione esistente e gli ordini pianificati approvati. Se in un qualsiasi punto è necessario materiale aggiuntivo, viene creato un ordine pianificato per coprire la domanda.

## <a name="scheduling-during-firming"></a>Pianificazione durante la stabilizzazione

Gli ordini di produzione pianificati includono l'ID ciclo di lavorazione richiesto per la pianificazione della produzione. Tuttavia, il supporto della pianificazione durante l'esecuzione della pianificazione per gli ordini pianificati è in sospeso. L'ID ciclo di lavorazione viene utilizzato per programmare gli ordini di produzione pianificati durante la stabilizzazione. Pertanto, il lead time sugli ordini di produzione pianificati può differire dal lead time sugli ordini di produzione stabilizzati programmati correlati generati da essi, come descritto di seguito:

- **Ordine di produzione pianificato** - Il lead time si basa sul lead time statico dal prodotto rilasciato.
- **Ordine di produzione stabilizzato** - Il lead time si basa sulla pianificazione che utilizza le informazioni sul percorso e i relativi vincoli di risorse.

Per ulteriori informazioni sulla disponibilità delle funzionalità previste, vedere [Analisi di adattamento dell'ottimizzazione della pianificazione](planning-optimization-fit-analysis.md).

Se dipendi dalla funzionalità di produzione che non è ancora disponibile per Ottimizzazione pianificazione, puoi continuare a utilizzare il motore di pianificazione generale integrato. Non è richiesta alcuna eccezione.

## <a name="delays"></a>Ritardi

Se il lead time per il materiale richiesto è più lungo del periodo compreso tra la data odierna e la data del fabbisogno di materiale, l'ordine pianificato per il materiale richiesto e il relativo ordine di produzione verranno ritardati. Per gli ordini pianificati, il ritardo (in giorni) viene calcolato in base al lead time dal prodotto rilasciato. Le informazioni sul ritardo vengono quindi propagate a tutti i livelli della struttura della distinta componenti. Pertanto, è possibile seguire l'impatto del ritardo delle materie prime fino all'ordine di vendita del cliente.

## <a name="modifying-planned-orders"></a>Modifica degli ordini pianificati

Quando si modificano le informazioni su un ordine pianificato, viene visualizzato il messaggio seguente: "Notare che l'impatto delle modifiche manuali sugli ordini pianificati non si rifletterà nel resto del piano fino alla successiva esecuzione della pianificazione generale".

Se desideri modificare le informazioni su un ordine pianificato e vedere l'impatto sui relativi requisiti di materiale, segui questi passaggi.

1. Aggiorna l'ordine pianificato.
2. Approva l'ordine pianificato.
3. Esegui la pianificazione generale.

Quando si esegue la pianificazione generale, non è consigliabile utilizzare filtri se sono inclusi gli ordini di produzione pianificati. Per ulteriori informazioni, vedi la sezione [Filgtri](#filters) più avanti in questo argomento.

> [!NOTE]
> Se la data di consegna dell'ordine pianificato viene modificata in una data successiva, la domanda potrebbe essere ancorata a un nuovo ordine pianificato. Questo comportamento si verifica quando la nuova data di fornitura causa un ritardo per la domanda con pegging ma, in base alle impostazioni del lead time, è possibile evitare il ritardo.

## <a name="explosion-page"></a>Pagina di esplosione

Puoi utilizzare la pagina **Esplosione** per analizzare la domanda richiesta per uno specifico ordine di produzione o ordine di produzione pianificato, la relativa copertura e le informazioni sul pegging. Le informazioni sulla pagina **Esplosione** vengono aggiornate durante la pianificazione generale. Non è possibile aggiornare le informazioni direttamente dalla pagina **Esplosione**.

## <a name="filters"></a><a name="filters"></a>Filtri

Per gli scenari di pianificazione che includono la produzione, si consiglia di evitare esecuzioni di pianificazione generale filtrate. Per garantire che Ottimizzazione pianificazione disponga delle informazioni necessarie per calcolare il risultato corretto, è necessario includere tutti i prodotti che hanno una relazione con i prodotti nell'intera struttura DBA dell'ordine pianificato.

Sebbene gli elementi figlio dipendenti vengano rilevati automaticamente e inclusi nelle esecuzioni della pianificazione generale quando viene utilizzato il motore di pianificazione generale integrato, Ottimizzazione pianificazione non esegue questa azione.

Ad esempio, se un singolo bullone dalla struttura DBA del prodotto A viene utilizzato anche per produrre il prodotto B, tutti i prodotti nella struttura DBA dei prodotti A e B devono essere inclusi nel filtro. Poiché può essere molto complesso garantire che tutti i prodotti facciano parte del filtro, si consiglia di evitare esecuzioni di pianificazione generale filtrate quando sono coinvolti ordini di produzione.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]