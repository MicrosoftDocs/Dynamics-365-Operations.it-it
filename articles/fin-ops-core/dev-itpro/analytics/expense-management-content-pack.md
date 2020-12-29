---
title: Contenuto di Power BI Gestione spese
description: In questo argomento viene descritto cosa è incluso nel pacchetto di contenuto Power BI Gestione spese.
author: RyanSand
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 9391676beea6aac831648d5fa55eae5eba3f6397
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682799"
---
# <a name="expense-management-power-bi-content"></a>Contenuto di Power BI Gestione spese

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto Power BI Gestione spese. 

## <a name="overview"></a>Panoramica
Due pacchetti di contenuti Power BI sono disponibili per l'utilizzo con Gestione spese nella versione 8.1 e versioni successive. 
- È presente un dashboard personale progettato per i dipendenti che inviano note spese. 

  Il dashboard fornisce informazioni chiave su importi non inviati e inviati nonché lo storico e dettagli importanti sullo storico delle transazioni di spesa. Il dashboard personale è una singola pagina contenente le informazioni più importanti per l'utente.

- È presente un dashboard di amministrazione destinato ai responsabili e agli addetti della contabilità fornitori. Il dashboard consente la registrazione e il reporting delle spese globali dei dipendenti. Fornisce metriche di spesa, ad esempio spese non inviate, chilometraggio e importi medi di note spese. Utilizza i dati transazionali e fornisce visualizzazioni aggregate della gestione delle spese per tutte le società. Fornisce inoltre una scomposizione per dipendente, con la possibilità di aggiungere dati di dimensione finanziaria. Analisi spesa di amministrazione contiene: 
  - Una panoramica con le metriche sugli importi delle spese e informazioni dettagliate su note spese in bozza, in elaborazione e completate. 
  - Una pagina con statistiche per esaminare singoli dettagli su un dipendente per periodo, tipo di costo e gruppo di statistiche. 
  - Una pagina di confronto per comparare più dipendenti nel tempo. 

Tutti gli importi sono visualizzati nella valuta della società. Sono visualizzati i dati di tutte le società, ma è possibile aggiungere un filtro società se necessario. 

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
È possibile trovare il contenuto Power BI Dashboard amministrazione spese.pbix e Dashboard personale spese.pbix nella libreria delle risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni su come scaricare il contenuto e implementarlo nell'organizzazione, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).
Il contenuto è disponibile nell'area di lavoro Gestione spese come contenuto Power BI incorporato. Qualsiasi titolare di spesa può accedere alle proprie spese personali, mentre solo i responsabili e gli addetti alla contabilità fornitori hanno accesso al contenuto di amministrazione per visualizzare i dati spesa di tutti gli utenti.

## <a name="refreshing-the-power-bi-content"></a>Aggiornamento del contenuto Power BI
Il contenuto Power BI Gestione spese richiede la misurazione TrvBiExpenseMeasurement e l'aggiornamento di BudgetActivityMeasure per essere aggiornato dall'Archivio entità. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Il contenuto include un set di pagine di report. Ciascuna pagina è costituita da un set di metriche visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel contenuto Power BI.

**Analisi spese personali**

| Pagina di report | Visualizzazione                             |
|-------------|-------------------------------------------|
| Spese personali | Importo chilometraggio                         |
|             | Note spese in elaborazione                |
|             | N. di spese non inviate               |
|             | Spese personali da pagare              |
|             | Importo non inviato                        |
|             | Importo inviato                          |
|             | Importo in attesa di rimborso             |
|             | Note spese con importi e stato   |
|             | Note spese inviate ma non approvate  |
|             | Spese per tipo di costo                     |
|             | Spese per esercente                      |
|             | Spese per spese elaborate            |
|             | Spese per progetto                       |
|             | Importo totale della transazione nel tempo        |

**Analisi spese di amministrazione**

| Pagina di report         | Visualizzazione                           |           
|---------------------|-----------------------------------------|
| Panoramica spese    | Importo spese in bozza                   |
|                     | Numero di righe spese in bozza           |
|                     | Righe spese in bozza                     |
|                     | Violazioni dei criteri per note spese        |
|                     | Importo arretrato                      |
|                     | Spese inviate ma non approvate       |
|                     | Spese approvate                       |
|                     | Importo spese totale                    |
|                     | Riepiloghi note spese                |
|                     | Spese per tipo di costo                   |
|                     | Spese per esercente                    |
|                     | Spese per dipendente                   |
|                     | Spese e progetto                     |
| Confronto dei dipendenti | Importi spese                         |
|                     | Importi spese nel tempo per dipendente   |
| Statistiche dipendenti | Note spese per tipo di costo            |
|                     | Spese personali                       |
|                     | Note spese per gruppo di statistiche     |
