---
title: Abilitare le notifiche di check-in dei clienti nel POS
description: Questo argomento descrive come abilitare le notifiche di check-in del cliente nel POS di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
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
ms.openlocfilehash: b42dc7766f8a69a7409c28d21b49cc96eca18dd4
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271427"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Abilitare le notifiche di check-in dei clienti nel POS

[!include [banner](includes/banner.md)]

Questo argomento descrive come abilitare le notifiche di check-in del cliente nel POS di Microsoft Dynamics 365 Commerce.

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

Aggiungere il collegamento o il pulsante al modello mappato al tipo di notifica **Imballaggio completato** e la modalità di consegna che utilizzi per l'evasione degli ordini all'esterno del punto vendita. Nel modello, crea un collegamento HTML o un pulsante che punti all'URL della pagina di conferma del check-in che hai creato. Ecco un esempio.

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
Per ulteriori informazioni su come configurare i modelli di posta elettronica, vedere [Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Un'attività di conferma del check-in viene creata in POS

Dopo che un cliente ha notificato al punto vendita che è presente per il ritiro, riceve una notifica di conferma del check-in e viene creata un'attività nell'elenco delle attività nel POS per il punto vendita in cui il cliente sta ritirando l'ordine. L'attività contiene tutte le informazioni sul cliente e sull'ordine necessarie per evadere l'ordine. Nell'attività, il campo delle istruzioni mostra tutte le informazioni raccolte dal cliente tramite il modulo delle informazioni aggiuntive. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo di check-in per il ritiro](check-in-pickup-module.md)
