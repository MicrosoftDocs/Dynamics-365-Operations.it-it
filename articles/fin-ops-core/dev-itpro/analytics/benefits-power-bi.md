---
title: Contenuto Benefit di Power BI
description: Questo argomento descrive il contenuto Benefit di Power BI. Descrive come accedere ai report inclusi e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefitWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: d0a5fe54bb4f5541f610f8ea76afa7813e3a599a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687257"
---
# <a name="benefits-power-bi-content"></a>Contenuto Benefit di Power BI

[!include [banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Benefit** di Microsoft Power BI. Descrive come accedere ai report inclusi e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto **Benefit** di Power BI viene visualizzato nell'area di lavoro **Gestione benefit** se si utilizza uno dei seguenti prodotti:

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI
I report inclusi nel contenuto **Benefit** di Power BI dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                      | Contenuto                                                                                       |
|-----------------------------|------------------------------------------------------------------------------------------------|
| Panoramica dell'iscrizione ai benefit | Piani con più o meno iscritti, iscrizione per gruppo di dipendenti e opzioni del piano di benefit selezionate |
| Benefit dei dipendenti           | Iscrizione del dipendente per benefit selezionato                                                        |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I seguenti dati vengono utilizzati per compilare i report nel contenuto **Benefit** di Power BI. Nella tabella seguente vengono illustrate le entità su cui è stato basato il contenuto.

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
