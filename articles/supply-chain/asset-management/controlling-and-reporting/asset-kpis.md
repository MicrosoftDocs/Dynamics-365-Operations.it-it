---
title: KPI del cespite
description: In questo argomento vengono descritti gli indicatori KPI dei cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectKPI
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3ebbb1016bafed8ad9fb998fc76152e215c08c3e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431048"
---
# <a name="asset-kpis"></a>KPI del cespite

[!include [banner](../../includes/banner.md)]

 

In Gestione cespiti, è possibile calcolare vari indicatori di prestazioni chiave (KPI) per i cespiti e i tipi di cespite. I KPI consentono di ottenere una panoramica delle prestazioni sui cespiti in relazione a, ad esempio, attività, inattività, tempo di riparazione e tempo medio tra i guasti (MTBF).

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **KPI del cespite**.

2. Nella finestra di dialogo **Calcola KPI cespiti**, selezionare la **Scala cronologica** da utilizzare nel calcolo e un periodo nei campi **Dal** e **Al**. 

3. Nella Scheda dettaglio **Record da includere**, è possibile selezionare specifici cespiti e tipi di cespite da includere nel calcolo, se necessario.

4. Fare clic su **OK** per avviare il calcolo.

5. Nella Scheda dettaglio **Panoramica**, i risultati del calcolo sono visualizzati nella visualizzazione griglia. Ogni cespite è visualizzato su una riga separata.

6. Nella Scheda dettaglio **KPI per riga selezionata**, sono visualizzati i calcoli per il cespite selezionato nella Scheda dettaglio **Panoramica**. I valori KPI sono classificati in base a **Ora**, **Disponibilità**, **Ordini di lavoro**, **Manutenzione**, **Errori**, **Tempi di fermo per la manutenzione** e **Costo**.

Nella tabella seguente, è riportata una descrizione dei campi nella pagina **KPI del cespite**.

| Campo                   | Descrizione                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cespite                   | ID cespite.                                                                                                                                                                                                                                                                                             |
| Tempo totale              | Il tempo totale impostato nel calendario utilizzato nel calcolo. Se il cespite è associato a una risorsa, viene utilizzato il calendario risorsa correlato. Se un cespite non è associato a una risorsa, viene utilizzato il calendario selezionato nel campo **Calendario standard** in **Parametri di gestione cespiti**. |
| Tempo di attività                  | Il tempo totale meno quello di inattività.                                                                                                                                                                                                                                                                            |
| Tempi di fermo                | Registrazioni di tempi di fermo per la manutenzione effettuate nel cespite nel periodo selezionato.                                                                                                                                                                                                                              |
| Ora di riparazione             | Il numero totale di ore lavorative consumate negli ordini di lavoro di riparazione.                                                                                                                                                                                                                                            |
| % disponibilità          | Il tempo di attività diviso per il tempo totale e moltiplicato per 100.                                                                                                                                                                                                                                                   |
| Numero di errori        | Il numero delle cause di errore registrate nei sintomi di errore nel cespite nel periodo selezionato.                                                                                                                                                                                                             |
| MTBF                    | Tempo medio tra i guasti, ovvero il tempo totale diviso per il numero di errori registrati nel cespite nel periodo selezionato. Se il numero di errori è pari a zero, MTBF è il tempo totale.                                                                                                                   |
| Frequenza di errore               | 1 diviso per MTBF.                                                                                                                                                                                                                                                                                    |
| MRT                     | Il tempo di riparazione medio, ovvero il tempo di riparazione diviso per il numero di errori registrati nel cespite nel periodo selezionato. Se il numero di errori è pari a zero, MRT è il tempo di riparazione.                                                                                                                           |
| Numero di arresti         | Il numero di registrazioni di tempi di fermo per la manutenzione creati nel cespite.                                                                                                                                                                                                                                     |
| MTBS                    | Il tempo medio tra interruzioni, ovvero il tempo totale diviso per il numero di registrazioni di tempi di fermo per la manutenzione. Se il numero di registrazioni di tempi di fermo per la manutenzione è zero nel periodo selezionato, il valore MTBS è il tempo totale.                                                                                      |
| Costo preventivo         | I costi registrati nel cespite correlati al tipo di costo "Preventivo" nel periodo selezionato. I tipi di costo sono impostati nei tipi di ordine di lavoro.                                                                                                                                                                       |
| Costo correttivo         | I costi registrati nel cespite correlati al tipo di costo "Correttivo" nel periodo selezionato. I tipi di costo sono impostati nei tipi di ordine di lavoro.                                                                                                                                                                       |
| Valore di sostituzione       | Il valore definito nel cespite come costo di sostituzione.                                                                                                                                                                                                                                                  |
| Tipo di cespite             | L'identificazione del tipo di cespite selezionato nel cespite.                                                                                                                                                                                                                                             |
| Produttore           | L'identificazione del produttore selezionato nel cespite.                                                                                                                                                                                                                                                 |
| Modello                   | L'identificazione del modello di produttore selezionato nel cespite.                                                                                                                                                                                                                                           |
| Dal               | La data di inizio del calcolo KPI. Se il cespite è stato creato dopo la data di inizio selezionata per il calcolo, la data di inizio del cespite viene visualizzata in questo campo.                                                                                                                                  |
| Al                 | La data di fine del calcolo KPI. Se il cespite è stato registrato come inattivo prima della data di fine selezionata per il calcolo, la data a partire dalla quale il cespite non è più attivo viene visualizzata in questo campo.                                                                                               |
| Scala cronologica              | Durante il calcolo dei KPI, selezionare una scala cronologica da utilizzare: Ore, Giorni, Settimane.                                                                                                                                                                                                            |
| Disponibilità            | Il tempo di attività diviso per il tempo totale.                                                                                                                                                                                                                                                                         |
| Ordini di lavoro             | Il numero totale di ordini di lavoro inclusi nel calcolo KPI.                                                                                                                                                                                                                                          |
| Ora dell'ordine di lavoro         | Il numero totale di ore lavorative consumate negli ordini di lavoro.                                                                                                                                                                                                                                               |
| Ordini di lavoro primari     | Il numero di ordini di lavoro principali inclusi nel calcolo KPI.                                                                                                                                                                                                                                        |
| Ordini di lavoro secondari   | Il numero di ordini di lavoro secondari inclusi nel calcolo KPI.                                                                                                                                                                                                                                      |
| Ordini di lavoro di manutenzione | Il numero di ordini di lavoro di manutenzione inclusi nel calcolo KPI. Un ordine di attività di manutenzione è un ordine di lavoro senza cause di errore correlate.                                                                                                                                                             |
| Data e ora di manutenzione        | Il numero totale di ore lavorative consumate negli ordini di lavoro di manutenzione.                                                                                                                                                                                                                                       |
| Riparazione ordini di lavoro      | Il numero di ordini di lavoro di riparazione inclusi nel calcolo KPI. Un ordine di lavoro di riparazione è un ordine di lavoro con una causa di errore correlata.                                                                                                                                                                        |
| % affidabilità           | Il calcolo basato sullo sviluppo esponenziale previsto nelle registrazioni di errore in un cespite, a indicare che, nel tempo, il cespite diventa meno affidabile a causa dell'usura. Il calcolo di questo KPI è basato sul valore MTBF e sul tempo totale.                                                            |
| MTPS                    | Il tempo medio delle interruzioni di produzione, ovvero i tempi di fermo per la manutenzione divisi per il numero di registrazioni di tempi di fermo per la manutenzione. Se il numero di registrazioni di tempi di fermo per la manutenzione è zero nel periodo selezionato, il valore MTPS è zero.                                                                               |
| Costo totale              | I costi totali registrati nel cespiti nel periodo selezionato.                                                                                                                                                                                                                                              |
| Costo di investimento         | I costi registrati sul cespite correlati al tipo di costo "Investimento" nel periodo selezionato. I tipi di costo sono impostati nei tipi di ordine di lavoro.                                                                                                                                                                       |

Nella figura seguente è illustrata una schermata di un calcolo KPI per quattro cespiti.

![Schermata di un calcolo KPI per quattro cespiti](media/11-controlling-and-reporting.png)

- È possibile selezionare più cespiti in **Tutti i cespiti** e fare clic sul pulsante **KPI del cespite** nella scheda **Generale**. Quindi, fare clic su **OK** nella finestra di dialogo **Calcola KPI cespite** per calcolare i KPI per i cespiti selezionati.  
- I risultati di un calcolo KPI possono o meno includere [registrazioni di tempi di fermo per la manutenzione](../work-orders/maintenance-downtime.md), in base all'impostazione e all'utilizzo dei codici motivo dei tempi di fermo per la manutenzione. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]