---
title: Visualizzare le notifiche degli ordini nel POS
description: In questo argomento viene descritto come abilitare le notifiche degli ordini nel POS e nel framework di notifica.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: c3b8e2774a189f2afefa757e7c4f3885b674918c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976790"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Visualizzare le notifiche degli ordini nel POS

[!include [banner](includes/banner.md)]

Nel moderno ambiente di vendita al dettaglio, ai collaboratori del POS vengono assegnate varie attività, come aiutare i clienti, inserire transazioni, eseguire conteggi di inventario e ricevere ordini nel POS. Il client POS fornisce un'applicazione unica in cui i collaboratori possono eseguire tutte queste attività e molto altro. Poiché è necessario svolgere diversi compiti durante il giorno, potrebbe essere necessario che i collaboratori vengano avvisati quando qualcosa richiede la loro attenzione. Il framework di notifica nel POS agevola tale operazione consentendo ai rivenditori di configurare notifiche basate su ruoli. A partire da Dynamics 365 for Retail con update 5 dell'applicazione, queste notifiche possono essere configurate solo per le operazioni di POS.


Attualmente, il sistema può visualizzare le notifiche solo per operazioni di evasione dell'ordine. Tuttavia, poiché il framework è progettato per essere estendibile, gli sviluppatori potranno finalmente scrivere un gestore di notifica per qualsiasi operazione e mostrare le notifiche per l'operazione specifica nel POS.

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Attivare le notifiche per le operazioni di evasione dell'ordine

Per attivare le notifiche per le operazioni di evasione dell'ordine, attenersi alla procedura seguente.

1. Passare a **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **POS** &gt; **Operazioni**.
2. Cercare l'operazione **Evasione ordine** e selezionare la relativa casella di controllo **Abilita notifiche** per specificare che il framework di notifica deve ascoltare il gestore per questa operazione. Se il gestore è implementato, le notifiche per l'operazione verranno quindi visualizzate nel POS.
3. Passare a **Retail e Commerce** &gt; **Dipendenti** &gt; **Lavoratori** &gt;, nella scheda Commercio, aprire le autorizzazioni POS associate al lavoratore. Espandere la scheda dettaglio **Notifiche**, aggiungere l'operazione **Evasione ordine** e impostare il campo **Ordine di visualizzazione** su **1**. Se più di una notifica è configurata, questo campo viene utilizzato per disporre le notifiche. Le notifiche che hanno un valore di **Ordine di visualizzazione** inferiore vengono visualizzate sopra a quelle con un valore superiore. Le notifiche con un valore di **Ordine di visualizzazione** di **1** vengono visualizzate nella parte superiore.

    Le notifiche vengono visualizzate solo per le operazioni che vengono aggiunte nella scheda dettaglio **Notifiche** ed è possibile aggiungere operazioni in tale posizione solo se la casella di controllo **Abilita notifiche** per queste operazioni è stata selezionata nella pagina **Operazioni POS**. Inoltre, le notifiche per un'operazione vengono mostrate ai lavoratori solo se l'operazione viene aggiunta alle autorizzazioni POS per tali lavoratori.

    > [!NOTE]
    > Le notifiche possono essere sostituite a livello di utente. Aprire il record del lavoratore, selezionare **Autorizzazioni POS** e quindi modificare la sottoscrizione di notifica dell'utente.

4. Passare a **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **Profili POS** &gt; **Profili funzionalità**. Nel campo **Intervallo di notifica**, specificare la frequenza con cui le notifiche devono essere recuperate. Per alcune notifiche, il POS deve effettuare chiamate in tempo reale all'applicazione di back-office. Queste chiamate utilizzano la capacità di calcolo dell'applicazione di back-office. Pertanto, quando si imposta l'intervallo di notifica, è consigliabile prendere in considerazione sia i requisiti aziendali che l'impatto delle chiamate in tempo reale all'applicazione di back-office. Un valore di **0** (zero) disattiva notifiche.
5. Selezionare **Retail e Commerce** &gt; **Vendita al dettaglio e commercio IT** &gt; **Programmazione della distribuzione**. Selezionare la programmazione **1060** (**Personale**) per sincronizzare le impostazioni di sottoscrizione della notifica e quindi selezionare **Esegui ora**. Quindi, selezionare la programmazione **1070** (**Configurazione canale**) per sincronizzare l'intervallo di autorizzazione, quindi selezionare **Esegui ora**.

## <a name="view-notifications-in-the-pos"></a>Visualizzare notifiche nel POS

Una volta completati i passaggi precedenti, i lavoratori potranno visualizzare le notifiche nel POS. Per visualizzare le notifiche, premere l'icona di notifica nell'angolo in altro a destra del POS. Viene visualizzato un centro di notifica in cui sono riportate le notifiche per l'operazione di evasione dell'ordine. Il centro di notifica deve riportare i seguenti gruppi nell'operazione di evasione dell'ordine:

- **Ritiro presso punto vendita** - Il gruppo riporta il conteggio degli ordini con una modalità di consegna **Prelievo** e per i quali il prelievo viene programmato dal punto vendita corrente. È possibile premere il numero sul gruppo per aprire la pagina **Evasione ordine**. In questo caso, la pagina verrà filtrata in modo da riportare solo gli ordini attivi impostati per il prelievo dal punto vendita corrente.
- **Spedizione da punto vendita** - Il gruppo riporta il conteggio degli ordini con modalità di consegna **Spedizione** e per i quali la spedizione è programmata dal punto vendita corrente. È possibile premere il numero sul gruppo per aprire la pagina **Evasione ordine**. In questo caso, la pagina verrà filtrata in modo da riportare solo gli ordini attivi impostati per la spedizione dal punto vendita corrente.

Se nuovi ordini vengono assegnati al punto vendita per l'evasione, l'icona di notifica viene modificata per indicare che sono presenti nuove notifiche e che il conteggio dei gruppi appropriati è aggiornato. Anche se i gruppi vengono aggiornati a intervalli regolari, gli utenti POS possono aggiornare manualmente i gruppi in qualsiasi momento facendo clic sul pulsante **Aggiorna** accanto al gruppo. Infine, se in un gruppo è presente un nuovo articolo, che il lavoratore corrente non ha visualizzato, il gruppo riporta un simbolo di esplosione per indicare la presenza di nuovo contenuto.

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
