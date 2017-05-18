---
title: Contenuto Power BI di retribuzioni e benefit
description: "In questo argomento vengono fornite le informazioni sul contenuto Power BI di retribuzioni e benefit di Dynamics 365 for Operations. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare un pacchetto di contenuti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: c3bb41aa8823e5ed59c33014c05ed76bb50e6843
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="compensation-and-benefits-power-bi-content"></a>Contenuto Power BI di retribuzioni e benefit

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite le informazioni sul contenuto Power BI di retribuzioni e benefit di Dynamics 365 for Operations. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare un pacchetto di contenuti.

<a name="accessing-the-content-pack"></a>Accesso al pacchetto di contenuti
--------------------------

Il pacchetto di contenuti di retribuzioni e benefit è disponibile nella libreria delle risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni su come scaricare il pacchetto di contenuti e collegarlo ai dati Microsoft Dynamics 365 for Operations, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel pacchetto di contenuti
Dopo aver collegato il pacchetto di contenuti ai dati di Microsoft Dynamics 365 for Operations, nei report vengono visualizzati i dati dell'organizzazione. Se non è mai stato usato Microsoft Power BI in precedenza, è possibile ottenere informazioni in merito nella [pagina Formazione guidata a Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel pacchetto di contenuti dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                     | Contenuto                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analisi di retribuzioni e benefit | Dipendenti con retribuzione oraria e quelli stipendiati per società, retribuzione oraria media, salario medio, dipendenti per tipo di impiego e iscrizione al piano |
| Benefit dei dipendenti          | Iscrizione del dipendente per benefit selezionato                                                                                               |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati di Dynamics 365 for Operations vengono utilizzati per compilare i report nel pacchetto di contenuti di retribuzioni e benefit. Nella tabella seguente vengono illustrate le entità su cui è stato basato il pacchetto di contenuti.

| Entità                            | Contenuto                                                                                                   | Relazioni con altre entità                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Forzalavoro\_OffsetCalendario         | Offset di calendario su report suddivisi                                                                          | Forzalavoro\_AssegnazionePosizionePrecedente Forzalavoro\_TendenzaPosizione Forzalavoro\_TendenzaLavoratore Forzalavoro\_LavoratoreCongedato                                                                                                                                                                                                                     |
| Forzalavoro\_Società                | Società in base a cui filtrare i report                                                                             | Forzalavoro\_RetribuzioneCorrente Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                        |
| Forzalavoro\_Retribuzione           | Tariffa retributiva e frequenza nel tempo                                                                           | Forzalavoro\_RetribuzioneCorrente Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                        |
| Forzalavoro\_RetribuzioneCorrente    | Tariffa retributiva e frequenza a partire dalla data corrente                                                              | Forzalavoro\_Società Forzalavoro\_Retribuzione Forzalavoro\_DatiDemografici Forzalavoro\_Mansione Forzalavoro\_Posizione                                                                                                                                                                                                                            |
| Forzalavoro\_PosizioneCorrente        | Posizione a partire dalla data corrente, equivalente a tempo pieno (FTE), posizioni aperte e posizioni da aperte ad assegnate | Forzalavoro\_Mansione Forzalavoro\_Posizione                                                                                                                                                                                                                                                                                               |
| Forzalavoro\_LavoratoreCorrente          | Lavoratori a partire dalla data corrente, età e numero di dipendenti                                                         | Forzalavoro\_Società Forzalavoro\_Retribuzione Forzalavoro\_PosizioneGeografica Forzalavoro\_Prestazioni Forzalavoro\_NomeLavoratore Forzalavoro\_NomeSuperiore Forzalavoro\_TitoloLavoratore Forzalavoro\_DatiDemografici Forzalavoro\_Mansione Forzalavoro\_Impiego Forzalavoro\_Posizione Forzalavoro\_BenefitLavoratore                                            |
| Forzalavoro\_Data                   | Giorni, settimane, mesi e anni.                                                                             | Forzalavoro\_AssegnazionePosizionePrecedente Forzalavoro\_TendenzaPosizione Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                     |
| Forzalavoro\_DatiDemografici           | Data di nascita, sesso, origine etnica e stato civile                                                   | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_Impiego             | Data di inizio, data di fine e data della transizione                                                                  | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_PosizioneGeografica     | Città, provincia, codice postale e stato/regione o provincia                                                           | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_Mansione                    | Funzione, tipo e titolo                                                                                  | Forzalavoro\_PosizioneCorrente Forzalavoro\_LavoratoreCorrente                                                                                                                                                                                                                                                                              |
| Forzalavoro\_AssegnazionePosizionePrecedente | Motivo dell'assegnazione, data di inizio, data di fine e mansione                                                           | Forzalavoro\_OffsetCalendario Forzalavoro\_Data Forzalavoro\_Mansione Forzalavoro\_Posizione                                                                                                                                                                                                                                                     |
| Forzalavoro\_Prestazioni            | Valutazione, descrizione e modello di valutazione                                                                      | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_Posizione               | Reparto, FTE, posizione, tipo di posizione e titolo                                                        | Forzalavoro\_PosizioneCorrente Forzalavoro\_LavoratoreCorrente                                                                                                                                                                                                                                                                              |
| Forzalavoro\_TendenzaPosizione          | Posizioni nel tempo, FTE e mansione                                                                          | Forzalavoro\_OffsetCalendario Forzalavoro\_Data Forzalavoro\_Mansione Forzalavoro\_Posizione                                                                                                                                                                                                                                                     |
| Forzalavoro\_NomeSuperiore    | Nome, cognome e nome completo                                                                       | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_Competenza                  | Competenza, tipo di competenza e valutazione                                                                              |                                                                                                                                                                                                                                                                                                                                  |
| Forzalavoro\_LavoratoreCongedato       | Lavoratori congedati, data del congedo, titolo, posizione e mansione                                             | Forzalavoro\_Società Forzalavoro\_Retribuzione Forzalavoro\_PosizioneGeografica Forzalavoro\_Prestazioni Forzalavoro\_NomeLavoratore Forzalavoro\_NomeSuperiore Forzalavoro\_OffsetCalendario Forzalavoro\_Data Forzalavoro\_TitoloLavoratore Forzalavoro\_DatiDemografici Forzalavoro\_Impiego Forzalavoro\_Mansione Forzalavoro\_Posizione Forzalavoro\_BenefitLavoratore |
| Forzalavoro\_BenefitLavoratore          | Data di validità, opzione di benefit, piano di benefit e tipo di benefit                                             | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_NomeLavoratore             | Nome, cognome e nome completo                                                                       | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_TitoloLavoratore            | Titolo e data di anzianità                                                                                   | Forzalavoro\_LavoratoreCorrente Forzalavoro\_LavoratoreCongedato Forzalavoro\_TendenzaLavoratore                                                                                                                                                                                                                                                       |
| Forzalavoro\_TendenzaLavoratore             | Lavoratori nel tempo, numero di dipendenti, società e posizione                                                        | Forzalavoro\_Società Forzalavoro\_Retribuzione Forzalavoro\_PosizioneGeografica Forzalavoro\_Prestazioni Forzalavoro\_NomeLavoratore Forzalavoro\_NomeSuperiore Forzalavoro\_OffsetCalendario Forzalavoro\_Data Forzalavoro\_TitoloLavoratore Forzalavoro\_DatiDemografici Forzalavoro\_Impiego Forzalavoro\_Mansione Forzalavoro\_BenefitLavoratore                     |

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Queste misure calcolate vengono quindi utilizzate per calcolare gli indicatori di prestazione chiave (KPI) e i report utilizzati nel pacchetto di contenuti. Se si desidera includere calcoli aggiuntivi nei report e nel dashboard, è possibile scaricare e modificare il file CompensationandBenefits.pbix da LCS. Questo file è il modello dati predefinito utilizzato per creare il pacchetto di contenuti. Una volta apportate le modifiche, è possibile creare un pacchetto di contenuti per l'organizzazione e un dashboard che contengono le informazioni aggiunte.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





