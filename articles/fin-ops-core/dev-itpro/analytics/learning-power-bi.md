---
title: Contenuto Learning di Power BI
description: Questo argomento descrive il contenuto Learning di Power BI.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 8f97d4f59765840e215710e666079df3d4ecb878
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3005781"
---
# <a name="learning-power-bi-content"></a>Contenuto Learning di Power BI

[!include [banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Learning** di Microsoft Power BI.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

I report inclusi nel contenuto **Learning** di Power BI dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                | Contenuto |
|-----------------------|----------|
| Panoramica di Learning     | Riepilogo di altri report |
| Analisi del corso       | Registrazione per località, partecipante per stato, corsi per tipo società e partecipazione al corso per processo |
| Analisi della registrazione | Elenco registrazione |
| Tipi di corso          | Tipi di corsi in base alla competenza |
| Analisi istruttore   | Indice dei corsi per istruttori, numero di istruttori, corsi per istruttore, corsi per istruttore e agenda del corso per istruttore |
| Corsi offerti       | Elenco di corsi |
| Progettazione dei corsi        | Agenda del corso |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I seguenti dati vengono utilizzati per compilare i report nel contenuto **Learning** di Power BI. Nella tabella seguente vengono illustrate le entità su cui è stato basato il contenuto.

| Entità           | Contenuto                                                         | Relazioni con altre entità |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Offset di calendario  | Offset di calendario su report suddivisi                                | Agenda del corso, partecipanti al corso |
| Società          | Società in base a cui filtrare i report                                   | Agenda del corso, partecipanti al corso |
| Corso           | Corso, descrizione, nome istruttore, ubicazione, sala e stato | Agenda del corso, partecipanti al corso, competenze del corso |
| Agenda del corso    | Programma, corso e orario di inizio e fine                          | Società, offset di calendario, data, corso |
| Partecipanti al corso | Nome, stato, mansione e data di registrazione                         | Società, offset di calendario, data, corso, Demografica, impiego, corso, nome del dipendente, posizione del dipendente, processo, ubicazione |
| Competenze del corso     | Competenza, tipo di competenza e livello                                     | Corso |
| Data             | Giorni, settimane, mesi e anni.                                   | Agenda del corso, partecipanti al corso |
| Dati demografici     | Data di nascita, sesso, origine etnica e stato civile         | Agenda del corso, partecipanti al corso |
| Impiego       | Data di inizio, data di fine e data della transizione                        | Agenda del corso, partecipanti al corso |
| Mansione              | Funzione, tipo e titolo                                        | Agenda del corso, partecipanti al corso |
| Posizione         | Posizione, titolo ed equivalente a tempo pieno (FTE)                  | Agenda del corso, partecipanti al corso |
| Nome dipendente    | Nome, cognome e nome completo                             | Partecipanti al corso |
| Posizione del dipendente   | Titolo e data di anzianità                                         | Partecipanti al corso |
