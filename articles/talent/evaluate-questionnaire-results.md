---
title: Visualizzare e valutare i risultati dei questionari
description: In questo argomento viene illustrato come è possibile visualizzare e valutare i risultati dei questionari che gli intervistati completano.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 38b694b6dd4b1b9a198452e409bd64d7934b4685
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518402"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a>Visualizzare e valutare i risultati dei questionari

[!include [banner](includes/banner.md)]

In questo argomento viene illustrato come è possibile visualizzare e valutare i risultati dei questionari che gli intervistati completano. 

Dopo che gli intervistati avranno compilato un questionario, sarà possibile vedere e valutare i risultati del questionario nei modi seguenti:

-   **Sessioni di risposte completate**: visualizzare i dettagli sui questionari completati degli intervistati e generare i report per riepilogare le risposte e anche tutti i punti che sono stati ottenuti.
-   **Gruppi di risultati**: visualizzare i dettagli e le statistiche del gruppo di risultati per i questionari. Le statistiche del gruppo di risultati possono essere generate per una singola sessione di risposte di un questionario o per tutte le sessioni di risposte di un questionario.
-   **Statistiche del questionario**: specificare i criteri per calcolare le statistiche per un gruppo specifico di intervistati.

È anche possibile generare i vari report per visualizzare i risultati ordinati per persona, sessione di risposte o gruppo di risultati. Sono disponibili i report seguenti relativi ai questionari completati:

-   Risposte
-   Risposte per questionario
-   Risposte per persona
-   Analisi riscontro

## <a name="answer-session-results"></a>Risultati della sessione di risposte
Dopo che gli intervistati hanno compilato un questionario, è possibile visualizzare i risultati delle sessioni di risposte completate. Una sessione di risposte corrisponde alla risposta di un utente a un questionario. È possibile visualizzare i dettagli sulle sessioni di risposte completate nella pagina **Risposte**. Le sessioni di risposte incluse nella pagina **Risposte** vengono filtrate in vari modi, in base alla modalità di apertura la pagina:

-   Tutti i questionari
-   Un questionario specifico
-   Una persona specifica

Dalla pagina **Risposte**, è possibile visualizzare i dettagli sulle risposte, i punti ottenuti, le risposte di un intervistato in ciascun gruppo di risultati e la gerarchia delle domande utilizzata nel questionario selezionato, se un gerarchia di domante è stata usata. È inoltre possibile generare e stampare i report seguenti:

-   **Report di risultati**: questo report mostra una rappresentazione grafica di punti che sono stati ottenuti per gruppo di risultati della sessione di risposte selezionata.
-   **Report risposte**: il report mostra le risposte che l'intervistato ha selezionato per ciascuna domanda del questionario.
-   **Risposte errate**: questo report mostra le informazioni correlate alle risposte errate selezionate dall'intervistato.

**Nota:** il report **Risultati** è disponibile solo se si utilizzano i gruppi di risultati del questionario e se è stato selezionato **Pagina risultati** nella pagina **Questionari**. Il report **Risposta** e il report **Risposte errate** sono disponibili solo se **Report risposte** è stato selezionato nella pagina **Questionari**.

## <a name="questionnaire-statistics"></a>Statistiche questionario
È possibile utilizzare le statistiche del questionario per analizzare i risultati di un questionario completato, basato sui calcoli definiti. Per definire i calcoli, è necessario completare le seguenti attività:

-   Selezionare i criteri per calcolare e visualizzare le statistiche.
    -   È possibile visualizzare le statistiche per questionario, domande, righe delle domande o gruppi di risultati.
    -   Selezionare il tipo di grafico da utilizzare quando si visualizzano i risultati.
    -   Selezionare i tipi di persone presenti in rete, ad esempio dipendenti, contatti o candidati, di cui includere le risposte. È inoltre possibile includere le risposte dei questionari completati in modo anonimo.
    -   Impostare intervalli basati sull'età o l'anzianità per analizzare i risultati.
-   Selezionare o verificare le impostazioni disponibili per definire più dettagliatamente il soggetto delle statistiche. Se ad esempio si seleziona un codice postale (CAP), sarà possibile analizzare i risultati per tutti gli intervistati all'interno dell'area geografica specifica corrispondente a tale codice.
-   Selezionare o verificare i criteri per analizzare i risultati per caratteristiche del questionario o dell'intervistato. Ad esempio, selezionando **Codice postale (CAP)**, è possibile analizzare la correlazione tra l'ubicazione di un intervistato e le risposte corrette.

Le impostazioni definite vengono salvate e possono essere utilizzate per ricalcolare periodicamente i risultati.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Progettazione di questionari](design-questionnaires.md)

[Utilizzo di questionari](questionnaires.md)

[Distribuzione e completamento di questionari](distribute-questionnaires.md)

