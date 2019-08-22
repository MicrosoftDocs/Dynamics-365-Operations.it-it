---
title: Contenuti Power BI sullo sviluppo e le competenze dei dipendenti
description: In questo argomento vengono fornite i contenuti Power BI sullo sviluppo e le competenze dei dipendenti in Finance and Operations.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1b1a0c8f756601dc342ab44364ea362cf2698f3c
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849739"
---
# <a name="employee-competencies-and-development-power-bi-content"></a>Contenuti Power BI sullo sviluppo e le competenze dei dipendenti

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite i contenuti Power BI sullo sviluppo e le competenze dei dipendenti in Finance and Operations. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel pacchetto di contenuti
Dopo aver collegato il pacchetto di contenuti ai dati di Finance and Operations, nei report vengono visualizzati i dati dell'organizzazione. Se non è mai stato usato Microsoft Power BI in precedenza, è possibile ottenere informazioni in merito nella pagina [Formazione guidata a Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel pacchetto di contenuti dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                            | Contenuto                                               |
|-----------------------------------|--------------------------------------------------------|
| Analisi di sviluppo e delle competenze | Tipi di competenza dei membri del team e competenze dei membri del team in base al tipo |
| Profilo competenze                     | Profilo competenze del dipendente selezionato                |
| Analisi competenze                    | Competenze per tipo e valutazione                              |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati di Finance and Operations vengono utilizzati per compilare i report nel pacchetto di contenuti sullo sviluppo e le competenze dei dipendenti. Nella tabella seguente vengono illustrate le entità su cui è stato basato il pacchetto di contenuti.

| Entità                            | Contenuto                                                                                                   | Relazioni con altre entità |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Forzalavoro\_OffsetCalendario         | Offset di calendario su report suddivisi                                                                          | |
| Forzalavoro\_Società                | Società in base a cui filtrare i report                                                                             | |
| Forzalavoro\_Retribuzione           | Tariffa retributiva e frequenza nel tempo                                                                           | |
| Forzalavoro\_RetribuzioneCorrente    | Tariffa retributiva e frequenza a partire dalla data corrente                                                              | Forzalavoro\_Società, Forzalavoro\_RetribuzioneCorrente, Forzalavoro\_DatiDemografici, Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_PosizioneCorrente        | Posizione a partire dalla data corrente, equivalente a tempo pieno (FTE), posizioni aperte e posizioni da aperte ad assegnate | Forzalavoro\_Mansione Forzalavoro\_Posizione |
| Forzalavoro\_LavoratoreCorrente          | Lavoratori a partire dalla data corrente, età e numero di dipendenti                                                         | Forzalavoro\_Società, Forzalavoro\_Retribuzione, Forzalavoro\_PosizioneGeografica, Forzalavoro\_Prestazioni, Forzalavoro\_CompetenzaPersona, Forzalavoro\_NomeLavoratore, Forzalavoro\_NomeSuperiore, Forzalavoro\_TitoloLavoratore, Forzalavoro\_DatiDemografici, Forzalavoro\_Mansione, Forzalavoro\_Impiego, Forzalavoro\_Posizione |
| Forzalavoro\_Data                   | Giorni, settimane, mesi e anni.                                                                             | |
| Forzalavoro\_DatiDemografici           | Data di nascita, sesso, origine etnica e stato civile                                                   | |
| Forzalavoro\_Impiego             | Data di inizio, data di fine e data della transizione                                                                  | |
| Forzalavoro\_PosizioneGeografica     | Città, provincia, codice postale e stato/regione o provincia                                                           | |
| Forzalavoro\_Mansione                    | Funzione, tipo e titolo                                                                                  | |
| Forzalavoro\_CompetenzaPreferitaMansione      | Importanza, valutazione, competenza e il livello di competenza                                                                 | Forzalavoro\_Competenza, Forzalavoro\_Mansione |
| Forzalavoro\_AssegnazionePosizionePrecedente | Motivo dell'assegnazione, data di inizio, data di fine e mansione                                                           | Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_Prestazioni            | Valutazione, descrizione e modello di valutazione                                                                      | |
| Forzalavoro\_CompetenzaPersona            | Livello, data livello e competenza                                                                               | Forzalavoro\_Competenza |
| Forzalavoro\_AnalisiCompetenzaPersona    | Certificato, livello, data livello e competenza                                                                    | Forzalavoro\_NomeLavoratore, Forzalavoro\_Competenza |
| Forzalavoro\_Posizione               | Reparto, FTE, posizione, tipo di posizione e titolo                                                        | |
| Forzalavoro\_TendenzaPosizione          | Posizioni nel tempo, FTE e mansione                                                                          | Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_NomeSuperiore    | Nome, cognome e nome completo                                                                       | |
| Forzalavoro\_Competenza                  | Competenza, tipo di competenza e valutazione                                                                              | |
| Forzalavoro\_LavoratoreCongedato       | Lavoratori congedati, data del congedo, titolo, posizione e mansione                                             | Forzalavoro\_Società, Forzalavoro\_Retribuzione, Forzalavoro\_PosizioneGeografica, Forzalavoro\_Prestazioni, Forzalavoro\_NomeLavoratore, Forzalavoro\_NomeSuperiore, Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_TitoloLavoratore, Forzalavoro\_DatiDemografici, Forzalavoro\_Impiego, Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_NomeLavoratore             | Nome, cognome e nome completo                                                                       | |
| Forzalavoro\_TitoloLavoratore            | Titolo e data di anzianità                                                                                   | |
| Forzalavoro\_TendenzaLavoratore             | Lavoratori nel tempo, numero di dipendenti, società e posizione                                                        | Forzalavoro\_Società, Forzalavoro\_Retribuzione, Forzalavoro\_PosizioneGeografica, Forzalavoro\_Prestazioni, Forzalavoro\_NomeLavoratore, Forzalavoro\_NomeSuperiore, Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_TitoloLavoratore, Forzalavoro\_DatiDemografici, Forzalavoro\_Impiego, Forzalavoro\_Mansione |
