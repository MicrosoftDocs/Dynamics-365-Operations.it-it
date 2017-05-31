---
title: Contenuto Power BI sulla selezione del personale
description: "In questo argomento vengono fornite le informazioni Power BI sulla selezione del personale in Dynamics 365 for Operations. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare un pacchetto di contenuti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4b12a2c8983cf7bef770417f76df324293f06fb2
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="recruiting-power-bi-content"></a>Contenuto Power BI sulla selezione del personale

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite le informazioni Power BI sulla selezione del personale in Dynamics 365 for Operations. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare un pacchetto di contenuti.

<a name="accessing-the-content-pack"></a>Accesso al pacchetto di contenuti
--------------------------

Il pacchetto di contenuti sulla selezione del personale è disponibile nella libreria delle risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni su come scaricare il pacchetto di contenuti e collegarlo ai dati Microsoft Dynamics 365 for Operations, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel pacchetto di contenuti
Dopo aver collegato il pacchetto di contenuti ai dati di Microsoft Dynamics 365 for Operations, nei report vengono visualizzati i dati dell'organizzazione. Se non è mai stato usato Microsoft Power BI in precedenza, è possibile ottenere informazioni in merito nella [pagina Formazione guidata a Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel pacchetto di contenuti dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                       | Contenuto                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Analisi dei candidati           | Candidati per mansione, origini del candidato, candidati per ubicazione e numero totale di candidati           |
| Stato candidati             | Candidati per tipo e stato e stato del candidato                                                    |
| Dati demografici dei candidati       | Candidati per età e sesso e candidati per livello di istruzione e stato                             |
| Analisi della selezione del personale          | Indice di assunzione netto, giorni medi di assunzione, percentuale di assunzioni errate e costi di selezione                    |
| Analisi progetto di selezione | Numero di progetti di selezione, aperture per progetto di selezione e candidati per progetto di selezione |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati di Dynamics 365 for Operations vengono utilizzati per compilare i report nel pacchetto di contenuti sulla selezione del personale. Nella tabella seguente vengono illustrate le entità su cui è stato basato il pacchetto di contenuti.

| Entità                          | Contenuto                                                         | Relazioni con altre entità                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Selezione\_Candidato           | Candidati, candidati assunti, indice di assunzione netto e costi          | Selezione\_NomeCandidato Selezione\_Società Selezione\_OffsetCalendario Selezione\_Data Selezione\_UbicazioneGeografica Selezione\_DatiDemografici Selezione\_Mansione Selezione\_Media Selezione\_ProgettodiSelezione                                |
| Selezione\_NomeCandidato       | Nome, cognome e nome completo del candidato                   | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_OffsetCalendario      | Offset di calendario su report suddivisi                                | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_Società             | Società in base a cui filtrare i report                                   | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_Data                | Giorni, settimane, mesi e anni.                                   | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_DatiDemografici        | Data di nascita, sesso, origine etnica e stato civile         | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_CandidatoImpiegato   | Candidato, prestazioni, data di inizio e tipo di candidato           | Selezione\_Società Selezione\_OffsetCalendario Selezione\_Data Selezione\_UbicazioneGeografica Selezione\_NomeCandidato Selezione\_Impiego Selezione\_Prestazioni Selezione\_Mansione Selezione\_Media Selezione\_ProgettodiSelezione          |
| Selezione\_Impiego          | Data di inizio, data di fine e data della transizione                        | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_UbicazioneGeografica  | Città, provincia, codice postale e stato/regione o provincia                 | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_Mansione                 | Funzione, tipo e titolo                                        | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_Media               | Origine dei candidati                                             | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_Prestazioni         | Valutazione, descrizione e modello di valutazione                            | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_ProgettodiSelezione  | Descrizione del progetto, stato del progetto e aperture                | Selezione\_Candidato Selezione\_CandidatoImpiegato Selezione\_CandidatoCongedato                                                                                                                                                               |
| Selezione\_CandidatoCongedato | Candidati congedati, motivo, prestazioni e data di fine rapporto | Selezione\_Società Selezione\_OffsetCalendario Selezione\_Data Selezione\_UbicazioneGeografica Selezione\_Prestazioni Selezione\_DatiDemografici Selezione\_Impiego Selezione\_Media Selezione\_ProgettodiSelezione Selezione\_NomeCandidato |

Queste entità sono state utilizzate per creare le misure calcolate. Queste misure calcolate vengono quindi utilizzate per calcolare gli indicatori di prestazione chiave (KPI) e i report utilizzati nel pacchetto di contenuti. Se si desidera includere calcoli aggiuntivi nei report e nel dashboard, è possibile scaricare e modificare il file Recruiting.pbix da LCS. Questo file è il modello dati predefinito utilizzato per creare il pacchetto di contenuti. Una volta apportate le modifiche, è possibile creare un pacchetto di contenuti per l'organizzazione e un dashboard che contengono le informazioni aggiunte.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





