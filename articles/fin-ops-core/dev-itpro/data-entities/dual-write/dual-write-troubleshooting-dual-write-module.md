---
title: Risoluzione dei problemi di doppia scrittura nelle app Finance and Operations
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo doppia scrittura nelle app Finance and Operations.
author: RamaKrishnamoorthy
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
ms.openlocfilehash: 6689fae215937f58c93cce72df3fa0a1b5aecd3a5ac9913981b253344a1ba13f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720738"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Risoluzione dei problemi di doppia scrittura nelle app Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo **doppia scrittura** nelle app Finance and Operations.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Non è possibile caricare il modulo doppia scrittura in un'app Finance and Operations

Se non si riesce ad aprire la pagina **Doppia scrittura** selezionando il riquadro **Doppia scrittura** nell'area di lavoro **Gestione dei dati**, il servizio di integrazione dei dati è probabilmente inattivo. Creare un ticket di supporto per richiedere il riavvio del servizio di integrazione dei dati.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Errore quando si tenta di creare una nuova mappa della tabella

**Credenziali richieste per risolvere il problema:** lo stesso utente che ha impostato la doppia scrittura.

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di configurare una nuova tabella per la doppia scrittura. L'unico utente che può creare una mappa è l'utente che imposta la connessione per la doppia scrittura.

*Il codice dello stato della risposta non indica l'esito positivo: 401 (non autorizzato).*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Errore quando si apre l'interfaccia utente a doppia scrittura

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di accedere alla doppia scrittura dall'area di lavoro **Gestione dei dati**:

*login.microsoftonline.com ha rifiutato di connettersi.*

Per risolvere il problema, accedere utilizzando una finestra InPrivate in Microsoft Edge, una finestra di navigazione in incognito in Chromium o una finestra di navigazione in incognito in Google Chrome. È inoltre necessario sbloccare o cancellare i cookie di terze parti.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Errore quando si collega l'ambiente per la doppia scrittura o si aggiunge un nuovo mapping della tabella

**Ruolo richiesto per correggere il problema:** amministratore di sistema nelle app Finance and Operations e Dataverse.

È possibile che si verifichi il seguente errore durante il collegamento o la creazione di mappe:

*Il codice dello stato della risposta non indica l'esito positivo: 403 (tokenexchange).<br> ID sessione: \<your session id\><br> ID attività radice: \<your root activity id\>*

Questo errore può verificarsi se non si dispone di autorizzazioni sufficienti per collegare la doppia scrittura o creare mappe. Questo errore può verificarsi anche se l'ambiente Dataverse è stato ripristinato senza scollegare la doppia scrittura. Qualsiasi utente con ruolo di amministratore di sistema nelle app Finance and Operations e Dataverse può collegare gli ambienti. Solo l'utente che imposta la connessione per la doppia scrittura può aggiungere nuove mappe della tabella. Dopo l'impostazione, qualsiasi utente con ruolo di amministratore di sistema può monitorare lo stato e modificare i mapping.

## <a name="error-when-you-stop-the-table-mapping"></a>Errore quando si interrompe il mapping della tabella

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di interrompere i mapping della tabella:

*\[Accesso negato\], \[{"stato": 403,"origine":"","messaggio":"Errore dello scambio di token: l'utente non è autorizzato ad accedere alla connessione dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Il server remoto ha restituito un errore: (403) Accesso negato.*

Questo errore si verifica quando l'ambiente Dataverse collegato non è disponibile.

Per risolvere il problema, creare un ticket per il team di integrazione dei dati. Collegare la traccia di rete in modo che il team di integrazione dei dati possa contrassegnare le mappe come **Non in esecuzione** nel back-end.

## <a name="error-while-trying-to-start-a-table-mapping"></a>Errore durante il tentativo di avviare un mapping della tabella

È possibile che venga visualizzato un errore simile al seguente quando si tenta di impostare lo stato di un mapping su **In esecuzione**:

*Impossibile completare la sincronizzazione iniziale dei dati. Errore: errore di doppia scrittura - registrazione del plug-in non riuscita: impossibile creare metadati di ricerca per la doppia scrittura. Errore di riferimento oggetto non impostato sull'istanza di un oggetto.*

La correzione di questo errore dipende dalla causa dell'errore:

+ Se il mapping prevede mapping dipendenti, assicurarsi di abilitare i mapping dipendenti di questo mapping della tabella.
+ Nel mapping potrebbero mancare le colonne di origine o destinazione. Se manca una colonna nell'app Finance and Operations, seguire i passaggi nella sezione [Problema delle colonne di tabella mancanti sulle mappe](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Se manca una colonna in Dataverse, fare clic sul pulsante **Aggiorna tabelle** sul mapping in modo che le colonne vengano automaticamente compilati nuovamente nel mapping.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]