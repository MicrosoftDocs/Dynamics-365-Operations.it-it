---
title: Verifica discrepanze tra prezzi ordini interaziendali
description: Questo argomento spiega come controllare le discrepanze tra i prezzi degli ordini interaziendali
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f9a0ba4980f8acf56d84dc865094b405b7402ad5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548346"
---
# <a name="check-intercompany-order-price-discrepancies"></a>Verifica discrepanze tra prezzi ordini interaziendali

[!include [banner](../../includes/banner.md)]

È possibile utilizzare questa procedura per verificare le discrepanze tra prezzi di ordini interaziendali.

1. Andare ad **Approvvigionamento \> Periodico \> Pulizia \> Verifica discrepanze tra prezzi di ordini interaziendali**.
1. Se necessario, impostare un processo batch, quindi selezionare **OK** per verificare i prezzi e gli sconti per gli ordini cliente e gli ordini fornitore interaziendali. In alternativa, selezionare **Annulla** per chiudere la pagina senza eseguire la verifica.

    > [!TIP]
    > Gli eventuali problemi relativi alla sincronizzazione o ai prezzi verranno visualizzati in un messaggio informativo. È possibile stampare il messaggio informativo come riferimento.

1. Nel messaggio informativo, selezionare la riga pertinente per aprire l'ordine nella persona giuridica corrente. Aprire l'ordine nella relativa persona giuridica selezionando **Interaziendale**, quindi **Ordine fornitore interaziendale** o **Ordine cliente interaziendale**.

    > [!NOTE]
    > Per consentire l'aggiornamento dell'ordine interaziendale:
    >
    > 1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
    > 1. Nel riquadro Azioni, selezionare la scheda **Generale**, quindi selezionare **Interaziendale**.
    > 1. Nella pagina **Interaziendale**, selezionare **Criteri ordine fornitore** o **Criteri ordine cliente**.
    > 1. Selezionare **Consenti modifica prezzi** e **Consenti modifica sconto** in entrambe le aree.

1. Aprire l'ordine interaziendale rilevante per il quale si desidera mantenere il prezzo.
1. Per ciascuna riga dell'ordine modificare il campo **Prezzo unitario** della riga, quindi ripristinare il valore originario. Ripetere la stessa operazione per il campo **Sconto** della riga e per i campi **Spese su acquisti** o **Addebiti vendite**. La modifica e il ripristino dei valori originari determinerà la sincronizzazione dei prezzi, degli sconti e degli addebiti dalla riga dell'ordine interaziendale corrente alla riga dell'ordine interaziendale di riferimento, in modo che le righe vengano allineate automaticamente.

    > [!NOTE]
    > La sincronizzazione è valida solo se l'ordine cliente interaziendale non è stato fatturato. Se la fattura dell'ordine cliente interaziendale è stata registrata ed è stato creato un giornale di registrazione fatture cliente per tale ordine, le modifiche devono essere apportate direttamente nelle righe dell'ordine fornitore interaziendale impostando i prezzi, gli sconti e gli addebiti equivalenti a quelli riportati nel giornale di registrazione fatture cliente interaziendale. In caso contrario, non sarà possibile registrare la fattura dell'ordine fornitore interaziendale poiché si verifica una mancata corrispondenza tra i totali degli ordini.

1. Ripetere la procedura finché tutti gli ordini cliente e fornitore interaziendali non saranno sincronizzati.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
