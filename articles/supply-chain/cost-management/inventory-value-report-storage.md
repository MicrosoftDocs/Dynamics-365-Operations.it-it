---
title: Report di archiviazione valori di magazzino
description: In questo argomento viene spiegato come eseguire un rapporto di archiviazione del valore di magazzino e rendere l'output disponibile in formato digitale, sia come pagina interattiva in Microsoft Dynamics 365 Supply Chain Management sia come documento esportato in uno dei diversi formati.
author: AndersGirke
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 1946ca72aa92b644e15e8a625577bdf4ef1506ff
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577746"
---
# <a name="inventory-value-storage-report"></a>Report di archiviazione valori di magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come eseguire un rapporto **Archiviazione valori di magazzino** e rendere l'output disponibile in formato digitale, sia come pagina interattiva in Microsoft Dynamics 365 Supply Chain Management o come documento esportato in uno dei diversi formati.

Quando visualizzi il rapporto nel tuo browser, le colonne e i saldi aggregati vengono regolati in modo dinamico, a seconda del layout che hai configurato. È possibile ordinare i risultati, filtrarli, approfondire i dati e altro ancora.

I risultati del report sono memorizzati nell'entità dati **Valore di inventario**. Di conseguenza, è possibile filtrare ed esportare i risultati in un formato come valori delimitati da virgole (CSV) o nel formato di Microsoft Excel.

Il report **Archiviazione del valore di inventario** è utile quando l'output contiene molte righe. Ad esempio, sono disponibili 50.000 articoli e sono stati creati 300 negozi come magazzini. In questo caso, se si richiedono saldi di fine inventario per articolo, sito e magazzino, l'output conterrà molte righe.

> [!NOTE]
> Nel report non vengono inclusi i subtotali che sono definiti nel layout del report. Inoltre non includerà i saldi di contabilità generale, anche quando sono definiti nel layout del report. La riconciliazione con la contabilità generale deve essere effettuata utilizzando i saldi di verifica.

## <a name="turn-on-the-inventory-value-storage-feature"></a>Attivare la funzione archiviazione valori di magazzino

Prima di poter generare un report **Archiviazione valori di magazzino**, è necessario attivare la funzionalità nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo** – Gestione costi
- **Nome della funzione** – Archiviazione valori di magazzino

## <a name="generate-an-inventory-value-storage-report"></a>Generare un report di archiviazione valori di magazzino

Seguire questi passaggi per generare e archiviare un report per l' **Archiviazione valori di magazzino**:

1. Passare a **Gestione costi \> Richieste di informazioni e report \> Report di archiviazione valori di magazzino**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Valore di inventario**, impostare i seguenti valori per definire quali record sono inclusi nel report:

    - Nella scheda dettaglio **Parametri**, immettere un nome univoco per il report e utilizzare i campi contenuti nella sezione **Intervallo date** per definire quali record sono inclusi nel report. Per definire l'intervallo di date, è possibile selezionare un intervallo predefinito (relativo alla data di generazione del report) nel campo **Codice intervallo di date** oppure selezionando date specifiche nei campi **Data iniziale** e **Data finale**.
    - Sulla scheda dettaglio **Record da includere**, impostare filtri e vincoli per definire quali dati sono inclusi nel report.
    - Nella scheda dettaglio **Esegui in background**, specificare come, quando e con quale frequenza viene generato il report.

    > [!NOTE]
    > Questo report viene sempre eseguito come parte di un processo batch.

1. Selezionare **OK** per applicare le impostazioni e chiudere la finestra di dialogo.

Al termine del processo batch, il report verrà elencato nella pagina **Report di archiviazione valori di magazzino**. Potrebbe essere necessario aggiornare la pagina per visualizzare il report.

## <a name="explore-an-inventory-value-storage-report"></a>Esplorare un report di archiviazione valori di magazzino

Dopo aver generato un report, è possibile visualizzarlo ed esplorarlo in qualsiasi momento seguendo questi passaggi.

1. Passare a **Gestione costi \> Richieste di informazioni e report \> Report di archiviazione valori di magazzino**.
1. Selezionare un report dell''elenco.
1. Selezionare **Visualizza dettagli** per mostrare il contenuto del report.
1. Esplorare il report seguendo uno di questi passaggi:

    - Come per la maggior parte delle pagine standard in Supply Chain Management, è possibile selezionare quasi qualsiasi intestazione di colonna per ordinare o filtrare la griglia in base ai valori in colonna.
    - Usare il campo **Filtro** per filtrare il report in base a qualsiasi valore in una delle diverse colonne disponibili.
    - Utilizzare il menu Visualizza (sopra il campo **Filtro** ) per salvare e caricare le combinazioni preferite di opzioni di ordinamento e filtro.

## <a name="export-an-inventory-value-storage-report"></a>Esportare un report di archiviazione valori di magazzino

Qualsiasi report generato viene archiviato nell'entità dati **Valori di inventario**. È possibile utilizzare le funzionalità standard di gestione dei dati di Supply Chain Management per esportare i dati da questa entità in qualsiasi formato di dati supportato, come CSV o Excel.

L'esempio seguente mostra come esportare un rapporto **Report valori di inventario**.

1. Passare all'**Amministrazione sistema \> Aree di lavoro \> Gestione dati**.
1. Nella sezione **Importare / Esportare**, selezionare il riquadro **Esportare**. 
1. Nella pagina visualizzata **Esportare**, impostare il processo di esportazione. Immettere innanzitutto un nome di gruppo per il lavoro.
1. Nella sezione **Entità selezionate**, selezionare **Aggiungi entità**.
1. Nella finestra di dialogo visualizzata, impostare i seguenti campi:

    - **Nome entità** - Selezionare **Valore di inventario**.
    - **Formato dei dati di destinazione** - Selezionare il formato in cui esportare i dati.

1. Selezionare **Aggiungi** per aggiungere la nuova riga e quindi selezionare **Chiudi** per chiudere la finestra di dialogo.
1. In genere, è possibile esportare un report alla volta. Per esportare un report singolo, impostare un filtro per la riga appena aggiunta alla finestra di dialogo **Richiesta**. In questo modo, è possibile definire quale report dall'entità **Valore di inventario** è incluso nell'esportazione. Seguire i passaggi seguenti per Impostare le opzioni di filtro ed esportare un singolo report:

    1. Nella scheda **Intervallo**, selezionare **Aggiungere** per aggiungere una nuova riga.
    2. Impostare il campo **Codice articolo** su **Valore di inventario**.
    3. Impostare il campo **Tabella derivata** su **Valore di inventario**.
    4. Impostare il campo **Campo** sul campo che si desidera filtrare. Generalmente, userete il campo **Nome esecuzione** e/o il campo **Tempo esecuzione**.
    5. Impostare il campo **Criteri** sul valore che si desidera cercare nel campo selezionato. (Se si è selezionato il campo **Nome esecuzione** nel passaggio precedente, questo valore sarà il nome del report. Se si è selezionato il campo **Tempo esecuzione**, sarà il momento in cui il report è stato generato).
    6. Se necessario, aggiungere più righe nella scheda **Intervallo** in base alle esigenze, fino a che non è stato identificato in modo univoco il report che si sta cercando.

1. Selezionare **OK** per salvare le impostazioni e chiudere la finestra di dialogo.
1. Selezionare **Salva** per salvare l'impostazione dell'esportazione.
1. Nella scheda **Opzioni di esportazione** selezionare **Esporta adesso** per generare il file di esportazione.
1. Nella pagina visualizzata **Riepilogo dell'esecuzione**, è possibile vedere lo stato del processo di esportazione e l' elenco delle entità esportate. Nella sezione **Stato elaborazione entità** selezionare l'entità **Valore di inventario** nell'elenco e quindi selezionare **Scarica file** per scaricare i dati esportati da tale entità.

Per ulteriori informazioni su come utilizzare la gestione dei dati per esportare i dati, vedere [Panoramica processi di importazione ed esportazione dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]