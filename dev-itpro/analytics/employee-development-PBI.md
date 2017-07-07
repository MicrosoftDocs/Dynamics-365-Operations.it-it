---
title: Contenuto di Power BI Sviluppo del dipendente
description: "Questo argomento descrive il contenuto Sviluppo del dipendente di Power BI. Descrive come accedere ai report e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: jcart1106
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: JCart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: d25f3be5821a02ea618a2356878bf2904765a6f7
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="employee-development-power-bi-content"></a>Contenuto di Power BI Sviluppo del dipendente

[!include[banner](../includes/banner.md)]

Questo argomento descrive il contenuto **Sviluppo del dipendente** di Microsoft Power BI. Descrive come accedere ai report e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

Se si utilizza l'aggiornamento di luglio 2017 di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition , è possibile trovare il pacchetto di contenuti **Sviluppo del dipendente** nella raccolta delle risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni su come scaricare il pacchetto di contenuti e connetterlo ai propri dati, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI
I report inclusi nel contenuto **Sviluppo del dipendente** di Power BI dispongono di grafici e tabelle contenenti informazioni aggiuntive. Nella seguente tabella vengono illustrati i report.

| Report                        | Contenuto |
|-------------------------------|----------|
| Panoramica sullo sviluppo del dipendente | Riepilogo di altri report |
| Analisi competenze del dipendente       | Tipi di competenza del dipendente e competenze del dipendente per tipo |
| Analisi del livello di competenza del dipendente | Livelli di competenza del dipendente per reparto, dipendenti per livello di competenza e tipo di competenza e livello più basso e livello più alto per competenza |
| Profilo competenze                 | Profilo competenze del dipendente selezionato |
| Analisi competenze                | Competenze per tipo e valutazione |
| Analisi della valutazione delle prestazioni   | Dipendenti per valutazione dal livello più basso al più alto per mansione, valutazioni del dipendente per reparto, dipendenti per tipo di posizione e valutazione e valutazioni più alta e più bassa per posizione  |
| Analisi delle prestazioni del dipendente | Valutazioni del dipendente per valutazione selezionata dal responsabile |

È possibile filtrare i grafici e i riquadri in questi report e aggiungerli al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
| Entità                   | Contenuto                                                                                                   | Relazioni con altre entità |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Offset di calendario          | Offset di calendario su report suddivisi                                                                          | Assegnazione della posizione passata, Tendenza della posizione, Tendenza del dipendente, Dipendente con rapporto di lavoro chiuso 
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
| Mansione                      | Funzione, tipo e titolo                                                                                      | Dipendente corrente, Posizione corrente, Tendenza del dipendente, Competenza preferita per la mansione, Assegnazione della posizione passata, Tendenza della posizione, Dipendente con rapporto di lavoro chiuso |
| Competenza preferita per la mansione      | Importanza, valutazione, competenza e il livello di competenza                                                                 | Mansione |
| Analisi competenze del dipendente  | Certificato, livello, data livello e competenza                                                                    | Nome del dipendente, Competenza |  
| Prestazioni              | Valutazione, descrizione e modello di valutazione                                                                      | Dipendente corrente, Posizione corrente, Tendenza del dipendente, Competenza preferita per la mansione, Assegnazione della posizione passata, Tendenza della posizione, Dipendente con rapporto di lavoro chiuso |
|  Competenza                   | Competenza, tipo di competenza e valutazione                                                                              | Analisi competenze del dipendente, Competenza preferita per la mansione |                                                                                                                        

Le entità sono state utilizzate per creare le misure calcolate nel modello dati. Queste misure calcolate vengono quindi utilizzate per calcolare gli indicatori di prestazione chiave (KPI) e i report utilizzati nel contenuto di Power BI. Se si desidera includere calcoli aggiuntivi nei report e nel dashboard, è possibile scaricare e modificare il file .pbix da LCS. Questo file è il modello dati predefinito utilizzato per creare il contenuto di Power BI. Una volta apportate le modifiche, è possibile creare un pacchetto di contenuti per l'organizzazione e un dashboard che contengono le informazioni aggiunte.

