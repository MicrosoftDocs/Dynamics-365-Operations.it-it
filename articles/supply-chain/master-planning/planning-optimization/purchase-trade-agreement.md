---
title: Pianificazione generale con accordi commerciali di acquisto
description: Questo articolo descrive come la pianificazione generale può trovare il fornitore e/o il lead time per un ordine pianificato, in base al prezzo o al lead time migliore presente negli accordi commerciali di acquisto.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c36827738b13d5ca71da910d32e8877c1a408f62
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740987"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Pianificazione generale con accordi commerciali di acquisto

[!include [banner](../../includes/banner.md)]

Questo articolo descrive come la pianificazione generale può trovare il fornitore e/o il lead time per un ordine pianificato, in base al prezzo o lead time migliore presente negli accordi commerciali di acquisto specificati per un determinato prodotto.

## <a name="turn-the-purchase-trade-agreements-for-planning-optimization-feature-on-or-off"></a>Attivare o disattivare la funzionalità Accordi commerciali di acquisto per Ottimizzazione pianificazione

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Accordi commerciali di acquisto per Ottimizzazione pianificazione* nell'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Preparare il sistema per valutare gli accordi commerciali di acquisto durante la pianificazione generale

Attenersi alla seguente procedura per configurare il sistema e applicare la pianificazione generale che valuta gli accordi commerciali di acquisto.

1. Andare a **Pianificazione generale \> Impostazioni \>Parametri di pianificazione generale**. Nella scheda **Ordini pianificati**, nella sezione **Fornitore**, impostare i seguenti valori:

    - **Trova accordi commerciali** - Impostare questa opzione su **Sì** per includere gli accordi commerciali di acquisto nella pianificazione generale.
    - **Criterio di ricerca** - Selezionare il fattore a cui assegnare la priorità per ciascun accordo commerciale di acquisto: **Lead time minimo** o **Prezzo unitario minimo**.

1. Andare a **Parametri di approvvigionamento \> Impostazioni \> Prezzi e sconti \> Attiva prezzo/sconto** e assicurarsi che l'opzione **Fornitore** sia impostata su **Sì**.
1. Andare a **Gestione informazioni sul prodotto \> Impostazioni \> Gruppi di varianti e dimensioni \> Gruppi di dimensioni di immagazzinamento** e selezionare un gruppo di dimensioni di immagazzinamento che viene applicato ai prodotti per i quali la pianificazione generale deve valutare gli accordi commerciali di acquisto. Assicurarsi che ogni dimensione di immagazzinamento pertinente in questo gruppo abbia un segno di spunta nella colonna **Per prezzi di acquisto**. Ripetere questo passaggio per tutti gli altri gruppi di dimensioni di immagazzinamento pertinenti.

## <a name="prepare-a-released-product-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Preparare un prodotto rilasciato per valutare gli accordi commerciali di acquisto durante la pianificazione generale

Dopo aver preparato il sistema come descritto nella sezione precedente, è necessario attenersi alla seguente procedura per assicurarsi che ogni prodotto che si desidera utilizzare con questa funzionalità sia impostato correttamente.

1. Andare a **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati** e aprire un prodotto di destinazione.
1. Nella Scheda dettaglio **Acquisto**, assicurarsi che nessun fornitore sia indicato nel campo **Fornitore**.
1. Nel riquadro azioni, nel gruppo **Piano** della scheda **Pianificazione**, selezionare **Copertura articolo** per aprire la pagina **Copertura articolo** per il prodotto selezionato. Verificare le seguenti impostazioni:

    - Nella scheda **Generale**, è possibile impostare le sostituzioni fornitore. Se la pianificazione generale deve utilizzare accordi commerciali di acquisto per selezionare un fornitore, è necessario impedire le sostituzioni fornitore deselezionando la casella di controllo **Usa impostazioni specifiche**.
    - Nella scheda **Lead time**, è possibile impostare le sostituzioni lead time. Se la pianificazione generale deve utilizzare accordi commerciali di acquisto per selezionare i lead time, è necessario impedire le sostituzioni lead time. Deselezionare la casella di controllo per ogni tipo di lead time che si desidera selezionare utilizzando accordi commerciali di acquisto ( **Acquisto**, **Produzione** e/o **Trasferimento**).

1. Chiudere la pagina **Copertura articolo** per tornare alla pagina dettagli del prodotto selezionato.
1. Nel riquadro azioni, nel gruppo **Previsione** della scheda **Piano**, selezionare **Previsione dell'offerta** per aprire la pagina **Previsione dell'offerta**. Assicurarsi che nessuna riga visualizzata qui abbia un valore nella colonna **Conto fornitore**.
1. Chiudere la pagina **Previsione dell'offerta** per tornare alla pagina dettagli del prodotto selezionato.
1. Nel riquadro azioni, nel gruppo **Accordi commerciali** della scheda **Acquisto**, selezionare **Visualizza accordi commerciali**. Assicurarsi che siano elencati tutti gli accordi commerciali di acquisto pertinenti. Assicurarsi anche che l'opzione **Ignora lead time** sia impostata su **No** per ogni accordo in cui la pianificazione generale deve utilizzare il lead time specificato per tale accordo.
1. Nel riquadro azioni, nel gruppo **Impostazioni ordine** della scheda **Piano** , selezionare **Impostazioni ordine predefinite** per aprire la pagina **Impostazioni ordine predefinite** per il prodotto selezionato. Nella Scheda dettaglio **Ordine fornitore**, visualizzare il valore del campo **Lead time acquisto**. Se non viene definita alcuna sostituzione lead time per la copertura dell'articolo, la pianificazione generale utilizzerà questo valore quando seleziona gli accordi commerciali in cui l'opzione **Ignora lead time** è impostata su **Sì**. Pertanto, è necessario rettificare questo valore come necessario.
1. Ripetere questa procedura per ogni prodotto pertinente.

> [!NOTE]
> La pianificazione generale supporta gli accordi commerciali di acquisto commerciali con più valute. Quando si cerca un accordo commerciale utilizzando l'opzione **Prezzo unitario più basso**, il sistema prenderà in considerazione le righe degli accordi commerciali di acquisto con valute diverse a condizione che sia stato definito un tasso di cambio tra la valuta della riga dell'accordo commerciale e la valuta contabile della persona giuridica. In caso contrario, la riga dell'accordo commerciale verrà ignorata e verrà visualizzato un errore durante la pianificazione generale. Pertanto, la pianificazione generale includerà le informazioni da tutte le righe degli accordi commerciali di acquisto pertinenti in cui i prezzi possono essere convertiti nella valuta contabile. È importante notare che le regole di arrotondamento non saranno prese in considerazione durante la conversione del prezzo di riga dell'accordo commerciale.

## <a name="examples-of-how-master-planning-finds-vendor-and-lead-times"></a>Esempi di come la pianificazione generale trova il fornitore e i lead time

La tabella seguente fornisce esempi che mostrano in che modo le varie impostazioni per un prodotto rilasciato e i relativi accordi commerciali di acquisto influenzano i valori rilevati per l'ordine fornitore pianificato risultante. I valori in **grassetto** nelle due colonne più a destra sono i valori selezionati dalla pianificazione generale. I valori in **_grassetto e corsivo_** nelle altre colonne sono le impostazioni che hanno prodotto quei valori risultanti per ogni riga.

| Prodotto rilasciato: Fornitore | Impostazioni ordine predefinite: Lead time | Copertura articolo: Sostituisci fornitore | Copertura articolo: Sostituisci lead time | Accordo commerciale: Fornitore | Accordo commerciale: Lead time | Accordo commerciale: Ignora lead time | Fornitore risultante | Lead time risultante |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001** _ | _*_1_*_ | No | No | US003 | 3 | No | _ *US001** | **1** |
| US001 | 1 | ***Sì: US002** _ | _*_Sì: 2_*_ | US003 | 3 | No | _ *US002** | **2** |
| *(Vuoto)* | 1 | No | No | ***US003** _ | _*_3_*_ | No | _ *US003** | **3** |
| *(Vuoto)* | ***1** _ | No | No | _*_US003_*_ | 3 | Sì | _ *US003** | **1** |
| *(Vuoto)* | ***1** _ | _*_Sì: US002_*_ | No | US003 | 3 | No | _ *US002** | **1** |
| *(Vuoto)* | ***1** _ | _*_Sì: US002_*_ | No | US003 | 3 | No | _ *US002** | **1** |
| *(Vuoto)* | 1 | No | Sì: 2 | ***US003** _ | _*_3_*_ | No | _ *US003** | **3** |
| *(Vuoto)* | 1 | No | ***Sì: 2** _ | _*_US003_*_ | 3 | Sì | _ *US003** | **2** |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Contratti di acquisto](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
