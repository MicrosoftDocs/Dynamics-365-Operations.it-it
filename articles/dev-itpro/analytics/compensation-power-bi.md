---
title: Contenuto Power BI per retribuzione
description: "Questo argomento descrive il contenuto Retribuzione di Power BI. Descrive come accedere ai report e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmCompensationWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 93c005d4b85b56f77ddd488c91e477970f4ccd07
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="compensation-power-bi-content"></a>Contenuto Power BI per retribuzione

[!include [banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Retribuzione** di Microsoft Power BI. Descrive come accedere ai report e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto **Retribuzione** di Power BI viene visualizzato nell'area di lavoro **Gestione retribuzioni** se si utilizza uno dei seguenti prodotti:

- Microsoft Dynamics 365 for Finance and Operations
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI
I report inclusi nel contenuto **Retribuzione** di Power BI dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                     | Contenuto |
|----------------------------|----------|
| Panoramica sulla retribuzione      | Riepilogo di altri report |
| Analisi della retribuzione      | Dipendenti con retribuzione oraria e quelli stipendiati per società, dipendenti totali per piano di retribuzione, dipendenti donne e dipendenti uomini per piano di retribuzione e retribuzione dipendente per reparto |
| Analisi della retribuzione per posizione      | Retribuzione oraria e stipendio più alto e più basso, posizioni con lo stipendio più alto e più basso e posizioni a tempo pieno e a tempo parziale |
| Analisi del piano di retribuzione | Iscrizione del dipendente per benefit selezionato |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I seguenti dati vengono utilizzati per compilare i report nel contenuto **Retribuzione** di Power BI. Nella tabella seguente vengono illustrate le entità su cui è stato basato il contenuto.

| Entità                   | Contenuto                                                                                                   | Relazioni con altre entità |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Offset di calendario          | Offset di calendario su report suddivisi                                                                          | Assegnazione della posizione passata, Tendenza della posizione, Tendenza del dipendente, Dipendente con rapporto di lavoro chiuso |
| Società                  | Società in base a cui filtrare i report                                                                             | Retribuzione corrente, Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Retribuzione             | Tariffa retributiva e frequenza nel tempo                                                                           | Retribuzione corrente, Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Retribuzione corrente     | Tariffa retributiva e frequenza a partire dalla data corrente                                                              | Società, Retribuzione, Dati demografici, Mansione, Posizione |
| Posizione corrente         | Posizione a partire dalla data corrente, equivalente a tempo pieno (FTE), posizioni aperte e posizioni da aperte ad assegnate | Lavoro, Posizione |
| Dipendente corrente         | Lavoratori a partire dalla data corrente, età e numero di dipendenti                                                         | Società, Retribuzione, Località geografica, Nome del dipendente, Subordinato a, Posizione del dipendente, Dati demografici, Mansione, Impiego, Posizione, Benefit |
| Data                     | Giorni, settimane, mesi e anni.                                                                             | Assegnazione della posizione passata, Tendenza della posizione, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Dati demografici             | Data di nascita, sesso, origine etnica e stato civile                                                   | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Impiego               | Data di inizio, data di fine e data della transizione                                                                  | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Località geografica      | Città, provincia, codice postale e stato/regione o provincia                                                           | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Mansione                      | Funzione, tipo e titolo                                                                                  | Posizione corrente, Dipendente corrente |
| Assegnazione della posizione passata | Motivo dell'assegnazione, data di inizio, data di fine e mansione                                                           | Offset di calendario, Data, Mansione, Posizione |
| Posizione                 | Reparto, FTE, posizione, tipo di posizione e titolo                                                        | Posizione corrente, Dipendente corrente |
| Tendenza della posizione           | Posizioni nel tempo, FTE e mansione                                                                          | Offset di calendario, Data, Mansione, Posizione |
| Subordinato a               | Nome, cognome e nome completo                                                                       | Lavoratore corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Dipendente con rapporto di lavoro chiuso      | Dipendenti con rapporto di lavoro chiuso, data di fine rapporto, titolo, posizione e mansione                                           | Società, Retribuzione, Località geografica, Nome del dipendente, Subordinato a, Offset di calendario, Data, Posizione del dipendente, Dati demografici, Impiego, Mansione, Posizione, Benefit |
| Benefit                 | Data di validità, opzione di benefit, piano di benefit e tipo di benefit                                             | Nome corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Nome dipendente            | Nome, cognome e nome completo                                                                       | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Posizione del dipendente           | Titolo e data di anzianità                                                                                   | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Tendenza del dipendente           | Lavoratori nel tempo, numero di dipendenti, società e posizione                                                        | Società, Retribuzione, Località geografica, Nome del dipendente, Subordinato a, Offset di calendario, Data, Posizione del dipendente, Dati demografici, Impiego, Mansione, Benefit |

