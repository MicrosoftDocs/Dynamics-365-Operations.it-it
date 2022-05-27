---
title: Richieste di informazioni di Costo sbarcato
description: In questo argomento viene descritto come trovare e utilizzare vari tipi di richieste di informazioni disponibili per il modulo Costo sbarcato.
author: Weijiesa
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8a1ec063f10634de92b1e7500d4dda111e879b62
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693418"
---
# <a name="landed-cost-inquiries"></a>Richieste di informazioni di Costo sbarcato

[!include [banner](../../includes/banner.md)]

## <a name="voyage-line-inquiries"></a>Richieste di informazioni Linee di viaggio

La richiesta di informazioni **Righe di viaggio** mostra tutte le righe di viaggio relative all'inventario. Questa richiesta di informazioni può essere utilizzata come filtro per trovare un articolo, un ordine fornitore o altre informazioni utili. Può anche essere utilizzata per identificare la data di consegna prevista di un articolo che potrebbe essere in uno o più viaggi. In questo modo, può aiutare nella gestione della ricezione dell'inventario prevista.

Per aprire questa richiesta, selezionare **Costo sbarcato \> Richieste di informazioni \> Righe di viaggio**.

### <a name="overview-tab"></a>Scheda Panoramica

La scheda **Panoramica** della pagina della richiesta di informazioni **Righe di viaggio** include una griglia che mostra le informazioni di base su ciascuna riga di viaggio pertinente. Nella tabella seguente vengono descritte le colonne nella griglia.

| Colonna | Descrizione |
|---|---|
| **Numero articolo** | L'articolo della riga di viaggio. |
| **Riferimento** | Il tipo di ordine (ordine fornitore o ordine di trasferimento). |
| **Numero** | Il numero di ordine fornitore o di ordine di trasferimento. |
| **Registrazione** | La registrazione associata alla riga di viaggio. |
| **Contenitore di spedizione** | Il contenitore di spedizione associato alla riga di viaggio. |
| **Viaggio** | Il viaggio associato alla riga di viaggio. |
| **Quantità** | La quantità dell'articolo per la riga di viaggio. |
| (Altre dimensioni) | È possibile visualizzare colonne per ulteriori dimensioni come necessario. Tali dimensioni includono il numero di batch, lo stato dell'inventario e il magazzino. Nel riquadro Azioni selezionare **Magazzino \> Visualizza dimensioni** per aprire una finestra di dialogo in cui è possibile selezionare le dimensioni da includere. |

### <a name="general-tab"></a>Scheda Generale

Selezionare la scheda **Generale** per visualizzare ulteriori informazioni sulla riga attualmente selezionata nella scheda **Panoramica**.

### <a name="dimensions-tab"></a>Scheda Dimensioni

Selezionare la scheda **Dimensioni** per visualizzare i valori per tutte le dimensioni disponibili della riga attualmente selezionata nella scheda **Panoramica**, indipendentemente dalle dimensioni selezionate per la visualizzazione in quella scheda.

## <a name="cost-estimate-inquiries"></a>Richieste di informazioni sulle stime dei costi

Ogni volta che si genera una stima dei costi, la stima viene aggiunta alla pagina della richiesta di informazioni **Stime dei costi**. Per dettagli completi su come generare, visualizzare e utilizzare le stime dei costi (comprese le stime nella pagina di della richiesta), vedere [Stimare e gestire i costi sbarcati](estimate-manage-landed-costs.md).

## <a name="item-tracking"></a>Tracciabilità articolo

Utilizzare la pagina **Tracciabilità articolo** per visualizzare le righe di ordini fornitore aperte e il relativo stato corrente. Le righe non devono essere associate a un viaggio per apparire qui. Tuttavia, se un articolo è associato a un viaggio, la riga del record Tracciabilità articolo mostra l'ID viaggio.

Per aprire questa pagina, selezionare **Costo sbarcato \> Richieste di informazioni \> Tracciabilità \> Tracciabilità articolo**.

Poiché il sistema probabilmente contiene un numero molto elevato di righe di ordine fornitore, la pagina **Tracciabilità articolo** inizialmente non mostra alcun record. Iniziare utilizzando i campi di filtro nella parte superiore della pagina per definire l'insieme di righe di ordine fornitore che si sta cercando. Quindi selezionare **Aggiorna** nel riquadro Azioni per generare l'elenco. È possibile usare un asterisco (\*) come carattere jolly in un qualsiasi campo di filtro. Ad esempio, per trovare tutte le righe di ordine fornitore per articoli che includono la parola "DVD" nel nome, impostare il campo **Tipo** su **Nome prodotto** ed immettere *\*DVD\** nel campo **Valore campo**.

> [!NOTE]
> Attualmente, gli ordini arretrati includono solo gli ordini cliente. Le offerte di vendita non sono mostrate o considerate come ordini arretrati.

La tabella seguente descrive le colonne nella griglia della pagina **Tracciabilità articolo**.

| Colonna | Descrizione |
|---|---|
| **Porto di destinazione** | La destinazione finale. |
| **Confermata** | La data confermata della riga di ordine fornitore. |
| **Data di consegna** | La data di consegna della riga di ordine fornitore. |
| **Viaggio** | Se la riga è associata a un viaggio, l'ID viaggio. |
| **Contenitore di spedizione** | Se la riga è associata a un contenitore di spedizione, l'ID contenitore. |
| **Porto di spedizione** | Il porto corrente, in base al primo scalo nel modulo di tracciabilità in cui non è impostata alcuna data effettiva per il contenitore di spedizione associato alla riga di ordine fornitore. |
| **Attività** | L'attività corrente, in base al primo scalo nel modulo di tracciabilità in cui non è impostata alcuna data effettiva per il contenitore di spedizione associato alla riga di ordine fornitore. |
| **Data di fine stimata** | La data in cui si prevede di ricevere il viaggio presso il magazzino di destinazione. |
| **Nome** | Il nome del fornitore. |
| **Stato viaggio** | Lo stato di spedizione associato alla riga di ordine fornitore. |
| **Numero articolo** | Il numero di articolo della riga di ordine fornitore. |
| **Esterno** | Il nome dell'articolo fornitore. |
| **Nome prodotto** | Il nome dell'articolo della riga di ordine fornitore. |
| **Quantità** | La quantità della riga di ordine fornitore. |
| **Unità** | L'unità di misura della riga di ordine fornitore. |
| **Riferimento** | Il tipo di ordine (ordine fornitore o ordine di trasferimento) |
| **Numero di riferimento** | Il numero di ordine fornitore o di ordine di trasferimento. |
| **Ordine arretrato** | Un simbolo indica che sono presenti ordini cliente arretrati per l'articolo. |
| (Altre dimensioni) | È possibile visualizzare colonne per ulteriori dimensioni come necessario. Tali dimensioni includono il numero di batch, lo stato dell'inventario e il magazzino. Nel riquadro Azioni selezionare **Visualizza dimensioni** per aprire una finestra di dialogo in cui è possibile selezionare le dimensioni da includere. |

### <a name="related-information-about-backorders"></a>Informazioni correlate sugli ordini arretrati

Per visualizzare ulteriori informazioni sugli ordini arretrati, selezionare la scheda **Informazioni correlate** sul lato destro della pagina, quindi selezionare **Ordini arretrati**. Per visualizzare ancora più informazioni su uno specifico ordine arretrato, selezionare la riga corrispondente, quindi selezionare il collegamento **Altro**.

## <a name="individual-shipping-container-tracking"></a>Tracciabilità contenitore di spedizione individuale

La richiesta di informazioni **Tracciabilità contenitore di spedizione individuale** fornisce un filtro che consente di trovare un contenitore di spedizione e quindi identificare tutte le righe di viaggio in quel contenitore.

Per aprire questa richiesta, selezionare **Costo sbarcato \> Richieste di informazioni \> Tracciabilità \> Tracciabilità contenitore di spedizione individuale**.

## <a name="multiple-shipping-container-tracking"></a>Tracciabilità più contenitori di spedizione

La richiesta di informazioni **Tracciabilità più contenitori di spedizione** fornisce un filtro che consente di trovare una raccolta di contenitori di spedizione e quindi identificare tutte le righe di viaggio in quei contenitori.

Per aprire questa richiesta, selezionare **Costo sbarcato \> Richieste di informazioni \> Tracciabilità \> Tracciabilità più contenitori di spedizione**.
