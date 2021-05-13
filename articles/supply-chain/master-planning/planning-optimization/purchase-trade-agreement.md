---
title: Pianificazione generale con accordi commerciali di acquisto
description: Questo argomento descrive come utilizzare l'ttimizzazione della pianificazione per trovare il fornitore e/o il lead time per un ordine pianificato, in base al prezzo o al lead time migliore presente negli accordi commerciali di acquisto.
author: ChristianRytt
ms.date: 06/29/2020
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
ms.author: crytt
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 4f50dfa5c2914ce2131cdc44582588be69b35335
ms.sourcegitcommit: 2eb7a9ae544f504155657c5c584cbac66c21dba4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "5961707"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Pianificazione generale con accordi commerciali di acquisto

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come utilizzare l'ottimizzazione della pianificazione per trovare il fornitore e/o il lead time per un ordine pianificato, in base al prezzo o lead time migliore presente negli accordi commerciali di acquisto specificati per un determinato prodotto.

## <a name="turn-on-the-purchase-trade-agreements-for-planning-optimization-feature"></a>Attivare la funzionalità Accordi commerciali di acquisto per ottimizzazione pianificazione

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Pianificazione generale*
- **Nome funzionalità:** *Accordi commerciali di acquisto per ottimizzazione pianificazione*

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Preparare il sistema per valutare gli accordi commerciali di acquisto durante la pianificazione generale

Attenersi alla seguente procedura per configurare il sistema e applicare l'ottimizzazione della pianificazione che valuta gli accordi commerciali di acquisto.

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

    - Nella scheda **Generale**, è possibile impostare le sostituzioni fornitore. Se l'ottimizzazione della pianificazione deve utilizzare accordi commerciali di acquisto per selezionare un fornitore, è necessario impedire le sostituzioni fornitore deselezionando la casella di controllo **Usa impostazioni specifiche**.
    - Nella scheda **Lead time**, è possibile impostare le sostituzioni lead time. Se l'ottimizzazione della pianificazione deve utilizzare accordi commerciali di acquisto per selezionare i lead time, è necessario impedire le sostituzioni lead time. Deselezionare la casella di controllo per ogni tipo di lead time che si desidera selezionare utilizzando accordi commerciali di acquisto ( **Acquisto**, **Produzione** e/o **Trasferimento**).

1. Chiudere la pagina **Copertura articolo** per tornare alla pagina dettagli del prodotto selezionato.
1. Nel riquadro azioni, nel gruppo **Previsione** della scheda **Piano**, selezionare **Previsione dell'offerta** per aprire la pagina **Previsione dell'offerta**. Assicurarsi che nessuna riga visualizzata qui abbia un valore nella colonna **Conto fornitore**.
1. Chiudere la pagina **Previsione dell'offerta** per tornare alla pagina dettagli del prodotto selezionato.
1. Nel riquadro azioni, nel gruppo **Accordi commerciali** della scheda **Acquisto**, selezionare **Visualizza accordi commerciali**. Assicurarsi che siano elencati tutti gli accordi commerciali di acquisto pertinenti. Assicurarsi anche che l'opzione **Ignora lead time** sia impostata su **No** per ogni accordo in cui l'ottimizzazione della pianificazione deve utilizzare il lead time specificato per tale accordo.
1. Nel riquadro azioni, nel gruppo **Impostazioni ordine** della scheda **Piano** , selezionare **Impostazioni ordine predefinite** per aprire la pagina **Impostazioni ordine predefinite** per il prodotto selezionato. Nella Scheda dettaglio **Ordine fornitore**, visualizzare il valore del campo **Lead time acquisto**. Se non viene definita alcuna sostituzione lead time per la copertura dell'articolo, l'ottimizzazione della pianificazione utilizzerà questo valore quando seleziona gli accordi commerciali in cui l'opzione **Ignora lead time** è impostata su **Sì**. Pertanto, è necessario rettificare questo valore come necessario.
1. Ripetere questa procedura per ogni prodotto pertinente.

> [!NOTE]
> Ottimizzazione pianificazione supporta gli accordi commerciali di acquisto commerciali con più valute. Quando si cerca un accordo commerciale utilizzando l'opzione **Prezzo unitario più basso**, il sistema prenderà in considerazione le righe degli accordi commerciali di acquisto con valute diverse a condizione che sia stato definito un tasso di cambio tra la valuta della riga dell'accordo commerciale e la valuta contabile della persona giuridica. In caso contrario, la riga dell'accordo commerciale verrà ignorata e verrà visualizzato un errore durante la pianificazione generale. Pertanto, la pianificazione generale includerà le informazioni da tutte le righe degli accordi commerciali di acquisto pertinenti in cui i prezzi possono essere convertiti nella valuta contabile.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>Esempi di come l'ottimizzazione della pianificazione trova il fornitore e i lead time

La tabella seguente fornisce esempi che mostrano in che modo le varie impostazioni per un prodotto rilasciato e i relativi accordi commerciali di acquisto influenzano i valori rilevati per l'ordine fornitore pianificato risultante. I valori in **grassetto** nelle due colonne più a destra sono i valori selezionati dall'ottimizzazione della pianificazione. I valori in **_grassetto e corsivo_** nelle altre colonne sono le impostazioni che hanno prodotto quei valori risultanti per ogni riga.

| Prodotto rilasciato: Fornitore | Impostazioni ordine predefinite: Lead time | Copertura articolo: Sostituisci fornitore | Copertura articolo: Sostituisci lead time | Accordo commerciale: Fornitore | Accordo commerciale: Lead time | Accordo commerciale: Ignora lead time | Fornitore risultante | Lead time risultante |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001** _ | _*_1_*_ | Nessuno | Nessuno | US003 | 3 | Nessuno | _ *US001** | **1** |
| US001 | 1 | ***Sì: US002** _ | _*_Sì: 2_*_ | US003 | 3 | Nessuno | _ *US002** | **2** |
| *(Vuoto)* | 1 | Nessuno | Nessuno | ***US003** _ | _*_3_*_ | Nessuno | _ *US003** | **3** |
| *(Vuoto)* | ***1** _ | Nessuno | Nessuno | _*_US003_*_ | 3 | Sì | _ *US003** | **1** |
| *(Vuoto)* | ***1** _ | _*_Sì: US002_*_ | Nessuno | US003 | 3 | Nessuno | _ *US002** | **1** |
| *(Vuoto)* | ***1** _ | _*_Sì: US002_*_ | Nessuno | US003 | 3 | Nessuno | _ *US002** | **1** |
| *(Vuoto)* | 1 | Nessuno | Sì: 2 | ***US003** _ | _*_3_*_ | Nessuno | _ *US003** | **3** |
| *(Vuoto)* | 1 | Nessuno | ***Sì: 2** _ | _*_US003_*_ | 3 | Sì | _ *US003** | **2** |

## <a name="additional-resources"></a>Risorse aggiuntive

[Contratti di acquisto](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
