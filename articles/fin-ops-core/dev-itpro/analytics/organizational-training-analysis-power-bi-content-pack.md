---
title: Contenuto Power BI sulla formazione nell'organizzazione
description: In questo articolo viene descritto il contenuto Power BI sulla formazione nell'organizzazione in Finance and Operations.
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
ms.openlocfilehash: ba332fc0c241969cbe0c25e7985101a2bbe12be4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892423"
---
# <a name="organizational-training-power-bi-content"></a>Contenuto Power BI sulla formazione nell'organizzazione

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto il contenuto Power BI sulla formazione nell'organizzazione in Finance and Operations.

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