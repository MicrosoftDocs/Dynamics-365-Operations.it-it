---
title: Aprire un URL nel POS
description: Questo argomento fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Dynamics 365 Retail.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 406dad1709dc837f7f87817241d7062f6b08d8fd
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025888"
---
# <a name="open-url-in-pos"></a>Aprire l'URL nel POS

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come configurare un pulsante nel Retail POS per aprire un URL. Questa funzionalità non richiede una personalizzazione del codice e può essere configurata da qualcuno cha ha un ruolo non sviluppatore. 

Questa funzionalità consente la configurazione di un pulsante nel POS, utilizzando la finestra di progettazione della griglia dei pulsanti per aprire un URL. Attualmente, è supportata nelle seguenti configurazioni:

- Apertura in una nuova finestra
- Apertura nel POS
- Apertura di un'app nativa

## <a name="open-in-new-window"></a>Apertura in nuova finestra

Questa configurazione definisce se aprire l'URL in una nuova finestra o nell'app. Quando la configurazione prevede l'apertura di un URL Web nell'app, il pannello di navigazione laterale e la barra superiore del POS sono visibili e disponibili per l'interazione dell'utente. Quando la configurazione prevede l'apertura in una nuova finestra, l'URL verrà aperto in Modern POS per Windows e in una nuova scheda del browser in tutti gli altri client del POS. Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.

## <a name="open-within-pos"></a>Apertura nel POS

L'apertura di un URL Web nel POS è attualmente supportata solo per Modern POS per Windows. In altri client, questa funzionalità è in fase di sviluppo e verrà integrata con aggiornamenti futuri. Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** non selezionata.

## <a name="open-a-native-app"></a>Apertura di un'app nativa

Questa configurazione consente inoltre di specificare URL non Web per aprire un'app nativa. Ad esempio, è possibile specificare protocolli URL come MailTo, SIP, IM o MSTEAMS, che potranno quindi essere gestiti dalle app native rispettive nel dispositivo host. Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.

- Per i computer Windows, vedere [Esportare o importare per impostare associazioni di applicazioni predefinite](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) per impostare le associazioni di protocollo predefinite se si configura il computer mediante DISM.
- Se si utilizza MDM, ad esempio Intune per gestire i computer Windows, vedere [CSP criteri - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).
- Se si è uno sviluppatore che crea un sito Web personalizzato, vedere [Avvio di un'app predefinita per un URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Apertura più agevole di un'app nativa

Windows, Android e IOS consentono inoltre un'apertura più agevole delle app, in base all'associazione di protocollo dell'app. Se l'app in uso non è già configurata per gestire l'apertura da un browser Web, è possibile che questa operazione debba essere eseguita da uno sviluppatore.

- Per Windows, vedere [Abilitare le app per i siti Web usando i gestori degli URI delle app](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).
- Per IOS, vedere [Universal Links for Developers](https://developer.apple.com/ios/universal-links/)..
- Per Android, vedere [Handling Android App Links](https://developer.android.com/training/app-links/)

| Cliente                | Apri in nuova finestra | Apertura di un'app nativa | Apertura nel POS | Dettagli                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| Modern POS per Windows | ✓\*                | ✓               | ✓              | \*Apertura in una nuova finestra di Modern POS |
| POS cloud             | ✓\*                | ✓               | X              | \*Apertura in una nuova scheda del browser        |
| Modern POS per IOS     | ✓\*                | ✓               | X              | \*Apertura in una nuova scheda del browser        |
| Modern POS per Android | ✓\*                | ✓               | X              | \*Apertura in una nuova scheda del browser        |

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare, leggere [Layout delle schermate per il POS](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>Aprire un URL nel POS

Per configurare un URL per l'apertura nel POS, effettuare le operazioni seguenti.

1. Nella sede centrale, accedere a **Vendita al dettaglio \> Impostazione canale \> Impostazione POS \> POS \> Layout schermo**.
2. Selezionare **Griglie dei pulsanti \> Progettazione**.
3. Creare un nuovo pulsante.
4. Selezionare le proprietà **Pulsante**.
5. Selezionare **Apri URL** come azione.
6. Immettere l'URL che si desidera utilizzare.
7. Specificare se aprire l'URL in una nuova finestra.
