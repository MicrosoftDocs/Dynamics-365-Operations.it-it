---
title: Risoluzione dei problemi durante l'impostazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che potrebbero verificarsi durante l'impostazione iniziale dell'integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 76e104c9ebd7db7ebcbaf214e84be6c4353e8a73
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275443"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Risoluzione dei problemi durante l'impostazione iniziale

[!include [banner](../../includes/banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante l'impostazione iniziale dell'integrazione doppia scrittura.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a>Non è possibile collegare un'app Finance and Operations a Common Data Service

**Ruolo richiesto per impostare la doppia scrittura:** Amministratore di sistema nelle app Finance and Operations e Common Data Service.

Gli errori nella pagina **Impostazione del collegamento a Common Data Service** sono generalmente causati da problemi di configurazione o permessi incompleti. Assicurarsi che l'intero controllo dello stato passi nella pagina **Impostazione del collegamento a Common Data Service**, come mostrato nella figura seguente. Non è possibile collegare la doppia scrittura a meno che non venga superato l'intero controllo dello stato.

![Controllo dello stato riuscito](media/health_check.png)

È necessario avere le credenziali di amministratore del tenant Azure AD per il collegamento degli ambienti Finance and Operations e Common Data Service. Dopo aver collegato gli ambienti, gli utenti possono accedere utilizzando le credenziali del proprio account e aggiornare una mappa di entità esistente.

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a>Errore quando si apre la pagina Collegamento a Common Data Service

**Credenziali richieste per risolvere il problema:** amministratore del tenant Azure AD

È possibile che venga visualizzato il seguente messaggio di errore quando si apre la pagina **Collegamento a Common Data Service** in un'app Finance and Operations:

*Il codice dello stato della risposta non indica l'esito positivo: 404 (non trovato).*

Questo errore si verifica quando il passaggio del consenso non è stato completato. Per verificare se il passaggio del consenso è stato completato, accedere a portal.Azure.com utilizzando l'account di amministratore del tenant Azure AD e verificare se l'app di terze parti con l'ID **33976c19-1db5-4c02-810e-c243db79efde** appare nell'elenco **Applicazioni aziendali** Azure AD. In caso contrario, è necessario fornire il consenso dell'app.

Per fornire il consenso all'app, attenersi alla seguente procedura.

1. Aprire il seguente URL usando le credenziali di amministratore. Viene richiesto di confermare il consenso.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Selezionare **Accetto** per indicare che si sta fornendo il consenso all'installazione dell'app con l'ID **33976c19-1db5-4c02-810e-c243db79efde** nel tenant.

    > [!TIP]
    > Questa app è necessaria per il collegamento di Common Data Service e delle app Finance and Operations. In caso di problemi con questo passaggio, aprire il browser in modalità di navigazione in incognito (in Google Chrome) o InPrivate (in Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Verificare che i dati dell'azienda e i team di doppia scrittura siano impostati correttamente durante il collegamento

Per garantire che la doppia scrittura funzioni correttamente, le società selezionate durante la configurazione vengono create nell'ambiente Common Data Service. Per impostazione predefinita, queste società sono di sola lettura e la proprietà **IsDualWriteEnable** è impostata su **True**. Inoltre, vengono creati il proprietario e il team della Business Unit proprietaria predefinita e viene incluso il nome dell'azienda. Prima di abilitare le mappe, verificare che sia specificato il proprietario del team predefinito. Per trovare l'entità **Companies (CDM\_Company)**, attenersi alla seguente procedura.

1. Nell'app basata su modello in Dynamics 365, selezionare il filtro nell'angolo in alto a destra.
2. Nell'elenco a discesa selezionare **Società**.
3. Selezionare **Esegui** per vedere i risultati.
4. Selezionare la società che è stata collegata quando è stata configurata la doppia scrittura.
5. Verificare che il campo **Team proprietario predefinito** abbia un valore. Nell'illustrazione seguente, il campo **Team proprietario predefinito** è impostato su **Doppia scrittura USMF**.

    ![Verifica del team proprietario predefinito](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a>Trovare il limite del numero di persone giuridiche o società che possono essere collegate per la doppia scrittura

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di abilitare le mappe:

*Doppia scrittura non riuscita - Registrazione plug-in non riuscita: \[(Impossibile ottenere la mappa della partizione per il progetto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Errore: il numero massimo di partizioni consentite è stato superato per il mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\]. Si sono verificati uno o più errori.*

Il limite attuale quando si collegano gli ambienti è di circa 40 persone giuridiche. Questo errore si verifica se si tenta di abilitare le mappe e più di 40 persone giuridiche sono collegate tra gli ambienti.
