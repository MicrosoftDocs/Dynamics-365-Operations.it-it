---
title: Visualizzare le notifiche degli ordini nel POS
description: In questo argomento viene descritto come abilitare le notifiche degli ordini nel POS e nel framework di notifica.
author: ShalabhjainMSFT
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: f7b28a33dff4af6bf2b97db825a5a8304213f3a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796488"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Visualizzare le notifiche degli ordini nel POS

[!include [banner](includes/banner.md)]

Ai dipendenti del negozio possono essere assegnate varie attività nel loro punto vendita, come evadere gli ordini o eseguire la ricezione dell'inventario o il conteggio delle scorte. Il client POS fornisce un'applicazione mediante la quale è possibile notificare tali attività ai dipendenti. Il framework di notifica nel POS agevola tale operazione consentendo ai rivenditori di configurare notifiche basate su ruoli. A partire dall' aggiornamento dell'applicazione 5 di Dynamics 365 Retail, le notifiche possono essere configurate per le operazioni POS.

Il sistema può mostrare notifiche per l'operazione *Evasione ordine* e, a partire dalla versione 10.0.18 di Commerce, le notifiche possono essere visualizzate per l'operazione *Richiama ordine*. Tuttavia, poiché il framework è progettato per essere estendibile, gli sviluppatori possono [scrivere un gestore di notifica](dev-itpro/extend-pos-notification.md) per qualsiasi operazione e mostrare le notifiche per l'operazione specifica nel POS.

## <a name="enable-notifications-for-order-fulfillment-or-recall-order-operations"></a>Attivare le notifiche per le operazioni Evasione ordine o Richiama ordine

Per attivare le notifiche per le operazioni Evasione ordine o Richiama ordine, procedere come segue:

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Operazioni**.
1. Cercare l'operazione **Evasione ordine** o **Richiama ordine** e selezionare **Abilita notifiche** per specificare che il framework di notifica deve ascoltare il gestore per questa operazione. Se il gestore è implementato, le notifiche per l'operazione verranno quindi visualizzate nel POS.
1. Passare a **Retail e Commerce \> Dipendenti \> Lavoratori**.
1. Selezionare la scheda **Commerce**, selezionare la riga di un lavoratore e quindi **Autorizzazioni POS**. Selezionare la Scheda dettaglio **Notifiche** per espanderla, quindi aggiungere le operazioni per le quali sono state abilitate le notifiche. Se si configura una singola notifica per un lavoratore, assicurarsi che il valore **Ordine di visualizzazione** sia impostato su **1**. Se si configura più di un'operazione, impostare i valori **Ordine di visualizzazione** per indicare l'ordine in cui devono essere visualizzate le notifiche. 

      Le notifiche vengono visualizzate solo per le operazioni aggiunte alla Scheda dettaglio **Notifiche**. È possibile aggiungere operazioni in quella scheda solo se le caselle di controllo **Abilita notifiche** per tali operazioni sono state selezionate nella pagina **Operazioni POS**. Inoltre, le notifiche per un'operazione sono visibili ai lavoratori solo se l'operazione viene aggiunta alle autorizzazioni POS per tali lavoratori.

    > [!NOTE]
    > Le notifiche possono essere sostituite a livello di utente. A questo proposito, aprire il record del lavoratore, selezionare **Autorizzazioni POS** e quindi modificare la sottoscrizione di notifica dell'utente.

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. Nel campo **Intervallo di notifica**, specificare la frequenza con cui le notifiche devono essere recuperate. Per alcune notifiche, il POS deve effettuare chiamate in tempo reale all'applicazione di back-office. Queste chiamate utilizzano la capacità di calcolo dell'applicazione di back-office. Pertanto, quando si imposta l'intervallo di notifica, è consigliabile prendere in considerazione sia i requisiti aziendali che l'impatto delle chiamate in tempo reale all'applicazione di back-office. Un valore di **0** (zero) disattiva notifiche.
1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**. Selezionare la programmazione **1060** (**Personale**) per sincronizzare le impostazioni di sottoscrizione della notifica e quindi selezionare **Esegui ora**. Quindi, selezionare la programmazione **1070** (**Configurazione canale**) per sincronizzare l'intervallo di autorizzazione, quindi selezionare **Esegui ora**.

## <a name="view-notifications-in-the-pos"></a>Visualizzare notifiche nel POS

Una volta completati i passaggi precedenti, i lavoratori potranno visualizzare le notifiche nel POS. Per visualizzare le notifiche, selezionare l'icona di notifica nell'angolo in alto a destra del POS. Viene visualizzato un pannello di notifica in cui sono riportate le notifiche per le operazioni configurate per il lavoratore. 

Per l'operazione **Evasione ordine**, il pannello di notifica visualizzerà i seguenti gruppi:

- **Ritiro presso punto vendita** - Questo gruppo indica il conteggio delle singole righe ordine per le quali il ritiro viene programmato presso il punto vendita corrente. È possibile selezionare il numero nel gruppo per aprire l'operazione **Evasione ordine** con un filtro di modo che mostri solo le righe ordine attive impostate per il ritiro presso il punto vendita corrente.
- **Spedito da punto vendita** - Questo gruppo mostra il conteggio delle singole righe ordine che sono state configurate per la spedizione dal punto vendita corrente dell'utente. È possibile selezionare il numero nel gruppo per aprire l'operazione **Evasione ordine** con una visualizzazione filtrata che mostra solo le righe ordine attive impostate per la spedizione dal punto vendita corrente.

Per l'operazione **Richiama ordine**, il pannello di notifica visualizzerà i seguenti gruppi:

- **Ordini da evadere** - Questo gruppo mostra il conteggio degli ordini configurati per il ritiro o l'evasione della spedizione per il punto vendita corrente dell'utente. È possibile selezionare il numero nel gruppo per aprire l'operazione **Richiama ordine** con una visualizzazione filtrata che mostra solo gli ordini aperti che devono essere evasi dal punto vendita corrente dell'utente per gli scenari di ritiro presso il punto vendita o di spedizione dal punto vendita.
- **Ordini da prelevare** - Questo gruppo indica il conteggio degli ordini programmati per il ritiro presso il punto vendita corrente. È possibile selezionare il numero nel gruppo per aprire l'operazione **Richiama ordine** con una visualizzazione filtrata che mostra solo gli ordini aperti che devono essere evasi per il ritiro da parte del cliente presso il punto vendita corrente dell'utente.
- **Ordini da spedire** - Questo gruppo mostra il conteggio degli ordini da spedire dal punto vendita corrente dell'utente. È possibile selezionare il numero nel gruppo per aprire l'operazione **Richiama ordine** con una visualizzazione filtrata che mostra solo gli ordini aperti che devono essere evasi per la spedizione dal punto vendita corrente dell'utente.

Per le notifiche relative all'evasione degli ordini e al richiamo degli ordini, quando nuovi ordini vengono prelevati tramite il processo, l'icona di notifica viene modificata per indicare che sono presenti nuove notifiche e che il conteggio dei gruppi appropriati è aggiornato. Anche se i gruppi vengono aggiornati ad intervalli regolari, gli utenti POS possono aggiornare manualmente i gruppi in qualsiasi momento selezionando **Aggiorna** accanto al gruppo. Infine, se in un gruppo è presente un nuovo articolo, che il lavoratore corrente non ha visualizzato, il gruppo riporta un simbolo di esplosione per indicare la presenza di nuovo contenuto.

## <a name="enable-live-content-on-pos-buttons"></a>Abilitare contenuto in diretta su pulsanti POS

I pulsanti POS possono ora riportare un conteggio per consentire ai lavoratori di determinare in modo semplice quali attività richiedono la loro attenzione immediata. Per visualizzare questo numero su un pulsante POS, è necessario completare l'impostazione di notifica descritta in precedenza in questo argomento, ovvero è necessario attivare le notifiche per un'operazione, impostare un intervallo di notifica e aggiornare il gruppo di autorizzazioni POS per il lavoratore. Inoltre, è necessario aprire la finestra di progettazione della griglia dei pulsanti, visualizzare le proprietà del pulsante e selezionare la casella di controllo **Abilita contenuto in diretta**. Nel campo **Allineamento contenuto**, è possibile selezionare se il conteggio viene visualizzato nell'angolo superiore destro del pulsante (**Destra in alto**) o al centro (**Centro**).

> [!NOTE]
> Il contenuto in diretta può essere abilitato per le operazioni solo se la relativa casella di controllo **Abilita notifiche** è stata selezionata nella pagina **Operazioni POS**, come descritto in precedenza in questo argomento.

La seguente illustrazione mostra le impostazioni del contenuto in diretta nella finestra di progettazione della griglia dei pulsanti.

![Impostazioni del contenuto in diretta nella finestra di progettazione della griglia dei pulsanti](./media/ButtonGridDesigner.png "Impostazioni del contenuto in diretta nella finestra di progettazione della griglia dei pulsanti")

Per visualizzare il conteggio di notifica su un pulsante, è necessario assicurarsi che venga aggiornato il layout dello schermo corretto. Per determinare il layout dello schermo utilizzato dal POS, selezionare l'icona **Impostazioni** nell'angolo superiore destro e verificare i campi **ID layout schermo** e **Risoluzione layout**. Ora utilizzando il nuovo browser Edge, passare alla pagina **Layout schermo**, cercare **ID layout schermo** e **Risoluzione layout** indicati sopra e selezionare la casella di controllo **Abilita contenuto in tempo reale**. Fare clic su **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione** ed eseguire il processo 1090 (dei registratori di cassa) per sincronizzare le modifiche del layout.

![Individuare il layout dello schermo utilizzato dal POS](./media/Choose_screen_layout.png "Individuare il layout dello schermo")

La seguente illustrazione mostra l'effetto della selezione di **Destra in alto** rispetto a **Centro** nel campo **Allineamento contenuto** per pulsanti di varie dimensioni.

![Contenuto in diretta su pulsanti POS](./media/ButtonsWithLiveContent.png "Contenuto in diretta su pulsanti POS")

[!INCLUDE[footer-include](../includes/footer-banner.md)]
