---
title: Contenuto Power BI di Fatturazione abbonamento
description: In questo argomento viene descritto cosa è incluso nel contenuto Microsoft Power BI di Fatturazione abbonamento.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-04-13
ms.openlocfilehash: fad96bdaf60e7772e9ea1ff937435b0274303505
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645420"
---
# <a name="subscription-billing-power-bi-content"></a>Contenuto Power BI di Fatturazione abbonamento

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto Microsoft Power BI di Fatturazione abbonamento. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto. 

## <a name="overview"></a>Panoramica

Il contenuto Power BI di Fatturazione abbonamento è stato creato per gli addetti alla fatturazione e i gestori degli abbonamenti. Fornisce parametri di fatturazione chiave per gli abbonamenti, come i ricavi mensili ricorrenti (MRR) per i programmi di fatturazione e il saldo decrescente e le informazioni della sequenza per i programmi di differimento. Utilizza i dati dei programmi di fatturazione e dei programmi di differimento per fornire una panoramica dei ricavi e delle entrate ricorrenti.

Il contenuto Power BI ha le tre schede seguenti che forniscono un totale di quattro report analitici: 

- **Analisi - MRR** – Questa scheda fornisce il report **Fatturazione mensile ricorrente** e il report **Dettagli programma di fatturazione**.
- **Analisi - Sequenza** – Questa scheda fornisce il report **Sequenza ricavi**.
- **Analisi - Ammortamento degressivo** – Questa scheda fornisce il report **Ammortamento degressivo**.

## <a name="view-data-on-the-analytical-reports"></a>Visualizzare i dati nei report analitici

Prima di poter visualizzare i dati nei report analitici, è necessario eseguire un processo periodico che generi i dati per ciascun report. Questi dati richiesti dai report devono essere generati perché non sono archiviati direttamente nel database. 

1. Vai a **Fatturazione abbonamento \> Fatturazione contratto ricorrente \> Attività periodiche \> Elaborazione batch report analitico MRR** e segui questi passaggi:

    1. Immetti un intervallo di date non superiore a tre anni.
    2. Facoltativo: imposta un processo di elaborazione batch ricorrente per aggiornare periodicamente i dati.
    3. Seleziona **OK**.

2. Al termine dell'esecuzione del processo batch, vai in **Amministrazione sistema \> Impostazione \> Archivio entità** e aggiorna la misura di aggregazione **Report MRR**. 
3. Vai a **Fatturazione abbonamento \> Differimenti ricavi e spese \> Attività periodiche \> Elaborazione batch report analitico sequenza** e segui questi passaggi:

    1. Immetti una data di inizio e una data di fine che non coprano più di 26 periodi. 
    2. Se vuoi visualizzare la quantità prevista di periodi passati nel periodo corrente, imposta l'opzione **Previsione di importi passati nel periodo corrente** su **sì**.
    3. Facoltativo: imposta un processo di elaborazione batch ricorrente per aggiornare periodicamente i dati.
    4. Seleziona **OK**. 

4. Al termine dell'esecuzione del processo batch, vai in **Amministrazione sistema \> Impostazione \> Archivio entità** e aggiorna la misura di aggregazione **Report sequenza**.
5. Vai a **Fatturazione abbonamento \> Differimenti ricavi e spese \> Attività periodiche \> Elaborazione batch report analitico ammortamento degressivo** e segui questi passaggi:

    1. Immetti una data di inizio e una data di fine che non coprano più di 26 periodi. 
    2. Se vuoi visualizzare la quantità prevista di periodi passati nel periodo corrente, imposta l'opzione **Previsione di importi passati nel periodo corrente** su **sì**.
    3. Facoltativo: imposta un processo di elaborazione batch ricorrente per aggiornare periodicamente i dati.
    4. Seleziona **OK**.

6. Al termine dell'esecuzione del processo batch, vai in **Amministrazione sistema \> Impostazione \> Archivio entità** e aggiorna la misura di aggregazione **Report ammortamento degressivo**.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

Il contenuto Power BI di Fatturazione abbonamento è mostrato nell'area di lavoro **Fatturazione abbonamento**.
