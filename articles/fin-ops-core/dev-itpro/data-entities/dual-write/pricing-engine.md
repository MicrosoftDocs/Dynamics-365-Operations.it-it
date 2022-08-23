---
title: Sincronizzare su richiesta con il motore di determinazione del prezzo di Supply Chain Management
description: Questo articolo descrive come utilizzare il motore di determinazione del prezzo in Dynamics 365 Supply Chain Management da Microsoft Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 727e60ceee3f5c8c33d2da93128eedc1dc7bcb9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288958"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Sincronizzare su richiesta con il motore di determinazione del prezzo di Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management include un motore di determinazione del prezzo che gestisce accordi commerciali, listini prezzi, programmi di fidelizzazione dei clienti, promozioni e sconti. Il motore di determinazione del prezzo utilizza regole complesse per determinare il prezzo migliore per un determinato preventivo od ordine. Quando si utilizza la doppia scrittura, si usa il prezzo statico o il motore di determinazione dei prezzi da Supply Chain Management nelle pagine **Offerta** e **Ordine** in Microsoft Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Utilizzare il motore di determinazione dei prezzi da Supply Chain Management in Sales

1. In Sales, andare a **Vendite \> Ordini**.
1. Selezionare **Nuovo** per creare un nuovo ordine o selezionare un ordine esistente nell'elenco **Ordini personali**.
1. Aggiungere una nuova riga ordine.
1. Se stai creando un nuovo ordine, selezionare **Prezzo ordine** nel riquadro Azione. Se stai aggiornando un ordine esistente, selezionare **Ricalcola** nel riquadro Azione.
1. Le colonne riportate di seguito vengono automaticamente popolate:

    - Dettagli importo
    - % sconto
    - Sconto
    - Importo pre-trasporto
    - Importo trasporto
    - Totale imposta
    - Importo totale

> [!NOTE]
> Un processo simile si applica quando si creano quotazioni.

## <a name="how-it-works"></a>Funzionamento

Quando si crea un ordine in Sales, l'ordine viene immediatamente sincronizzato con Supply Chain Management utilizzando i valori immessi in Sales. Quando selezioni **Prezzo ordine** o **Prezzo offerta** in Sales, Supply Chain Management calcola il prezzo per ciascuna riga di ordine e l'ordine totale, in base alle regole di un accordo commerciale definite in Supply Chain Management. I nuovi valori calcolati vengono quindi sincronizzati in Sales.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Impostare le opzioni di valutazione dell'accordo commerciale in Supply Chain Management

Puoi configurare Supply Chain Management affinché rispetti o ignori gli accordi commerciali quando calcola il prezzo di un ordine creato in Sales. Per impostare questa opzione, esegui la procedura seguente.

1. Accedi all'ambiente Supply Chain Management.
1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
1. Nella scheda **Prezzi**, nella Scheda dettaglio **Valutazione accordo commerciale** aggiungi o rimuovi la riga per i criteri **Inserimento manuale** come necessario. La presenza o l'assenza di questi comandi dei criteri se il motore dei prezzi di Supply Chain Management prevarranno automaticamente il prezzo di vendita immesso in Sales.

    - Se i criteri **Inserimento manuale** *non sono* presenti nella configurazione **Valutazione accordo commerciale**, Supply Chain Management è il master dei prezzi. Quando un utente seleziona **Prezzo ordine** o **Prezzo offerta** nel riquadro Azioni in Sales, il motore dei prezzi di Supply Chain Management viene chiamato e il prezzo delle vendite immesso in Sales viene sovrascritto, a meno che non sia uguale al prezzo di vendita calcolato in Supply Chain Management.
    - Se i criteri **Inserimento manuale** *non sono* presenti nella configurazione **Valutazione accordo commerciale**, Sales è il master dei prezzi. Il prezzo delle vendite immesso in Sales non possono essere automaticamente sovrascritti quando un utente seleziona **Prezzo ordine** o **Prezzo offerta** nel riquadro Azioni in Sales.
    - Le righe di ordine e di offerta che hanno un valore **Prezzo unitario** e/o **Sconto** di *0* (zero) in Sales vengono trattati come caso speciale. Se è disponibile il prezzo del relativo accordo commerciale, Supply Chain Management lo applicherà *sempre* a questi campi, indipendentemente dalla configurazione **Valutazione accordo commerciale**.

    Per un esempio di ciascuno di questi casi consultare lo scenario seguente.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>Esempio scenario 1: valutazione dell'accordo commerciale senza l'opzione Immissione manuale

In questo scenario, se la configurazione **Valutazione accordo commerciale** in Supply Chain Management *non* include i criteri **Immissione manuale**. Un utente Sales immette una riga di ordine che ha prezzo di vendita diverso da zero in Sales e nessun prezzo di vendita è definito per l'articolo in Supply Chain Management.

1. In Sales, un utente crea una riga di ordine con valore **Prezzo unitario** di 1 USD.
1. La riga di ordine è sincronizzata in Supply Chain Management con un prezzo di vendita di 1 USD.
1. In Sales, l'utente seleziona **Prezzo ordine** nel riquadro Azioni.
1. Supply Chain Management cerca i prezzi e gli sconti rilevanti e quindi calcola i totali. Poiché l'articolo non ha prezzo di vendita in Supply Chain Management, il calcolo aggiorna la riga in modo che abbia un prezzo di vendita di 0 USD.
1. Il nuovo prezzo di vendita di una riga è sincronizzato in Sales.
1. Il risultato è una riga di ordine in Sales con un prezzo di vendita di 0 USD.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>Esempio scenario 2: valutazione dell'accordo commerciale con l'opzione Immissione manuale

In questo scenario, se la configurazione **Valutazione accordo commerciale** in Supply Chain Management *include* i criteri **Immissione manuale**. Un utente di Sales immette una riga di ordine con prezzo di vendita diverso da zero in Sales. Supply Chain Management include un accordo commerciale che imposta un prezzo di vendita di 2 USD per l'articolo ordinato.

1. In Sales, un utente crea una riga di ordine per un articolo con valore **Prezzo unitario** di 1 USD.
1. La riga di ordine è sincronizzata in Supply Chain Management con un prezzo di vendita di 1 USD.
1. In Sales, l'utente seleziona **Prezzo ordine** nel riquadro Azioni.
1. Poiché la configurazione **Valutazione accordo commerciale** in Supply Chain Management include i criteri **Immissione manuale**, il prezzo di vendita non viene modificato anche se l'accordo commerciale applicabile specifica altri prezzi di vendita.
1. Il prezzo di vendita rimane invariato in Sales e in Supply Chain Management.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>Scenario di esempio 3: valutazione accordo commerciale per un articolo che ha prezzo di vendita di zero in Sales

In questo scenario, se la configurazione **Valutazione accordo commerciale** in Supply Chain Management *include* i criteri **Immissione manuale**. L'utente di Sales immette una riga di ordine con prezzo di vendita di 0 (zero) in Sales. Supply Chain Management include un accordo commerciale che imposta un prezzo di vendita di 2 USD per un articolo ordinato.

1. In Sales, un utente crea una riga di ordine con valore **Prezzo unitario** di 0 USD e un valore **Sconto riga** di 0 USD.
1. La riga di ordine è sincronizzata in Supply Chain Management con un prezzo di vendita di 0 USD.
1. Poiché riceve una riga di ordine che ha un prezzo di vendita di 0 (zero), Supply Chain Management chiama il relativo motore dei prezzi, anche se l'opzione **Immissione manuale** è abilitata. Il motore dei prezzi restituisce il prezzo di vendita di 2 USD che è stato stabilito dall'accordo commerciale e aggiorna la riga dell'ordine in Supply Chain Management.
1. Il prezzo di vendita aggiornato non è ancora sincronizzato con la riga dell'ordine in Sales.
1. In Sales, l'utente seleziona **Prezzo ordine** nel riquadro Azioni.
1. La riga di ordine in Supply Chain Management mantiene il relativo prezzo di vendita di 2 USD, ora sincronizzato nuovamente in Sales. Pertanto, il valore di **Prezzo unitario** della riga di ordine in Sales viene aggiornato da 0 USD a 2 USD.
1. In Sales, l'utente immette un nuovo valore **Sconto riga** di 0,50 USD. Sales ora calcola che il valore **Importo totale** per la linea è 1,50 USD.
1. La riga di ordine è sincronizzata in Supply Chain Management con un valore **Sconto riga** di 0,50 USD.
1. In Sales, l'utente seleziona **Prezzo ordine** nel riquadro Azioni.
1. Nessuna modifica ai prezzi o agli sconti per la riga di ordine in Sales.

## <a name="limitations"></a>Limiti

Quando le colonne in Sales sono compilate, si applicano le seguenti limitazioni:

- L'impostazione degli addebiti e delle allocazioni degli addebiti in Supply Chain Management non viene replicata in Sales.
- Il prezzo non considera i prezzi al dettaglio speciali specificati nella colonna **Canale al dettaglio** della pagina della riga ordine cliente in Supply Chain Management.
- Gli sconti definiti nella sezione **Gestione indennità commerciali** di Supply Chain Management non sono considerati.
- Il prezzo non tiene conto dei contratti di vendita.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
