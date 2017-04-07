---
title: Contenuto di selezione di Power BI
description: "In questo argomento viene descritto Dynamics 365 per le operazioni di contenuto del personale di Power BI. Descrive come accedere ai report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità che sono stati utilizzati per sviluppare un pacchetto di contenuto."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Contenuto di selezione di Power BI

In questo argomento viene descritto Dynamics 365 per le operazioni di contenuto del personale di Power BI. Descrive come accedere ai report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità che sono stati utilizzati per sviluppare un pacchetto di contenuto.

<a name="accessing-the-content-pack"></a>Accesso al collo di contenuto
--------------------------

Per trovare il collo di contenuto del personale nella raccolta delle risorse condivise nei servizi (LCS) del ciclo di vita di Microsoft Dynamics. Per ulteriori informazioni su come download del collo di contenuto e collegarlo al sistema Microsoft Dynamics 365 per le operazioni dati, vedere [di Power BI nel contenuto LC da Microsoft e dai partner power-bi-content-microsoft-partners.md] ().

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel collo di contenuto
Dopo aver collegato il collo al contenuto Dynamics 365 per i dati delle operazioni, i report sono illustrati i dati dell'organizzazione. Se non è stato utilizzato mai potenza di Microsoft BI prima, possono ottenere ulteriori informazioni sulla Guida [quattro pagina per Power BI] (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel collo di contenuto hanno e i grafici da tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                       | Contenuto                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Analisi del candidato           | Candidati dal processo, da origini del candidato, candidati per ubicazione e il numero totale dei candidati           |
| Stato candidato             | Candidati per tipo e lo stato e lo stato del candidato                                                    |
| Demographics del candidato       | Candidati dalla validità e sesso e candidati dal livello di formazione e lo stato                             |
| Analisi del personale          | Report netto di assunzione, il tempo medio alle assunzioni, percentuale di non idonei assunzioni e costi del personale                    |
| Analisi del progetto di selezione | Numero di progetti di selezione, di aperture dal progetto di selezione e candidati dal progetto di selezione |

È possibile filtrare i grafici e i mattonelle nei report e appuntate i grafici e i mattonelle al dashboard. Per ulteriori informazioni su come filtrarne e nel perno Power BI, vedere [creare e configurare un dashboard] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Dynamics 365 per i dati delle operazioni viene utilizzato per inserire i report in colli di contenuto del personale. Nella tabella seguente vengono illustrate le entità che il collo di contenuto è basato su.

| Entità                          | Contenuto                                                         | Relazioni con altre entità                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Candidato di selezione\_           | Candidati i dipendenti, candidati, Report di assunzione di rete e costi          | \_ApplicantName selezione del personale che la società\_che selezione\_CalendarOffset Recuriting\_\_data di GeographicLocation selezione del personale il Demographics\_selezione\_che il processo\_selezione\_che\_che reclutano\_RecruitmentProject                                |
| \_di selezione ApplicantName       | Nome del candidato, e cognome nome completo                   | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| \_di selezione CalendarOffset      | Contropartite al calendario della sezione con report                                | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| Società di selezione\_             | Società per filtrare i report per                                   | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| Data di selezione\_                | Giorni, settimane, mesi e anni                                   | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| Demographics di selezione\_        | Data di nascita, il sesso, l'origine etnica e lo stato civile         | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| \_di selezione EmployedApplicant   | Candidato, prestazioni, data di inizio e tipo del candidato           | Società di selezione\_in\_CalendarOffset selezione del personale la data\_a\_GeographicLocation selezione del personale\_ApplicantName che il lavoro\_che la prestazione\_che il processo\_selezione\_che\_che reclutano\_RecruitmentProject          |
| Impiego di selezione\_          | Data di inizio, Data di fine e data della transizione                        | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| \_di selezione GeographicLocation  | Città, provincia, codice postale e stato/regione o provincia                 | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| Processo di selezione\_                 | Funzione, il tipo e titolo                                        | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| Selezione media\_               | Origine dei candidati                                             | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| Prestazioni di selezione\_         | Valutazione, la descrizione e modello di determinazione prezzo                            | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| \_di selezione RecruitmentProject  | Descrizione del progetto, lo stato del progetto e aperture                | Candidato di selezione\_in\_ employedApplicant selezione del personale TerminatedApplicant\_                                                                                                                                                               |
| \_di selezione TerminatedApplicant | Candidati terminati, motivo, le prestazioni e data di scadenza | Società di selezione\_in\_CalendarOffset selezione del personale la data\_a\_GeographicLocation selezione del personale\_che il Demographics\_che il lavoro\_che il supporto media\_che reclutano\_RecruitmentProject che il ApplicantName\_ |

Le entità sono state utilizzate per creare le misure calcolate. Le misure calcolate vengono utilizzate per calcolare gli indicatori di prestazione chiave (KPIs) e i report utilizzati nel collo di contenuto. Se si desidera includere i calcoli aggiuntive nei report e dashboard, è possibile scaricare e modificare il file di Recruiting.pbix da LC. Questo file è il modello dati predefinito utilizzato per creare il collo di contenuto. Dopo aver apportato le modifiche, è possibile creare un collo e il dashboard contenuto delle persone che contengono informazioni che sono stati aggiunti.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



