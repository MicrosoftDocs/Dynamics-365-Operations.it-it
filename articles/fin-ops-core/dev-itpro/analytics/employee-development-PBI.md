---
title: Contenuto di Power BI Sviluppo del dipendente
description: Questo articolo descrive il contenuto Sviluppo del dipendente di Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 67fd3b5907cb52dc1f10d754e12316e21876e888
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850989"
---
# <a name="employee-development-power-bi-content"></a>Contenuto di Power BI Sviluppo del dipendente

[!include [banner](../includes/banner.md)]

Questo articolo descrive il contenuto **Sviluppo del dipendente** di Microsoft Power BI.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI
I report inclusi nel contenuto **Sviluppo del dipendente** di Power BI dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                        | Contenuto |
|-------------------------------|----------|
| Panoramica sullo sviluppo del dipendente | Riepilogo di altri report |
| Analisi competenze del dipendente       | Tipi di competenza del dipendente e competenze del dipendente per tipo |
| Analisi del livello di competenza del dipendente | Livelli di competenza del dipendente per reparto, dipendenti per livello di competenza e tipo di competenza e livello più basso e livello più alto per competenza |
| Profilo competenze                 | Profilo competenze del dipendente selezionato |
| Analisi competenze                | Competenze per tipo e valutazione |
| Analisi della valutazione delle prestazioni   | Dipendenti per valutazione dal livello più basso al più alto per mansione, valutazioni del dipendente per reparto, dipendenti per tipo di posizione e valutazione e valutazioni più alta e più bassa per posizione |
| Analisi delle prestazioni del dipendente | Valutazioni del dipendente per valutazione selezionata dal responsabile |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

| Entità                   | Contenuto                                                                                                   | Relazioni con altre entità |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Offset di calendario          | Offset di calendario su report suddivisi                                                                          | Assegnazione della posizione passata, Tendenza della posizione, Tendenza del dipendente, Dipendente con rapporto di lavoro chiuso |
| Società                  | Società in base a cui filtrare i report                                                                             | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Posizione corrente         | Posizione a partire dalla data corrente, equivalente a tempo pieno (FTE), posizioni aperte e posizioni da aperte ad assegnate | Lavoro, Posizione |
| Dipendente corrente         | Lavoratori a partire dalla data corrente, età e numero di dipendenti                                                         | Società, Località geografica, Nome del dipendente, Subordinato a, Posizione del dipendente, Dati demografici, Mansione, Impiego, Posizione |
| Data                     | Giorni, settimane, mesi e anni.                                                                             | Assegnazione della posizione passata, Tendenza della posizione, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Dati demografici             | Data di nascita, sesso, origine etnica e stato civile                                                   | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Impiego               | Data di inizio, data di fine e data della transizione                                                                  | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Località geografica      | Città, provincia, codice postale e stato/regione o provincia                                                           | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Mansione                      | Funzione, tipo e titolo                                                                                  | Posizione corrente, Dipendente corrente |
| Assegnazione della posizione passata | Motivo dell'assegnazione, data di inizio, data di fine e mansione                                                           | Offset di calendario, Data, Mansione, Posizione |
| Posizione                 | Reparto, FTE, posizione, tipo di posizione e titolo                                                        | Posizione corrente, Dipendente corrente |
| Tendenza della posizione           | Posizioni nel tempo, FTE e mansione                                                                          | Offset di calendario, Data, Mansione, Posizione |
| Subordinato a               | Nome, cognome e nome completo                                                                       | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Dipendente con rapporto di lavoro chiuso      | Lavoratori congedati, data del congedo, titolo, posizione e mansione                                             | Società, Località geografica, Nome del dipendente, Subordinato a, Offset di calendario, Data, Posizione del dipendente, Dati demografici, Impiego, Mansione, Posizione |
| Nome dipendente            | Nome, cognome e nome completo                                                                       | Lavoratore corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Posizione del dipendente           | Titolo e data di anzianità                                                                                   | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Tendenza del dipendente           | Lavoratori nel tempo, numero di dipendenti, società e posizione                                                        | Società, Località geografica, Nome del dipendente, Subordinato a, Offset di calendario, Data, Posizione del dipendente, Dati demografici, Impiego, Mansione |
| Mansione                      | Funzione, tipo e titolo                                                                                  | Dipendente corrente, Posizione corrente, Tendenza del dipendente, Competenza preferita per la mansione, Assegnazione della posizione passata, Tendenza della posizione, Dipendente con rapporto di lavoro chiuso |
| Competenza preferita per la mansione      | Importanza, valutazione, competenza e il livello di competenza                                                                 | Mansione |
| Analisi competenze del dipendente  | Certificato, livello, data livello e competenza                                                                    | Nome del dipendente, Competenza |
| Prestazioni              | Valutazione, Descrizione e modello di valutazione                                                                      | Dipendente corrente, Posizione corrente, Tendenza del dipendente, Competenza preferita per la mansione, Assegnazione della posizione passata, Tendenza della posizione, Dipendente con rapporto di lavoro chiuso |
| Competenza                    | Competenza, tipo di competenza e valutazione                                                                              | Analisi competenze del dipendente, Competenza preferita per la mansione |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]