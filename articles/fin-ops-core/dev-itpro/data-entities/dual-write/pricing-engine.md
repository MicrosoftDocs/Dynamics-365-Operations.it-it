---
title: Sincronizzare su richiesta con il motore di determinazione del prezzo di Supply Chain Management
description: Questo argomento descrive come utilizzare il motore di determinazione del prezzo in Microsoft Dynamics 365 Supply Chain Management da Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: bf4154816f01040a236dde77b92ee69396158614
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750766"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Sincronizzare su richiesta con il motore di determinazione del prezzo di Supply Chain Management

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Supply Chain Management include un motore di determinazione del prezzo che gestisce accordi commerciali, listini prezzi, programmi di fidelizzazione dei clienti, promozioni e sconti. Il motore di determinazione del prezzo utilizza regole complesse per determinare il prezzo migliore per un determinato preventivo od ordine. Quando si utilizza la doppia scrittura, si usa il prezzo statico o il motore di determinazione dei prezzi da Dynamics 365 Supply Chain Management nelle pagine Offerta e Ordine in Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Utilizzare il motore di determinazione dei prezzi da Supply Chain Management in Sales

1. In Sales, andare a **Vendite \> Ordini**.
2. Selezionare **Nuovo** per creare un nuovo ordine o selezionare un ordine esistente nell'elenco **Ordini personali**.
3. Aggiungere una nuova riga ordine.
4. Se stai creando un nuovo ordine, selezionare **Prezzo ordine** nel riquadro Azione. Se stai aggiornando un ordine esistente, selezionare **Ricalcola** nel riquadro Azione.

    Le colonne riportate di seguito vengono automaticamente popolate:

    + Dettagli importo
    + % sconto
    + Sconto
    + Importo pre-trasporto
    + Importo trasporto
    + Totale imposta
    + Importo totale
    
5. Per assicurarsi che il sistema consideri gli accordi per i contratti di vendita per calcolare il prezzo:
    1. Accedere all'ambiente Supply Chain Management.
    2. Spostarsi su **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
    3. Selezionare la scheda **Prezzi** nella barra di spostamento laterale.
    4. Sotto la scheda dettaglio **Valutazione dell'accordo commerciale**, deselezionare l'opzione **Immissione manuale**.

## <a name="how-it-works"></a>Funzionamento

Quando si seleziona **Prezzo ordine** in Sales, la funzione **Totali** nella scheda **Ordine di vendita \> Visualizza** in Supply Chain Management viene chiamata per l'ordine di vendita associato. I valori nel totale dell'ordine in Sales vengono utilizzati per compilare le colonne corrispondenti in Supply Chain Management.

Quando il totale dell'ordine cliente viene calcolato in Supply Chain Management, il calcolo valuta gli accordi commerciali e gli accordi di vendita esistenti per il cliente e i prodotti elencati nell'ordine di vendita. Questa informazione viene utilizzata per calcolare i totali. Quando **Prezzo ordine** è selezionato, Sales riflette automaticamente tutte le impostazioni applicate in Supply Chain Management.

## <a name="limitations"></a>Limiti

Quando le colonne in Sales sono compilate, si applicano le seguenti limitazioni:

+ L'impostazione degli addebiti e delle allocazioni degli addebiti in Supply Chain Management non viene replicata in Sales.
+ Il prezzo non considera i prezzi al dettaglio speciali specificati nella colonna **Canale al dettaglio** della pagina della riga ordine cliente in Supply Chain Management.
+ Gli sconti definiti nella sezione **Gestione indennità commerciali** di Supply Chain Management non sono considerati.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]