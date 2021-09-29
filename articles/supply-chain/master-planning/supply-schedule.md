---
title: Programmazione fornitura
description: In questo argomento vengono fornite informazioni sulla pagina Programmazione fornitura e le relative funzionalità.
author: crytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: ReqSupplyDemandSchedule, ReqSupplyDemandScheduleFilters, ReqSupplyDemandItemDetails, ReqTransFuturesActionsPart, ReqSupplyDemandOverviewLegendPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0760fcd5408d3960dcc55f773b4e09efc3c9f81c
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505581"
---
# <a name="supply-schedule"></a>Programmazione fornitura

[!include [banner](../includes/banner.md)]

La pagina **Programmazione fornitura** mostra una panoramica completa della domanda e dell'offerta per un prodotto o una famiglia di prodotti. Le informazioni vengono filtrate per ubicazione, piano generale e periodi. È inoltre possibile utilizzare la pagina per creare nuovi ordini, modificare ordini pianificati esistenti ed eseguire la pianificazione generale.

## <a name="open-the-supply-schedule-page"></a>Aprire la pagina Programmazione fornitura

Puoi aprire la pagina **Programmazione fornitura** in uno dei seguenti modi:

- Vai a **Pianificazione generale \> Pianificazione generale \> Programmazione fornitura**. Nella finestra di dialogo **Modifica filtro** specifica il piano e il prodotto che stai cercando inserendo i valori del filtro nei campi forniti. (Nel resto di questo argomento, la raccolta di valori di filtro immessi viene denominata "il filtro" o "il filtro corrente".) Al termine, seleziona **OK**.
- Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**. Seleziona o apri un prodotto. Quindi, nel riquadro azioni, nella scheda **Piano**, nel gruppo **Visualizza**, seleziona **Programmazione fornitura**.
- Vai a **Pianificazione generale \> Impostazioni \> Previsione della domanda \> Chiavi di allocazione articoli**. Seleziona una chiave di allocazione articolo utilizzata come famiglia di prodotti. Quindi nel riquadro azioni seleziona **Programmazione fornitura**.
- Andare a **Pianificazione generale \> Pianificazione generale \> Ordini pianificati**. Selezionare o aprire un ordine pianificato. Quindi, nel riquadro azioni, nella scheda **Visualizza**, nel gruppo **Visualizza**, seleziona **Programmazione fornitura**.

> [!NOTE]
> Quando apri la pagina **Programmazione fornitura** da un prodotto, una famiglia di prodotti o un ordine pianificato, non è necessario immettere valori di filtro. Il sistema utilizzerà il modello di periodo predefinito.

## <a name="use-the-supply-schedule-page"></a>Usare la pagina Programmazione fornitura

La pagina **Programmazione fornitura** è composta da una sezione superiore, la scheda dettaglio **Inventario di fine periodo**, una Scheda dettaglio aggiuntiva che diventa visibile, in base alla riga selezionata nella sezione superiore e al riquadro Dettaglio informazioni. (Per aprire il riquadro Dettaglio informazioni e visualizzare un Dettaglio informazioni, seleziona **Informazioni correlate** sul bordo destro della pagina.)

### <a name="upper-section"></a>Sezione superiore

La parte superiore della pagina **Programmazione fornitura** contiene una griglia che mostra i seguenti dati per un prodotto o una famiglia di prodotti. Questi dati sono suddivisi per periodi definiti dal valore **Modello di periodo** dal filtro.

- **Inventario di inizio periodo** – Questa riga mostra il saldo scorte previsto all'inizio del periodo se vengono eseguiti tutti gli ordini nel sistema.
- **Inventario di fine periodo** – Questa riga mostra il saldo scorte previsto alla fine del periodo se vengono eseguiti tutti gli ordini nel sistema.
- **Inventario sottoposto a pegging di fine periodo** – Questa riga mostra la quantità di scorte alla fine del periodo sottoposto a pegging rispetto alla domanda futura.
- **Offerta netta per periodo** – Questa riga mostra la differenza tra domanda e offerta nel periodo.
- **Inventario minimo** – Questo nodo mostra le scorte di sicurezza per un prodotto o una famiglia di prodotti. Per espandere o comprimere questo nodo, selezionalo, quindi seleziona **Espandi** o **Comprimi** sulla barra degli strumenti. Questo nodo viene visualizzato solo quando sono presenti scorte di sicurezza per il prodotto o la famiglia di prodotti.
- **Domanda** – Questo nodo mostra la domanda per un prodotto o una famiglia di prodotti. La domanda è raggruppata per tipo di transazione. Per espandere o comprimere questo nodo, selezionalo, quindi seleziona **Espandi** o **Comprimi** sulla barra degli strumenti. I tipi di transazione della domanda includono vendite, trasferimenti e giornali di registrazione magazzino. Questo nodo viene visualizzato solo quando è presente la domanda per il prodotto o la famiglia di prodotti.
- **Offerta** – Questo nodo mostra l'offerta per un prodotto o una famiglia di prodotti. L'offerta è raggruppata per tipo di transazione. Per espandere o comprimere questo nodo, selezionalo, quindi seleziona **Espandi** o **Comprimi** sulla barra degli strumenti. I tipi di transazione di offerta includono produzione, acquisto e trasferimenti. Questo nodo viene visualizzato solo quando è presente l'offerta per il prodotto o la famiglia di prodotti.

Molti dei pulsanti della barra degli strumenti disponibili, dei riquadri Dettaglio informazioni e delle visualizzazioni Scheda dettaglio dipendono dalle selezioni nella sezione superiore. In genere, sceglierai un tipo di transazione selezionando una delle righe sotto il nodo **Offerta** o **Domanda**. Sceglierai quindi un periodo selezionando una colonna specifica per la riga selezionata.

La barra degli strumenti sopra la griglia nella parte superiore della pagina **Programmazione fornitura** fornisce i seguenti pulsanti:

- **Espandi/Comprimi** – Espandi o comprimi un nodo selezionato, come il nodo **Domanda**, il nodo **Offerta** e i relativi sottonodi. (I nodi mostrano il prefisso **\[+\]** o **\[-\]** per indicare se sono attualmente compressi o espansi.)
- **Nuovo** – Apri un menu in cui ogni comando, a sua volta, apre una finestra di dialogo o una pagina che consente di aggiungere un tipo specifico di elemento per la selezione. I comandi disponibili includono **Offerta prevista**, **Ordine pianificato**, **Kanban programmato**, **Nuovo ordine di produzione**, **Ordine fornitore**, e **Ordine di trasferimento**.
- **Pianificazione generale** – Esegui la pianificazione generale. Viene visualizzata una finestra di dialogo in cui è possibile specificare il piano da eseguire. Il campo **Piano generale** viene impostato per impostazione predefinita in base al filtro corrente.
- **Dichiarazione di finito max** - Apri la pagina **Dichiarazione di finito max** per il prodotto definito nel filtro corrente.
- **Aggiorna ordini pianificati** - Apri la pagina **Ordini pianificati** che mostra gli ordini pianificati per il prodotto o la famiglia di prodotti definita nel filtro corrente.
- **Livello** – Distribuisci gli ordini pianificati in base alle impostazioni dalla finestra di dialogo che appare.
- **Criteri del piano materiali per ubicazione** - Apri la pagina **Copertura articolo** per il prodotto definito nel filtro corrente.
- **Regola Kanban** - Apri la pagina **Regole Kanban** per il prodotto definito nel filtro corrente.

### <a name="fasttabs"></a>Schede dettaglio

La pagina **Programmazione fornitura** può contenere le seguenti Schede dettaglio:

- **Inventario di fine periodo** – Questa Scheda dettaglio mostra i dati di inventario di fine periodo in formato grafico.
- **Profilo offerta** – Questa Scheda dettaglio mostra i dati dell'offerta in formato grafico. Diventa visibile quando selezioni il nodo **Offerta** o una riga sottostante nella sezione superiore.
- **Riepilogo** – Questa Scheda dettaglio mostra i dettagli di riepilogo relativi al tipo di transazione selezionato nella sezione superiore. Ad esempio, se selezioni **Vendite** sotto il nodo **Domanda**, questa Scheda dettaglio mostra i campi relativi agli ordini cliente, come ad esempio **Righe ordine cliente richieste** o **Importo totale**. Se selezioni **Ordini di produzione** nel sottonodo **Produzione** del nodo **Offerta**, questa Scheda dettaglio mostra i campi relativi agli ordini di produzione, ad esempio **Ordini di produzione programmati** o **Totale programmato**. I valori dei campi dipendono dal periodo selezionato nella sezione superiore. 
- **\[Tipo di transazione\] - \[Periodo\]** – Questa Scheda dettaglio mostra gli ordini per il tipo di transazione e il periodo selezionati nella sezione superiore. Il nome della Scheda dettaglio riflette tali selezioni. Ad esempio, potrebbe essere denominata **Ordini di vendita - Backlog** o **Ordini di produzione - Settimana 37**.

### <a name="action-pane"></a>Riquadro azioni

I seguenti pulsanti sono disponibili nel riquadro azioni:

- **Modifica filtro** - Apri la finestra di dialogo **Modifica filtro** in cui è possibile aggiornare i valori del filtro e quindi riapri la pagina **Programmazione fornitura** che riflette le impostazioni del filtro aggiornate.
- **Mostra ritardi** – Evidenzia le righe pertinenti nella sezione superiore se è presente un ordine ritardato di quel tipo di transazione.

### <a name="factbox-pane"></a>Riquadro Dettaglio informazioni

Per aprire il riquadro Dettaglio informazioni e visualizzare un Dettaglio informazioni, seleziona **Informazioni correlate** sul bordo destro della pagina. I seguenti riquadri Dettaglio informazioni sono disponibili nella pagina **Programmazione fornitura**:

- **Dettagli articolo** – Questo riquadro Dettaglio informazioni mostra le informazioni di base sul prodotto che è definito nel filtro corrente. È vuoto se hai definito una famiglia di prodotti nel filtro.
- **Azioni** – Questo riquadro Dettaglio informazioni mostra le azioni per gli ordini del tipo di transazione selezionato nella sezione superiore.
- **Ritardi** – Questo riquadro Dettaglio informazioni mostra i ritardi per gli ordini del tipo di transazione selezionato nella sezione superiore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
