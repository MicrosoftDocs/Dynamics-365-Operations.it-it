---
title: Rendiconti di vendita al dettaglio
description: Questo argomento descrive la creazione e la registrazione dei rendiconti.
author: ashishmsft
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 8d6687ddaae28ebf278aca6a78ba798e2e79edd8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791923"
---
# <a name="retail-statements"></a>Rendiconti di vendita al dettaglio

[!include [banner](includes/banner.md)]

In Dynamics 365 Commerce il processo di registrazione dei rendiconti viene utilizzato per gestire le transazioni che si verificano nei punti vendita nel cloud (POS) o nei Modern POS (MPOS). Il processo di registrazione dei rendiconti utilizza la programmazione di distribuzione per recuperare un set di transazioni POS nel client della sede centrale (HQ). I parametri che vengono definiti nelle pagine **Parametri di commercio** e **Punti vendita** vengono utilizzati per selezionare le transazioni che vengono inserite nei singoli rendiconti.

L'illustrazione seguente mostra il processo di registrazione dei rendiconti. In questo processo le transazioni registrate nel POS vengono trasmesse al client utilizzando l'utilità di pianificazione di commercio. Dopo che il client riceve le transazioni, è possibile creare, calcolare e registrare il rendiconto delle transazioni per il punto vendita.

[![Processo di registrazione dei rendiconti](./media/retail-statements.png)](./media/retail-statements.png)

## <a name="creating-and-posting-statements"></a>Creazione e registrazione dei rendiconti

È possibile creare un rendiconto manualmente o utilizzando i processi batch impostati per essere eseguiti periodicamente durante il giorno. In entrambi i casi, per creare e registrare i rendiconti vengono utilizzati i passaggi riportati di seguito.

### <a name="create-the-statement"></a>Creare il rendiconto

In questo passaggio viene identificato il punto vendita per cui il rendiconto viene creato manualmente. Se configura un processo batch, è possibile creare automaticamente i rendiconti per tutti i punti vendita, in base a una programmazione definita.

### <a name="calculate-the-statement"></a>Calcolare il rendiconto

In questo passaggio le righe di transazione vengono selezionate in base ai criteri definiti per ogni punto vendita nelle pagine **Parametri di commercio** e **Punti vendita**. In queste pagine si definiscono i criteri e si specifica il modo in cui le transazioni vengono calcolate. Per visualizzare un elenco delle transazioni incluse nel rendiconto prima di calcolare il rendiconto, utilizzare la pagina **Transazioni**.

Il calcolo del rendiconto utilizza i riepiloghi incassi dei registratori di cassa come importo conteggiato. In alternativa, è possibile immettere l'importo conteggiato manualmente. Il rendiconto mostra la differenza tra l'importo delle vendite relativo alle transazioni e l'importo conteggiato effettivo in tutti i metodi di pagamento. Il rendiconto viene registrato solo se questa differenza è inferiore alla differenza massima di registrazione definita per il punto vendita.

> [!NOTE]
> Il processo di calcolo del rendiconto utilizza la sequenza numerica globale.

Quando viene calcolato un rendiconto, il calcolo include le attività seguenti:

- Per l'intervallo di date selezionato, contrassegnare le transazioni che non sono state incluse in un calcolo di rendiconti precedente.
- Calcolare gli importi totali pagati nelle transazioni selezionate. I risultati vengono mostrati nelle righe del rendiconto in base al metodo di rendiconto:

    - Se il metodo di rendiconto è **Totale**, viene creata una riga per ogni tipo di metodo di pagamento nelle transazioni selezionate.
    - Se il metodo di rendiconto è **Personale**, viene creata una riga per ogni metodo di pagamento nelle transazioni eseguite dal membro del personale selezionato.
    - Se il metodo di rendiconto è **Terminale POS**, viene creata una riga per ogni metodo di pagamento nelle transazioni eseguite dal registratore di cassa selezionato.
    - Se il metodo di rendiconto è **Turno**, viene creata una riga per ogni metodo di pagamento nelle transazioni eseguite durante un turno.

Se la casella di controllo **Dividi per metodo rendiconto** è selezionata nella pagina **Punti vendita**, viene creato un rendiconto separato in base al valore selezionato nel campo **Metodo rendiconto**.

Se le ore operative del punto vendita si estendono oltre la mezzanotte, è possibile configurare la registrazione dei rendiconti in base alla fine del giorno lavorativo anziché alla fine del giorno di calendario.

Nella pagina **Punti vendita**, nella Scheda dettagli **Rendiconto/Chiusura**, nel campo **Fine giorno lavorativo** immettere l'ora in cui deve essere registrata l'ultima transazione perché sia inclusa nel rendiconto del giorno lavorativo. Selezionare la casella di controllo **Registra come giorno lavorativo** per registrare le transazioni nello stesso giorno lavorativo. Quando il rendiconto viene registrato, le transazioni registrate nello stesso giorno lavorativo possono essere incluse nello stesso ordine cliente, anche se alcune transazioni si verificano prima di mezzanotte e altre dopo mezzanotte.

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a>Esempio: registrare un rendiconto per un giorno lavorativo che estende per due giorni di calendario

Un punto vendita è aperto tra le 8.00 e le 3.00 del mattino e la casella di controllo **Registra come giorno lavorativo** è selezionata nella configurazione del punto vendita. Il 31 maggio il punto vendita registra transazioni tra le 8.00 e mezzanotte. Il 1° giugno il punto vendita registra transazioni anche tra le 12.01 e le 3:00 del mattino.

Quando nel punto vendita viene registrato il rendiconto per la chiusura del giorno lavorativo, viene generato un ordine cliente che include tutte le transazioni registrate nell'orario di lavoro compreso tra le 8.00 e le 3.00, anche se le transazioni si sono verificate in due giorni, il 31 maggio e il 1° giugno.

Se la casella di controllo **Registra come giorno lavorativo** è deselezionata per lo stesso punto vendita, quando nel punto vendita viene registrato il rendiconto per la chiusura del giorno lavorativo, vengono generati ordini cliente separati. Un ordine cliente include le transazioni registrate nell'orario di lavoro compreso tra le 8.00 e la mezzanotte del 31 maggio e il secondo ordine cliente include le transazioni registrate tra le 12.01 e le 3.00 del 1° giugno.

> [!NOTE]
> Prima di creare rendiconti, è necessario chiudere i turni nel periodo di rendiconto.

### <a name="post-the-statement"></a>Registrare il rendiconto

Quando si registra un rendiconto, gli ordini cliente e le fatture vengono creati per le vendite nel rendiconto.

- Le vendite cash and carry vengono aggregate in un ordine cliente e fatturate per il cliente predefinito assegnato al punto vendita.
- Le vendite per cui un cliente è stato aggiunto alla transazione in  POS generano ordini cliente e fatture separati, uno per ciascun cliente univoco.

I giornali di registrazione pagamenti vengono creati automaticamente per i pagamenti nel rendiconto e il magazzino viene aggiornato per il punto vendita relativo al POS.


[!INCLUDE[footer-include](../includes/footer-banner.md)]