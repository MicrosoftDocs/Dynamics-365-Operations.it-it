---
title: Contenuto Power BI sulla formazione nell'organizzazione
description: "In questo argomento viene descritto il contenuto Power BI sulla formazione nell'organizzazione in Finance and Operations. Spiega come accedere al pacchetto di contenuti e descrive il modello dati e le entità che sono stati utilizzati per creare il pacchetto di contenuti."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 26499bf5423bc3711d110bd7e548eda238162b7a
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="organizational-training-power-bi-content"></a>Contenuto Power BI sulla formazione nell'organizzazione

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto il contenuto Power BI sulla formazione nell'organizzazione in Finance and Operations. Spiega come accedere al pacchetto di contenuti e descrive il modello dati e le entità che sono stati utilizzati per creare il pacchetto di contenuti.

<a name="accessing-the-content-pack"></a>Accesso al pacchetto di contenuti
--------------------------

Il pacchetto di contenuti sulla formazione nell'organizzazione è disponibile nella libreria delle risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni su come scaricare il pacchetto di contenuti e collegarlo ai dati Microsoft Dynamics 365 for Finance and Operations, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel pacchetto di contenuti
Dopo aver collegato il pacchetto di contenuti ai dati di Finance and Operations, nei report vengono visualizzati i dati dell'organizzazione. Se non è mai stato usato Microsoft Power BI in precedenza, è possibile ottenere informazioni in merito nella [pagina Formazione guidata a Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel pacchetto di contenuti dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report          | Contenuto                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analisi del corso | Registrazione in base all'ubicazione, partecipanti al corso in base allo stato ed elenco di registrazione |
| Tipi di corso    | Tipi di corsi in base alla competenza                                                       |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati di Finance and Operations vengono utilizzati per compilare i report nel pacchetto di contenuti sulla formazione nell'organizzazione. Nella tabella seguente vengono illustrate le entità su cui è stato basato il pacchetto di contenuti.

| Entità                    | Contenuto                                                         | Relazioni con altre entità                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Formazione\_OffsetCalendario  | Offset di calendario su report suddivisi                                | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso                                                                                                                                                   |
| Formazione\_Società         | Società in base a cui filtrare i report                                   | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso                                                                                                                                                   |
| Formazione\_Corso          | Corso, descrizione, nome istruttore, ubicazione, sala e stato | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso Formazione\_CompetenzaCorso                                                                                                                             |
| Formazione\_ProgrammaCorso    | Programma, corso e orario di inizio e fine                          | Formazione\_Società Formazione\_OffsetCalendario Formazione\_Data Formazione\_Corso                                                                                                                         |
| Formazione\_PartecipantiCorso | Nome, stato, mansione e data di registrazione                         | Formazione\_Società Formazione\_OffsetCalendario Formazione\_Data Formazione\_DatiDemografici Formazione\_Impiego Formazione\_Corso Formazione\_NomeLavoratore Formazione\_TitoloLavoratore Formazione\_Mansione Formazione\_Posizione |
| Formazione\_CompetenzaCorso     | Competenza, tipo di competenza e livello                                     | Formazione\_Corso                                                                                                                                                                                   |
| Formazione\_Data            | Giorni, settimane, mesi e anni.                                   | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso                                                                                                                                                   |
| Formazione\_DatiDemografici    | Data di nascita, sesso, origine etnica e stato civile         | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso                                                                                                                                                   |
| Formazione\_Impiego      | Data di inizio, data di fine e data della transizione                        | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso                                                                                                                                                   |
| Formazione\_Mansione             | Funzione, tipo e titolo                                        | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso                                                                                                                                                   |
| Formazione\_Posizione        | Posizione, titolo ed equivalente a tempo pieno (FTE)                  | Formazione\_ProgrammaCorso Formazione\_PartecipantiCorso                                                                                                                                                   |
| Formazione\_NomeLavoratore      | Nome, cognome e nome completo                             | Formazione\_PartecipantiCorso                                                                                                                                                                          |
| Formazione\_TitoloLavoratore     | Titolo e data di anzianità                                         | Formazione\_PartecipantiCorso                                                                                                                                                                          |

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Queste misure calcolate vengono quindi utilizzate per calcolare gli indicatori di prestazione chiave (KPI) e i report utilizzati nel pacchetto di contenuti. Se si desidera includere calcoli aggiuntivi nei report e nel dashboard, è possibile scaricare e modificare il file Training.pbix da LCS. Questo file è il modello dati predefinito utilizzato per creare il pacchetto di contenuti. Una volta apportate le modifiche, è possibile creare un pacchetto di contenuti per l'organizzazione e un dashboard che contengono le informazioni aggiunte.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





