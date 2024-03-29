---
title: Risoluzione dei problemi durante l'impostazione iniziale
description: Questo articolo fornisce informazioni che possono aiutarti a risolvere i problemi che potrebbero verificarsi durante l'impostazione iniziale dell'integrazione doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d33fc6f4895b53f16cc6957a3a2fc6b1abe90a2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289516"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Risoluzione dei problemi durante l'impostazione iniziale

[!include [banner](../../includes/banner.md)]

In questo articolo vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app per la finanza e le operazioni e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante l'impostazione iniziale dell'integrazione doppia scrittura.

> [!IMPORTANT]
> Alcuni problemi che questo articolo tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Non puoi collegare un'app per la finanza e le operazioni a Dataverse

**Ruolo richiesto per impostare la doppia scrittura**: Amministratore di sistema nelle app per la finanza e le operazioni e Dataverse.

Gli errori nella pagina **Impostazione del collegamento a Dataverse** sono generalmente causati da problemi di configurazione o permessi incompleti. Assicurarsi che l'intero controllo dello stato passi nella pagina **Impostazione del collegamento a Dataverse**, come mostrato nella figura seguente. Non è possibile collegare la doppia scrittura a meno che non venga superato l'intero controllo dello stato.

![Controllo dello stato riuscito.](media/health_check.png)

È necessario avere le credenziali di amministratore del tenant Azure AD per il collegamento degli ambienti di finanza e operazioni e Dataverse. Dopo aver collegato gli ambienti, gli utenti possono accedere utilizzando le credenziali del proprio account e aggiornare una mappa della tabella esistente.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Trovare il limite del numero di tavoli giuridici o società che possono essere collegate per la doppia scrittura

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di abilitare le mappe:

*Doppia scrittura non riuscita - Registrazione plug-in non riuscita: [(Impossibile ottenere la mappa della partizione per il progetto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Errore: il numero massimo di partizioni consentite è stato superato per il mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], si sono verificati uno o più errori.*

Il limite attuale quando si collegano gli ambienti è di circa 40 tavoli giuridici. Questo errore si verifica se si tenta di abilitare le mappe e più di 40 tavoli giuridici sono collegati tra gli ambienti.

## <a name="connection-set-failed-while-linking-environment"></a>Set di connessioni non riuscito durante il collegamento dell'ambiente

Durante il collegamento dell'ambiente a doppia scrittura, l'azione non riesce con un messaggio di errore:

*Salvataggio del set di connessioni non riuscito. È già stato aggiunto un elemento con la stessa chiave.*

La doppia scrittura non supporta più persone giuridiche/società con lo stesso nome. Ad esempio, se hai due società con il nome "DAT" in Dataverse, verrà visualizzato questo messaggio di errore.

Per sbloccare il cliente, rimuovi i record duplicati dalla tabella **cdm_company** in Dataverse. Inoltre, se la tabella **cdm_company** contiene dei record con nome vuoto, rimuovi o correggi questi record.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Errore durante l'apertura della pagina Doppia scrittura nelle app per la finanza e le operazioni

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di collegare un ambiente Dataverse per la doppia scrittura:

*Il codice dello stato della risposta non indica l'esito positivo: 404 (non trovato).*

Questo errore si verifica quando il passaggio del consenso dell'app non è completo. Puoi confermare se il consenso è stato fornito accedendo a `portal.azure.com` utilizzando l'account amministratore del tenant e controllando se l'app di terze parti con ID `33976c19-1db5-4c02-810e-c243db79efde` viene visualizzata nell'elenco delle applicazioni aziendali di AAD. In caso negativo, esegui nuovamente il passaggio del consenso come descritto nella sezione successiva.

### <a name="providing-app-consent"></a>Fornire il consenso all'app

+ Avvia il seguente URL con le credenziali di amministratore.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Seleziona **Accetta** per fornire il consenso. Stai fornendo il consenso per installare l'app (con `id=33976c19-1db5-4c02-810e-c243db79efde`) nel tuo tenant.
+ Questa app è necessaria perché Dataverse comunichi con le app per la finanza e le operazioni.

    ![Risoluzione dei problemi durante l'impostazione della sincronizzazione iniziale.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Se non funziona, avvia l'URL in modalità privata di Microsoft Edge o modalità in incognito di Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>L'ambiente di finanza e operazioni non è individuabile

Potrebbe essere visualizzato il seguente messaggio di errore:

*Ambiente delle app per la finanza e le operazioni \*\*\*.cloudax.dynamics.com non rilevabile.*

Ci sono due fattori che possono causare un problema con l'ambiente non individuabile:

+ L'utente utilizzato per l'accesso non è nello stesso tenant dell'istanza di finanza e operazioni.
+ Ci sono alcune istanze di finanza e operazioni legacy ospitate da Microsoft che hanno riscontrato un problema con l'individuazione. Per risolvere questo problema, aggiorna l'istanza di finanza e operazioni. L'ambiente diventa individuabile con qualsiasi aggiornamento.

## <a name="403-forbidden-error-while-connections-are-being-created"></a>Errore 403 (Accesso negato) durante la creazione delle connessioni

Come parte del processo di collegamento in doppia scrittura, due connessioni Power Apps (note anche come connessioni *Apihub*) vengono create per conto dell'utente nell'ambiente Dataverse collegato. Se il cliente non dispone di una licenza per l'ambiente Power Apps, la creazione delle connessioni ApiHub non riesce e viene visualizzato un errore 403 (Accesso negato). Di seguito è riportato un esempio del messaggio di errore:

> MSG=\[Impossibile configurare l'ambiente a doppia scrittura. Dettagli errore: Il codice di stato della risposta non indica un'operazione riuscita: 403 (Accesso negato). - Il codice di stato della risposta non indica un'operazione riuscita: 403 (Accesso negato).\] STACKTRACE=\[    in Microsoft.Dynamics.Integrator.ProjectManagementService.DualWrite.DualWriteConnectionSetProcessor.\<CreateDualWriteConnectionSetAsync\>d\_\_29.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\DualWrite\\DualWriteConnectionSetProcessor.cs:line 297 --- Fine traccia dello stack da posizione precedente dove è stata generata l'eccezione --- inSystem.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw() in System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task) in Microsoft.Dynamics.Integrator.ProjectManagementService.Controllers.DualWriteEnvironmentManagementController.\<SetupDualWriteEnvironmentAsync\>d\_\_34.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\Controllers\\DualWriteEnvironmentManagementController.cs:line 265\]

Questo errore si verifica a causa della mancanza di una licenza Power Apps. Assegna una licenza appropriata (ad esempio, la licenza di valutazione di Power Apps Piano 2) all'utente, di modo che questi disponga dell'autorizzazione per creare le connessioni. Per verificare la licenza, il cliente può accedere al sito [Account personale](https://portal.office.com/account/?ref=MeControl#subscriptions) per visualizzare le licenze attualmente assegnate all'utente.

Per ulteriori informazioni sulla licenza Power Apps, vedi gli articoli seguenti:

- [Assegnare licenze a utenti](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)
- [Acquistare Power Apps per l'organizzazione](/power-platform/admin/signup-for-powerapps-admin)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

