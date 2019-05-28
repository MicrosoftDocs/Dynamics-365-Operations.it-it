---
title: Contenuto Power BI di retribuzioni e benefit
description: In questo argomento vengono fornite le informazioni sul contenuto Power BI di retribuzioni e benefit di Finance and Operations.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6834940b16749461066e8f1000cbb7c2d4371109
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548745"
---
# <a name="compensation-and-benefits-power-bi-content"></a>Contenuto Power BI di retribuzioni e benefit

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite le informazioni sul contenuto Power BI di retribuzioni e benefit di Finance and Operations. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel pacchetto di contenuti
Dopo aver collegato il pacchetto di contenuti ai dati di Finance and Operations, nei report vengono visualizzati i dati dell'organizzazione. Se non è mai stato usato Microsoft Power BI in precedenza, è possibile ottenere informazioni in merito nella pagina [Formazione guidata a Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel pacchetto di contenuti dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                     | Contenuto                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analisi di retribuzioni e benefit | Dipendenti con retribuzione oraria e quelli stipendiati per società, retribuzione oraria media, salario medio, dipendenti per tipo di impiego e iscrizione al piano |
| Benefit dei dipendenti          | Iscrizione del dipendente per benefit selezionato                                                                                               |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati di Finance and Operations vengono utilizzati per compilare i report nel pacchetto di contenuti di retribuzioni e benefit. Nella tabella seguente vengono illustrate le entità su cui è stato basato il pacchetto di contenuti.

| Entità                            | Contenuto                                                                                                   | Relazioni con altre entità |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Forzalavoro\_OffsetCalendario         | Offset di calendario su report suddivisi                                                                          | Forzalavoro\_AssegnazionePosizionePrecedente, Forzalavoro\_TendenzaPosizione, Forzalavoro\_TendenzaLavoratore, Forzalavoro\_LavoratoreCongedato |
| Forzalavoro\_Società                | Società in base a cui filtrare i report                                                                             | Forzalavoro\_RetribuzioneCorrente, Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, LavoratoreCongedato\_TendenzaLavoratore |
| Forzalavoro\_Retribuzione           | Tariffa retributiva e frequenza nel tempo                                                                           | Forzalavoro\_RetribuzioneCorrente, Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, LavoratoreCongedato\_TendenzaLavoratore |
| Forzalavoro\_RetribuzioneCorrente    | Tariffa retributiva e frequenza a partire dalla data corrente                                                              | Forzalavoro\_Società, Forzalavoro\_Compensazione, Forzalavoro\_Datidemografici, Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_PosizioneCorrente        | Posizione a partire dalla data corrente, equivalente a tempo pieno (FTE), posizioni aperte e posizioni da aperte ad assegnate | Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_LavoratoreCorrente          | Lavoratori a partire dalla data corrente, età e numero di dipendenti                                                         | Forzalavoro\_Società, Forzalavoro\_Retribuzione, Forzalavoro\_PosizioneGeografica, Forzalavoro\_Prestazioni, Forzalavoro\_NomeLavoratore, Forzalavoro\_NomeSuperiore, Forzalavoro\_TitoloLavoratore, Forzalavoro\_DatiDemografici, Forzalavoro\_Mansione, Forzalavoro\_Impiego, Forzalavoro\_Posizione, Forzalavoro\_BenefitLavoratore |
| Forzalavoro\_Data                   | Giorni, settimane, mesi e anni.                                                                             | Forzalavoro\_AssegnazionePosizionePrecedente, Forzalavoro\_TendenzaPosizione, Forzalavoro\_TendenzaLavoratore, Forzalavoro\_LavoratoreCongedato |
| Forzalavoro\_DatiDemografici           | Data di nascita, sesso, origine etnica e stato civile                                                   | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_Impiego             | Data di inizio, data di fine e data della transizione                                                                  | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_PosizioneGeografica     | Città, provincia, codice postale e stato/regione o provincia                                                           | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_Mansione                    | Funzione, tipo e titolo                                                                                  | Forzalavoro\_PosizioneCorrente, Forzalavoro\_LavoratoreCorrente |
| Forzalavoro\_AssegnazionePosizionePrecedente | Motivo dell'assegnazione, data di inizio, data di fine e mansione                                                           | Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_Prestazioni            | Valutazione, descrizione e modello di valutazione                                                                      | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_Posizione               | Reparto, FTE, posizione, tipo di posizione e titolo                                                        | Forzalavoro\_PosizioneCorrente, Forzalavoro\_LavoratoreCorrente |
| Forzalavoro\_TendenzaPosizione          | Posizioni nel tempo, FTE e mansione                                                                          | Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_Mansione, Forzalavoro\_Posizione |
| Forzalavoro\_NomeSuperiore    | Nome, cognome e nome completo                                                                       | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_Competenza                  | Competenza, tipo di competenza e valutazione                                                                              | |
| Forzalavoro\_LavoratoreCongedato       | Lavoratori congedati, data del congedo, titolo, posizione e mansione                                             | Forzalavoro\_Società, Forzalavoro\_Retribuzione, Forzalavoro\_PosizioneGeografica, Forzalavoro\_Prestazioni, Forzalavoro\_NomeLavoratore, Forzalavoro\_NomeSuperiore, Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_TitoloLavoratore, Forzalavoro\_DatiDemografici, Forzalavoro\_Impiego, Forzalavoro\_Mansione, Forzalavoro\_Posizione, Forzalavoro\_BenefitLavoratore |
| Forzalavoro\_BenefitLavoratore          | Data di validità, opzione di benefit, piano di benefit e tipo di benefit                                             | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_NomeLavoratore             | Nome, cognome e nome completo                                                                       | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_TitoloLavoratore            | Titolo e data di anzianità                                                                                   | Forzalavoro\_LavoratoreCorrente, Forzalavoro\_LavoratoreCongedato, Forzalavoro\_TendenzaLavoratore |
| Forzalavoro\_TendenzaLavoratore            | Lavoratori nel tempo, numero di dipendenti, società e posizione                                                        | Forzalavoro\_Società, Forzalavoro\_Retribuzione, Forzalavoro\_PosizioneGeografica, Forzalavoro\_Prestazioni, Forzalavoro\_NomeLavoratore, Forzalavoro\_NomeSuperiore, Forzalavoro\_OffsetCalendario, Forzalavoro\_Data, Forzalavoro\_TitoloLavoratore, Forzalavoro\_DatiDemografici, Forzalavoro\_Impiego, Forzalavoro\_Mansione, Forzalavoro\_BenefitLavoratore |
