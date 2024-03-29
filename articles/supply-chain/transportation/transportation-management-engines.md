---
title: Motori di gestione del trasporto
description: I motori di gestione del trasporto definiscono la logica utilizzata per generare ed elaborare le tariffe di trasporto in Gestione trasporto.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine, TMSFreightBillTypeAssignment, TMSZoneMaster, TMSEngineParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4a49ed7a91ec9a1b89564d40bef38cc4ea45532
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669602"
---
# <a name="transportation-management-engines"></a>Motori di gestione del trasporto

[!include [banner](../includes/banner.md)]

I motori di gestione del trasporto definiscono la logica utilizzata per generare ed elaborare le tariffe di trasporto in Gestione trasporto. 

Il motore di gestione del trasporto calcola le attività, ad esempio la tariffa di trasporto del vettore. Il sistema di motore consente di modificare le strategie di calcolo in fase di esecuzione, in base ai dati presenti in Supply Chain Management. Il motore di gestione del trasporto è simile a un plug-in correlato a un contratto di vettore specifico.

## <a name="what-engines-are-available"></a>Quali motori sono disponibili?
Nella seguente tabella vengono illustrati i motori di gestione del trasporto disponibili.

| Motore di gestione del trasporto | Descrizione                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motore tariffe**                  | Calcola le tariffe.                                                                                                                                                                                                                                                                                                           |
| **Motore generico**               | Semplici motori ausiliari utilizzati da altri motori che non richiedono dati da Supply Chain Management, ad esempio, un motore di ripartizione. I motori di ripartizione vengono utilizzati per ridurre i costi di trasporto finali a ordini e righe specifici, in base alle dimensioni, ad esempio volume e peso. |
| **Motore chilometraggio**               | Calcola la distanza di trasporto.                                                                                                                                                                                                                                                                                     |
| **Motore tempo di transito**          | Calcola il tempo necessario per andare dalla destinazione iniziale a quella finale.                                                                                                                                                                                                                                       |
| **Motore zona**                  | Calcola la zona in base all'indirizzo corrente e calcola il numero di zone da attraversare per andare dall'indirizzo A all'indirizzo B.                                                                                                                                                                    |
| **Tipo di fattura trasporto**            | Standardizza la fattura di trasporto e le relative righe e viene utilizzato per l'abbinamento automatico della fattura di trasporto.                                                                                                                                                                                                                |


## <a name="what-engines-must-be-configured-to-rate-a-shipment"></a>Che motori è necessario configurare per valutare una spedizione?

Per valutare una spedizione utilizzando un vettore specifico, è necessario configurare più motori di gestione del trasporto. **Motore tariffe** è necessario, ma per supportare **Motore tariffe** potrebbero essere necessari altri motori di gestione del trasporto. Ad esempio, **Motore tariffe** può essere utilizzato per recuperare i dati dal **motore chilometraggio** per calcolare la tariffa in base al chilometraggio tra l'origine e la destinazione.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>Che cosa è necessario per inizializzare un motore di gestione del trasporto?
Un motore di gestione del trasporto per funzionare in un determinato modo richiede l'impostazione dei dati di inizializzazione. L'impostazione può includere i seguenti tipi di dati:
-   Riferimenti ad altri motori di gestione del trasporto. Per informazioni dettagliate, vedere l'esempio di configurazione in questa sezione.
-   Riferimenti ai tipi .NET utilizzati dal motore di gestione del trasporto.
-   Dati di configurazione semplici.

Nella maggior parte dei casi, per configurare i dati di inizializzazione è possibile fare clic sul pulsante **Parametri** nei moduli di impostazione del motore di gestione del trasporto. **Esempio di configurazione di un motore tariffe che fa riferimento a un motore** Nel seguente esempio viene illustrata l'impostazione necessaria per un motore tariffe basato sul tipo di motore .NET Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEnginee e viene fatto riferimento a un motore chilometraggio.

|          Parametro           |                                                                                  Descrizione                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <em>RateBaseAssigner</em>   | Tipo .NET che interpreta i dati di assegnazione di base della tariffa per uno schema specifico. La sintassi del valore del parametro è costituita da due segmenti delimitati da una barra verticale ( |
|  <em>MileageEngineCode</em>  |                       Codice del motore chilometraggio che identifica il record motore chilometraggio nel database.                        |
| <em>ApportionmentEngine</em> |                        Codice motore generico che identifica il motore di ripartizione nel database.                        |

## <a name="how-is-metadata-used-in-transportation-management-engines"></a>Come vengono utilizzati i metadati nei motori di gestione del trasporto?

I motori di gestione del trasporto che si basano sui dati definiti in Supply Chain Management possono utilizzare diversi schemi di dati. Il sistema di gestione del trasporto consente l'utilizzo delle stesse tabelle di database fisiche generiche da parte dei diversi motori di gestione del trasporto. Per assicurarsi che l'interpretazione dei dati del motore in fase di esecuzione sia corretta, è possibile definire i metadati per le tabelle di database. Questo consente di ridurre il costo della compilazione di nuovi motori di gestione del trasporto poiché in Operations non sono necessarie strutture di tabelle e moduli aggiuntive.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>Cosa può essere utilizzato come dati di ricerca nei calcoli delle tariffe?
I dati utilizzati quando si calcolano le tariffe sono controllati dalla configurazione dei metadati. Ad esempio, se si desidera cercare le tariffe in base ai codici postali è necessario impostare i metadati in base al tipo di ricerca di un codice postale.

## <a name="do-all-engine-configurations-require-metadata"></a>I metadati sono necessari per le configurazioni di tutti i motori?
No, i motori di gestione del trasporto utilizzati per recuperare i dati richiesti per il calcolo delle tariffe da sistemi esterni non richiedono i metadati. I dati relativi alle tariffe di questi motori possono essere recuperati dai sistemi di vettori di trasporto esterni, in genere tramite un servizio Web. Ad esempio, in è possibile utilizzare un motore chilometraggio che recupera i dati direttamente da Bing Maps in modo che per questo motore non siano necessari i metadati.

| **Nota**                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I motori di gestione del trasporto forniti con Supply Chain Management si basano sui dati recuperati dall'applicazione. I motori che si connettono ai sistemi esterni non sono inclusi in Operations. Tuttavia, il modello di estendibilità basato sul motore consente di creare estensioni utilizzando Visual Studio Tools. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>Come si configurano i metadati per il motore di gestione del trasporto?
I metadati per i motori di gestione del trasporto vengono configurati in modo diverso per diversi tipi di motori.

| Motore di gestione del trasporto               | Configurazione dei metadati                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motore tariffe**                                | Richiede un **tipo di base della tariffa**. Il tipo di base della tariffa contiene i metadati per l'anagrafica delle tariffe e i dati di assegnazione di base della tariffa. La struttura dei metadati di base della tariffa è determinata dal tipo di motore tariffe. La struttura dei metadati di assegnazione di base della tariffa è determinata dal tipo di assigner di base della tariffa associato al motore tariffe. Impostare il tipo di base della tariffa del motore tariffe nella pagina **Motore tariffe** e nella pagina **Tariffa principale**. |
| **Motore zona**                                | Richiede l'impostazione diretta dei metadati nella master zona.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Motore di tempo di transito** e **Motore di trasferta** | Recupera i metadati direttamente dal modulo di impostazione della configurazione del motore chilometraggio.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Esempio di metadati per il motore tariffe** Il motore di gestione del trasporto richiede l'identificazione dell'indirizzo di origine, lo stato/regione e il paese di destinazione e il punto iniziale e finale della spedizione. Utilizzando tali requisiti, i metadati assomiglierebbero ai dati della tabella seguente. La tabella include inoltre informazioni sul tipo di dati di input necessari.
-   Definire queste informazioni in **Gestione trasporto** &gt; **Impostazioni** nella pagina **Tipo di base tariffa**.

| Sequenza | Nome                          | Tipo di campo | Tipo di dati | Tipo di ricerca    | Obbligatorio |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1        | Codice postale origine            | Assegnazione | Stringa    | CAP    | Selezionata  |
| 2        | Stato/regione di destinazione             | Assegnazione | Stringa    | Statale          |           |
| 3        | Codice postale di inizio destinazione | Assegnazione | Stringa    | CAP    | Selezionata  |
| 4        | Codice postale di fine destinazione   | Assegnazione | Stringa    | CAP    | Selezionate  |
| 5        | Paese di destinazione           | Assegnazione | String    | Paese/area geografica |           |

### <a name="whitepaper"></a>White paper

Per ulteriori informazioni, scarica il seguente white paper (scritto per supportare AX2012, ma è ancora valido per Dynamics 365 Supply Chain Management)

- [Motori di gestione trasporto](https://download.microsoft.com/download/e/0/9/e0957665-c12f-43c7-94c0-611cc49d7d61/TransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]