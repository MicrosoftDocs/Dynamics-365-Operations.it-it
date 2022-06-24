---
title: Metodo di allocazione costi totali
description: Questo articolo fornisce le indicazioni per l'utilizzo dell'allocazione costi totali (TCA). L'allocazione costi totali (TCA) è un metodo di calcolo del costo tra l'articolo formula principale per un ordine batch e i co-prodotti definiti per la formula.
author: JennySong-SH
ms.date: 04/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 213db8303c27934050f5b414a67f6e510486dc94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862687"
---
# <a name="total-cost-allocation-method"></a>Metodo di allocazione costi totali

[!include [banner](../includes/banner.md)]

L'allocazione costi totali (TCA) è un metodo di calcolo del costo tra l'articolo formula principale per un ordine batch e i co-prodotti definiti per la formula. Questo metodo è dinamico. Calcola il costo come media ponderata tra le quantità dichiarate finite per l'articolo formula e i co-prodotti. Quando si utilizza l'allocazione costi totale, non è necessario rivedere le allocazioni costi per ogni ordine batch. Se non si utilizza l'allocazione costi totali, il calcolo della formula utilizza la funzionalità esistente.

## <a name="using-tca-for-coproducts"></a>Utilizzo dell'allocazione costi totali per co-prodotti
Di seguito sono riportate alcune indicazioni per l'utilizzo dell'allocazione costi totali per co-prodotti:

-   Se si imposta il dispositivo di scorrimento **Allocazione costi totali** su **Sì** per una versione della formula, i co-prodotti devono avere un prezzo di costo maggiore di 0 (zero). Il valore può essere recuperato dalla versione di costo attiva per lo stesso sito o per il primo sito per una formula non specifica del sito. Questa condizione viene convalidata all'approvazione della formula.

    -   Non è necessario immettere manualmente le percentuali di allocazione costi per i co-prodotti. In alternativa, viene creata automaticamente la percentuale di allocazione costi come media dei prezzi di costo attivi di co-prodotti. 
    -   Non è necessario immettere il costo standard per voci di costo non standard che corrispondono a co-prodotti. Sono disponibili due tipi di versioni di determinazione costi nel sistema: costo standard e costo pianificato 
    -   Se un articolo non è valutato con il metodo di valutazione Costo standard, si consiglia utilizzare un prezzo di costo attivo nella versione di determinazione costi pianificati. Questo prezzo viene utilizzato per la stima dei costi, ad esempio, il calcolo DBA, la stima dei costi di produzione e il prezzo di fallback nel processo di valutazione del magazzino. 

-   Se si imposta il dispositivo di scorrimento di **Allocazione costi totali** su **Sì** per la versione della formula e le seguenti condizioni sono vere, il metodo di allocazione dei costi è **TCA** e la percentuale di allocazione dei costi è invariata:
    -   Sono stati aggiunti co-prodotti.
    -   È stato utilizzato un metodo diverso di allocazione dei costi per i co-prodotti.
-   Se si imposta il dispositivo di scorrimento di **Allocazione costi totali** su **No** per la versione della formula e le seguenti condizioni sono vere, il metodo di allocazione dei costi viene impostato su **Manuale** e la percentuale di allocazione dei costi è invariata:
    -   Sono stati aggiunti co-prodotti.
    -   La percentuale di allocazione costi è maggiore di 0 (zero).
-   Prima di poter eseguire correttamente un calcolo della formula, è necessario stimare le percentuali di allocazione dei costi. È possibile completare questo passaggio manualmente o utilizzando l'opzione **Stima costo** nella pagina **Co-prodotti**. **Nota:** l'opzione **Stima costo** è disponibile solo quando il dispositivo di scorrimento **Allocazione costi totali** è impostato su **Sì** per la versione della formula. È possibile visualizzare l'allocazione prevista se le quantità degli ordini batch dichiarate finite corrispondono alle quantità visualizzate nella formula.
-   Quando si crea un ordine batch manualmente o si stabilizza un ordine pianificato, il valore del dispositivo di scorrimento **Allocazione costi totali** per la versione della formula viene copiato nell'ordine batch. Tuttavia, è possibile modificare questa impostazione nell'ordine batch. Se il dispositivo di scorrimento di **Allocazione costi totali** è impostato su **No** per la versione della formula e viene impostato su **Sì** per l'ordine batch, il metodo di allocazione dei costi per ogni riga impostato su **Manuale** viene impostato su **TCA**. Un'allocazione dei costi pari a **Nessuno** è invariata. Se il dispositivo di scorrimento di **Allocazione costi totali** è impostato su **Sì** per la versione della formula e viene impostato su **No** per l'ordine batch, il metodo di allocazione dei costi per ogni co-prodotto di tipo **Produzione** viene impostato su **Manuale**. Qualsiasi percentuale stimata dell'allocazione dei costi è invariata.
-   La pagina **Allocazione costi co-prodotto** mostra la percentuale di allocazione dei costi calcolata. È possibile aprire questa pagina dalla pagina **Ordine batch**. Queste informazioni sono utili quando i prodotti e le quantità dichiarati sono diversi dalle quantità programmate o iniziate nell'ordine batch. Se il costo viene completato, le nuove allocazioni percentuali dall'allocazione costi totali vengono visualizzate nella pagina **Allocazione costi co-prodotti**.

## <a name="calculating-the-burden-for-byproducts"></a>Calcolo del carico per i sottoprodotti
Il campo **Allocazione costi sottoprodotti** nella pagina **Co-prodotti** è un campo di enumeratore utilizzato solo per i sottoprodotti. Per i co-prodotti, il valore di questo campo è sempre **Nessuno**. Per le righe di sottoprodotti, questo campo determina come viene aggiunto l'importo costi per la riga del sottoprodotto al costo totale della produzione. Sono disponibili le seguenti opzioni:

-   **Nessuno** ─ non viene aggiunto alcun importo al costo totale di produzione per la riga del sottoprodotto.
-   **Percentuale** ─ l'importo costi viene calcolato come percentuale del costo totale delle materie prime consumate nella produzione. La percentuale utilizzata per il calcolo viene immessa nel campo.
-   **Per serie** ─ l'importo costi viene calcolato come importo per dimensioni batch standard dell'ordine di produzione. Questo importo è indipendente dalla quantità dichiarata nella produzione. L'importo utilizzato per il calcolo viene immesso nel campo.
-   **Per quantità** ─ l'importo costi viene calcolato come importo per quantità dichiarata dell'articolo formula nella produzione. L'importo utilizzato per il calcolo viene immesso nel campo.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]