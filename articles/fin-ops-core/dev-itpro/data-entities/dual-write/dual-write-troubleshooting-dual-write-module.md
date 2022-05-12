---
title: Risoluzione dei problemi di doppia scrittura nelle app per finanza e operazioni
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo doppia scrittura nelle app per finanza e operazioni.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 0696d525e985f1cfcac1998d4c0bd8a380ca9551
ms.sourcegitcommit: 7faf82fa7ce269c0201abb8473af861ef7ce00bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "8613884"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Risoluzione dei problemi di doppia scrittura nelle app per finanza e operazioni

[!include [banner](../../includes/banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra Finanza e operazioni e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo **doppia scrittura** nelle app per finanza e operazioni.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Non è possibile caricare il modulo doppia scrittura in un'app per finanza e operazioni

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

**Ruolo richiesto per risolvere il problema:** amministratore di sistema sia nelle app per finanza e operazioni che in Dataverse.

È possibile che si verifichi il seguente errore durante il collegamento o la creazione di mappe:

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

Questo errore può verificarsi se non si dispone di autorizzazioni sufficienti per collegare la doppia scrittura o creare mappe. Questo errore può verificarsi anche se l'ambiente Dataverse è stato ripristinato senza scollegare la doppia scrittura. Qualsiasi utente con ruolo di amministratore di sistema nelle app per finanza e operazioni e Dataverse può collegare gli ambienti. Solo l'utente che imposta la connessione per la doppia scrittura può aggiungere nuove mappe della tabella. Dopo l'impostazione, qualsiasi utente con ruolo di amministratore di sistema può monitorare lo stato e modificare i mapping.

## <a name="error-when-you-stop-the-table-mapping"></a>Errore quando si interrompe il mapping della tabella

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di interrompere i mapping della tabella:

*\[Accesso negato\], \[{"stato": 403,"origine":"","messaggio":"Errore dello scambio di token: l'utente non è autorizzato ad accedere alla connessione dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Il server remoto ha restituito un errore: (403) Accesso negato.*

Questo errore si verifica quando l'ambiente Dataverse collegato non è disponibile.

Per risolvere il problema, creare un ticket per il team di integrazione dei dati. Collegare la traccia di rete in modo che il team di integrazione dei dati possa contrassegnare le mappe come **Non in esecuzione** nel back-end.

## <a name="enable-parallel-processing-in-finance-and-operations-apps-to-improve-performance"></a>Abilitare l'elaborazione parallela nelle app per la finanza e le operazioni per migliorare le prestazioni

L'abilitazione dell'elaborazione parallela può ridurre il tempo necessario per importare i dati dalle app Dynamics 365 Customer Engagement e Microsoft Dataverse alle app per la finanza e le operazioni. 

Per abilitare l'elaborazione parallela nelle app per la finanza e le operazioni completa i seguenti passaggi.

1. Accedi all'ambiente delle app per la finanza e le operazioni.
2. Vai a **Gestione dati > Parametri framework**.
3. Seleziona **Impostazioni entità** e seleziona **Configura parametri di esecuzione entità**.
4. Aggiungi i parametri per l'elaborazione parallela:
    - **Conteggio record soglia di importazione** – Il numero di record che devono essere soddisfatti prima dell'abilitazione dell'elaborazione parallela.
    - **Conteggio attività di importazione** – Il numero di thread (attività) da eseguire in parallelo.
5. Seleziona **Salva**.


## <a name="errors-while-trying-to-start-a-table-mapping"></a>Errori durante il tentativo di avviare un mapping della tabella

### <a name="unable-to-complete-initial-data-sync"></a>Impossibile completare la sincronizzazione iniziale dei dati

È possibile che venga visualizzato un errore simile al seguente quando si tenta di eseguire la sincronizzazione iniziale dei dati:

*Impossibile completare la sincronizzazione iniziale dei dati. Errore: errore di doppia scrittura - registrazione del plug-in non riuscita: impossibile creare metadati di ricerca per la doppia scrittura. Errore di riferimento oggetto non impostato sull'istanza di un oggetto.*

Quando si tenta di impostare lo stato di un mapping su **In esecuzione** potrebbe essere visualizzato questo errore. La correzione dipende dalla causa dell'errore:

+ Se il mapping prevede mapping dipendenti, assicurarsi di abilitare i mapping dipendenti di questo mapping della tabella.
+ Nel mapping potrebbero mancare le colonne di origine o destinazione. Se manca una colonna nell'app per finanza e operazioni, seguire i passaggi nella sezione [Problema delle colonne di tabella mancanti sulle mappe](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Se manca una colonna in Dataverse, fare clic sul pulsante **Aggiorna tabelle** sul mapping in modo che le colonne vengano automaticamente compilati nuovamente nel mapping.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>Errore di mancata corrispondenza della versione e aggiornamento delle soluzioni a doppia scrittura

È possibile che vengano visualizzati i seguenti messaggi di errore quando si tenta di eseguire i mapping della tabella:

+ *Gruppi di clienti (msdyn_customergroups): doppia scrittura non riuscita - Soluzione Dynamics 365 for Sales "Dynamics365Company" con mancata corrispondenza della versione. Versione: '2.0.2.10' Versione richiesta: '2.0.133'*
+ Soluzione *Dynamics 365 for Sales "Dynamics365FinanceExtended" con mancata corrispondenza della versione. Versione: "1.0.0.0" Versione richiesta: "2.0.227"*
+ Soluzione *Dynamics 365 for Sales "Dynamics365FinanceAndOperationsCommon" con mancata corrispondenza della versione. Versione: "1.0.0.0" Versione richiesta: "2.0.133"*
+ Soluzione *Dynamics 365 for Sales "CurrencyExchangeRates" con mancata corrispondenza della versione. Versione: "1.0.0.0" Versione richiesta: "2.0.133"*
+ Soluzione *Dynamics 365 for Sales "Dynamics365SupplyChainExtended" con mancata corrispondenza della versione. Versione: "1.0.0.0" Versione richiesta: "2.0.227"*

Per risolvere i problemi, aggiorna le soluzioni a doppia scrittura in Dataverse. Assicurati di eseguire l'aggiornamento alla soluzione più recente che corrisponda alla versione della soluzione richiesta.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
