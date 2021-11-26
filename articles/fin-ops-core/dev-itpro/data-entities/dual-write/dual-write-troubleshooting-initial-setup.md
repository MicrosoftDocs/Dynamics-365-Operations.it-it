---
title: Risoluzione dei problemi durante l'impostazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che potrebbero verificarsi durante l'impostazione iniziale dell'integrazione doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c9bf5d9017579b4207e09769cff38361442e3938
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781442"
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

![Controllo dello stato riuscito.](media/health_check.png)

È necessario avere le credenziali di amministratore del tenant Azure AD per il collegamento degli ambienti Finance and Operations e Dataverse. Dopo aver collegato gli ambienti, gli utenti possono accedere utilizzando le credenziali del proprio account e aggiornare una mappa della tabella esistente.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Trovare il limite del numero di tavoli giuridici o società che possono essere collegate per la doppia scrittura

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di abilitare le mappe:

*Doppia scrittura non riuscita - Registrazione plug-in non riuscita: [(Impossibile ottenere la mappa della partizione per il progetto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Errore: il numero massimo di partizioni consentite è stato superato per il mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], si sono verificati uno o più errori.*

Il limite attuale quando si collegano gli ambienti è di circa 40 tavoli giuridici. Questo errore si verifica se si tenta di abilitare le mappe e più di 40 tavoli giuridici sono collegati tra gli ambienti.

## <a name="connection-set-failed-while-linking-environment"></a>Set di connessioni non riuscito durante il collegamento dell'ambiente

Durante il collegamento dell'ambiente a doppia scrittura, l'azione non riesce con un messaggio di errore:

*Salvataggio del set di connessioni non riuscito. È già stato aggiunto un elemento con la stessa chiave.*

La doppia scrittura non supporta più persone giuridiche/società con lo stesso nome. Ad esempio, se hai due società con il nome "DAT" in Dataverse verrà visualizzato questo messaggio di errore.

Per sbloccare il cliente, rimuovi i record duplicati dalla tabella **cdm_company** in Dataverse. Inoltre, se la tabella **cdm_company** contiene dei record con nome vuoto, rimuovi o correggi questi record.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Errore durante l'apertura della pagina di doppia scrittura nelle app Finance and Operations

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di collegare un ambiente Dataverse per la doppia scrittura:

*Il codice dello stato della risposta non indica l'esito positivo: 404 (non trovato).*

Questo errore si verifica quando il passaggio del consenso dell'app non è completo. Puoi confermare se il consenso è stato fornito accedendo a `portal.azure.com` utilizzando l'account amministratore del tenant e controllando se l'app di terze parti con ID `33976c19-1db5-4c02-810e-c243db79efde` viene visualizzata nell'elenco delle applicazioni aziendali di AAD. In caso negativo, esegui nuovamente il passaggio del consenso come descritto nella sezione successiva.

### <a name="providing-app-consent"></a>Fornire il consenso all'app

+ Avvia il seguente URL con le credenziali di amministratore.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Seleziona **Accetta** per fornire il consenso. Stai fornendo il consenso per installare l'app (con `id=33976c19-1db5-4c02-810e-c243db79efde`) nel tuo tenant.
+ Questa app è necessaria perché Dataverse comunichi con le app Finance and Operations.

    ![Risoluzione dei problemi durante l'impostazione della sincronizzazione iniziale.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Se non funziona, avvia l'URL in modalità privata di Microsoft Edge o modalità in incognito di Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>L'ambiente Finance and Operations non è individuabile

Potrebbe essere visualizzato il seguente messaggio di errore:

Ambiente delle app *Finance and Operations \*\*\*.cloudax.dynamics.com non individuabile.*

Ci sono due fattori che possono causare un problema con l'ambiente non individuabile:

+ L'utente utilizzato per l'accesso non è nello stesso tenant dell'istanza di Finance and Operations.
+ Ci sono alcune istanze di Finance and Operations legacy ospitate da Microsoft che hanno riscontrato un problema con l'individuazione. Per risolvere questo problema, aggiorna l'istanza di Finance and Operations. L'ambiente diventa individuabile con qualsiasi aggiornamento.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
