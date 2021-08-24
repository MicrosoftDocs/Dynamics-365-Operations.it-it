---
title: Contenuto Power BI sulla formazione nell'organizzazione
description: Questo argomento descrive il contenuto Finance and Operations - Formazione organizzativa Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cd48c12ea3ea31904c437f678888a51e5381cfcfbeef0e1c709858b0c6cb857d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763550"
---
# <a name="organizational-training-power-bi-content"></a>Contenuto Power BI sulla formazione nell'organizzazione

[!include [banner](../includes/banner.md)]

Questo argomento descrive il contenuto Finance and Operations - Formazione organizzativa Power BI.

## <a name="reports-that-are-included-in-the-content-pack"></a>Report inclusi nel pacchetto di contenuti
Dopo aver collegato il pacchetto di contenuti ai dati, nei report vengono visualizzati i dati dell'organizzazione. Se non è mai stato usato Microsoft Power BI in precedenza, è possibile ottenere informazioni in merito nella pagina [Formazione guidata a Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). I report inclusi nel pacchetto di contenuti dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report          | Contenuto                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analisi del corso | Registrazione in base all'ubicazione, partecipanti al corso in base allo stato ed elenco di registrazione |
| Tipi di corso    | Tipi di corsi in base alla competenza                                                       |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati dell'applicazione vengono utilizzati per compilare i report nel pacchetto di contenuti sulla formazione nell'organizzazione. Nella tabella seguente vengono illustrate le entità su cui è stato basato il pacchetto di contenuti.

| Entità                    | Contenuto                                                         | Relazioni con altre entità |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| Formazione\_OffsetCalendario  | Offset di calendario su report suddivisi                                | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso |
| Formazione\_Società         | Società in base a cui filtrare i report                                   | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso |
| Formazione\_Corso          | Corso, Descrizione, nome istruttore, ubicazione, sala e stato | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso, Formazione\_CompetenzaCorso |
| Formazione\_ProgrammaCorso    | Programma, corso e orario di inizio e fine                          | Formazione\_Società, Formazione\_OffsetCalendario, Formazione\_Data, Formazione\_Corso |
| Formazione\_PartecipantiCorso | Nome, stato, mansione e data di registrazione                         | Formazione\_Società, Formazione\_OffsetCalendario, Formazione\_Data, Formazione\_DatiDemografici, Formazione\_Impiego, Formazione\_Corso, Formazione\_NomeLavoratore, Formazione\_TitoloLavoratore, Formazione\_Mansione, Formazione\_Posizione |
| Formazione\_CompetenzaCorso     | Competenza, tipo di competenza e livello                                     | Formazione\_Corso |
| Formazione\_Data            | Giorni, settimane, mesi e anni.                                   | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso |
| Formazione\_DatiDemografici    | Data di nascita, sesso, origine etnica e stato civile         | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso |
| Formazione\_Impiego      | Data di inizio, data di fine e data della transizione                        | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso |
| Formazione\_Mansione             | Funzione, tipo e titolo                                        | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso |
| Formazione\_Posizione        | Posizione, titolo ed equivalente a tempo pieno (FTE)                  | Formazione\_ProgrammaCorso, Formazione\_PartecipantiCorso |
| Formazione\_NomeLavoratore      | Nome, cognome e nome completo                             | Formazione\_PartecipantiCorso |
| Formazione\_TitoloLavoratore     | Titolo e data di anzianità                                         | Formazione\_PartecipantiCorso |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]