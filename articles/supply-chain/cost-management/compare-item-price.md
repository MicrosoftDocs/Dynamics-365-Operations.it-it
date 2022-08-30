---
title: Report per confrontare i prezzi degli articoli in magazzino
description: Informazioni su come generare un report per confrontare i prezzi degli articoli in magazzino e quindi sfogliare e/o esportare il risultato.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c6373679299b68413d75236ca8cc18ceba03e091
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334987"
---
# <a name="compare-item-prices-storage-report"></a>Report per confrontare i prezzi degli articoli in magazzino

[!include [banner](../includes/banner.md)]

Questo articolo spiega come eseguire a report per **confrontare i prezzi degli articoli in magazzino** e rendere disponibile l'output in formato digitale, sia come pagina interattiva in Dynamics 365 Supply Chain Management o come documento esportato in uno dei diversi formati.

Quando si visualizza il report in un browser, le colonne e i saldi aggregati vengono modificati in modo dinamico, a seconda del layout configurato. È possibile ordinare i risultati, filtrarli, approfondire i dati e altro ancora.

I risultati del report sono memorizzati nell'entità dati **Confronta prezzi articoli**, che consente di filtrare ed esportare i risultati in un formato come CSV o Microsoft Excel.

Il report per **confrontare i prezzi degli articoli in magazzino** è utile nei casi in cui l'output contiene molte righe. Ad esempio, l'output conterrà molte righe se nella versione di determinazione costi sono presenti più di 40.000 articoli con un prezzo in sospeso.

## <a name="turn-the-compare-item-prices-storage-feature-on-or-off"></a>Attivare o disattivare la funzionalità Archiviazione confronto prezzi articoli

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Archiviazione confronto prezzi articoli* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="generate-a-compare-item-prices-storage-report"></a>Generare un report in cui vengono confrontati i prezzi degli articoli in magazzino

Seguire questi passaggi per generare e archiviare un report per **confrontare i prezzi degli articoli in magazzino**:

1. Andare a **Gestione costi > Richieste di informazioni e report > Report costi predeterminati > Confronta prezzi degli articoli in magazzino**.

1. Selezionare **Nuovo** per aprire il riquadro **Confronta prezzi articoli**. Impostare le seguenti opzioni per definire quali prezzi confrontare nel report:

    - Sulla scheda dettaglio **Parametri**, assegnare al report un **Nome** univoco e usare i campi nelle sezioni **Prezzi in sospeso da confrontare** e **Prezzi utilizzati per il confronto** per definire quali prezzi e date confrontare.
    - Sulla scheda dettaglio **Record da includere**, impostare filtri e vincoli per definire quali dati includere nel report.
    - Sulla scheda dettaglio **Esegui in background**, impostare come, quando e la frequenza con cui si desidera generare il report.
    > [!NOTE]
    > Questo report viene sempre eseguito come parte di un processo batch.

1. Selezionare **OK** per applicare le impostazioni e chiudere il riquadro.

1. Una volta completato, il processo batch viene elencato nella pagina **Confronta prezzi degli articoli in magazzino**. È possibile dover aggiornare la pagina per visualizzare il report.

## <a name="explore-the-compare-item-prices-storage-report"></a>Esplorare il report in cui vengono confrontati i prezzi degli articoli in magazzino

Dopo aver generato un report, puoi visualizzarlo ed esplorarlo in qualsiasi momento come segue:

1. Andare a **Gestione costi > Richieste di informazioni e report > Report costi predeterminati > Confronta prezzi degli articoli in magazzino**.

1. Selezionare un report dall'elenco.

1. Effettuare una delle seguenti operazioni:

    - Selezionare **Panoramica** per visualizzare una panoramica dei risultati del report.
    - Selezionare **Visualizza dettagli** per visualizzare una visione più dettagliata del report

1. Una volta aperte le visualizzazioni selezionate, è possibile effettuare le seguenti operazioni:

    - Selezionare quasi qualsiasi intestazione di colonna per ordinare o filtrare la tabella in base ai valori di quella colonna, proprio come per la maggior parte dei moduli standard in Supply Chain Management. Nota che non è possibile ordinare o filtrare la colonna **Prezzo di variazione netto %** perché è un campo calcolato.
    - Selezionare **Visualizzazione dimensioni** per aprire un riquadro in cui è possibile scegliere quale colonna dimensione includere nel modulo. Impostare **Salva impostazione** su **Sì** se si desidera salvare queste impostazioni in modo che vengano conservate alla successiva apertura del report. Selezionare **OK** per applicare le impostazioni e chiudere.
    - Selezionare una riga qualsiasi nel modulo, quindi selezionare **Visualizza dettagli** per visualizzare ulteriori informazioni sull'articolo selezionato. Da qui sarà possibile approfondire i dati.
    - Selezionare una riga qualsiasi nel modulo, quindi selezionare **Visualizza grafico di confronto** per visualizzare una rappresentazione grafica interattiva dei risultati in relazione all'articolo selezionato. È possibile esplorare questi risultati selezionando vari elementi grafici nella legenda del grafico e nel grafico.
    - Selezionare una riga qualsiasi nel modulo, quindi selezionare **Visualizza dettagli calcolo** per visualizzare ulteriori informazioni sui calcoli correlati all'articolo selezionato. Da qui sarà possibile approfondire i dati.

## <a name="export-the-compare-item-prices-storage-report"></a>Esportare il report in cui vengono confrontati i prezzi degli articoli in magazzino

Ogni report generato viene archiviato nell'entità di dati **Confronta prezzi degli articoli**. È possibile utilizzare le funzionalità standard di gestione dei dati di Supply Chain Management per esportare i dati da questa entità in qualsiasi formato di dati supportato, incluso CSV o Microsoft Excel.

Il seguente è un esempio di come esportare nel report **Confronta prezzi degli articoli in magazzino**:

1. Andare a **Amministrazione sistema > Aree di lavoro > Gestione dati**.

1. Selezionare il pulsante **Esporta** nella sezione **Gestione dati**.

1. Viene visualizzata la pagina **Esporta** che verrà utilizzata per impostare il processo di esportazione. Iniziare assegnando al processo un **Nome gruppo**.

1. Nella sezione **Entità selezionate** selezionare **Aggiungi entità** per aprire una finestra di dialogo in cui è possibile impostare le seguenti opzioni:

    - **Nome entità** - Selezionare **Confronta prezzi articoli**.
    - **Formato dei dati di destinazione** - Scegliere il formato in cui si desidera esportare.

1. Selezionare **Aggiungi** per aggiungere la nuova riga e quindi selezionare **Chiudi** per chiudere la finestra di dialogo.

1. Di solito si esporta un report alla volta. Per fare ciò, impostare un **Filtro** per la riga appena aggiunta al riquadro **Richiesta informazioni**. Questo permetterà di definire i report dell'entità **Confronta prezzi articoli** che si desidera includere nell'esportazione. Impostare le seguenti opzioni di filtro per esportare un singolo report:

    - Sulla scheda **Intervallo**, selezionare **Aggiungi** per aggiungere una nuova riga.
    - Impostare **Tabella** su **Confronta prezzi articoli**.
    - Impostare **Tabella derivata** su **Confronta prezzi articoli**.
    - Impostare **Campo** sul campo in base al quale si desidera filtrare. Di solito si usa **Nome esecuzione** o **Tempo esecuzione**.
    - Impostare **Criteri** sul valore del campo selezionato che si desidera cercare (il nome del report o l'ora in cui il report è stato generato).
    - Se necessario, aggiungere più righe alla tabella **Intervallo** fino a quando non è stato identificato in modo univoco il report che si sta cercando.

1. Selezionare **OK** per salvare le impostazioni e chiudere.

1. Selezionare **Salva** per salvare l'impostazione dell'esportazione.

1. Aprire la scheda **Opzioni di esportazione** e selezionare **Esporta ora** per generare il file di esportazione.

1. Viene visualizzata la pagina **Riepilogo dell'esecuzione** in cui è possibile vedere lo stato del processo di esportazione e un elenco di entità esportate. Selezionare l'entità **Confronta prezzi articoli** elencata nell'area **Stato elaborazione entità** e quindi selezionare **Scarica file** per scaricare i dati esportati da tale entità.

Per ulteriori informazioni su come utilizzare la gestione dei dati per esportare i dati, vedere [Panoramica processi di importazione ed esportazione dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]