---
title: Richiesta compensazione dei saldi contabili
description: Questo articolo descrive la finestra di richiesta di liquidazione contabile
author: kweekley
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ae49d9503c0a83bda7e0093ab6ef69fb4aef0a
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853128"
---
# <a name="ledger-settlement-inquiry"></a>Richiesta compensazione dei saldi contabili

[!include [banner](../includes/banner.md)]

Questo articolo descrive la **richiesta di liquidazione contabile** che può essere utilizzata per visualizzare le transazioni contabili liquidate, non liquidate o entrambe liquidate e non liquidate per un periodo fiscale.

## <a name="view-ledger-settlement-transactions"></a>Visualizzare le transazioni di liquidazione contabile
1.  Vai a **Contabilità generale > Richieste di informazioni e report > Richiesta compensazione dei saldi contabili**.
2.  Utilizza i campi **Data iniziale** e **Data finale** o il campo **Intervallo di date** per specificare un intervallo di date. Per quanto riguarda il bilancio di verifica, l'intervallo di date deve rientrare in un unico anno fiscale.
3.  Nel campo **Conti principali** seleziona uno o più conti principali di cui visualizzare i movimenti contabili. L'elenco a discesa mostra solo i conti principali impostati per la liquidazione contabile nella pagina **Parametri contabilità generale**.
4.  Utilizza il campo **Set di dimensioni finanziarie** per visualizzare le dimensioni finanziarie nella griglia. Poiché il conto principale è obbligatorio, il valore del campo **Conto principale** verrà sempre visualizzato come prima colonna, anche se selezioni un set di dimensioni finanziarie che non include il conto principale.
5.  Nel campo **Stato** seleziona:
-   **Tutto** per visualizzare sia le transazioni liquidate che quelle non liquidate
-   **Non liquidate** per visualizzare solo le transazioni non liquidate 
-   **Liquidate** per visualizzare solo le transazioni liquidate
6.  Seleziona **Mostra transazioni**. Le transazioni contabili vengono visualizzate nella griglia, in base ai criteri immessi. È inoltre possibile esportare i risultati della richiesta in Microsoft Excel per ulteriori analisi. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella griglia.

### <a name="column-details"></a>Dettagli colonna
La griglia nella pagina **Richiesta compensazione dei saldi contabili** include le seguenti colonne:
-   **Conto principale**: questo campo è obbligatorio ed è sempre visualizzato.
-   **Dimensioni finanziarie**: le dimensioni finanziarie vengono visualizzate in base al set di dimensioni finanziarie selezionato.
-   **Data della transazione**: la data di registrazione della transazione contabile.
-   **Data della transazione originale**: se è stata eseguita la chiusura di fine anno e la liquidazione contabile è impostata in modo da mantenere i dettagli del conto principale, le transazioni non liquidate vengono riportate in dettaglio come saldo iniziale. La data di registrazione originale della transazione contabile viene mantenuta nel campo **Data transazione originale**.
-   **Validità transazione**: il valore è 0 (zero) per tutte le transazioni liquidate. Per le transazioni non liquidate, il valore viene calcolato come il numero di giorni dalla data della transazione originale o dalla data della transazione alla data in cui viene eseguita la richiesta.
Ad esempio, una transazione contabile ha una data transazione del 1 gennaio 2022 (1/1/2022) e una data transazione originale del 30 dicembre 2021 (30/12/2021). Se la richiesta viene eseguita il 2 gennaio 2022 (1/2/2022) per l'anno fiscale 2022, il **Valore validità transazione** sarà 4. Questo valore viene calcolato come numero di giorni tra la data della transazione originale (30/12/2021) e il 2/1/2022.

Se non esiste una data della transazione originale, viene utilizzata la data della transazione.
-   **(Altre informazioni sulle transazioni)**: le colonne aggiuntive mostrano informazioni come il numero del giustificativo, la descrizione e gli importi in dare e avere in tutte e tre le valute (transazione, contabilità e dichiarazione).
-   **Stato**: Questo valore è **Liquidato** o **Non liquidato**.
-   **ID liquidazione**: l'ID assegnato alle transazioni liquidate.

[![Pagina Richiesta compensazione dei saldi contabili](./media/Inquiry1.png)](./media/Inquiry1.png)

 
I totali possono essere visualizzati sotto la griglia.
1.  Seleziona i puntini di sospensione (...) a destra della griglia, quindi seleziona **Mostra piè di pagina**.
2.  Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) in ogni colonna di importo e seleziona **Raggruppa per questa colonna** per visualizzare i totali. I totali sono visualizzati nel piè di pagina. Se la richiesta è filtrata in modo da mostrare solo le transazioni non liquidate, è possibile utilizzare i totali per riconciliare gli importi con il saldo di verifica.







