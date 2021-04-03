---
title: Blocco scorte
description: Questo articolo fornisce una panoramica del blocco scorte, che fa parte del processo di ispezione qualità in Supply Chain Management. È possibile utilizzare il blocco scorte per impedire l'elaborazione o il consumo degli articoli.
author: perlynne
manager: tfehr
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1d4b006f37904c0ae20691aaa98c75f1d5833b7
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5487899"
---
# <a name="inventory-blocking"></a>Blocco scorte

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica del blocco scorte, che fa parte del processo di ispezione qualità in Supply Chain Management. È possibile utilizzare il blocco scorte per impedire l'elaborazione o il consumo degli articoli.

È possibile bloccare gli articoli di magazzino in uno dei modi seguenti.

- Manualmente
- Creando un ordine di controllo qualità
- Utilizzando un processo che genera un ordine di controllo qualità
- Utilizzando il blocco dello stato delle scorte

## <a name="blocking-items-manually"></a>Blocco manuale degli articoli

È possibile bloccare una quantità di un articolo creando una transazione nella pagina **Blocco scorte**. È possibile bloccare manualmente solo gli articoli presenti come scorte disponibili. Per le quantità bloccate manualmente, è necessario decidere se nelle attività di pianificazione devono essere incluse le entrate previste come quantità disponibile prevista. Le entrate previste sono articoli bloccati che si prevedono come scorte disponibili al termine dell'ispezione. È possibile gestire la data prevista. Per impostazione predefinita, l'opzione **Entrate previste** è selezionata per gli articoli bloccati tramite un ordine di controllo qualità. È possibile annullare il blocco manuale di una quantità eliminando la transazione nella pagina **Blocco scorte**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Blocco degli articoli tramite un ordine di controllo qualità

È possibile specificare gli articoli che devono essere controllati tramite un ordine di controllo qualità nella pagina **Ordini di controllo qualità**. Quando si crea un ordine di controllo qualità, viene bloccata la quantità specificata per un articolo. il piano di campionamento associato all'ordine di controllo qualità controlla solo la quantità di articoli che devono essere sottoposti a ispezione, non quelli bloccati. La quantità immessa nell'ordine di controllo qualità è quella bloccata, indipendentemente dalla quantità da sottoporre a ispezione in base a quanto specificato dal piano di campionamento.

> [!NOTE]
> L'uso contemporaneo delle funzionalità Data di scadenza batch e Blocco stato delle scorte non è supportato dalla pianificazione generale. Ciò potrebbe comportare una doppia esclusione delle scorte disponibili, che può verificarsi durante la pianificazione generale. Si consiglia di utilizzare codici smaltimento a batch, anziché lo stato di magazzino, per bloccare batch scaduti.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Blocco degli articoli mediante un processo che genera un ordine di controllo qualità

Se un processo di controllo qualità indica che un articolo deve essere sottoposto a ispezione, una quantità di tale articolo viene bloccata automaticamente. Pertanto, quando viene generato automaticamente un ordine di controllo qualità, il piano di campionamento articoli associato all'ordine di controllo qualità controlla sia la quantità di articoli bloccata che quella sottoposta a ispezione. Se l'opzione **Bloccaggio totale** nella pagina **Campionamento articoli** è selezionata, durante l'ispezione viene bloccata, ad esempio, l'intera quantità di una riga dell'ordine fornitore indipendentemente dalla quantità di campionamento articoli.

### <a name="example"></a>Esempio

Nell'esempio seguente viene generato un ordine di controllo qualità quando viene registrato un documento di trasporto dell'ordine fornitore. Nel modulo **Associazioni di controllo qualità** la registrazione di un documento di trasporto dell'ordine fornitore viene specificata come il processo che attiva l'ordine di controllo qualità.

|Impostazione |Azione utente |Risultato |
|----|---|---|
| Un'associazione di controllo qualità specifica che al momento della registrazione di un documento di trasporto dell'ordine fornitore deve essere generato un ordine di controllo qualità. L'impostazione del campionamento articoli dell'ordine di controllo qualità specifica che deve essere sottoposto a ispezione il 10% della quantità della riga dell'ordine fornitore. Se è selezionata la casella di controllo **Bloccaggio totale**, l'impostazione del campionamento articoli indica inoltre che durante l'ispezione deve essere bloccata l'intera quantità delle riga dell'ordine fornitore indipendentemente dalla quantità da sottoporre a ispezione. | Viene registrato il documento di trasporto. | Viene generato un ordine di controllo qualità. Viene sottoposto a ispezione il 10% della quantità nell'ordine fornitore dell'articolo. Viene bloccata l'intera quantità della riga dell'ordine fornitore. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Blocco degli articoli tramite il blocco dello stato delle scorte

È possibile specificare quali stati di magazzino sono stati di blocco tramite il parametro **Blocco scorte** nella pagina **Stati inventario**.  Non è possibile utilizzare gli stati di magazzino come stati di blocco per ordini di produzione, ordini cliente, ordini di trasferimento, transazioni in uscita o integrazioni di progetto. Per il lavoro in uscita, utilizzare articoli con uno stato di magazzino disponibile. Se si dispone di articoli con stato **Rotto** e la pianificazione generale viene eseguita su tali articoli, questi vengono considerati mancanti e l'inventario viene automaticamente rifornito.

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>Prestare attenzione quando si bloccano articoli che utilizzano il blocco dello stato delle scorte e quello dell'ordine di controllo qualità

È possibile creare un ordine di controllo qualità associato alle scorte con uno stato di magazzino il cui parametro **Blocco scorte** è abilitato. In questo caso, l'ordine di controllo qualità genererà un record di blocco scorte aggiuntivo oltre a quello creato dallo stato di inventario. Poiché il blocco delle scorte dell'ordine di controllo qualità avrà il parametro **Entrate previste** abilitato, viene generata una transazione *Scorte ordinate* anch'essa bloccata dal relativo stato di inventario. Questa combinazione può portare a difficoltà nella comprensione del significato delle transazioni di magazzino generate, poiché sembrerà che la quantità bloccata totale sia superiore alla quantità totale disponibile. Esaminiamo le transazioni in un esempio di entrata di 10 pezzi dell'articolo A0001 con un ordine di controllo qualità generato per campionare 1 pezzo. Il comportamento dipenderà anche dall'abilitazione o meno dell'opzione **Prenota articoli ordinati** nella pagina **Parametri di gestione articoli e magazzino**.

>[!NOTE]
>Se si utilizzano contemporaneamente il blocco dello stato di magazzino e gli ordini di controllo qualità, consigliamo vivamente di abilitare l'opzione **Prenota articoli ordinati**.

### <a name="example-with-reserve-ordered-items-enabled"></a>Esempio con l'opzione "Prenota articoli ordinati" abilitata

Quando l'opzione **Prenota articoli ordinati** è abilitata, tutte le transazioni di blocco del magazzino avranno lo stato *Fisico prenotato* o *Ordinato prenotato*.

| Riferimento della transazione di magazzino | Ricevimento | Uscita | Quantità | Sito | Magazzino | Stato inventario | Posizione | Targa | Commento |
|---|---|---|---|---|---|---|---|---|---|
| Ordine fornitore | Acquistato | | 10 pz | 2 | 24 | Blocco | RECV | receiptLp1 | | 
| Blocco scorte | | Fisico prenotato | -9 pz | 2 | 24 | Blocco | | | Transazione generata dal blocco dello stato di magazzino |
| Blocco scorte | | Fisico prenotato | -1 pz | 2 | 24 | Blocco | RECV | receiptLp1 | Transazione generata dal blocco del campionamento dell'ordine di controllo qualità |
| Blocco scorte | Quantità ordinata | | 1 pz | 2 | 24 | Blocco | RECV | receiptLp1 | Entrate previste dal blocco del campionamento dell'ordine di controllo qualità |
| Blocco scorte | | Ordinato prenotato | 1 pz | 2 | 24 | Blocco | | | Transazione generata dal blocco dello stato di magazzino

### <a name="example-with-reserve-ordered-items-disabled"></a>Esempio con l'opzione "Prenota articoli ordinati" disabilitata

Quando l'opzione **Prenota articoli ordinati** è disabilitata, le entrate previste non possono essere prenotate perché il relativo stato è *Ordinate*, quindi alcuni blocchi manterranno lo stato *Merci ordinate in corso di consegna*.

| Riferimento della transazione di magazzino | Ricevimento | Uscita | Quantità | Sito | Magazzino | Stato inventario | Posizione | Targa | Commento |
|---|---|---|---|---|---|---|---|---|---|
| Ordine fornitore | Acquistato | | 10 pz | 2 | 24 | Blocco | RECV | receiptLp1 | |
| Blocco scorte | | Fisico prenotato | -9 pz | 2 | 24 | Blocco | | | Transazione generata dal blocco dello stato di magazzino |
| Blocco scorte | | Fisico prenotato | -1 pz | 2 | 24 | Blocco | RECV | receiptLp1 | Transazione generata dal blocco del campionamento dell'ordine di controllo qualità |
| Blocco scorte | Quantità ordinata | | 1 pz | 2 | 24 | Blocco | RECV | receiptLp1 | Entrate previste dal blocco del campionamento dell'ordine di controllo qualità |
| Blocco scorte | | Merci ordinate in corso di consegna | 1 pz | 2 | 24 | Blocco | RECV | receiptLp1 | Transazione generata dal blocco dello stato di magazzino

Notare la differenza nello stato della transazione e nelle dimensioni tra i due casi. Per questo motivo, consigliamo di abilitare l'opzione **Prenota articoli ordinati**.

<!-- KFM: (Enable this section when the feature leaves private preview)

### Disable expected receipts from quality orders that sample blocked inventory feature

To simplify the inventory transactions in the case of quality orders that sample inventory blocked as a consequence of inventory status, the system provides a feature that disables expected receipts from such quality orders. As the expected receipt is in any case immediately blocked by inventory status blocking, there is no reduction of on-hand inventory because of this change.

-->

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare e gestire un blocco scorte](tasks/create-maintain-inventory-blocking.md)

[Processi di gestione qualità](quality-management-processes.md)

[Verificare la qualità delle merci](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]