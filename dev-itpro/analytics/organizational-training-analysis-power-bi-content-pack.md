---
title: Organizational Training Power BI content
description: "In questo argomento viene descritto Dynamics 365 per le operazioni di contenuto organizzativo di potenza di formazione BI. Descrive come accedere al collo di contenuto e viene descritto il modello dati e le entità che sono stati utilizzati per sviluppare un pacchetto di contenuto."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 104164f8ffd0d2bc3a64bf15d2fb5213234046ce
ms.lasthandoff: 03/31/2017


---

# <a name="organizational-training-power-bi-content"></a>Organizational Training Power BI content

In questo argomento viene descritto Dynamics 365 per le operazioni di contenuto organizzativo di potenza di formazione BI. Descrive come accedere al collo di contenuto e viene descritto il modello dati e le entità che sono stati utilizzati per sviluppare un pacchetto di contenuto.

<a name="accessing-the-content-pack"></a>Accesso al collo di contenuto
--------------------------

Per trovare il collo organizzativo del contenuto di formazione nella raccolta delle risorse condivise nei servizi (LCS) del ciclo di vita di Microsoft Dynamics. Per ulteriori informazioni su come download del collo di contenuto e collegarlo al sistema Microsoft Dynamics 365 per le operazioni dati, vedere [di Power BI nel contenuto LC da Microsoft e dai partner power-bi-content-microsoft-partners.md] ().

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel collo di contenuto
Dopo aver collegato il collo al contenuto Dynamics 365 per i dati delle operazioni, i report sono illustrati i dati dell'organizzazione. Se non è stato utilizzato mai potenza di Microsoft BI prima, possono ottenere ulteriori informazioni sulla Guida [quattro pagina per Power BI] (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel collo di contenuto hanno e i grafici da tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report          | Contenuto                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analisi del corso | Registrazione per ubicazione, partecipanti al corso dallo stato e elenco di registrazione |
| Tipi di corso    | Tipi di corsi in base alla competenza                                                       |

È possibile filtrare i grafici e i mattonelle nei report e appuntate i grafici e i mattonelle al dashboard. Per ulteriori informazioni su come filtrarne e nel perno Power BI, vedere [creare e configurare un dashboard] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Dynamics 365 per i dati delle operazioni viene utilizzato per inserire i report in colli organizzativo del contenuto di formazione. Nella tabella seguente vengono illustrate le entità che il collo di contenuto è basato su.

| Entità                    | Contenuto                                                         | Relazioni con altre entità                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Addestramento\_CalendarOffset  | Contropartite al calendario della sezione con report                                | Addestramento\_CourseAgenda che prepara CourseAttendees\_                                                                                                                                                   |
| Società\_di formazione         | Società per filtrare i report per                                   | Addestramento\_CourseAgenda che prepara CourseAttendees\_                                                                                                                                                   |
| Corso\_di formazione          | Corso, Descrizione, nome dell'istruttore, l'ubicazione, la stanza e lo stato | Addestramento\_CourseAgenda che prepara\_CourseAttendees che prepara CourseSkill\_                                                                                                                             |
| Addestramento\_CourseAgenda    | Agenda, corso e ore di inizio e fine                          | Società\_di formazione che prepara\_CalendarOffset che prepara la data\_che prepara corso\_                                                                                                                         |
| Addestramento\_CourseAttendees | Nome, lo stato, processo e data di registrazione                         | Società\_di formazione che prepara\_CalendarOffset che prepara la data\_che consente di preparare Demographics\_che prepara lavoro\_che prepara corso\_che prepara\_WorkerName che prepara\_WorkerTitle che prepara posizione\_di formazione sull'utilizzo\_ |
| Addestramento\_CourseSkill     | Competenza, tipo e a livello                                     | Corso\_di formazione                                                                                                                                                                                   |
| Data\_di formazione            | Giorni, settimane, mesi e anni                                   | Addestramento\_CourseAgenda che prepara CourseAttendees\_                                                                                                                                                   |
| Demographics\_di formazione    | Data di nascita, il sesso, l'origine etnica e lo stato civile         | Addestramento\_CourseAgenda che prepara CourseAttendees\_                                                                                                                                                   |
| Impiego\_di formazione      | Data di inizio, Data di fine e data della transizione                        | Addestramento\_CourseAgenda che prepara CourseAttendees\_                                                                                                                                                   |
| Processo\_di formazione             | Funzione, il tipo e titolo                                        | Addestramento\_CourseAgenda che prepara CourseAttendees\_                                                                                                                                                   |
| Posizione\_di formazione        | Ubicazione, funzione e a tempo pieno equivalente (FTE)                  | Addestramento\_CourseAgenda che prepara CourseAttendees\_                                                                                                                                                   |
| Addestramento\_WorkerName      | Nome, e cognome nome completo                             | Addestramento\_CourseAttendees                                                                                                                                                                          |
| Addestramento\_WorkerTitle     | Data di anzianità e del titolo                                         | Addestramento\_CourseAttendees                                                                                                                                                                          |

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Le misure calcolate vengono utilizzate per calcolare gli indicatori di prestazione chiave (KPIs) e i report utilizzati nel collo di contenuto. Se si desidera includere i calcoli aggiuntive nei report e dashboard, è possibile scaricare e modificare il file di Training.pbix da LC. Questo file è il modello dati predefinito utilizzato per creare il collo di contenuto. Dopo aver apportato le modifiche, è possibile creare un collo e il dashboard contenuto delle persone che contengono informazioni che sono stati aggiunti.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



