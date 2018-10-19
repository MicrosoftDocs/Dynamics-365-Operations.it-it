---
title: Pagina elenco di transazioni fornitore
description: Questo argomento fornisce informazioni sulla pagina elenco Transazioni fornitore per Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: 53740f6ed0d463de5ba962f1ba15b208634a0739
ms.contentlocale: it-it
ms.lasthandoff: 10/01/2018

---

# <a name="vendor-transactions-list-page"></a>Pagina elenco di transazioni fornitore

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Visualizza liquidazioni

Il pulsante **Visualizza liquidazioni** del riquadro azioni offre un accesso rapido allo storico delle liquidazioni e altre informazioni sull'intera transazione delle liquidazioni. È inoltre possibile mostrare altre transazioni che sono correlate alla transazione selezionata, perché fanno parte della stessa liquidazione o perché sono pagamenti creati nello stesso giornale di registrazione pagamenti.

1. Selezionare **Contabilità fornitori \> Tutti i fornitori**.
2. Selezionare un fornitore con transazioni e quindi nel riquadro azioni, nella scheda **Fornitore**, selezionare **Transazioni**.
3. Selezionare una transazione da cercare, quindi nel riquadro azioni selezionare **Visualizza liquidazioni**.

    Verrà visualizzata la finestra di dialogo **Visualizza liquidazioni** che mostra la transazione selezionata e tutti i documenti che sono stati liquidati ad essa collegati. Questa finestra di dialogo assomiglia alla visualizzazione dello storico delle liquidazioni, ma include tutti i documenti correlati.

4. Nella finestra di dialogo è possibile eseguire varie attività. Selezionare uno o più giustificativi e quindi selezionare uno dei pulsanti seguenti:

    - **Visualizza correlato** - Mostra tutte le transazioni del giornale di registrazione pagamenti che sono state create nel giornale di registrazione pagamenti che è correlato al documento selezionato. Vengono inoltre visualizzate tutte le liquidazioni correlate a tali pagamenti. Durante la visualizzazione dei pagamenti correlati, l'etichetta di questo pulsante cambia in **Visualizza liquidazioni**. Selezionare **Visualizza liquidazioni** per mostrare solo le transazioni che erano visualizzate la prima volta che è stata aperta la finestra di dialogo **Visualizza liquidazioni**.
    - **Visualizza storico** - Mostra la cronologia delle liquidazioni per i giustificativi. Selezionare **Chiudi** per chiudere la finestra di dialogo.
    - **Visualizza contabilità** - Mostra tutti i giustificativi che sono correlati ai documenti selezionati. Selezionare **Chiudi** per chiudere la finestra di dialogo.
    - **Esporta** - Esportare i giustificativi selezionati in Microsoft Excel.
    - **Liquida transazioni** - Questo pulsante viene visualizzato solo se il documento originale che era selezionato non è stato completamente liquidato. Quando si seleziona questo pulsante, viene visualizzata la finestra di dialogo **Liquida transazioni**, nella quale è possibile selezionare le transazioni da liquidare.
    - **Annulla liquidazioni** - Questo pulsante viene visualizzato solo se il documento originale che era stato selezionato era stato completamente liquidato. Quando si seleziona questo pulsante, viene visualizzata la finestra di dialogo **Annulla liquidazioni** nella quale è possibile annullare le liquidazioni eseguite per il documento.

## <a name="global-transactions"></a>Transazioni globali

Il pulsante **Transazioni globali** è stato aggiunto alla pagina del fornitore. Il pulsante consente di visualizzare tutte le transazioni relative a un fornitore per tutte le persone giuridiche. La pagina elenco **Transazioni fornitore** mostra le transazioni solo per le persone giuridiche a cui l'utente ha accesso, in base alle relative impostazioni di sicurezza.

Nella pagina elenco vengono visualizzate tutte le transazioni per i fornitori con lo stesso ID terzi del fornitore con cui si è iniziato. Se ad esempio il fornitore US-001 in una persona giuridica ha lo stesso ID terzi del fornitore DE-001 in un'altra persona giuridica, vengono visualizzate tutte le transazioni per entrambi gli ID fornitore.

I menu nella pagina elenco **Transazioni fornitore** variano in base alla persona giuridica per la transazione. Se ad esempio una funzionalità è disponibile solo per le persone giuridiche svizzere, le opzioni di menu per tale funzionalità vengono visualizzate solo quando viene selezionata una transazione svizzera.

Per accedere alla funzionalità, seguire questi passaggi.

1. Selezionare **Contabilità fornitori** \> **Tutti i fornitori**.
2. Selezionare un fornitore e quindi, nel riquadro azioni, nella scheda **Fornitore**, nel gruppo **Transazioni** selezionare **Transazioni globali**.

## <a name="more-transaction-filters"></a>Altri filtri di transazioni

Il filtro per la visualizzazione delle transazioni aperte è stato sostituito con un nuovo filtro che consente di visualizzare più combinazioni di transazioni. Le opzioni seguenti sono disponibili nel campo **Mostra**:

- **Tutte** - Mostra tutte le transazioni per i fornitori selezionati (aperte e chiuse).
- **Chiuse** - Mostra solo le transazioni che sono state completamente liquidate e chiuse.
- **Aperte** - Mostra solo le transazioni che non sono state completamente liquidate.
- **Apri a partire da data** - Mostra solo le transazioni che non sono state completamente liquidate a una data specificata. Quando si seleziona questa opzione, è possibile modificare la data che viene visualizzata accanto al filtro. Le transazioni con un valore in **Ultima data di liquidazione** posteriore alla data specificata vengono visualizzate nell'elenco, anche se queste transazioni alla data corrente sono completamente liquidate. Il saldo rappresenta tuttavia i saldi alla data corrente, non a quella selezionata.

È stato aggiunto un filtro che consente di nascondere le transazioni di conversione di valuta. Selezionare semplicemente la casella di controllo **Nascondi rivalutazioni valuta**.

## <a name="more-easily-modify-due-dates-and-discount-dates"></a>Modificare più facilmente le date di scadenza e le date di sconto

È possibile aggiornare le date di scadenza e di sconto per le transazioni cliente aperte. Nella versione 8.1 l'esperienza è stata migliorata. È ora possibile aggiungere le date di scadenza nella pagina elenco **Transazioni fornitore**. Facendo clic su nella data di scadenza nella pagina elenco **Transazioni fornitore**, è possibile modificare le date di scadenza, le date di sconto, i termini di pagamento e dello sconto di cassa nella finestra di dialogo **Aggiorna data di scadenza e date dello sconto di cassa**.

### <a name="activate-the-feature"></a>Attivare la funzionalità

Per aggiungere le date di scadenza nella pagina elenco **Transazioni fornitore** e per modificare le impostazioni di pagamento per una transazione utilizzando la finestra di dialogo **Aggiorna data di scadenza e date dello sconto di cassa**, seguire questi passaggi.

1. Selezionare **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
2. Nella scheda **Liquidazioni** impostare l'opzione **Mostra data di scadenza e consenti modifica** su **Sì**.
3. Per abilitare questa funzionalità, sono stati aggiunti nuovi campi alle transazioni fornitore. Questi campi verranno completati quando viene completata una nuova transazione. Verranno completati anche quando si apre la finestra di dialogo **Aggiorna data di scadenza e date dello sconto di cassa**. Quando si imposta l'opzione **Mostra data di scadenza e consenti modifica** su **Sì**, verrà visualizzata la finestra di dialogo **Aggiorna informazioni di pagamento**.  Per aggiornare immediatamente le transazioni esistenti, selezionare **Aggiorna tutte le transazioni esistenti**. In alternativa, per completare i campi solo per le nuove transazioni, selezionare **Continua senza aggiornamento**.

La data di scadenza viene ora aggiunta alla pagina elenco **Transazioni fornitore** ed è possibile modificare più facilmente la data di scadenza e le date di sconto di cassa per le transazioni.

### <a name="modify-the-payment-settings"></a>Modificare le impostazioni di pagamento

La pagina elenco **Transazioni fornitore** visualizza tutte le transazioni per un fornitore. Quando si seleziona la data di scadenza di una transazione, viene visualizzata una finestra di dialogo. Questa finestra di dialogo visualizza la data di base per i calcoli degli sconti e della data di scadenza, la data di scadenza, i termini di pagamento, i termini di sconto di cassa e le date di sconto di cassa.

Ciascun campo ha un effetto diverso sulla transazione quando lo si modifica:

- **Modifica data di base:** la data di scadenza e le date di sconto vengono modificate come se la data di base fosse la data del documento.
- **Modifica data di scadenza:** solo la data di scadenza viene modificata.
- **Modifica date di sconto:** solo le date di sconto vengono modificate.
- **Modifica termini di pagamento:** viene modificata la data di scadenza in base alla data di base e ai termini di pagamento.
- **Modifica termini di sconto di cassa:** vengono modificati gli sconti di cassa in base alla data di base e ai termini di sconto di cassa.

Dopo avere modificato le impostazioni di pagamento, selezionare **Chiudi** per salvare le modifiche.

