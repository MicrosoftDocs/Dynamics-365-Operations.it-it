---
title: Contenuto Power BI sulle metriche della forza lavoro
description: In questo argomento viene descritto il contenuto Power BI Metriche forza lavoro.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorkforceWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d0622cebcfca15acf50cf62e8a77af360d4f1bda
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092793"
---
# <a name="workforce-metrics-power-bi-content"></a>Contenuto Power BI sulle metriche della forza lavoro

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto il contenuto Microsoft Power BI **Metriche forza lavoro**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto Power BI **Metriche forza lavoro** viene visualizzato nell'area di lavoro **Gestione dipendente** se si utilizza uno di questi prodotti:

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Nella seguente tabella vengono elencate le metriche disponibili in ciascun report.

| Report                                           | Metriche |
|--------------------------------------------------|---------|
| Metriche relative alle persone                                   | Riepilogo di altri report |
| Analisi numero dipendenti Società, Reparto, Ubicazione | Numero dipendenti per società, numero dipendenti per reparto, numero dipendenti per ubicazione e numero dipendenti totale |
| Analisi numero dipendenti Mansione, Grado, Responsabile            | Numero dipendenti per mansione, numero dipendenti per grado, numero dipendenti per responsabile e numero dipendenti totale |
| Analisi tendenza numero dipendenti                         | Numero dipendenti nell'anno attuale rispetto all'anno precedente per società e rollup del numero dipendenti per gli ultimi 12 mesi |
| Analisi FTE                                     | Totale equivalente al tempo pieno (FTE), totale FTE assegnato, FTE per reparto, FTE per gli ultimi 12 mesi e FTE per processo |
| Forzalavoro DatiDemografici                           | Numero dipendenti per età e sesso, numero dipendenti per origini etniche, numero dipendenti per stato di veterano, numero dipendenti per stato civile, numero di studenti a tempo pieno, rapporto di lavoro medio, età media, rapporto tra dipendenti donne e dipendenti uomini e lingue parlate dai dipendenti |
| Analisi posizioni                                | Posizioni aperte per reparto, posizioni aperte da completare, posizioni da attive a inattive e posizioni per reparto |
| Analisi abbandoni                               | Abbandoni nell'anno attuale rispetto all'anno precedente, abbandoni, dipendenti che si congedano per età e sesso, rapporto di lavoro medio delle persone che si congedano, dipendenti che si congedano nel mese in corso e dipendenti che si congedano per un motivo |
| Persone per reparto                             | Dipendenti con un numero di personale per reparto, posizione e date di inizio e di fine di assegnazione |
| Analisi di anzianità                               | Rapporto di lavoro medio, anni di servizio medi per società ed elenco di anzianità |
| Anniversari dipendenti                           | Anniversari del mese in corso, anniversari del mese successivo, dipendenti in base agli anni di servizio e anniversari, anni di servizio per reparto |
| Compleanni dipendenti                               | Compleanni del mese in corso, compleanni del mese successivo, compleanni dei dipendenti e compleanni per mese e reparto |
| Progetti di assunzione collettiva                               | Progetti di assunzione collettiva totali, progetti di assunzione collettiva in base allo stato, progetti di assunzione collettiva per reparto e proprietario, progetti di assunzione collettiva per mansione e progetti di assunzione collettiva |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)

Assicurarsi di scaricare il contenuto di Power BI **Metriche forza lavoro** applicabile alla versione di Microsoft Dynamics 365 in uso.

> [!NOTE]
> I file .pbix disponibili in Lifecycle Services si applicano solo alle app Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Nella tabella seguente vengono illustrate le entità su cui si è basato il contenuto.

| Entità                   | Contenuto                                                                            | Relazioni con altre entità |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| Offset di calendario          | Offset di calendario su report suddivisi                                                   | Assegnazione della posizione passata, Tendenza della posizione, Tendenza del dipendente, Dipendente con rapporto di lavoro chiuso |
| Società                  | Società in base a cui filtrare i report                                                      | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Posizione corrente         | Posizione a partire dalla data corrente, FTE, posizioni aperte e posizioni da aperte ad assegnate | Lavoro, Posizione |
| Dipendente corrente         | Lavoratori a partire dalla data corrente, età e numero di dipendenti                                  | Società, Località geografica, Nome del dipendente, Subordinato a, Posizione del dipendente, Dati demografici, Mansione, Impiego, Posizione |
| Data                     | Giorni, settimane, mesi e anni.                                                      | Assegnazione della posizione passata, Tendenza della posizione, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Dati demografici             | Data di nascita, sesso, origine etnica e stato civile                            | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Impiego               | Data di inizio, data di fine e data della transizione                                           | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Località geografica      | Città, provincia, codice postale e stato/regione o provincia                                    | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Mansione                      | Funzione, tipo e titolo                                                           | Posizione corrente, Dipendente corrente |
| Assegnazione della posizione passata | Motivo dell'assegnazione, data di inizio, data di fine e mansione                                    | Offset di calendario, Data, Mansione, Posizione |
| Posizione                 | Reparto, FTE, posizione, tipo di posizione e titolo                                 | Posizione corrente, Dipendente corrente |
| Tendenza della posizione           | Posizioni nel tempo, FTE e mansione                                                   | Offset di calendario, Data, Mansione, Posizione |
| Subordinato a               | Nome, cognome e nome completo                                                | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Dipendente con rapporto di lavoro chiuso      | Lavoratori congedati, data del congedo, titolo, posizione e mansione                      | Società, Località geografica, Nome del dipendente, Subordinato a, Offset di calendario, Data, Posizione del dipendente, Dati demografici, Impiego, Mansione, Posizione |
| Nome dipendente            | Nome, cognome e nome completo                                                | Lavoratore corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Posizione del dipendente           | Titolo e data di anzianità                                                            | Dipendente corrente, Dipendente con rapporto di lavoro chiuso, Tendenza del dipendente |
| Tendenza del dipendente           | Lavoratori nel tempo, numero di dipendenti, società e posizione                                 | Società, Località geografica, Nome del dipendente, Subordinato a, Offset di calendario, Data, Posizione del dipendente, Dati demografici, Impiego, Mansione |
| Progetto di assunzione collettiva        | Numero di progetti di assunzione collettiva, proprietario del progetto e stato del progetto                     | Società, Riga assunzione collettiva |
| Riga assunzione collettiva           | Reparto, tipo di impiego e posizione                                           | Data, mansione, progetto di assunzione collettiva |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]