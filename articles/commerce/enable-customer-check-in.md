---
title: Abilitare le notifiche di check-in del cliente nel POS
description: Questo articolo descrive come abilitare le notifiche di check-in del cliente nel POS di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ae53657c95128eae793f670bd9dbc31d9fac0fe4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885147"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Abilitare le notifiche di check-in del cliente nel POS

[!include [banner](includes/banner.md)]

Questo articolo descrive come abilitare le notifiche di check-in del cliente nel POS di Microsoft Dynamics 365 Commerce.

Nelle loro e-mail di ordine pronto per il ritiro, le organizzazioni possono fornire un collegamento o un pulsante che consente ai clienti di notificare al punto vendita che si trovano sul posto e che aspettano che il loro pacco venga loro consegnato. I clienti ricevono quindi una conferma del check-in e il punto vendita riceve una notifica come attività nella sua applicazione POS. Questa attività serve come richiesta per un addetto alle vendite di consegnare l'ordine al veicolo del cliente. Pertanto, il cliente non deve entrare nel punto vendita.

Il flusso di lavoro del check-in del cliente può anche essere configurato per raccogliere informazioni aggiuntive dai clienti, come il numero del parcheggio, la marca, il modello e il colore del veicolo e le istruzioni di consegna. L'addetto del punto vendita al dettaglio può utilizzare queste informazioni per facilitare l'evasione degli ordini.

## <a name="enable-customer-check-in"></a>Abilitare il check-in del cliente

Quando la funzionalità di check-in del cliente è attivata, Commerce genera un ID di conferma dell'ordine (noto anche come ID di riferimento canale). Genera inoltre ID di conferma dell'ordine per gli ordini creati tramite i canali POS o call center. 

Per attivare la funzionalità di check-in del cliente in Commerce Headquarters, segui questa procedura.

1. Vai a **Aree di lavoro \> Gestione funzionalità**.
2. Cerca la funzionalità **Genera un formato ID di riferimento canale coerente per tutti i canali**. 
3. Selezionare la funzionalità, quindi nel riquadro delle proprietà selezionare **Abilita ora**. 

## <a name="create-a-check-in-confirmation-page"></a>Creare una pagina di conferma del check-in

Sul tuo sito di e-commerce, devi creare una nuova pagina che fungerà da esperienza di conferma del check-in. Attraverso una configurazione aggiuntiva, la pagina può anche includere un modulo che raccoglie informazioni aggiuntive dai clienti per facilitare l'evasione degli ordini. Per informazioni su come impostare la pagina e il modulo, vedere [Modulo check-in del cliente](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Configurare il modello di messaggio di posta elettronica transazionale

Devi aggiungere un collegamento o pulsante **Sono qui** al modello per il messaggio di posta elettronica transazionale che i clienti ricevono quando il loro ordine è pronto per il ritiro. I clienti utilizzeranno questo collegamento o pulsante per notificare al punto vendita che sono arrivati per ritirare l'ordine. 

Aggiungere il collegamento o il pulsante al modello mappato al tipo di notifica **Imballaggio completato** e la modalità di consegna che utilizzi per l'evasione degli ordini all'esterno del punto vendita. Nel modello, crea un collegamento o un pulsante HTML che punti all'URL della pagina di conferma del check-in che hai creato e che includa i nomi e i valori dei parametri, come mostrato nell'esempio seguente.

`<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%confirmationid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>`

Per ulteriori informazioni su come configurare i modelli di posta elettronica, vedere [Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Un'attività di conferma del check-in viene creata in POS

Dopo che un cliente ha notificato al negozio che è presente per il ritiro, la pagina del check-in mostra un messaggio di conferma e un codice QR opzionale che contiene l'ID di conferma dell'ordine del cliente. Allo stesso tempo, viene creata un'attività nell'elenco delle attività nel POS per il negozio in cui il cliente ritira l'ordine. Questa attività contiene tutte le informazioni sul cliente e sull'ordine necessarie per evadere l'ordine. Il campo delle istruzioni dell'attività mostra tutte le informazioni raccolte dal cliente tramite il modulo delle informazioni aggiuntive.

## <a name="end-to-end-testing"></a>Test end-to-end

Il check-in del cliente richiede che parametri e valori specifici vengano passati alla pagina del check-in e quindi all'API check-in del cliente. Pertanto, l'approccio più semplice consiste nel testare la funzionalità in un ambiente in cui è possibile creare e imballare un ordine di test. In questo modo, è possibile generare un'e-mail di "ordine pronto per il ritiro" con un URL che contiene i nomi e i valori dei parametri richiesti.

Per testare la funzionalità di check-in del cliente, segui questi passaggi.

1. Crea la pagina di check-in del cliente, quindi aggiungi e configura il modulo di check-in del cliente. Per ulteriori informazioni, vedi [Check-in per il modulo di ritiro](check-in-pickup-module.md). 
1. Archivia la pagina ma non pubblicarla.
1. Aggiungi il seguente collegamento a un modello di e-mail richiamato dal tipo di notifica di completamento dell'imballaggio per una modalità di consegna di ritiro. Per ulteriori informazion vedi [Creare modelli e-mail per eventi transazionali](email-templates-transactions.md).

    - **Per gli ambienti di pre-produzione (UAT):** Aggiungi il frammento di codice dalla sezione [Configurare il modello di messaggio di posta elettronica transazionale](#configure-the-transactional-email-template) precedente in questo articolo.
    - **Per ambienti di produzione:** Aggiungi il seguente codice commentato in modo che i clienti esistenti non siano interessati.

        `<!-- https://[DOMAIN]/[CHECK_IN_PAGE]?channelReferenceId=%confirmationid%&channelId=%pickupchannelid%&packingSlipId=%packingslipid%&preview=inprogress -->`

1. Crea un ordine in cui è specificata la modalità di consegna del ritiro.
1. Quando ricevi l'e-mail che viene attivata dal tipo di notifica di completamento dell'imballaggio, verifica il flusso di check-in aprendo la pagina di check-in con l'URL che hai aggiunto in precedenza. Poiché l'URL include il flag `&preview=inprogress`, ti verrà chiesto di autenticarti prima di poter visualizzare la pagina.
1. Immetti tutte le informazioni aggiuntive necessarie per configurare il modulo.
1. Verifica che la vista di conferma del check-in venga visualizzata correttamente.
1. Apri il terminale POS per il negozio in cui verrà ritirato l'ordine.
1. Seleziona il riquadro **Ordini da ritirare** e verifica che venga visualizzato l'ordine.
1. Verifica che eventuali informazioni aggiuntive configurate nel modulo di check-in vengano visualizzate nel riquadro dei dettagli.

Dopo aver verificato che la funzione di check-in del cliente funziona end-to-end, segui questi passaggi.

1. Pubblica la pagina di check-in.
1. Se stai testando in un ambiente di produzione, decommenta l'URL nel modello di e-mail "ordine pronto per il ritiro", in modo che il collegamento o il pulsante **io sono qui** viene visualizzato. Quindi ricarica il modello.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo di check-in per il ritiro](check-in-pickup-module.md)

[Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna](customize-email-delivery-mode.md)

[Creare modelli e-mail per eventi transazionali](email-templates-transactions.md)
