---
title: Controllo dello stato per periferiche e servizi POS
description: Questo argomento offre una panoramica dell'operazione di controllo dello stato nel punto vendita (POS).
author: rubendel
manager: AnnBe
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: b818553b7763ad03e2e23b869b364bb21c8afd57
ms.sourcegitcommit: 267864eb0dccd6e26d49d280bd4ad1b770a73a77
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "3515813"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Controllo dello stato per periferiche e servizi POS

[!include [banner](includes/banner.md)]

Questo argomento descrive l'operazione di controllo dello stato nel punto vendita (POS).

## <a name="overview"></a>Panoramica

I punti vendita al dettaglio possono essere ambienti complessi in cui vengono utilizzate molte applicazioni e dispositivi. Man mano che le operazioni crescono, può essere difficile garantire che vengano eseguite sempre senza problemi, a causa delle dipendenze, ad esempio, da periferiche che possono rompersi o accidentalmente scollegarsi nel corso della giornata. La risoluzione dei problemi relativi a dispositivi e servizi può essere costosa per i commercianti più grandi e altrettanto frustrante per le operazioni più piccole.

Microsoft Dynamics 365 Commerce versione 10.0.10 e successive includono un'operazione di controllo dello stato che può aiutare a evitare parte di questi costi e frustrazioni. Questa operazione fornisce un metodo per testare i dispositivi direttamente dal POS al di fuori delle normali operazioni. Pertanto, può aiutare i rivenditori a rilevare i problemi prima che si verifichino.

## <a name="key-terms"></a>Termini importanti

| Termine | descrizione |
|---|---|
| Periferica | Qualsiasi dispositivo utilizzato dall'applicazione POS per facilitare le transazioni e altre operazioni nel negozio. Gli esempi includono registratori di cassa, scanner di codici a barre e terminali di pagamento. |
| Gestione assistenza | In questo argomento, un servizio è un'applicazione accessoria dalla quale l'applicazione POS dipende per eseguire transazioni e operazioni quotidiane. Gli esempi includono app che aiutano con i calcoli delle imposte o di spedizione. |

## <a name="health-check-operation"></a>Operazione di controllo dello stato

L'operazione di controllo dello stato è l'operazione 717 nella pagina **Operazioni POS** di Commerce Headquarters. Può essere utilizzata mentre il POS è in modalità non cassetto. Tuttavia, una stazione hardware deve essere attiva.

Per impostazione predefinita, il controllo dello stato viene eseguito solo per i dispositivi configurati nel profilo hardware per la stazione hardware attualmente attiva per un registro. Se un registro utilizza più stazioni hardware nel corso della giornata, per eseguire i controlli dello stato è necessario collegarsi a una stazione hardware alla volta. Non esiste un controllo dello stato a livello di negozio. Tuttavia, è possibile che questo tipo di controllo possa essere eseguito tramite l'estendibilità Commerce Server.

### <a name="out-of-box-health-checks"></a>Controlli dello stato predefiniti

| Tipo | Connessione | Dettagli |
|---|---|---|
| Stampante | OPOS | Questo controllo verifica il collegamento e l'incorporamento di oggetti di base per le funzioni POS (OPOS). Di seguito sono riportati alcuni esempi.<ul><li>Aprire: **Apri** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Chiudere: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Chiudi**</li></ul> |
| Visualizzazione riga | OPOS | Questo controllo verifica le funzioni OPOS di base. Di seguito sono riportati alcuni esempi.<ul><li>Aprire: **Apri** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Chiudere: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Chiudi**</li></ul> |
| Doppio schermo | Windows | Questo controllo assicura che il sistema operativo rilevi un secondo schermo di Windows. | 
| MSR | OPOS | Questo controllo verifica le funzioni OPOS di base. Di seguito sono riportati alcuni esempi.<ul><li>Aprire: **Apri** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Chiudere: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Chiudi**</li></ul> |
| Traente | OPOS | Questo controllo verifica le funzioni OPOS di base. Di seguito sono riportati alcuni esempi.<ul><li>Aprire: **Apri** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Chiudere: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Chiudi**</li></ul> | 
| Scanner | OPOS | Questo controllo verifica le funzioni OPOS di base. Di seguito sono riportati alcuni esempi.<ul><li>Aprire: **Apri** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Chiudere: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Chiudi**</li></ul> | 
| Ridimensionamento | OPOS | Questo controllo verifica le funzioni OPOS di base. Di seguito sono riportati alcuni esempi.<ul><li>Aprire: **Apri** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Chiudere: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Chiudi**</li></ul> |
| Tastierino PIN | OPOS | Questo controllo verifica le funzioni OPOS di base. Di seguito sono riportati alcuni esempi.<ul><li>Aprire: **Apri** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Chiudere: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Chiudi**</li></ul> |
| Terminale di pagamento | SDK per pagamenti | Questo controllo verifica le funzioni di base del terminale di pagamento fornite dall'SDK per pagamenti. <ul><li>Blocca</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Chiusura</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Utilizzo dell'operazione di controllo dello stato nel POS

Quando l'operazione di controllo dello stato viene avviata nel POS, un riquadro a destra elenca i dispositivi configurati e mostra lo stato di ciascun dispositivo. Per eseguire un controllo dello stato di un singolo dispositivo, selezionare il dispositivo, quindi selezionare **Test selezionato**. Per eseguire un controllo dello stato di tutti i dispositivi, selezionare **Verifica tutto**. La funzione **Verifica tutto** esegue il test di tutti i dispositivi, uno alla volta, e aggiorna lo stato di ciascun dispositivo nella colonna **Stato**.

La colonna **Ultimo controllo** mostra quando è stato eseguito l'ultimo controllo dello stato per ciascun dispositivo.

Se viene superato il controllo dello stato di un dispositivo (ovvero, se non si verificano errori), lo stato del dispositivo sarà **OK**. Se il controllo dello stato non riesce, lo stato indicherà che si è verificato un errore. In questo caso, il riquadro a destra fornisce i dettagli relativi all'errore o indica all'utente di contattare l'amministratore di sistema.

Alcuni dispositivi, come il blocco dei tasti OPOS, non dispongono di test di controllo dello stato predefiniti. Se un test di controllo dello stato non viene rilevato per qualsiasi dispositivo utilizzato, lo stato sarà **Non supportato**.

### <a name="extending-health-checks"></a>Estensione dei controlli dello stato

I test del controllo dello stato predefiniti sono configurati per fornire alcuni messaggi intuitivi per errori tipici. Tuttavia, non tutti gli scenari sono coperti. Grazie all'estendibilità, i commercianti possono mappare i messaggi intuitivi su errori che potrebbero essere specifici del loro ambiente.

È inoltre possibile creare controlli dello stato personalizzati per testare i dispositivi che non sono supportati e per testare qualsiasi servizio da cui dipende il POS.

## <a name="related-articles"></a>Articoli correlati

[Trigger e stampa di Modern POS (MPOS)](https://docs.microsoft.com/en-us/dynamics365/commerce/dev-itpro/pos-trigger-printing)
