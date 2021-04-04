---
title: Risoluzione dei problemi durante l'impostazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che potrebbero verificarsi durante l'impostazione iniziale dell'integrazione doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f6ff9a304de8a94b86e6866d6d2cb65fbfdfb02f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561180"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Risoluzione dei problemi durante l'impostazione iniziale

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante l'impostazione iniziale dell'integrazione doppia scrittura.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Non è possibile collegare un'app Finance and Operations a Dataverse

**Ruolo richiesto per impostare la doppia scrittura:** Amministratore di sistema nelle app Finance and Operations e Dataverse.

Gli errori nella pagina **Impostazione del collegamento a Dataverse** sono generalmente causati da problemi di configurazione o permessi incompleti. Assicurarsi che l'intero controllo dello stato passi nella pagina **Impostazione del collegamento a Dataverse**, come mostrato nella figura seguente. Non è possibile collegare la doppia scrittura a meno che non venga superato l'intero controllo dello stato.

![Controllo dello stato riuscito](media/health_check.png)

È necessario avere le credenziali di amministratore del tenant Azure AD per il collegamento degli ambienti Finance and Operations e Dataverse. Dopo aver collegato gli ambienti, gli utenti possono accedere utilizzando le credenziali del proprio account e aggiornare una mappa della tabella esistente.

## <a name="error-when-you-open-the-link-to-dataverse-page"></a>Errore quando si apre la pagina Collegamento a Dataverse

**Credenziali richieste per risolvere il problema:** amministratore del tenant Azure AD

È possibile che venga visualizzato il seguente messaggio di errore quando si apre la pagina **Collegamento a Dataverse** in un'app Finance and Operations:

*Il codice dello stato della risposta non indica l'esito positivo: 404 (non trovato).*

Questo errore si verifica quando il passaggio del consenso non è stato completato. Per verificare se il passaggio del consenso è stato completato, accedere a portal.Azure.com utilizzando l'account di amministratore del tenant Azure AD e verificare se l'app di terze parti con l'ID **33976c19-1db5-4c02-810e-c243db79efde** appare nell'elenco **Applicazioni aziendali** Azure AD. In caso contrario, è necessario fornire il consenso dell'app.

Per fornire il consenso all'app, attenersi alla seguente procedura.

1. Aprire il seguente URL usando le credenziali di amministratore. Viene richiesto di confermare il consenso.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Selezionare **Accetto** per indicare che si sta fornendo il consenso all'installazione dell'app con l'ID **33976c19-1db5-4c02-810e-c243db79efde** nel tenant.

    > [!TIP]
    > Questa app è necessaria per il collegamento di Dataverse e delle app Finance and Operations. In caso di problemi con questo passaggio, aprire il browser in modalità di navigazione in incognito (in Google Chrome) o InPrivate (in Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Verificare che i dati dell'azienda e i team di doppia scrittura siano impostati correttamente durante il collegamento

Per garantire che la doppia scrittura funzioni correttamente, le società selezionate durante la configurazione vengono create nell'ambiente Dataverse. Per impostazione predefinita, queste società sono di sola lettura e la proprietà **IsDualWriteEnable** è impostata su **True**. Inoltre, vengono creati il proprietario e il team della Business Unit proprietaria predefinita e viene incluso il nome dell'azienda. Prima di abilitare le mappe, verificare che sia specificato il proprietario del team predefinito. Per trovare la tabella **Companies (CDM\_Company)**, attenersi alla seguente procedura.

1. Nell'app basata su modello in Dynamics 365, selezionare il filtro nell'angolo in alto a destra.
2. Nell'elenco a discesa selezionare **Società**.
3. Selezionare **Esegui** per vedere i risultati.
4. Selezionare la società che è stata collegata quando è stata configurata la doppia scrittura.
5. Verificare che la colonna **Team proprietario predefinito** abbia un valore. Nell'illustrazione seguente, la colonna **Team proprietario predefinito** è impostata su **Doppia scrittura USMF**.

    ![Verifica del team proprietario predefinito](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Trovare il limite del numero di tavoli giuridici o società che possono essere collegate per la doppia scrittura

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di abilitare le mappe:

*Doppia scrittura non riuscita - Registrazione plug-in non riuscita: \[(Impossibile ottenere la mappa della partizione per il progetto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Errore: il numero massimo di partizioni consentite è stato superato per il mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\]. Si sono verificati uno o più errori.*

Il limite attuale quando si collegano gli ambienti è di circa 40 tavoli giuridici. Questo errore si verifica se si tenta di abilitare le mappe e più di 40 tavoli giuridici sono collegati tra gli ambienti.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]