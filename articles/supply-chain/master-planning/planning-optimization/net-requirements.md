---
title: Fabbisogni netti e informazioni di pegging con Ottimizzazione pianificazione
description: Questo argomento fornisce informazioni sui fabbisogni netti calcolati e sul pegging in Ottimizzazione pianificazione.
author: crytt
ms.date: 7/28/2021
ms.topic: article
ms.search.form: ReqTransOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77b04f417e5bd8d236fa53810f9cbfe5860d9dd7
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343240"
---
# <a name="net-requirements-and-pegging-information-with-planning-optimization"></a>Fabbisogni netti e informazioni di pegging con Ottimizzazione pianificazione

[!include [banner](../../includes/banner.md)]

Quando si esegue Ottimizzazione pianificazione, è importante comprenderne l'output, il modo in cui l'offerta esistente copre la domanda e il motivo per cui è stata generata l'offerta specifica. Puoi usare la pagina **Fabbisogni netti** per comprendere meglio i fabbisogni calcolati prodotti dalla pianificazione generale.

La pagina **Fabbisogni netti** mostra i fabbisogni netti calcolati per il prodotto da Ottimizzazione pianificazione. Mostra anche le impostazioni di copertura che sono state applicate durante l'esecuzione della pianificazione generale, un'analisi dei totali dei fabbisogni per tipo di transazione e informazioni sul pegging.

## <a name="open-the-net-requirements-page"></a>Aprire la pagina dei fabbisogni netti

Puoi aprire la pagina **Fabbisogni netti** in uno dei seguenti modi:

- Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**. Seleziona o apri un prodotto. Quindi, nel riquadro azioni, nella scheda **Piano**, nel gruppo **Fabbisogno**, seleziona **Fabbisogni netti**.
- Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**. Apri un ordine cliente. Poi, nella scheda dettaglio **Righe ordine cliente** sulla barra degli strumenti, seleziona **Prodotto e fornitura \> Fabbisogni netti**.
- Andare a **Pianificazione generale \> Pianificazione generale \> Ordini pianificati**. Selezionare o aprire un ordine pianificato. Quindi, nel riquadro azioni, nella scheda **Visualizza**, nel gruppo **Fabbisogni**, seleziona **Profilo del fabbisogni**.

## <a name="use-the-net-requirements-page"></a>Usare la pagina dei fabbisogni netti

La pagina **Fabbisogni netti** è composta da una sezione superiore e una inferiore. Il riquadro azioni in questa pagina include un pulsante **Aggiorna**. Quando questo pulsante è selezionato, viene visualizzato un menu di comandi.

### <a name="select-a-master-plan-to-view"></a>Selezionare un piano generale da visualizzare

Prima di esaminare i fabbisogni netti del prodotto, assicurati di selezionare il piano principale pertinente nel campo **Piano** nella parte superiore della pagina.

### <a name="upper-section"></a>Sezione superiore

La sezione superiore della pagina fornisce le seguenti schede:

- **Panoramica** – Visualizza i fabbisogni dell'articolo delle dimensioni del prodotto.
- **Copertura articolo** – Visualizza le impostazioni di copertura utilizzate durante il calcolo dei fabbisogni.
- **Riepilogo** – Visualizza una ripartizione dei totali dei fabbisogni per tipo di transazione.
- **Periodo** – Visualizza le entrate, le uscite e l'inventario disponibile previsto per ogni periodo definito dal modello di periodo. È inoltre possibile ottenere una visualizzazione grafica dell'inventario disponibile previsto.

### <a name="lower-section"></a>Sezione inferiore

La sezione inferiore della pagina fornisce le seguenti schede:

- **Panoramica** – Visualizza l'elenco dei fabbisogni di prodotto che sono stati calcolati durante l'esecuzione della pianificazione generale, insieme alle transazioni in entrata e in uscita che corrispondono ai fabbisogni. Per impostazione predefinita, l'elenco è ordinato in base alla data del fabbisogno. Quando selezioni un fabbisogno, la scheda dettaglio **Pegging** nella sezione inferiore mostra l'origine del fabbisogno o le transazioni che soddisfano il fabbisogno.
- **Generale** – Visualizza informazioni dettagliate sul fabbisogno selezionato.
- **Azione** – Visualizza i messaggi di azione per i fabbisogni.

### <a name="the-action-pane"></a>Riquadro azioni

I seguenti comandi sono disponibili nel riquadro azioni:

- **Aggiorna \> Pianificazione generale** – Esegui la pianificazione generale direttamente dalla pagina **Fabbisogni netti**.
- **Aggiorna \> Pianificazione previsionale** – Esegui la pianificazione previsionale direttamente dalla pagina **Fabbisogni netti**. L'ottimizzazione della pianificazione non supporta ancora questa operazione.
- **Aggiorna \> Programmazione continuità** – Esegui la programmazione della continuità direttamente dalla pagina **Fabbisogni netti**. L'ottimizzazione della pianificazione non supporta ancora questa operazione.

## <a name="example-scenario"></a>Scenario di esempio

Questo esempio mostra come vengono presentate le informazioni di pegging nella pagina **Fabbisogni netti**.

### <a name="prerequisites"></a>Prerequisiti

Prima di esaminare questo scenario, devono essere soddisfatti i seguenti prerequisiti:

1. Devi lavorare su un sistema in cui sono disponibili i dati di esempio standard e devi impostare la persona giuridica su *USMF*.
2. Questo esempio utilizza il prodotto *1000*, che fa parte dei dati di esempio USMF. Assicurati che questo prodotto sia disponibile e che sia configurato nel modo seguente:

    - **Tipo di ordine predefinito:** *Ordine fornitore*
    - **Scorte disponibili:** *10,00*

3. Crea un ordine cliente per una quantità pari a *25,00* del prodotto *1000*. Utilizza le dimensioni di stoccaggio in cui si trovano le scorte disponibili.
4. Esegui la pianificazione generale per il piano generale *DynPlan*.

### <a name="review-the-calculated-requirements"></a>Esaminare i fabbisogni calcolati

Successivamente, apri la pagina **Fabbisogni netti** per il prodotto *1000* per esaminare come i fabbisogni calcolati corrispondano tra loro.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Seleziona il prodotto che ha un valore di **Codice articolo** pari a *1000*.
1. Nel riquadro azioni, nella scheda **Piano**, nel gruppo **Fabbisogno**, seleziona **Fabbisogni netti**.
1. Nella pagina **Fabbisogni netti** imposta il campo **Piano** su *DynPlan*.
1. Nella scheda **Panoramica** nella parte inferiore della pagina, verifica che i seguenti fabbisogni siano elencati come righe nella griglia.

    | Riferimento | Quantità del fabbisogno | Cumulato |
    |---|---|---|
    | Disponibilità | 10.00 | 10.00 |
    | Ordini fornitore pianificati | 15.00 | 25.00 |
    | Ordine cliente | -25,00 | (Vuoto) |

    > [!NOTE]
    > Il campo **Quantità fabbisogno** rappresenta la quantità totale che il fabbisogno richiede (se il valore è negativo) o fornisce (se il valore è positivo). Il campo **Cumulato** rappresenta le quantità totali di entrata e uscita cumulate durante il periodo selezionato.

1. Seleziona la riga del fabbisogno *Scorte disponibili* e poi, nella scheda dettaglio **Pegging** esamina i fabbisogni coperti da questa fornitura. La riga seguente viene visualizzata.

    | Riferimento | Quantità del fabbisogno | Quantità coperta |
    |---|---|---|
    | Ordine cliente | -25,00 | -10.00 |

    Le scorte disponibili esistenti coprono parzialmente la domanda proveniente dall'ordine cliente.

    ![Informazioni di pegging per le scorte disponibili](media/pegging-on-hand.png "Informazioni di pegging per le scorte disponibili")

1. Seleziona la riga del fabbisogno *Ordini fornitore pianificati* e poi, nella scheda dettaglio **Pegging** esamina i fabbisogni coperti da questa offerta. La riga seguente viene visualizzata.

    | Riferimento | Quantità del fabbisogno | Quantità coperta |
    |---|---|---|
    | Ordine cliente | -25,00 | -15,00 |

    Poiché l'ordine cliente è già stato parzialmente coperto, il sistema crea un ordine fornitore pianificato per la quantità scoperta rimanente.

    ![Informazioni di pegging per l'ordine fornitore pianificato](media/pegging-planned-purchase-order.png "Informazioni di pegging per l'ordine fornitore pianificato")

1. Seleziona la riga del fabbisogno *Ordine cliente* e poi, nella scheda dettaglio **Pegging** esamina i fabbisogni coperti da questa domanda. Le righe seguenti vengono visualizzate.

    | Riferimento | Quantità del fabbisogno | Quantità coperta |
    |---|---|---|
    | Disponibilità | 10.00 | 10.00 |
    | Ordini fornitore pianificati | 15.00 | 15.00 |

    ![Informazioni di pegging per l'ordine cliente](media/pegging-planned-purchase-order.png "Informazioni di pegging per l'ordine cliente")

> [!NOTE]
> Poiché Ottimizzazione pianificazione non supporta ancora alcune funzionalità, i tipi di fabbisogno *Scorta di sicurezza* e *Lotto scaduto* non sono inclusi nella pagina **Fabbisogni netti**. Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).
>
> Se stai utilizzando il motore di pianificazione generale integrato, i prodotti controllati da batch sono supportati. Per i prodotti controllati da batch le scorte disponibili scadute sono mostrate nella pagina **Fabbisogni netti**, ma non è sottoposto a pegging con i fabbisogni della domanda. Le righe delle scorte disponibili scadute di questo tipo sono visualizzate come righe di fabbisogno *Batch scaduto* nella pagina **Fabbisogni netti**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
