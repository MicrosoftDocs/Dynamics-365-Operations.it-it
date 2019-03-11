---
title: Contenuto Power BI per prestazioni di magazzino
description: In questo argomento viene descritto cosa è incluso nel contenuto Power BI per prestazioni di magazzino. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.
author: Mirzaab
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: WHSWarehousePerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.region: Global
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 99966a67fa1fd91fc54e7100f8e2e41b87f6a406
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "365364"
---
# <a name="warehouse-performance-power-bi-content"></a>Contenuto Power BI per prestazioni di magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto Power BI per **prestazioni di magazzino**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto Power BI per **Prestazioni di magazzino** è stato creato per consentire ai responsabili di magazzini e operazioni di monitorare le metriche chiave per le operazioni di entrata e uscita e del magazzino. Vengono utilizzati la gestione magazzino, i prodotti e altri dati transazionali del sistema in uso e viene fornita sia una visualizzazione aggregata delle prestazioni del magazzino che una scomposizione per fornitori, gruppi di prodotti e prodotti e siti e magazzini.

I responsabili di magazzino possono utilizzare il contenuto Power BI **Prestazioni di magazzino** per misurare le seguenti tre aree:

- **Prestazioni in entrata**: la misurazione delle prestazioni di un fornitore rispetto ai requisiti di un cliente (ovvero la misurazione delle prestazioni di consegna) e la misurazione delle prestazioni di stoccaggio, in modo da poter identificare eventuali problemi che interessano i lavoratori o gli articoli in un periodo. È importante sapere se i fornitori consegnano con puntualità, in anticipo o in ritardo, in modo da poter determinare in che misura le prestazioni del fornitore hanno effetto sulle prestazioni di stoccaggio complessive. Un fornitore che consegna in date diverse dalle date concordate può causare pressione aggiuntiva in magazzino, a causa di lavoro non previsto e può aumentare il tempo medio di stoccaggio.
- **Prestazioni di spedizione**: misurazione delle prestazioni della spedizione completa e puntuale dal magazzino ai clienti (ovvero misurare le spedizioni in uscita e le prestazioni di consegna), in modo da poter identificare eventuali problemi che interessano prodotti, siti o magazzini o clienti dedicati. Se si rilevano che le spedizioni avvengono in ritardo per aree o città specifiche, potrebbe essere necessario prestare maggiore attenzione alla gestione del trasporto o del conto.
- **Precisione inventariale dell'ubicazione**: la precisione inventariale rappresenta importante dato di business intelligence (BI) interna del magazzino. È molto importate determinare il livello di accuratezza generale. Tuttavia, è anche importate determinare il livello di accuratezza nello stoccaggio degli articoli nelle ubicazioni corrette e mettere in evidenza eventuali discrepanze, in modo che sia possibile trovare migliori ubicazioni per gli articoli o avviare il conteggio totale di articoli specifici. (Attualmente, la nuova la funzionalità di conteggio basata sugli articoli viene fornita come aggiornamento rapido). Se si utilizza il contenuto Power BI per verificare la precisione dei dati sulle scorte disponibili per ubicazione, è anche possibile identificare eventuali furti nei negozi. È inoltre possibile verificare se nelle ubicazioni sono presenti quantità disponibili diverse dai dati ERP (Enterprise Resource Planning). Tali ubicazioni possono essere troppo grandi oppure impossibili da conteggiare. In alternativa, alcuni posizionamenti fisici potrebbero essere non validi, per cui risulta difficile mantenere un unico tipo di articolo sincronizzato rispetto ai dati di disponibilità.

## <a name="accessing-the-power-bi-content-pack"></a>Accesso al pacchetto di contenuti Power BI
Il contenuto di Power BI **Prestazioni di magazzino** viene mostrato nella pagina **Prestazioni di magazzino** (**Gestione magazzino** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di magazzino** \> **Prestazioni di magazzino**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Il contenuto di Power BI **Prestazioni di magazzino** include un report. Il report è costituito da un set di metriche visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel contenuto Power BI per **Prestazioni di magazzino**.

| Pagina di report                 | Grafici                                   | descrizione |
|-----------------------------|------------------------------------------|-------------|
| Prestazioni in entrata         | Totale stoccaggio                          | Numero di righe di lavoro di stoccaggio elaborate nel periodo specificato. |
| Prestazioni in entrata         | Tempo medio di stoccaggio                    | Il tempo medio, in ore, per tutte le righe di stoccaggio dell'ordine fornitore elaborate, dalla registrazione degli articoli fino all'elaborazione dell'ultimo stoccaggio. |
| Prestazioni in entrata         | Ricevuta in anticipo                           | Il numero di righe dell'ordine fornitore ricevute in anticipo. |
| Prestazioni in entrata         | Ricevuta puntualmente                         | Il numero di righe dell'ordine fornitore ricevute puntuali. |
| Prestazioni in entrata         | Ricevimento in ritardo                            | Il numero di righe dell'ordine fornitore ricevute in ritardo. |
| Prestazioni in entrata         | Puntuale per fornitore                        | Visualizzazione della percentuale di righe ordine fornitore ricevute da un fornitore o da un gruppo di fornitori in anticipo, con puntualità o in ritardo. |
| Prestazioni in entrata         | Media stoccaggio da banchina a scorte (ore) | Il tempo medio, in ore, di stoccaggio dalla banchina alle scorte nel tempo. |
| Prestazioni in entrata         | Media stoccaggio per lavoratore               | Il tempo medio, in ore, impiegato da un lavoratore per l'elaborazione dello stoccaggio di righe ordine fornitore. |
| Prestazioni in entrata         | Tempo medio in ore per fornitore          | Il tempo medio, in ore, di stoccaggio per fornitore o gruppo di fornitori. |
| Prestazioni in entrata         | Tempo medio in ore per prodotto         | Il tempo medio, in ore, di stoccaggio per articolo o gruppo di articoli. |
| Precisione inventariale dell'ubicazione | Conteggio totale                              | Numero di righe di lavoro di conteggio elaborate per un periodo specificato. |
| Precisione inventariale dell'ubicazione | Tasso di discrepanza                         | Tasso totale di discrepanza espresso come percentuale di tutte le righe conteggiate per un determinato periodo. |
| Precisione inventariale dell'ubicazione | Conteggio senza discrepanza                | Il numero totale di righe lavoro di conteggio elaborate, il numero di righe elaborate senza discrepanze. |
| Precisione inventariale dell'ubicazione | Articoli conteggiati nel tempo                  | Percentuale di articoli conteggiati nel tempo con o senza discrepanza. |
| Precisione inventariale dell'ubicazione | Discrepanza quantità di articoli maggiore di % | Visualizzazione di tabella del numero di righe di conteggio con discrepanze che superano la percentuale specificata. Nella tabella sono riportate informazioni su ubicazioni, articoli, la discrepanza media, il numero totale di righe lavoro di conteggio elaborate, il numero totale di righe di conteggio con discrepanze relative all'ubicazione, la quantità media conteggiata, la quantità totale prevista che verrà conteggiata e la quantità effettiva degli articoli conteggiata. |
| Precisione inventariale dell'ubicazione | Conteggio articoli per lavoratore                     | Le prestazioni di conteggio dei lavoratori. Le prestazioni sono espresse come percentuale di righe di lavoro di conteggio con e senza discrepanze. |
| Precisione inventariale dell'ubicazione | Conteggio articoli per sito/magazzino           | Prestazioni di conteggio per numero di righe di lavoro di conteggio elaborate per sito o magazzino che hanno o non hanno discrepanze. |
| Precisione inventariale dell'ubicazione | Tasso di discrepanza per prodotto              | Tasso di discrepanza per le prestazioni di conteggio. Il tasso è espresso come percentuale di righe di lavoro di conteggio elaborate per articolo o gruppo di articoli. |
| Prestazioni di spedizione        | Righe spedite                            | Il numero totale di righe di spedizione spedite per un periodo specificato. |
| Prestazioni di spedizione        | In anticipo                                    | Percentuale delle righe di spedizione che vengono spedite in anticipo. |
| Prestazioni di spedizione        | Puntuale                                  | Percentuale delle righe di spedizione che vengono spedite con puntualità. |
| Prestazioni di spedizione        | In ritardo                                     | Percentuale delle righe di spedizione che vengono spedite in ritardo. |
| Prestazioni di spedizione        | Spedizioni nel tempo                      | Percentuale delle righe di spedizione che vengono spedite in anticipo, puntualmente o in ritardo in un determinato periodo. La riga della tendenza mostra la tendenza per le righe che vengono spedite puntualmente. |
| Prestazioni di spedizione        | Spedizioni in ritardo per città                     | Visualizzazione di una mappa delle città e aree interessate dalle spedizioni in ritardo. |
| Prestazioni di spedizione        | Spedizioni per prodotto                       | Percentuale delle righe di spedizione che vengono spedite in anticipo, puntualmente o in ritardo per articolo o gruppo di articoli. |
| Prestazioni di spedizione        | Spedizioni per cliente                      | Percentuale delle righe di spedizione che vengono spedite in anticipo, puntualmente o in ritardo per cliente o gruppo di clienti. |
| Prestazioni di spedizione        | Spedizioni per sito/magazzino              | Percentuale delle righe di spedizione che vengono spedite in anticipo, puntualmente o in ritardo per sito o magazzino. |

## <a name="understanding-the-data-model-and-calculations"></a>Informazioni su modelli di dati e calcoli
I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Prestazioni di magazzino**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Le seguenti misure aggregazione chiave vengono utilizzate come base del contenuto.

| Pagina di report                 | Grafici                                   | Tabelle                                | Descrizioni di calcolo |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Prestazioni in entrata         | Totale stoccaggio                          | WHSWorkLine                           | Conteggio delle righe di lavoro in cui il tipo di lavoro è **stoccaggio**. |
| Prestazioni in entrata         | Tempo medio di stoccaggio                    | WHSWorkLine                           | Somma del tempo massimo delle righe di lavoro divisa per il conteggio del tempo massimo delle righe di lavoro, dove il tempo massimo delle righe di lavoro rappresenta il divario massimo tra la data di creazione e la data di chiusura del lavoro. |
| Prestazioni in entrata         | Ricevuta in anticipo                           | WHSWorkLine                           | Conteggio delle righe di lavoro in cui la data della creazione di lavoro è precedente alla data di consegna utilizzata. Se la data di spedizione confermata non è impostata, utilizzare la data di spedizione predefinita. |
| Prestazioni in entrata         | Ricevuta puntualmente                         | WHSWorkLine                           | Conteggio delle righe di lavoro in cui la data della creazione di lavoro è uguale alla data di consegna utilizzata. Se la data di spedizione confermata non è impostata, utilizzare la data di spedizione predefinita. |
| Prestazioni in entrata         | Ricevimento in ritardo                            | WHSWorkLine                           | Conteggio delle righe di lavoro in cui la data della creazione di lavoro è successiva alla data di consegna utilizzata. Se la data di spedizione confermata non è impostata, utilizzare la data di spedizione predefinita. |
| Prestazioni in entrata         | Puntuale per fornitore                        | WHSWorkLine                           | Ricevuto in anticipo, con puntualità o in ritardo (vedere le relative descrizioni in precedenza nella tabella). |
| Prestazioni in entrata         | Media stoccaggio da banchina a scorte (ore)   | WHSWorkLine                           | Tempo medio di stoccaggio (vedere la relativa descrizione in precedenza nella tabella). |
| Prestazioni in entrata         | Media stoccaggio per lavoratore               | WHSWorkLine                           | Tempo medio di stoccaggio (vedere la relativa descrizione in precedenza nella tabella). |
| Prestazioni in entrata         | Tempo medio in ore per fornitore          | WHSWorkLine                           | Tempo medio di stoccaggio (vedere la relativa descrizione in precedenza nella tabella). |
| Prestazioni in entrata         | Tempo medio in ore per prodotto         | WHSWorkLine                           | Tempo medio di stoccaggio (vedere la relativa descrizione in precedenza nella tabella). |
| Precisione inventariale dell'ubicazione | Conteggio totale                              | WHSWorkLineCycleCount                 | Conteggi ciclo in cui la quantità di discrepanza assoluta è uguale o maggiore di 0 (zero). |
| Precisione inventariale dell'ubicazione | Tasso di discrepanza                         | WHSWorkLineCycleCount                 | Conteggi ciclo con discrepanze, suddivisi per conteggio totale. Un conteggio ciclo viene considerato con discrepanze se la quantità discrepanza assoluta è maggiore di 0 (zero). |
| Precisione inventariale dell'ubicazione | Conteggio senza discrepanza                | WHSWorkLineCycleCount                 | Conteggi ciclo in cui la quantità di discrepanza assoluta è maggiore di 0 (zero). |
| Precisione inventariale dell'ubicazione | Conteggio con discrepanza                   | WHSWorkLineCycleCount                 | Conteggi ciclo in cui la quantità di discrepanza assoluta è uguale a 0 (zero). |
| Precisione inventariale dell'ubicazione | Articoli conteggiati nel tempo                  | WHSWorkLineCycleCount                 | Conteggio senza discrepanza e conteggio con discrepanza (vedere le relative descrizioni in precedenza nella tabella). |
| Precisione inventariale dell'ubicazione | Discrepanza quantità di articoli maggiore di % | WHSWorkLineCycleCount                 | La discrepanza media corrisponde alla quantità di discrepanza assoluta divisa per la quantità prevista in cui la quantità discrepanza assoluta è maggiore di 0 (zero). La quantità di discrepanza media corrisponde alla quantità di discrepanza assoluta media in cui la quantità discrepanza assoluta è maggiore di 0 (zero). Conteggio con discrepanza, conteggio totale, quantità prevista e quantità conteggiata in cui l'intera quantità è raggruppata per articolo e ubicazione (vedere le relative descrizioni in precedenza nella tabella). |
| Precisione inventariale dell'ubicazione | Conteggio articoli per lavoratore                     | WHSWorkLineCycleCount                 | Conteggio senza discrepanza e conteggio con discrepanza (vedere le relative descrizioni in precedenza nella tabella). |
| Precisione inventariale dell'ubicazione | Conteggio articoli per sito/magazzino           | WHSWorkLineCycleCount                 | Conteggio senza discrepanza e conteggio con discrepanza (vedere le relative descrizioni in precedenza nella tabella). |
| Precisione inventariale dell'ubicazione | Tasso di discrepanza per prodotto              | WHSWorkLineCycleCount                 | Tasso discrepanza (vedere la descrizione in precedenza nella tabella). |
| Prestazioni di spedizione        | Righe spedite                            | SalesLine               | Il numero di righe di vendita in cui le righe di vendita vengono spedite. |
| Prestazioni di spedizione        | In anticipo                                    | CustPackingSlipOnTimeStatus           | Righe di vendita in cui lo stato della data di spedizione è **1 (in anticipo)**. In anticipo significa che la data di spedizione del documento di trasporto è precedente alla data di spedizione confermata della riga di vendita. Se la data di spedizione confermata non è impostata, utilizzare la data di spedizione richiesta. |
| Prestazioni di spedizione        | Puntuale                                  | CustPackingSlipOnTimeStatus           | Righe di vendita in cui lo stato della data di spedizione è **2 (puntuale)**. Puntuale significa che la data di spedizione del documento di trasporto è uguale alla data di spedizione confermata della riga di vendita. Se la data di spedizione confermata non è impostata, utilizzare la data di spedizione richiesta. |
| Prestazioni di spedizione        | In ritardo                                     | CustPackingSlipOnTimeStatus           | Righe di vendita in cui lo stato della data di spedizione è **3 (in ritardo)**. In ritardo significa che la data di spedizione del documento di trasporto è successiva alla data di spedizione confermata della riga di vendita. Se la data di spedizione confermata non è impostata, utilizzare la data di spedizione richiesta. |
| Prestazioni di spedizione        | Spedizioni nel tempo                      | SalesLine CustPackingSlipOnTimeStatus | Ordini interamente spediti, dove l'intera quantità delle righe di vendita è stata spedita più in anticipo, con puntualità o in ritardo (vedere le relative descrizioni in precedenza nella tabella). |
| Prestazioni di spedizione        | Spedizioni in ritardo per città                     | CustPackingSlipOnTimeStatus           | In ritardo (vedere le descrizioni in precedenza nella tabella). |
| Prestazioni di spedizione        | Spedizioni per prodotto                       | CustPackingSlipOnTimeStatus           | In anticipo, puntuale e in ritardo (vedere le relative descrizioni in precedenza nella tabella). |
| Prestazioni di spedizione        | Spedizioni per cliente                      | CustPackingSlipOnTimeStatus           | In anticipo, puntuale e in ritardo (vedere le relative descrizioni in precedenza nella tabella). |
| Prestazioni di spedizione        | Spedizioni per sito/magazzino              | CustPackingSlipOnTimeStatus           | In anticipo, puntuale e in ritardo (vedere le relative descrizioni in precedenza nella tabella). |
