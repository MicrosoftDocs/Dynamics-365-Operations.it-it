---
title: Contenuto Learning di Power BI
description: "Questo argomento descrive il contenuto Learning di Power BI. Descrive come accedere ai report e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0136080b12c6c2bd8e65063e99278f163212178c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="learning-power-bi-content"></a>Contenuto Learning di Power BI

[!include[banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Learning** di Microsoft Power BI. Spiega come accedere al contenuto e descrive il modello dati e le entità che sono stati utilizzati per creare il contenuto.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017), è possibile trovare il contenuto **Learning** di Power BI nella raccolta delle risorse condivise in Microsoft Dynamics Lifecycle Services (LCS).. Per ulteriori informazioni su come scaricare il contenuto e implementarlo nell'organizzazione, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md). Per guardare una demo che mostra come implementare il contenuto di Power BI, vedere [Contenuto di Power BI da Microsoft e partner in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

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

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Queste misure calcolate vengono quindi utilizzate per calcolare gli indicatori di prestazione chiave (KPI) e i report utilizzati nel contenuto. Se si desidera includere calcoli aggiuntivi nei report e nel dashboard, è possibile scaricare e modificare il file .pbix da LCS. Questo file è il modello dati predefinito utilizzato per creare il contenuto. Una volta apportate le modifiche, è possibile creare un pacchetto di contenuti per l'organizzazione e un dashboard che contengono le informazioni aggiunte.

