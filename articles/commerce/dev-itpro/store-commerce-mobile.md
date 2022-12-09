---
title: App Store Commerce per piattaforme mobili
description: Questo articolo descrive come iniziare a utilizzare l'app Microsoft Dynamics 365 Commerce Store Commerce per Android e iOS.
author: stuharg
ms.date: 11/30/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2018-10-29
ms.openlocfilehash: dc952698a2a3301aff312e8310c58cbbb9cfe290
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815785"
---
# <a name="store-commerce-app-for-mobile-platforms"></a>App Store Commerce per piattaforme mobili

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Questo articolo descrive come iniziare a utilizzare le app Microsoft Dynamics 365 Commerce Store Commerce per Android e iOS.

Le app per dispositivi mobili Dynamics 365 Commerce per Android e iOS rendono il processo di distribuzione di dispositivi mobili POS (Mobile Point of Sale) con funzionalità complete per il tuo ambiente di vendita al dettaglio semplice e veloce. Le app per dispositivi mobili Store Commerce offrono quasi tutte le funzionalità e i vantaggi dell'app [Store Commerce per Windows](store-commerce.md) e funzionare su un'ampia gamma di tablet e telefoni iOS e Android. Le app per dispositivi mobili Store Commerce possono essere installate direttamente dagli app store di Apple e Google Play e non richiedono che uno sviluppatore crei un nuovo pacchetto di applicazioni per distribuirle o aggiornarle. 

Le app per dispositivi mobili Store Commerce mantengono la piena parità funzionale con le attuali app ibride per vendita al dettaglio. Inoltre, Store Commerce per iOS include il supporto per una stazione hardware dedicata, in modo che i dispositivi iOS possano comunicare con terminali di pagamento in rete, stampanti per ricevute e cassetti di cassa senza richiedere la distribuzione di una stazione hardware condivisa. 

> [!IMPORTANT]
> Le app Store Commerce per Windows, Android e iOS sono la prossima generazione di applicazioni POS per Dynamics 365 Commerce. Le app Store Commerce offrono numerosi miglioramenti rispetto ai loro predecessori pur mantenendo la piena parità funzionale e di funzionalità. Microsoft ritirerà le app Retail POS hybrid per iOS e Android ed MPOS alla fine del 2023 e consiglia di utilizzare Store Commerce o Cloud POS (CPOS) per tutte le nuove distribuzioni POS. I clienti esistenti dovrebbero pianificare la migrazione dalle app ibride per vendita al dettaglio a Store Commerce. Per ulteriori informazioni, vedi [Migrazione del POS moderno in Store Commerce](pos-extension/migrate-mpos-store-commerce.md). 

## <a name="app-architecture"></a>Architettura dell'app

Le app per dispositivi mobili Store Commerce usano la stessa topologia dell'app Store Commerce per Windows quando è distribuita in modalità ibrida. Le app per dispositivi mobili Store Commerce sono applicazioni shell che eseguono il rendering di CPOS direttamente dalla Commerce Scale Unit (CSU) e si collegano a Commerce headless e Commerce headquarters tramite la CSU. Il modello di applicazione shell consente alle app Store Commerce di supportare una stazione hardware dedicata per l'integrazione diretta con un terminale di pagamento, una stampante, un cassetto di cassa e altre periferiche. Non è necessario configurare una stazione hardware condivisa per utilizzare i dispositivi hardware. 

Per aggiornare un'app per dispositivi mobili Store Commerce, basta aggiornare la CSU. Tutte le nuove funzionalità e caratteristiche del POS verranno automaticamente raccolte dall'app. Per ulteriori informazioni su come aggiornare la CSU, vedi [Applicare aggiornamenti ed estensioni a Commerce Scale Unit (cloud)](../../fin-ops-core/dev-itpro/deployment/update-retail-channel.md).

Le app shell vengono gestite tramite gli aggiornamenti dell'app store. Quando una versione secondaria raggiunge la disponibilità generale (GA), Microsoft la pubblicherà negli app store. Microsoft potrebbe anche pubblicare patch tra gli aggiornamenti di versione secondaria per rilasciare le correzioni di bug ad alta priorità.

## <a name="prerequisites"></a>Prerequisiti

Le app per dispositivi mobili Store Commerce richiedono Dynamics 365 Commerce, in particolare i componenti Commerce headquarters e CSU. La tabella seguente elenca le versioni minime del sistema operativo (SO) e della CSU richieste dalle app per dispositivi mobili Android e iOS. 

| Prerequisito | Android      | iOS  |
| ------------ | ------------ | ---- |
| Versione sistema operativo   | 7.0          | 15.0 |
| Versione CSU  | 9.38.22266.8 | Da definire  |

## <a name="install-the-app"></a>Installa l'app

Puoi installare le app per dispositivi mobili Store Commerce direttamente dal Google Play Store o dall'App Store di Apple. 

- [App Store Commerce per Android](https://aka.ms/storecommerceandroid)
- [App Store Commerce per iOS](https://aka.ms/storecommerceios)

I pacchetti di app Android (.apk) e app Apple (.ipa) possono anche essere scaricati dalla libreria di risorse condivise in Microsoft Dynamics Lifecycle Services. 

## <a name="device-and-register-setup"></a>Impostazione di registri e dispositivi

Prima di poter attivare un registro sulle app per dispositivi mobili Store Commerce, è necessario configurare un dispositivo e un registro in Commerce headquarters. Per ulteriori informazioni, vedi [Dispositivi e registri](../implementation-considerations-devices.md). 

### <a name="device-setup"></a>Impostazione dei dispositivi

Per creare e configurare un nuovo dispositivo, attieniti alla seguente procedura.

1. In Commerce headquarters vai a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Dispositivi**. 
1. Crea un nuovo dispositivo e seleziona **Modern POS - Android** o **Modern POS - iOS** come tipo di applicazione, a seconda dell'app per dispositivi mobili che stai distribuendo. 

    > [!NOTE] 
    > I tipi di applicazione **Modern POS - Android** e **Modern POS - iOS** vengono usati anche per distribuire le attuali app ibride per Android e iOS. Dopo il ritiro di MPOS, le etichette per questi tipi di applicazioni verranno aggiornate a **Store Commerce - Android** e **Modern POS - iOS**. 

### <a name="register-setup"></a>Impostazione registro

Puoi creare un nuovo registro e associarlo al dispositivo che hai creato, oppure puoi associare un registro esistente al tuo nuovo dispositivo. Per ulteriori informazioni sui registri, vedi [Creare e associare registri](../tasks/create-associate-registers.md).

### <a name="screen-layout-setup"></a>Impostazione del layout schermo

Se stai riproponendo un layout dello schermo incluso nei dati demo forniti con la tua licenza Dynamics 365 Commerce, l'app Store Commerce selezionerà automaticamente il layout compatto incluso se la risoluzione dello schermo del tuo dispositivo è inferiore a 480 &times; 853 pixel con orientamento verticale. Tuttavia, se stai creando un layout dello schermo da zero o se il tuo dispositivo mobile utilizza una risoluzione maggiore di quella supportata dal layout compatto, assicurati di creare una risoluzione e le griglie dei pulsanti associate che siano appropriate per il telefono o il tablet in cui prevedi di distribuire. Per ulteriori informazioni sulle configurazioni del layout dello schermo, vedi [Configurazioni visive dell'interfaccia utente POS](../pos-screen-layouts.md). 

Dopo aver configurato dispositivi e registri, in Commerce headquarters, vai a **Vendita al dettaglio e commercio \> ID vendita al dettaglio e commercio \> Programmazioni della distribuzione** ed esegui il processo di registrazione.

## <a name="activate-a-device"></a>Attivare un dispositivo

Per attivare un dispositivo su un'app per dispositivi mobili Store Commerce, segui questi passaggi.

1. Apri l'app sul dispositivo mobile.
1. Inserisci l'URL CPOS, che puoi trovare nella pagina dei dettagli dell'ambiente in Lifecycle Services, o nella pagina **Profili canale** in Commerce headquarters (**Vendita al dettaglio e commercio \> Impostazione canale \> Profili canale**).
1. Accedi utilizzando le credenziali di un lavoratore che dispone dell'autorizzazione a gestire i dispositivi.
1. Seleziona il punto vendita associato al registro che hai creato o riutilizzato in Commerce headquarters.
1. Seleziona il registro che hai associato al dispositivo che hai creato in Commerce headquarters.
1. Il tuo dispositivo ora dovrebbe essere attivato. Puoi accedere al registro utilizzando l'ID operatore e la password del lavoratore associato al punto vendita che hai selezionato. 

Per ulteriori informazioni sull'attivazione del dispositivo, vedi [Attivazione del dispositivo punto vendita (POS)](retail-device-activation.md#activate-a-modern-pos-or-cloud-pos-device-by-using-guided-activation).

## <a name="feature-parity-with-store-commerce-for-windows"></a>Parità di funzionalità con Store Commerce per Windows

La tabella seguente confronta le funzionalità dell'app Store Commerce sulle piattaforme Windows, Android e iOS.

| Funzionalità                                                                               | Windows | Android | iOS |
| ------------------------------------------------------------------------------------- | ------- | ------- | --- |
| Stazione hardware dedicata                                                            | Sì     | Sì     | Sì |
| Stazione hardware condivisa                                                               | Sì     | Sì     | Sì |
| Comunicazione con le periferiche in rete (terminale di pagamento, stampante e cassetto di cassa) | Sì     | Sì     | Sì |
| Periferiche OLE for Point of Sale (OPOS) tramite una stazione hardware locale             | Sì     | Numero      | Numero  |
| Modalità offline                                                                          | Sì     | Numero      | Numero  |

## <a name="additional-resources"></a>Risorse aggiuntive

[App Store Commerce](store-commerce.md)

[Scegliere tra Store Commerce e Cloud POS](../mpos-or-cpos.md)

[Risolvere i problemi di configurazione e installazione di Store Commerce](../troubleshoot/store-commerce-setup-installation.md)
