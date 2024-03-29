---
title: Aprire un URL nel POS
description: Questo articolo fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.custom: 141393
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: ad82cf1039515e58d1717453ee3fb4e3dafd84fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276429"
---
# <a name="open-url-in-pos"></a>Aprire un URL nel POS

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come configurare un pulsante in POS Dynamics 365 Commerce per aprire un URL. Questa funzionalità non richiede una personalizzazione del codice e può essere configurata da qualcuno cha ha un ruolo non sviluppatore. 

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

- Per i computer Windows, vedere [Esportare o importare per impostare associazioni di applicazioni predefinite](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) per impostare le associazioni di protocollo predefinite se si configura il computer mediante DISM.
- Se si utilizza MDM, ad esempio Intune per gestire i computer Windows, vedere [CSP criteri - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults).
- Se si è uno sviluppatore che crea un sito Web personalizzato, vedere [Avvio di un'app predefinita per un URI](/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Apertura più agevole di un'app nativa

Windows, Android e IOS consentono inoltre un'apertura più agevole delle app, in base all'associazione di protocollo dell'app. Se l'app in uso non è già configurata per gestire l'apertura da un browser Web, è possibile che questa operazione debba essere eseguita da uno sviluppatore.

- Per Windows, vedere [Abilitare le app per i siti Web usando i gestori degli URI delle app](/windows/uwp/launch-resume/web-to-app-linking).
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

1. Nella sede centrale, accedere a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Layout schermo**.
2. Selezionare **Griglie dei pulsanti \> Progettazione**.
3. Creare un nuovo pulsante.
4. Selezionare le proprietà **Pulsante**.
5. Selezionare **Apri URL** come azione.
6. Immettere l'URL che si desidera utilizzare.
7. Specificare se aprire l'URL in una nuova finestra.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
