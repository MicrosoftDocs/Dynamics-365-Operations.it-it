---
title: Contenuto Learning di Power BI
description: Questo argomento descrive il contenuto Learning di Power BI.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: e5a78812aabaa5c835fe23787a9cbb57d1a7770e
ms.contentlocale: it-it
ms.lasthandoff: 12/19/2017

---

# <a name="learning-power-bi-content"></a>Contenuto Learning di Power BI

[!include[banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Learning** di Microsoft Power BI.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

I report inclusi nel contenuto **Learning** di Power BI dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                | Contenuto |
|-----------------------|----------|
| Panoramica di Learning     | Riepilogo di altri report |
| Analisi del corso       | Registrazione per località, partecipante per stato, corsi per tipo società e partecipazione al corso per processo |
| Analisi della registrazione | Elenco registrazione |
| Tipi di corso          | Tipi di corsi in base alla competenza |
| Analisi istruttore   | Indice dei corsi per istruttori, numero di istruttori, corsi per istruttore, corsi per istruttore e agenda del corso per istruttore |
| Corsi offerti       | Elenco di corsi |
| Progettazione dei corsi        | Agenda del corso |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

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



