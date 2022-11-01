---
title: Imposta il Regulatory Configuration Service (RCS)
description: Questo articolo spiega come configurare Regulatory Configuration Service (RCS).
author: gionoder
ms.date: 10/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 32ced98925ee66e02f0b073b4acbd586666ac20c
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710783"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>Imposta il Regulatory Configuration Service (RCS)

[!include [banner](../includes/banner.md)]

Questo articolo spiega come configurare Regulatory Configuration Service (RCS).

## <a name="turn-on-globalization-features"></a>Attivare le funzionalità di globalizzazione

1. Accedi al tuo account RCS.
2. Selezionare il riquadro **Gestione funzionalità**.
3. Nell'area di lavoro **Gestione funzionalità**, selezionare **Funzionalità di globalizzazione** nell'elenco, quindi selezionare **Abilita ora**.

Un riquadro dell'area di lavoro **Funzionalità di globalizzazione** dovrebbe ora apparire nella dashboard principale di RCS.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Configurare i parametri per l'integrazione RCS con la fatturazione elettronica

1. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Impostazioni correlate**, selezionare **Parametri per la creazione di report elettronici**.
2. La prima volta che si configurano i parametri, verrà richiesto di connettersi a Life Cycle Services (LCS). Seleziona **Fare clic qui per connettersi a Lifecycle Services** e dopo aver stabilito la connessione, seleziona **OK**.

    > [!IMPORTANT]
    > Nei paesi o nelle aree geografiche in cui viene applicata la residenza dei dati e se il provisioning di RCS è stato effettuato in un'area geografica diversa in cui è stato eseguito il provisioning di LCS, potresti ricevere il seguente messaggio di errore di connessione in RCS: "Non è stata trovata alcuna risorsa HTTP che corrisponda all'URI della richiesta". Seleziona **OK**. Potresti ricevere un altro messaggio di errore in RCS: "Impossibile generare il token utente per Dynamics Lifecycle Services per conto dell'utente (). Contattare l'amministratore di sistema."
    >  
    > Ciò accade perché LCS è un servizio globale e il suo provisioning viene eseguito in un'area geografica degli Stati Uniti. A causa dei criteri di residenza dei dati, l'RCS della tua area geografica attuale non è in grado di connettersi a LCS. In queste circostanze, ci sono 2 possibili soluzioni:
    > - Elimina RCS dalla tua area geografica attuale e ricrealo nell'area geografica degli Stati Uniti.
    > - Ignora gli errori e continua con la configurazione della fatturazione elettronica. Questi errori non hanno alcun impatto sulla funzionalità di fatturazione elettronica.

3. Nella scheda **Fatturazione elettronica**, nel campo **URI endpoint del servizio**, immettere l'endpoint del servizio appropriato per l'area geografica di Microsoft Azure, come mostrato nella tabella seguente.

    | Area geografica del data center di Azure | URI endpoint servizio |
    |----------------------------|----------------------|
    | Stati Uniti              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Regno Unito             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Giappone                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Svizzera                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasile                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Emirati Arabi Uniti       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Australia                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canada                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Francia                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | India                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Regno di Norvegia                     | <p>`https://gw.no-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Sudafrica               | <p>`https://gw.za-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Rivedi e immetti nel campo **ID applicazione** il valore fisso **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Assicurati che venga immesso solo un identificatore univoco globale (GUID) e che il valore non includa altri simboli, come spazi, virgole, punti o virgolette.
4. Nel campo **ID ambiente LCS** immetti l'ID dell'ambiente Microsoft Dynamics Lifecycle Services (LCS). Questo valore è il riferimento all'ambiente Finance o Supply Chain Management che utilizzerai con il servizio di fatturazione elettronica. Per ottenere il tuo ID, accedi a [LCS](https://lcs.dynamics.com/), apri il tuo progetto e poi, nella scheda **Gestisci ambiente**, nella sezione **Dettagli ambiente**, guarda nel campo **ID ambiente**.

    > [!IMPORTANT]
    > Se il componente aggiuntivo di fatturazione elettronica è installato in più ambienti Finance o Supply Chain Management in LCS, utilizza sempre l'ID ambiente dell'ambiente installato più di recente. Se decidi di installare il componente aggiuntivo in un nuovo ambiente dopo aver configurato e utilizzato la funzionalità di fatturazione elettronica, aggiorna il campo **ID ambiente LCS** in RCS al valore più recente.

5. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="configuration-providers"></a>Provider di configurazione

È possibile utilizzare i provider di configurazione per distinguere i proprietari delle configurazioni di reporting elettronico (ER) utilizzate nei processi di fatturazione elettronica e le funzionalità di globalizzazione dei proprietari. Per tutte le funzionalità di globalizzazione fornite da Microsoft e pubblicate nel repository globale, il provider di configurazione è impostato su **Microsoft** (`http://microsoft.com`).

È possibile modificare solo le configurazioni ER e le funzionalità di globalizzazione che appartengono al provider di configurazione attivo. È possibile utilizzare queste configurazioni e funzionalità come modelli per creare configurazioni e funzionalità che appartengono al provider di configurazione attivo, in modo da poterle modificare.

In primo luogo, crea i provider di configurazioni. Quindi impostane uno come attivo. Non puoi impostare il provider di configurazione **Microsoft** come attivo.

### <a name="create-a-configuration-provider"></a>Creare un provider di configurazioni

1. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Provider di configurazione**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome** immettere un nome univoco per il provider di configurazione.
4. Nel campo **Indirizzo Internet** immetti l'URL univoco del provider di configurazione.
5. Selezionare **Salva**, quindi chiudere la pagina.

### <a name="select-a-configuration-provider-as-active"></a>Selezionare un provider di configurazione come attivo

1. Nell'elenco dei provider di configurazione, seleziona il provider di configurazione che desideri impostare come attivo.
2. Selezionare **Imposta come attivo**.

## <a name="import-er-configurations-from-the-global-repository"></a>Importare le configurazioni ER dal Repository globale

1. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Provider di configurazione**.
2. Nell'elenco dei provider di configurazioni, seleziona **Microsoft** e seleziona **Repository**.
3. Seleziona **Globale** e nel riquadro azioni seleziona **Apri**.
4. Importa i seguenti modelli ER:

    - **Modello contesto fattura cliente**
    - **Modello di fattura**
    - **Documenti fiscali** (per scenari brasiliani, se richiesto)
    - **Modello messaggio di risposta**

5. Se **Mapping di modello di fattura** non è stato importato automaticamente, importalo.
6. Chiudi la pagina.
