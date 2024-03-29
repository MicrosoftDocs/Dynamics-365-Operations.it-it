---
title: Contenuto Power BI sulla selezione del personale
description: Questo articolo descrive il contenuto Power BI Selezione del personale.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.form: HcmRecruitmentWorkspace
ms.openlocfilehash: 412a1225544bb73649c9f0e703ec7b9a0d2613e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276598"
---
# <a name="recruiting-power-bi-content"></a>Contenuto Power BI sulla selezione del personale

[!include [banner](../includes/banner.md)]

Questo articolo descrive il contenuto Microsoft Power BI **Selezione del personale**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto Power BI **Selezione del personale** viene visualizzato nell'area di lavoro **Gestione della selezione del personale**.

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Report e rappresentazioni nell'area di lavoro di Gestione della selezione del personale
L'area di lavoro **Gestione della selezione del personale** contiene una scheda **Analisi**. Questa scheda include il contenuto di Power BI incorporato per la selezione del personale. Il contenuto è costituito da una scheda Panoramica e le schede aggiuntive che contengono dettagli. Nella seguente tabella vengono illustrati i report su ciascuna scheda.

| Report               | Contenuto |
|----------------------|----------|
| Panoramica della selezione del personale | Riepiloga altri report |
| Analisi dei candidati   | Numero total di candidati, candidati per mansione, origini del candidato, candidati femmine e maschi e candidati per località |
| Stato candidati     | Candidati per tipo e stato e stato del candidato |
| Analisi della selezione del personale  | Indice di assunzione netto, giorni medi di assunzione, percentuale di assunzioni errate, costi di selezione, numero di progetti di selezione, percentuale di assunzioni rispetto alle candidature e candidati rispetto alle aperture per progetto di selezione |

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

Nella tabella seguente vengono illustrate le entità su cui si basa il contenuto di Power BI **Selezione del personale**.

| Entità               | Contenuto                                                         | Relazioni con altre entità |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Richiedente            | Candidati, candidati assunti, indice di assunzione netto e costi          | Nome candidato, Società, Offset di calendario, Data, Località geografica, Dati demografici, Mansione, Multimediale, Progetto di selezione |
| Nome candidato       | Nome, cognome e nome completo del candidato                   | Candidato, candidato impiegato, candidato congedato |
| Offset di calendario      | Offset di calendario su report suddivisi                                | Candidato, candidato impiegato, candidato congedato |
| Società              | Società in base a cui filtrare i report                                   | Candidato, candidato impiegato, candidato congedato |
| Data                 | Giorni, settimane, mesi e anni.                                   | Candidato, candidato impiegato, candidato congedato |
| Dati demografici         | Data di nascita, sesso, origine etnica e stato civile         | Candidato, candidato impiegato, candidato congedato |
| Candidato impiegato   | Candidato, prestazioni, data di inizio e tipo di candidato           | Società, Offset di calendario, Data, Località geografica, Nome candidato, Impiego, Prestazioni, Mansione, Multimediale, Progetto di selezione |
| Impiego           | Data di inizio, data di fine e data della transizione                        | Candidato, candidato impiegato, candidato congedato |
| Località geografica  | Città, provincia, codice postale e stato/regione o provincia                 | Candidato, candidato impiegato, candidato congedato |
| Mansione                  | Funzione, tipo e titolo                                        | Candidato, candidato impiegato, candidato congedato |
| Multimediale                | Origine dei candidati                                             | Candidato, candidato impiegato, candidato congedato |
| Prestazioni          | Valutazione, Descrizione e modello di valutazione                            | Candidato, candidato impiegato, candidato congedato |
| Progetto di selezione  | Descrizione del progetto, stato del progetto e aperture                | Candidato, candidato impiegato, candidato congedato |
| Candidato congedato | Candidati congedati, motivo, prestazioni e data di fine rapporto | Società, Offset di calendario, Data, Località geografica, Prestazioni, Dati demografici, Impiego, Multimediale, Progetto di selezione, Nome candidato |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
